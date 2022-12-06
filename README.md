# InterestRateModelling_usingPCA
The purpose of this project is demonstrate principal component analysis of interest rates using R. 

Principal component analysis is frequently used to capture the variability in the movement of interest rates along the term structure. Understanding the varability allows for creation of stressed interest rate term structures that can be applied as part of a risk management program wherever the uncertainty of interest rates is a concern. Varying degrees of stress can be applied in the fashion of analytical Value-at-Risk (VaR) techniques. This exercise focuses on the 99.5th percentile as this degree is commonly the focus for many insurance companies and is aligned with benchmarks set by industry standards such as Solvency II Standard Formula. This technique is described in many places but this exercise will follow the process outlined in [How to Estimate and Calibrate Analytical VaR for Interest Rate Risk](https://hugepdf.com/queue/how-to-estimate-and-calibrate-analytical-var-for-interest-rate-risk_pdf?queue_id=-1).

Swap rate data is obtained for the following terms: 1-year, 3-year, 5-year, 7-year, 10-year, and 30-year. The source of the data is the Federal Reserve (H15 Discontinued Series, data available from July 2000 to September 2016). The data is available in the form of downloadable comma separated value (csv) files.

Libor daily data source: http://iborate.com/usd-libor/
I have calculated the monthly frequency libor as the average of daily libor rates for the corresponding yearmonth for all three maturities 1 month, 3 month and 6 month.

This project utilizes **reshape2, ggplot2, data.table, lubridate, zoo and xts packages**. 

**Principal component analysis based shocks are developed by considering the product of the principal component vectors (eigenvectors) and their standard deviations (square root of the eigenvalues). The degree of the stress is obtained by applying the desired number of standard deviation. The normal distribution is assumed for this purpose in combination with the 99.5th percentile.**

**Shocked rates are obtaind by applying the principal component analysis based shocks described above to the current interest rate term structure. Finally, the square root of 12 is applied to convert the monthly volatility to an annual figure.**
