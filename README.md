# Eigenportfolio Construction and Statistical Arbitrage Strategy

This repository contains a Python project on eigenportfolio construction and a statistical arbitrage strategy implementation. The project uses wavelet analysis, principal component analysis (PCA), the Marchenko-Pastur theorem, and an ARMA-GARCH model.

## Project Overview

The project involves the following steps:

1. **Data Preprocessing**: The EGX ticker price data is preprocessed using wavelets, specifically the Sym18 filter, to denoise the time series and retain long-term, significant changes.

2. **PCA on Denoised Returns' Correlation Matrix**: PCA is applied on the denoised returns' correlation matrix, obtained by eigenvalue decomposition.

3. **Eigenvalue Filtering Using the Marchenko-Pastur Theorem**: The Marchenko-Pastur theorem is used to filter the eigenvalues, retaining only the top 2 eigenvalues which are significant.

4. **Eigenportfolio Construction**: The two corresponding eigenportfolios are constructed, and their statistical properties such as their autocorrelation and respective allocations are examined.

5. **Market Neutrality of the 2nd Eigenportfolio**: The eigenvectors' property of orthogonality is used to infer that the 2nd Eigenportfolio is market neutral, since it is uncorrelated with the 1st eigenportfolio, which is generally considered to be the 'market force'.

6. **Statistical Arbitrage Strategy Implementation**: The 2nd eigenportfolio, which is found to be mean-reverting, is used as a mean-reverting portfolio and a statistical-arbitrage strategy is implemented on it.

7. **ARMA-GARCH Model for Expected Returns and Volatility Prediction**: An ARMA-GARCH model is used to model the mean-reverting portfolio, then used to predict the expected returns as well as volatility.

8. **Position Sizing Using Kelly Criterion**: The Kelly criterion is used for position sizing.

9. **Backtesting**: The strategy is backtested and it outperforms the market by a large margin.

## Detailed Description

### Data Preprocessing

The EGX ticker price data is preprocessed using wavelets, specifically the Sym18 filter. This step helps to denoise the time series and retain long-term, significant changes.

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/1be361c1-f72c-4119-a2ec-585fa0a4258b)


### PCA on Denoised Returns' Correlation Matrix

PCA is applied on the denoised returns' correlation matrix, obtained by eigenvalue decomposition. This step helps to identify the principal components that explain most of the variance in the data.

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/76fe7896-2bda-4313-8e8c-97daa9692e34)


### Eigenvalue Filtering Using the Marchenko-Pastur Theorem

The Marchenko-Pastur theorem is used to filter the eigenvalues. Only the top 2 eigenvalues are retained as they are found to be significant. The theorem states that:

Let $X$ be an $n \times p$ matrix whose entries are independent and identically distributed random variables with mean 0 and variance 1. Let $\gamma = \frac{p}{n}$ be the aspect ratio of the matrix. The sample covariance matrix is given by $S = \frac{1}{n}XX^T$. The Marchenko-Pastur theorem states that, as $n$ and $p$ tend to infinity with $\gamma$ fixed, the empirical distribution of the eigenvalues of $S$ converges almost surely to a non-random distribution known as the Marchenko-Pastur distribution.

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/9a7444ba-20fd-4928-ae30-f31b3549b303)

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/002b375b-8408-49ee-aab9-3922980ab35d)



### Eigenportfolio Construction

The two corresponding eigenportfolios are constructed using the eigenvectors corresponding to the top two significant eigenvalues. Their statistical properties such as their autocorrelation and respective allocations are examined.

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/1b40e955-446f-4afa-b935-42b46d5f9fb4)


![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/59979446-cdb2-4bc6-ae67-9ccd3c41910e)


### Market Neutrality of the 2nd Eigenportfolio

The eigenvectors' property of orthogonality is used to infer that the 2nd Eigenportfolio is market neutral since it is uncorrelated with the 1st eigenportfolio, which is generally considered to be the 'market force'.

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/a6c71a88-65d4-4c90-89b1-d6c8e76163b8)

### ARMA-GARCH Model for Expected Returns and Volatility Prediction

An ARMA-GARCH model is used to model the mean-reverting portfolio. This model is then used to predict expected returns as well as volatility.

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/18e5a8c1-8412-4917-8ac0-8d27f1d1fde3)


### Position Sizing Using Kelly Criterion

The Kelly criterion is used for position sizing based on predicted returns and volatility from ARMA-GARCH model.

$$
f^* = \frac{r - r_f}{v}
$$

### Backtesting

The strategy is backtested and it outperforms the market by a large margin. Maintaining market-neutrality and acheiving a daily alpha of 0.18%.

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/a77e8960-cd06-4da2-be5f-1816068f86a2)

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/184af4f9-5403-4454-baa1-1bddba15add6)

![image](https://github.com/omarequalmars/Eigenportfolios-using-Wavelets/assets/90857121/a3eaefed-1b97-4d3f-8f64-7fbd927561d2)

## Conclusion

This project demonstrates how wavelet analysis, PCA, Marchenko-Pastur theorem, ARMA-GARCH model can be combined together in constructing an effective statistical arbitrage strategy that outperforms market by a large margin.
