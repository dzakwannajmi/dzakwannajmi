<img src="https://my-badges.github.io/my-badges/fix-6+.png" alt="I did 7 sequential fixes." title="I did 7 sequential fixes." width="128">
<strong>I did 7 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/181b1aa0a22a62efc8c5bccbc50c4c978af12742">181b1aa</a>: fix(activity): add poolId to on-chain fetched notes

- fetchOnChainNotes now saves poolId with each decrypted note
- fixes pending notes not showing after pool filter was added
- notes without poolId correctly hidden from activity
- <a href="https://github.com/dzakwannajmi/Growthip/commit/cc52df4e9221dd1ab2f060194eaa3f9c4d893b32">cc52df4</a>: fix(activity): filter notes by current pool ID

- loadNotes now filters by NEXT_PUBLIC_POOL_ID and NEXT_PUBLIC_POOL_USDC_ID
- legacy notes without poolId hidden from activity page
- only current pool notes shown in pending and withdrawn tabs
- <a href="https://github.com/dzakwannajmi/Growthip/commit/6fb36d093f3ec50df87db2772c403ee5081c1c24">6fb36d0</a>: fix(pool): deploy new XLM pool CBNENJSA... (CAX3 full 8/8)

- update NEXT_PUBLIC_POOL_ID to CBNENJSASWTULXMJT3MI35Z4MZRY5WVNB6MROEVQIU5TBVEGPKRZOKMK
- add inline unlock form in activity page for pending notes
- add encryption unlock polling in activity page
- <a href="https://github.com/dzakwannajmi/Growthip/commit/b789e9d81ed361353aa08368cf5e587f84e4eb03">b789e9d</a>: fix(analytics): use creator notes for Received by Token and Average Tip

- Received by Token now sums from creator localStorage notes (not global pool)
- Average Tip Amount now calculated from creator notes per token
- tip counts now reflect creator's actual received tips
- <a href="https://github.com/dzakwannajmi/Growthip/commit/4c067ff4b0ee9844b68dabdf283af3404a886026">4c067ff</a>: fix(tip): generate amount presets from contract tip_amount

- presets now generated as 1x/5x/10x/20x of contract base amount
- fixes UI only showing 10 XLM when base is 10 XLM
- presets now correctly show 10/50/100/200 XLM
- <a href="https://github.com/dzakwannajmi/Growthip/commit/fd53662ad37b35417a23ffef454c4663397cfb42">fd53662</a>: fix(tip): fetch tip_amount from contract, filter valid presets

- fetch tip_amount from pool contract on page load
- filter AmountSelector presets to only show valid 1x/5x/10x/20x multiples
- add rpcUrl to Client instantiation for tip_amount fetch
- add minimum tip notice below amount selector
- <a href="https://github.com/dzakwannajmi/Growthip/commit/e49e6e6472098407b3833eb18b2b1477367012c4">e49e6e6</a>: fix(analytics): hide legacy notes without poolId

- legacy notes from old pools no longer shown in analytics
- only notes with matching current pool ID are displayed


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>