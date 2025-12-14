
# Introduction to Financial Instruments & Portfolios  
**Sukrit Mittal**  
ACM India Winter School 2025 – AI and Finance  
**December 8, 2025**

---

## Slide 0 – Session Goals
- Understand key financial instruments  
- Understand the no-arbitrage principle  
- Build intuition for forwards and options  

---

## Slide 1 – Session Agenda
- Types of financial instruments  
- No-arbitrage principle  
- Risk & return  
- Forward contracts  
- Options pricing & risk  

---

## Slide 2 – Types of Financial Instruments

### Risk-free
- **Bonds**: Loans to governments or companies with fixed interest and repayment of principal at maturity  
- **Money Market**: Very short-term, low-risk debt instruments (T-bills, deposits)

### Risky
- **Stocks**: Partial ownership in a company with claim on profits and assets  
- **Commodities**: Physical goods like oil, gold, wheat  
- **Derivatives**: Contracts whose value is derived from an underlying asset, rate, or index  

---

## Slide 3 – Risky & Risk-free Assets

### Risky Asset (Stock)
- Current price: \( S(0) \) (known)  
- Future price: \( S(T) \) (uncertain)  

Return:
\[
K_S = \frac{S(T) - S(0)}{S(0)}
\]

### Risk-free Asset
- Current price: \( A(0) \) (known)  
- Future price: \( A(T) \) (guaranteed)

Return:
\[
K_A = \frac{A(T) - A(0)}{A(0)}
\]

---

## Slide 4 – Portfolio

Portfolio with \(x\) stocks and \(y\) bonds:
\[
V(t) = xS(t) + yA(t)
\]

Change in value:
\[
V(T) - V(0) = x(S(T)-S(0)) + y(A(T)-A(0))
\]

Portfolio return:
\[
K_V = \frac{V(T) - V(0)}{V(0)}
\]

---

## Slide 5 – Some More Terms

- **Divisibility**: Ability to hold fractional shares or bonds  
- **Liquidity**: Assets can be bought or sold freely at market prices  
- **Long position**: Positive holding of an asset  
- **Short position**: Negative holding (asset is borrowed and sold)

---

## Slide 6 – Shorting an Asset

Can you profit when prices fall?
1. Borrow shares  
2. Sell them at current price  
3. Buy them back later  
4. Return shares to lender  

- Price falls → profit  
- Price rises → loss  

---

## Slide 7 – Shorting: Portfolio Representation

Shorting represented with negative positions:
\[
V(t) = -xS(t) - yA(t) + C(t) \ge 0
\]

Here, \(C(t)\) is collateral or cash reserve ensuring obligations can be met.

---

## Slide 8 – Arbitrage

**Arbitrage**: Risk-free profit with no net investment.

Classic example:
- Buy gold cheaper in one market  
- Sell simultaneously at a higher price in another  

Key properties:
- Simultaneous transactions  
- No risk (in theory)  
- No net capital required  

---

## Slide 9 – No-Arbitrage Principle

Markets do **not** allow:
- Risk-free profit  
- With zero initial investment  

Arbitrage exists only when someone makes a pricing mistake.

---

## Slide 10 – One-step Binomial Model: Assumptions

- Stock price has only two possible future values  
- Despite simplicity, captures core intuition  

---

## Slide 11 – Example (Binomial Model)

Given:
\[
S(0) = 100
\]

\[
S(T) =
\begin{cases}
125 & \text{with probability } p \\
105 & \text{with probability } 1-p
\end{cases}
\]

Bond:
\[
A(0)=100, \quad A(T)=110
\]

Returns:
- Stock: 25% (up), 5% (down)  
- Bond: 10%  

---

## Slide 12 – General Representation

One-step binomial tree:
\[
S(T) =
\begin{cases}
S_u(T) & p \\
S_d(T) & 1-p
\end{cases}
\]

Constraint:
\[
S_d(T) < S_u(T)
\]

Prices must satisfy no-arbitrage conditions.

---

## Slide 13 – Proposition (No-Arbitrage Condition)

To avoid arbitrage:
\[
\frac{S_d(T)}{S(0)} < \frac{A(T)}{A(0)} < \frac{S_u(T)}{S(0)}
\]

---

## Slide 14 – Case 1

If:
\[
\frac{A(T)}{A(0)} \le \frac{S_d(T)}{S(0)}
\]

Strategy:
- Borrow risk-free  
- Buy stock  

Result: Guaranteed non-negative payoff → arbitrage.

---

## Slide 15 – Case 2

If:
\[
\frac{A(T)}{A(0)} \ge \frac{S_u(T)}{S(0)}
\]

Strategy:
- Short the stock  
- Invest proceeds risk-free  

Again, arbitrage arises.

---

## Slide 16 – Modern Arbitrage

- Executed by algorithms in milliseconds  
- Opportunities are small and short-lived  
- Arbitrage keeps markets correctly priced  

Formal statement:
\[
V(0)=0, \quad V(T) \ge 0 \text{ a.s., and } P(V(T)>0)>0
\]
is impossible.

---

## Slide 17–21 – Understanding Risk

Risk = uncertainty of returns.

Investors:
- Prefer predictability  
- Demand higher return for higher risk  

---

## Slide 22 – Risk & Return

Assume returns follow a normal distribution.

Risk measured by standard deviation:
\[
\sigma(K) = \sqrt{\mathbb{E}[(K-\mu)^2]}
\]

---

## Slide 23 – Risk–Return Tradeoff

- Low risk → low return  
- High risk → high potential return  

---

## Slide 24–26 – Risk–Return Example

Portfolio outcomes:
\[
V(T)=
\begin{cases}
11600 & \text{up} \\
9600 & \text{down}
\end{cases}
\]

Returns:
\[
K_V =
\begin{cases}
16\% \\
-4\%
\end{cases}
\]

Expected return:
\[
\mathbb{E}[K_V]=12\%
\]

Risk:
\[
\sigma_V=8\%
\]

---

## Slide 27 – Forward Contracts

Forward contract:
- Agreement today  
- Buy/sell at time \(T\)  
- Price \(F\) fixed today  
- No upfront payment  

---

## Slide 28 – Options

- Right, not obligation  
- **Call**: right to buy at strike \(X\)  
- **Put**: right to sell at strike \(X\)  

Payoffs:
\[
\text{Call} = \max(S(T)-X,0)
\]
\[
\text{Put} = \max(X-S(T),0)
\]

---

## Slide 29 – Options Pricing

Portfolio:
\[
V(t)=xS(t)+yA(t)+zC(t)
\]

Pricing an option means finding \(C(0)\).

---

## Slide 30 – Replicating the Option

Solve:
\[
xS_u + yA_T = C_u
\]
\[
xS_d + yA_T = C_d
\]

Result:
\[
x=\frac{1}{2}, \quad y=-\frac{4}{11}
\]

Option price:
\[
C(0)=13.64
\]

---

## Slide 31 – Managing Risk with Options

- Options amplify returns  
- Can also reduce downside risk when structured properly  

---

## Slide 32 – Thank You
