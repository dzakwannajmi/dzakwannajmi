<img src="https://my-badges.github.io/my-badges/fix-2.png" alt="I did 2 sequential fixes." title="I did 2 sequential fixes." width="128">
<strong>I did 2 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/722983da137fa0b3a6dae80a9b7fbfd524f38313">722983d</a>: fix(audit): apply H1/H3/L1/M1/M3 findings + redeploy pool V3

H1: deposit() is now private (deposit_internal) — prevents free commitment spam
H3: add upgrade() function — pool can now be upgraded without state loss
L1: get_recipient_hash returns Option — no panic on missing recipient
M1: add test_claim_to_with_v3_verifier_and_proof — closes V2/V3 test gap
M3: add privacy-safe events for deposit and claim

New pool deployment: CCSYSAWOUWWBAHDLXXBZ4NL7VIXGCHAMYWNZHNUVUQQUMY4TSGC6IV56
Verifier V3: CD3O37X2FIGAHZSM4KVR7XW72HYZOQ75MJF7IZX4LEA6PCKOHMW3N6D2
23 tests passing (16 pool + 3 verifier-v3 + others)
- <a href="https://github.com/dzakwannajmi/Growthip/commit/894d2ff22132664d8a8855ed5ab87c4908d7b4ca">894d2ff</a>: fix(frontend): convert commitment from decimal to hex (32 bytes)

- GROWTHIP_COMMITMENT_HEX was stored as decimal string causing 38-byte error
- converted to proper 32-byte hex: 04a6f832...03fd8
- deposit_paid and claim_to now receive correct byte length


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>