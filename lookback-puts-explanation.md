# Lookback Puts: A Technical Explanation

## What Is a Floating-Strike Lookback Put?

A floating-strike lookback put pays the difference between the highest price the underlying reached during the option's life and the price at expiry. So if the index peaks at ten thousand and finishes at eight thousand, you collect two thousand per contract regardless of when that peak happened. The strike isn't set at inception. It floats up to the running maximum as the market climbs, which is exactly why it suits a bubble scenario where you suspect more upside before the fall. A vanilla put struck at today's level would expire worthless if the market rallies first and then crashes from a higher watermark. The lookback doesn't care. It always locks in the best exit.

## Pricing

Pricing comes from the Goldman-Sosin-Gatto framework, extending Black-Scholes with a reflection term. The key state variable is the running maximum, not just spot. At inception, when the max equals spot, a floating put runs roughly two and a half times the cost of an equivalent vanilla put in one benchmark simulation. That's the price of hindsight. There's no closed-form escape from it. Discrete monitoring, daily or weekly sampling instead of continuous, trims the premium a bit because you miss intra-day extremes, but you're still paying a substantial markup over vanilla.

## My Honest Take

The logic is sound for exactly this situation. If the AI trade has further to run before it breaks, a vanilla put you buy today could bleed away on theta while the market grinds higher, and you'd be forced to roll at worse levels. The lookback removes that regret. But three things give me pause.

First, the premium is steep enough that even a correct directional call can lose money if the drawdown from the peak is smaller than the extra cost you paid.

Second, liquidity is thin. These are mostly structured products through dealers like Bank of America, not exchange-listed contracts, so bid-ask spreads and early unwind costs can be ugly.

Third, the payoff is linear in the drawdown from the max, which means a shallow correction that recovers quickly still costs you the full premium with little to show.

## A Middle Path

Some desks pair the lookback put with a short vanilla put at a lower strike, an expanding put spread that partially funds the exotic leg. That keeps defined risk while preserving most of the path protection. For a seven million dollar book with heavy tech weight, I'd size it as a sleeve, not the whole hedge, and I'd want a derivatives specialist to model the Greeks before committing, because the delta and vanna behavior of a path-dependent option is not intuitive.

---

*Disclaimer: This is general educational information, not financial advice. Consult a qualified financial advisor before making investment decisions.*