# 布林强盗突破策略

## 策略说明

MB中轨：10日的简单移动平均

UP上轨：中轨 + 1.5倍30日标准差

DN下轨：中轨 - 1.5倍30日标准差

如果收盘价上穿布林上轨，则买入，价格丢破中轨平仓

如果收盘价下穿布林下轨，则卖出，价格突破中轨平仓

**请注意，该策略是在K线收盘时对走势进行简单预测，根据预测结果进行开仓及平仓操作，该预测不提供准确性保证，也仅是一个简单的交易策略，请不要在实际环境直接使用，否则，你必然会亏钱！**

**不过，如果你想在实际环境中利用策略获得盈利，我们希望你能够在sandbox环境配合其他参数或是策略进行测试调整，以使你能够获得盈利。当然，如果这个过程中，你遇到任何问题需要帮助亦或是有好的想法想要分享，请在ISSUE中反映，我们会努力及时响应。**

## 如何使用

* 克隆该策略项目至本地后，安装依赖：
  ```shell script
  pip install python-kumex
  ```

* 复制config.json.example，并重命名为config.json，然后完善相关的配置信息

  ```json
  {  
    "api_key": "api key",
    "api_secret": "api secret",
    "api_passphrase": "api pass phrase",
    // 是否是沙盒环境
    "is_sandbox": true,
    // 合约名称，比如：XBTUSDTM 
    "symbol": "contract name",
    // 杠杆倍数，比如：5
    "leverage": "Leverage of the order",
    // 开仓数量，比如：1
    "size": "Order size. Must be a positive number",
    // K线图基准，单位是分钟，比如：60，代表60min，即1h为基准的K线图
    "resolution": "kline resolution,count by minute,such as 60,it means 60min(1h) kline",
    // 阈值
    "valve": "valve",
  }
  ```

  

* 让你的策略运行起来：

  ```shell
  ./bollinger.py
  ```

  