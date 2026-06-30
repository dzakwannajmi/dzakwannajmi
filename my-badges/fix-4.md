<img src="https://my-badges.github.io/my-badges/fix-4.png" alt="I did 4 sequential fixes." title="I did 4 sequential fixes." width="128">
<strong>I did 4 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/d89edde20cf02dad918618d8f2ed933fd3e7439c">d89edde</a>: fix(ts): add show prop to WalletModal in tip page

- tip/[id]/page.tsx: pass show={showWalletModal} to WalletModal
- remove stale conditional wrapper
- WalletModal now has consistent bounce animation everywhere
- <a href="https://github.com/dzakwannajmi/Growthip/commit/d4e85918d94f31cf221d81381fbc7c7e139d72bf">d4e8591</a>: fix(ts): QRCodeSVG value null check in dashboard
- <a href="https://github.com/dzakwannajmi/Growthip/commit/709734713fc4dbb3233d3f284c348f2a27de2900">7097347</a>: fix(modal): WalletModal bounce close animation + share message limits

- WalletModal: add show prop so Modal component knows when to play bounceOut
- dashboard: pass show={showWalletModal} to WalletModal
- share textarea: maxLength=280 + slice(0,280) to enforce hard limit
- counter turns red at 260+ characters
- applies to both dashboard and links page
- <a href="https://github.com/dzakwannajmi/Growthip/commit/2a473254e0c73edf6dbd87115ecfdec2ddd1fcdd">2a47325</a>: fix(modal): X button close + bounceOut animation

- useEffect watches show prop changes from parent
- X button calls onClose() → show becomes false → bounceOut plays
- backdrop click also triggers bounceOut before unmount
- consistent open/close animation across all modals


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>