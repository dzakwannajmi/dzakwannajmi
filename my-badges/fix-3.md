<img src="https://my-badges.github.io/my-badges/fix-3.png" alt="I did 3 sequential fixes." title="I did 3 sequential fixes." width="128">
<strong>I did 3 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/dzakwannajmi/Growthip/commit/d29f970ec3ecf5eb8b21a0c7e457fb16d3e57180">d29f970</a>: fix(crypto): wrap info with toBufferSource in deriveKey HKDF call

- info from TextEncoder also has ArrayBufferLike buffer type
- wrapping with toBufferSource ensures plain ArrayBuffer for Vercel TS strict
- <a href="https://github.com/dzakwannajmi/Growthip/commit/b31c3db36cab3b2cd2c23635279e46c5b949d5e6">b31c3db</a>: fix(crypto): fix BufferSource type error for TypeScript 5.x strict mode

- toBufferSource now creates explicit new ArrayBuffer via new ArrayBuffer(n)
- avoids SharedArrayBuffer vs ArrayBuffer incompatibility on Vercel
- resolves Vercel build failure on cryptoUtils.ts
- <a href="https://github.com/dzakwannajmi/Growthip/commit/964f1eb1e5953bff6665148bc31102324e1d94b4">964f1eb</a>: fix(crypto): fix ArrayBuffer type compatibility for Vercel TypeScript

- toBufferSource now checks instanceof ArrayBuffer before cast
- fixes Type error: SharedArrayBuffer not assignable to ArrayBuffer
- resolves Vercel build failure on cryptoUtils.ts:156


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>