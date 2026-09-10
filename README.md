# Option-pricing-project
Black-Scholes pricing of European options, Greeks derived analytically, Monte Carlo valuation compared to Black-Scholes valuation, with an implied volatility surface built from real SPY options data.

# Features
Black-Scholes pricer for European options with put-call parity verification.

Greeks derived analytically (Delta, Gamma, Vega, Rho, Theta). Each Greek was derived by differentiating the Black-Scholes price formula with respect to the relevant parameter, and applying the chain rule. 

Vectorised Monte Carlo pricer and convergence analysis with Black-Scholes with 95% confidence interval bands

Visualisations of Greeks against spot and expiry

Implied volatility backsolved for confirmation against real market data 

IV smile and surface plotted for real SPY data

# Results
Implied volatility surface on SPY call options with various expiries

<img width="306" height="308" alt="SPY IV surface" src="https://github.com/user-attachments/assets/6fa85e24-ca0e-466d-b13e-ccc4892ebc92" />

IV against moneyness (K/S)

IV increasing away from ATM, with higher IV for deep ITM calls, Having the same IV as OTM puts, this is the standard equity index skew

Surface minimum around 1.05 moneyness (K/S)

Implied volatility smile on an SPY call option with a relatively short expiry (T = 0.12)

<img width="428" height="338" alt="SPY volatility smile" src="https://github.com/user-attachments/assets/99d1daa9-7127-41ae-862c-4d1337767195" />

IV against strike

# Methododlogy

SciPy's brentq used in the IV solving, as it is more reliable than other methods such as Newton-Raphson, which is faster but can diverge

Monte Carlo method used to verify the Black-Scholes price, as well as verification of the call-put parity

# Data

Data used from Finance API.

Manual data taken of calls from Yfinace, with Yfinance API having a known Rate limiting issue

The data was captured on the date 04/09/2026, including the spot and the calls dataframe

# Limitations

Deep ITM calls unstable at short expiries

European pricing used on an American style option

A constant risk free rate of 0.05 used throughout

only five discrete expiries due to the Yfinance rate limiting issue

# Tech stack

NumPy, SciPy, Yfinance, Pandas, Matplotlib













