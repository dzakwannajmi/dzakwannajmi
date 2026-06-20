<img src="https://my-badges.github.io/my-badges/chore-commit.png" alt="I did a little housekeeping! 🧹" title="I did a little housekeeping! 🧹" width="128">
<strong>I did a little housekeeping! 🧹</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/8901f2e4d5ca1696e0d586f4caf3ed1c0d160e71">8901f2e</a>: chore: migrate soroban-sdk 25.1.0 -> 26.0.1, fix deprecated APIs

Required for poseidon_permutation host function (CAP-0075), which is
gated behind the hazmat-crypto feature and was added as a publicly
callable env.crypto_hazmat() entry point starting in SDK 26.x.

Also fixes deprecation warnings surfaced by the upgrade across all
workspace members:
- crypto::bn254::Fr -> Bn254Fr (avoids ambiguity with Bls12381Fr)
- Events::publish() -> #[contractevent] macro (DepositEvent, ClaimEvent
  structs in growthip-pool)

Whole-workspace build and test suite confirmed clean (0 warnings,
0 errors) after migration.


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>