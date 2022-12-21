# Roll-Returns-Extraction
Roll returns are the divergence or the difference between the futures returns and the spot returns. Which means that the roll returns are the excess benefit or cost of owning the underlying asset. They can also be thought of the divergence in the futures and spot returns.

### 1. Import modules
First, we will import the necessary libraries.

### 2. Read silver spot and futures data
Then, we will read the silver futures and spot prices from the csv file. 

1) SI is the continuous futures contract for silver. This is chained together from the futures contracts with different month expiries that are traded at COMEX.

2) Spot or underlying asset requires physical inventory which is difficult and not feasible for retail traders. Therefore, you will use SLV which closely tracks silver spot to less than an annual expense ratio of 0.5%. SLV stands for iShares Silver Trust. SLV buys and sells physical silver, to track silver prices.

### 3. Plot spot, ETF and near-term futures data
We will plot the line graphs to have a comparison between the Silver spot, SLV and futures.


### 4. Calculate the position
Roll returns are the excess cost or benefits of owning the underlying assets. It is calculated using the formula:

Roll returns = Futures Returns - Spot Returns 

1) We first calculate the roll returns as the difference in the near-term future returns, and the ETF and SLV, which tracks the silver spot.

2) After that, we calculate the position based on the term structure. That is if the term structure is in contango or backwardation. If near futures prices are greater than the spot, the term structure is in contango. Or else it is in backwardation. In contango, we take a short position on the futures prices and long position on the spot prices. In the case of backwardation, we take a long position on the futures prices and short prices on the spot prices. While it is extremely rare to have a situation where the near future prices are equal to the spot price, this would lead to no signal being generated.

### 5. Plot the positions taken based on the term structure
We plot the daily positions taken. The positions are taken based on whether the term structure is in contango or backwardation.

### 6. Evaluate the strategy
We calculate the strategy returns based on the positions you took and the roll returns you extracted from these positions. We also calculate the cost as follows:

1 SIL Futures Contract cost = IBKR Execution Fee USD 0.5 + Exchange Fee USD 0.85 + Clearing Fee USD 0.00 + Regulatory Fee USD 0.02 = USD 1.37

USD 1.37 is the contract cost for 1 lot or 5000 units of the underlying asset.

In order to extract roll returns we will be buying/selling both the futures contract and the ETF. Thus, we multiply the cost by 2.

### Conclusion
The strategy was able to give a 21% return over a period of around one year with a max drawdown of 4.91%. 
