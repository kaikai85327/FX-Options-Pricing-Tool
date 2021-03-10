# FX-Options-Pricing-Tool
DualCurrencyDeposit_DCD 

**DCD Explanation**
DCD is a very popular and liquidly traded standard FX-linked investment. It is basically the combination of a money deposit and selling a call. The investor gets higher return with enhanced rate than market interest rate. In return, the investor also takes on FX risk. At the beginning both side set a pre-agreed conversion rate (strike) for the domestic and foreign currency. If at maturity, the spot rate is lower than the conversion rate, the investor gets back the full deposit in domestic currency with the interest calculated with enhance rate. However, if the spot rate exceeds the conversion rate at maturity, the investor gets back the deposit in foreign currency with the pre-agreed conversion rate. In whichever case the interest rate will be returned in domestic currency. Due to the depreciation, the deposit returned in foreugn currency worths less than the amount deposited at the beginning. Therefore, the investor faces the risk of losing his capital.


**Pricing Tool Technics**
Based on certain market condition, we could calculate the price for a dual currency contract. The formula is as below: 

**N ∗ Re ∗ d/360 = N ∗ Rd ∗ d/360 + Premium - Margin**

N = notional amount
Re = Enhanced rate
d/360 = Time to maturity
Rd = market interest rate
Premium of the vanilla in the unit of the underlying

We could calculate premium with the help of black and scholes formula:

𝐏𝐫𝐞𝐦𝐢𝐮𝐦/𝑵  = exp(−(𝒓𝒅−𝒓𝒇) ∗ 𝑻) ∗ [𝑭 ∗ 𝑵(𝒅+) − 𝑲 ∗ 𝑵(𝒅−)]

Our goal is to be able to calculate the value of any missing variable. Here I took the function from black.py as reference and modified so that it could be used to FX options. Afterwards, I combined the function with TKinter so that the pricing tool could visualized.

The scenario example could be: Given certain sales margin and enhanced rate, what conversion rate (strike) is proper? Or given enhanced rate and strike, how much margin will be earned. 

With this tool, the number of any variable could be easily calculated. The investor and the bank can also flexibly adapt the variables according to their needs.

