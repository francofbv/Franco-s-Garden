#Finance #Math

---

**Method for pricing options**

- Suggests that stock shares or futures contracts will have a lognormal distribution of prices following a [[random walk]] with constant drift and volatility.

### Assumptions

- No dividends are paid out during the life of the option
- Markets are random bc market movements can't be predicted
- There are no transaction costs in buying the option
- The [[risk-free interest rate]] and volatility of the underlying asset are known and constant
- The returns of the underlying asset are normally distributed
- The option is European and can only be exercised at expiration

### Formula

$C = SN(d_1) - Ke^{-rt}N(d_2)$ 
$d_1 = \frac{\ln\left(\frac{S}{K}\right) + \left(r + \frac{\sigma^2}{2}\right)t}{\sigma \sqrt{t}}$ 
$d_2 = d_1 - \sigma_s \sqrt{t}$ 
- $C =$ Call option price
- $S =$ Current underlying asset price
- $K =$ Strike price
- $r =$ Risk-free interest rate
- $t =$ Time to maturity
- $N =$ Normal distribution
	- $N(d_1), N(d_2) =$ standard normal CDF, probability under risk-neutral measure that the option finishes in the money
- $\sigma =$ Volatility
- $SN(d_1) =$ present value of receiving the stock if the option is exercised
- $Ke^{-rt}N(d_2) =$ present value of paying the strike price only if the option is exercised
	- expected value of getting the stock - expected cost of exercising the option