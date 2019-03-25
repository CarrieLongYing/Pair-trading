# Pair-trading
This is a investment strategy about pair trading: we want to find two stocks (one pair) such that their price movement should be similar:  
- For exmaple, if we think the stock prices of Facebook and Google are one pair, that is to said, if the price of Facebook goes up, then Google will also goes up
- In other words, the price difference of a pair should usually around 0, or technically, normalized with mean zero and a fixed standard deviation

In this project, beside the traditional method, we will also try one more novel method

## traditional method
If the price of stock Y and stock X satisify the OLS model (we will conduct a co-integration test to ensure the relationship is stable)
- Y =  a + b * X + error, where error is a white noise,

We can trade Y - a - b * X as a pair, and call Y - a - b * X as distance:
- When Y - a - b * X is larger that 0, it is very possible to go back to 0; when Y - a - b * X is less than 0, it will go up to 0
- That is to say, when the distance is large, it will tend to converge to 0

The best pair is when the standatd deviation of their price difference is very small, which shows that the two stocks move very close; 

Thus we can believe that when their price differen become large, it will converge eventually

## Novel method to construct pairs
- The problem of the traditional method: the two stocks move so close that they would barely diverge and we would have very few investment oppotunities 

#### Novel idea: 
- condition 1: the two stock price will intercept very often, which can tell us the two are similar stock
- condition 2: the standard deviation of the two stock is large, so we can have investment oppotunities
- NOTE: condition 1 is far more important than condition 2, cause we have to make sure the stocks are pair 
