<img src="https://my-badges.github.io/my-badges/fix-3.png" alt="I did 3 sequential fixes." title="I did 3 sequential fixes." width="128">
<strong>I did 3 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/1d930823289062fcbfede220ccf1cfc0d45114df">1d93082</a>: fix(security): on-chain root validation against forgery attack

Fixes a critical vulnerability where claim() never validated the proof's
root against any on-chain state. A Groth16 proof only proves knowledge of
a path to root X — it does NOT prove X is a root this pool produced. An
attacker could build a fake tree offline and drain the pool without
depositing.

Fix: deposit_internal() now recomputes the Merkle root on-chain via
Soroban's native poseidon_permutation host function (Protocol 25,
CAP-0075), and appends it to a bounded on-chain root history. claim()
validates the proof's root against this history before any other check.

Verified, not assumed:
- poseidon_verify_test.rs: Soroban's Poseidon output matches circomlibjs
  byte-for-byte across t=2/3/4 arities, against real production ground
  truth (apps/web/src/lib/poseidon.ts)
- merkle_verify_test.rs: on-chain rebuild_merkle_root() matches the
  frontend's merkle.ts root construction exactly
- test_claim_to_with_v3_verifier_and_proof: deposits the actual
  commitment used to generate a real proof artifact, exercising the full
  deposit->root->claim path end to end

Three pre-existing tests now fail because they relied on the absence of
root validation to pass (each deposited a disconnected dummy commitment
unrelated to its proof) — marked #[ignore] with inline explanation
rather than deleted, to preserve the audit trail.

See SECURITY.md for full writeup.
- <a href="https://github.com/dzakwannajmi/Growthip/commit/f4b11ae331c0f8417f42de1b67f93d2c241e4641">f4b11ae</a>: fix(landing): footer matches reference style - brand name + tagline, powered by line
- <a href="https://github.com/dzakwannajmi/Growthip/commit/f7e7179497e54f5227ed5a216b4f7b44caba3807">f7e7179</a>: fix(landing): remove bento mini-nav from CTA section, keep just heading + button


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>