<img src="https://my-badges.github.io/my-badges/fix-5.png" alt="I did 5 sequential fixes." title="I did 5 sequential fixes." width="128">
<strong>I did 5 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/e61c0dff55b2ac23394c62d246f6ea671c9c0861">e61c0df</a>: fix(pool): remove contract-level root check, root verified by ZK proof

- remove if root != current_root check from claim() function
- root is now verified by Groth16 proof itself (pairing check)
- this fixes claim always failing because admin root never matches
  computed Merkle root after deposits
- update tests: test_invalid_proof uses wrong proof size instead of wrong root
- update test_claim_rejects_wrong_root: tamper public inputs not stored root
- deploy new XLM pool: CAIQGZ4...T4T3O (base 1 XLM)
- deploy new USDC pool: CBXOZCWT...CNXYJ (base 0.1 USDC)
- regenerate TypeScript binding
- 16 tests passing
- <a href="https://github.com/dzakwannajmi/Growthip/commit/31418196bab450cfbaed90e39f1b8fd46d85cb50">3141819</a>: fix(claim): check claim_to return value before declaring success

- claim_to returns bool, not just tx success
- if result === false, throw descriptive error instead of showing success
- prevents false positive success state when contract rejects claim
- <a href="https://github.com/dzakwannajmi/Growthip/commit/f9668c55f097105a81ffd96f5ff14e4fdd903ffb">f9668c5</a>: fix(sidebar): toggle button always visible when collapsed
- <a href="https://github.com/dzakwannajmi/Growthip/commit/9f1b244693b2d301c9a59d644805da5ccade2cd2">9f1b244</a>: fix(dashboard): fix sidebar double render using route groups

- move /, /deposit, /claim to (main) route group with navbar layout
- dashboard route group has its own layout with sidebar only
- remove NavbarWrapper client component (was causing double render)
- root layout now clean without any wrapper
- sidebar only renders once via dashboard/layout.tsx
- <a href="https://github.com/dzakwannajmi/Growthip/commit/15ce293259f1f74ba4773ca8e1b954508c6b442a">15ce293</a>: fix(dashboard): collapsible sidebar with smooth transition

- sidebar uses inline style width for smooth collapse animation
- collapse to 56px icon-only, expand to 224px with labels
- sticky positioning (tidak fixed) untuk proper flex layout
- hide top navbar on /dashboard/* via NavbarWrapper


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>