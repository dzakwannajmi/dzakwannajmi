<img src="https://my-badges.github.io/my-badges/fix-6.png" alt="I did 6 sequential fixes." title="I did 6 sequential fixes." width="128">
<strong>I did 6 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/72cd1fa89497c637baf6030980ac38bf8dd44be7">72cd1fa</a>: fix(dashboard): stabilize DashboardStats with multi-token support

- lazy-load Stellar client to fix SSR error on Vercel
- support multiple pools (XLM + USDC) with per-token breakdown
- auto-refresh every 30 seconds
- manual refresh button
- aggregate totals across all pools
- fix pool balance calculation (was hardcoded * 10)
- show last updated timestamp
- <a href="https://github.com/dzakwannajmi/Growthip/commit/8b2571b1890ba8b6c7bf7e17d9174bbf0e52fd88">8b2571b</a>: fix(dashboard): stabilize DashboardStats with multi-token support

- lazy-load Stellar client to fix SSR error on Vercel
- support multiple pools (XLM + USDC) with per-token breakdown
- auto-refresh every 30 seconds
- manual refresh button
- aggregate totals across all pools
- fix pool balance calculation (was hardcoded * 10)
- show last updated timestamp
- <a href="https://github.com/dzakwannajmi/Growthip/commit/94b1da6f7aac02e5662e03b3269b78a6050c6ebe">94b1da6</a>: fix(amount): fix presetToContractAmount to use baseUnit multiplier

- presetToContractAmount now calculates multiplier relative to baseUnit
- XLM: 1/5/10/20 XLM maps correctly to 10M/50M/100M/200M stroops
- USDC: 0.1/0.5/1/2 USDC maps correctly to 1M/5M/10M/20M stroops
- add frontend validation before deposit to catch invalid amounts early
- fixes UnreachableCodeReached when wrong amount sent to pool
- <a href="https://github.com/dzakwannajmi/Growthip/commit/b049dcd43f922d9f658e7e57d081f1183a715ed7">b049dcd</a>: fix(claim): add force: true to signAndSend for claim_to and deposit_paid

- claim/page.tsx: force sign claim_to transaction
- FreighterPayDemo.tsx: force sign deposit_paid transaction
- fixes 'This is a read call' warning from Stellar SDK
- <a href="https://github.com/dzakwannajmi/Growthip/commit/f19dc81638479a72f0355f49bbe697fd0fa538f7">f19dc81</a>: fix(deposit): reset AmountSelector state on token change via key prop

- add key={token.symbol} to AmountSelector to force re-mount on token switch
- prevents stale amount from previous token being sent to wrong pool
- fixes UnreachableCodeReached error when 0.5 XLM sent to XLM pool
- <a href="https://github.com/dzakwannajmi/Growthip/commit/65092d8a427d462a276d1ea76adb94b1406591dc">65092d8</a>: fix(deposit): reset AmountSelector state on token change via key prop

- add key={token.symbol} to AmountSelector to force re-mount on token switch
- prevents stale amount from previous token being sent to wrong pool
- fixes UnreachableCodeReached error when 0.5 XLM sent to XLM pool


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>