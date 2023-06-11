# OKX-API-Trade-with-SuperTrend-parameter
个人实验项目

调用OKX API 

对于crypto交易对中 TraderView中的超级趋势参数 出现以及消失**上限线或下限线** 前后过程进行确认 

从而根据该参数指标的出现 进行多次买卖

模拟盘实验 请见 ‘Demo.py’ 文件
    该代码可用于在OKE模拟盘上自动交易加密货币。它的大致流程如下：
    
 - 导入必要的库和设置API密钥信息以及交易参数。
 
 - 实例化`OKXTrader`类，并初始化账户API和期货API，以及历史K线缓存。
 
 - 定义`get_historical_klines`函数，用于获取历史K线数据，并将其转换为numpy数组。如果缓存中已经存在该交易对的K线数据，则直接从缓存中读取；否则使用API获取历史K线数据，并将其保存到缓存中。
 
 - 定义`calculate_super_trend`函数，用于计算超级趋势指标。该函数接受收盘价序列、ATR指标的时间窗口大小、计算上轨和下轨的倍数等参数，并返回新的上轨、下轨、买入信号和卖出信号。

 - 定义`execute_trade_strategy`函数，用于执行交易策略。该函数接受交易对、下单数量、下单价格、买入信号、卖出信号、止损比例和止盈比例等参数，并根据当前仓位和交易信号执行相应的交易操作。
 
 - 实例化`OKXTrader`类，并调用`get_historical_klines`函数获取历史K线数据。
 
 - 调用`calculate_super_trend`函数计算超级趋势指标，并根据买入信号和卖出信号执行交易策略。如果存在买入或卖出信号，则获取最新成交价作为下单价格，计算下单数量并调用`execute_trade_strategy`函数执行交易。如果不存在买入或卖出信号，则输出信息提示没有发出买入或卖出信号。   

