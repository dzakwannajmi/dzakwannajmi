<img src="https://my-badges.github.io/my-badges/fix-2.png" alt="I did 2 sequential fixes." title="I did 2 sequential fixes." width="128">
<strong>I did 2 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/d984fbd5f799149b93ee4aecee6b1e97587ab7a2">d984fbd</a>: fix(security): deposit-amount-aware claims via V3.1 circuit + index public output

CRITICAL BUG FOUND IN PRODUCTION: claim_to() always paid out a flat
TipAmount base unit regardless of how much was actually deposited
(1x/5x/10x/20x). A supporter tipping 20 XLM saw the creator receive
only 0.99 XLM (99% of the 1x base unit), with the remaining ~19 XLM
permanently locked in the pool -- no function existed to recover it.
Confirmed via on-chain transaction audit during testnet E2E testing.

Root cause: the circuit's public_inputs never carried the deposit's
leaf index, so claim_to() had no way to look up the actual deposited
amount (DataKey::CommitmentAmount(index)) and fell back to a flat
base-unit transfer.

Fix (V3.1):
- circuits/growthip_merkle_note_v3_1.circom: adds  as a 4th
  public output, derived from the existing pathIndices[] bits (no new
  private inputs needed -- index = sum(pathIndices[i] * 2^i)).
  Verified the bit ordering matches merkle.ts's getMerklePathByIndex()
  (LSB-first) before trusting it, and verified the circuit's computed
  index against a manual calculation for a non-trivial leaf (index=5,
  not the trivially-correct index=0 case).
- New trusted setup (phase-2 ceremony, same pot12 ptau reused) and a
  new verifier crate (growthip-merkle-verifier-v3-1), since the
  circuit's r1cs changed. parameters.json conversion formula verified
  by reproducing the EXISTING (working) V3 parameters.json byte-for-byte
  from its verification_key.json before trusting it for the new circuit.
- growthip-pool: claim() and claim_to() both updated to expect 4 public
  inputs (found and fixed a bug where I'd only updated claim()'s check
  initially, missing claim_to()'s separate duplicate check -- caught via
  systematic isolation debugging, not luck). claim_to() now extracts
  index from public_inputs[3], looks up CommitmentAmount(index), and
  uses that as the payout base instead of flat TipAmount.
- New regression test deposits 5x base unit at a non-trivial leaf
  index (5) and asserts the recipient receives 99% of the ACTUAL 5x
  amount, not 1x -- this test would have caught the original bug.

Redeployed: verifier V3.1, pool XLM, pool USDC (all with fresh state,
no real deposits existed yet on the buggy contracts to migrate).

See SECURITY.md for the full writeup (to be added).
- <a href="https://github.com/dzakwannajmi/Growthip/commit/6eed770a3578d7d8c35a72c3885331d3d72cb2fe">6eed770</a>: fix: auto-register wallet as tip recipient on connect

Root cause of 'claim_to returns false' bug found via on-chain audit:
register_recipient() was only ever called as a side-effect inside the
Send Tip flow (when address === recipient, i.e. testing-to-self), never
when a creator connects their wallet to receive tips via their public
/tip/[id] link. After every pool redeploy, recipient registration
storage resets to empty -- a creator who'd registered on a prior pool
deployment was NOT carried over and could not claim.

Fix: connectWallet() now calls autoRegisterRecipient(), which checks
and registers (if not already registered) on every available token
pool (XLM, USDC). Per-pool failures are caught and logged without
blocking wallet connect or other pools' registration.


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>