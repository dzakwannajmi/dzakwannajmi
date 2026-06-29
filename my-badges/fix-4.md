<img src="https://my-badges.github.io/my-badges/fix-4.png" alt="I did 4 sequential fixes." title="I did 4 sequential fixes." width="128">
<strong>I did 4 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/4923e3a2f2835cf14910b61f1b7a0f3eedd25521">4923e3a</a>: fix(dashboard): set registered flag before async loop to prevent spam

- flag set immediately before register_recipient loop starts
- prevents re-entry from 2s polling interval during async operations
- fixes duplicate Freighter popups on dashboard load
- <a href="https://github.com/dzakwannajmi/Growthip/commit/40ea3d430b37e1d48e831e0939c847da1e5e826d">40ea3d4</a>: fix(dashboard): auto-register recipient in all pools (XLM + USDC)

- register_recipient now called for both POOL_ID and POOL_USDC_ID
- fixes claim rejected for USDC pool when wallet is new
- per-pool silent fail so one failure doesn't block the other
- <a href="https://github.com/dzakwannajmi/Growthip/commit/ef6b7a89f4b466e61693694ffeeee6ce429dd1be">ef6b7a8</a>: fix(dashboard): auto-register only once per wallet, not on every poll

- add growthip:registered:{addr} flag to localStorage
- prevents spam register_recipient calls every 2s from polling interval
- register only triggers on first dashboard load per wallet
- <a href="https://github.com/dzakwannajmi/Growthip/commit/da96027ca79ac9ff467a47de360b9f032998f8fc">da96027</a>: fix(dashboard): auto-register recipient hash on pool connect

- dashboard now checks if creator is registered in pool on mount
- if not registered, auto-triggers register_recipient transaction
- fixes 'Claim rejected by contract' for new wallets on pool V4
- silent fail so non-critical path doesn't break the UI
- also remove debug merkle log from merkle.ts


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>