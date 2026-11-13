# Tostado, a demo store for Proofed

A made-up coffee roaster that [Proofed](https://github.com/t1dem/proofed) checks on every pull request. Names, prices and the shop itself are invented for the demo.

The store is a Vite + React app with no backend: a price list, a bag with promo codes (`WELCOME10` takes 10% off), free shipping from €50, and a checkout that ends on an order page. The money logic lives in `src/pricing.ts`, which is where the demo PRs break things.

Three scenarios in `.proofed/scenarios/` describe what must keep working: the promo code total, the free shipping threshold, and placing an order. A PR runs only the scenarios whose files it touches.

[PR #1](https://github.com/t1dem/proofed-demo-store/pull/1) shows the whole loop: a one-line "simplification" breaks lowercase promo codes, Kane catches it in Chrome, Claude Code fixes it, and Kane checks the fix before it lands on the branch.

```sh
pnpm install
pnpm dev
```
