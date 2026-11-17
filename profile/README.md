# Hyperloop Finance

**A non-liquidative lending protocol pairing each loan with a matching put option**

---

Long-duration BTC holders — treasuries, family offices, listed-company shareholders — need liquidity against their collateral without the path-dependent risk of forced liquidation. Traditional DeFi lending refuses this demand; it gets served bilaterally over-the-counter, expensively.

Hyperloop brings this market on-chain.

## What we're building

**[Awakening](https://github.com/hyperloop-finance/awakening-core)** — a non-liquidative, fixed-rate, fixed-maturity lending protocol on EVM.

- **Non-liquidative.** Borrowers are never subject to interim liquidation during the term of a loan. Lender principal is protected by a put option attributed to each loan at origination — if the collateral terminates below strike at maturity, the put pays out and the lender receives the full notional. There is no oracle path during the loan term that triggers forced action on borrower positions.

- **Fixed-rate, fixed-maturity.** Every market has a defined maturity date and a strike. Interest rates are discovered through offer-based order matching, not variable pool utilization curves. A 90-day loan against a 90-day put is one product, not two.

- **Options routed from real venues.** Puts are sourced and attributed at fill-time from established option markets:
  - **[Deribit](https://www.deribit.com/)** — via qualified custodian attestation (institutional put liquidity)
  - **[Derive](https://www.derive.xyz/)** — on-chain native, no attestation needed
  - Internal put writer pool as fallback for maturities/strikes not listed elsewhere

  Makers hedge externally on these venues and quote against the net funding cost — Awakening does not create option liquidity, it routes existing option liquidity into non-liquidative credit.

- **Built on [Morpho Midnight](https://github.com/morpho-org/midnight).** We inherit Midnight's offer-based market primitive (isolated, immutable, permissionlessly created markets) and add the put attribution token (PAT) layer that eliminates interim liquidation.

*Status: under active development. Not audited. Not deployed to any mainnet.*

## Connect

- Website — [hyperloop-fi.xyz](https://www.hyperloop-fi.xyz/)
- Twitter — [@hyperloop_fi_](https://x.com/hyperloop_fi_)
- Email — [deal@hyperloop-fi.xyz](mailto:deal@hyperloop-fi.xyz)
- Based in Hong Kong
