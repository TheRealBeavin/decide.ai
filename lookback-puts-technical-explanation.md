# Lookback Puts: Technical Explanation and Assessment

## What Is a Floating-Strike Lookback Put?

A floating-strike lookback put pays the difference between the highest price the underlying reached during the option's life and the price at expiry. So if an index peaks at ten thousand and finishes at eight thousand, the holder collects two thousand per contract regardless of when that peak occurred. The strike is not set at inception. It floats up to the running maximum as the market climbs.

This is exactly why the structure suits a bubble scenario where you suspect more upside before the fall. A vanilla put struck at today's level would expire worthless if the market rallies first and then crashes from a higher watermark. The lookback does not care. It always locks in the best exit.

There is also a fixed-strike variant, where the payoff compares a predetermined strike against the realized minimum price. Fixed-strike lookbacks can expire worthless if the realized extreme never crosses the strike threshold, so they behave more like vanilla options in that respect. The floating-strike version is the purer instrument: its payoff is always non-negative.

## Payoff Formulas

- Floating-strike call: S(T) minus S(min), where S(min) is the realized minimum price over the option's life.
- Floating-strike put: S(max) minus S(T), where S(max) is the realized maximum price over the option's life.
- Fixed-strike call: max of (S(max) minus K, zero).
- Fixed-strike put: max of (K minus S(min), zero).

Where S(T) is the terminal price, S(max) is the running maximum, S(min) is the running minimum, and K is the contractual strike.

## Pricing

Pricing comes from the Goldman-Sosin-Gatto framework (1979), which extends Black-Scholes to path-dependent payoffs using the reflection principle. The key state variable is the running maximum or minimum, not just spot. The formula combines two normal cumulative distribution function terms with a reflection term scaled by a cost-of-carry power exponent equal to two times (r minus q) divided by sigma squared, where r is the risk-free rate, q is the dividend yield, and sigma is volatility.

At inception, when the extreme equals spot, the floating-strike price reduces to the pure lookback premium over a vanilla at-the-money option. In one benchmark Monte Carlo simulation with spot of one hundred, strike of one hundred, five percent rates, twenty percent volatility, and one year to expiry, the floating put priced around thirteen point five versus roughly five point six for the vanilla equivalent, about two and a half times the cost. Discrete monitoring, daily or weekly sampling instead of continuous, trims the premium slightly because intra-day extremes are missed, but the markup remains substantial.

Because lookbacks capture extreme price movements, they are among the most expensive path-dependent exotic options. The holder is paying for perfect hindsight, the ability to enter or exit at the optimal price after the fact.

## Why They Fit a Bubble Hedge

If the AI trade has further to run before it breaks, a vanilla put bought today bleeds theta while the market grinds higher, forcing rolls at worse levels. The lookback removes that regret. Bank of America's head of exotics noted decent client demand for exactly this use case: hedging the scenario where markets rally before the selloff, with the strike setting at the max index level over the life of the trade.

To offset cost, desks pair the lookback put with a short vanilla put at a lower strike, an expanding put spread that partially funds the exotic leg while keeping defined risk.

## Caveats

1. The premium is steep enough that even a correct directional call loses money if the drawdown from the peak is smaller than the extra cost paid.
2. Liquidity is thin. These are mostly structured products through dealers, not exchange-listed contracts, so bid-ask spreads and early unwind costs can be ugly.
3. The payoff is linear in the drawdown from the max, so a shallow correction that recovers quickly still costs the full premium with little to show.
4. Delta and vanna behavior of a path-dependent option is not intuitive and should be modeled by a derivatives specialist before committing size.

## Bottom Line

Sound logic for a concentrated tech book worried about a delayed bust, but size it as a sleeve rather than the whole hedge, and have the Greeks stress-tested before execution.
