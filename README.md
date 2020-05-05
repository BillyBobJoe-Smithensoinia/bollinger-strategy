# Bollinger_strategy

## Strategy description

MB middle line: simple moving average of 10 days

UP line: middle line + 1.5x(standard deviation of 30 days)

DN line: middle line - 1.5x(standard deviation of 30 days) 

If the close position breaks up the UP line, open long position, and if price drops down below middle line, close the postion.

If the close position breaks down the DN line, open short position, and if price breaks up middle line, close the postion.  

**Please note that this strategy is to simply predict the trend from the close price, and to open and close positions based on the predicted results. The prediction does not provide accuracy guarantee.**

**Moreover, KuCoin provides the transaction data of level 3, great matching engine, and the commission discount specially offers to the API customers, which could greatly reduce the disadvantages of the trading operations. At the same time, we offer the sandbox environment as the data testing support to avoid the risks.**

**Only a simple and incomplete trading strategy is provided here, so please pay attention to avoiding risks when using it. Of course, we do not want you to suffer more losses, so please do not directly run it in the actual environment before you have tested it yourself. We do not want you to become a philanthropist! ! !**

**If you want to use the strategy in the actual environment to earn stable profits, we hope that you can make test adjustments in the sandbox environment with other parameters or strategies to enable you to achieve your goals. We also look forward to sharing your test data and Insights.**

**Surely, if you encounter any problems in this process, or you have a profitable strategy to share, please reflect in ISSUE, we will try to respond in a timely manner.**



## How to use

* After clone this project to your local, install the dependency: 

  ```shell script
  pip install python-kumex
  ```

* Paste config.json.example,  rename as config.json, then add the relevant configuration information:  

  ```
  {  
    "api_key": "api key",
    "api_secret": "api secret",
    "api_passphrase": "api pass phrase",
    // if sandbox
    "is_sandbox": true,
    // contract name, e.g.: XBTUSDM 
    "symbol": "contract name",
    // leverage, e.g.:5
    "leverage": "Leverage of the order",
    // order size, e.g.: 1
    "size": "Order size. Must be a positive number",
    // time frame of Kline, mesure time by minute, e.g.:60(60min)
    "resolution": "kline resolution,count by minute,such as 60,it means 60min(1h) kline",
    // threshold value
    "valve": "valve",
  }
  ```

  

* Run your strategy

  ```shell
  ./bollinger.py
  ```

  