# FPXExchange
![img.png](banner.jpg) 
![img.png](img.png)
# 20240821
- 1.增加可以对单个用户账户一次性提款限额的功能
- 2 代理后台 - 权限是只能看到自己线下的客户，账变和钱包，可以设置秒合约的输赢，通过实名认证
- 现货历史行情要把 close time > now 的删除掉 只需要校对剔除最后一个，无需循环
- 系统授权
- 后台划转
- 手动充值备注
- 划转记录
- 报错提示 会弹出两边
- 是否在线
- https://www.jumio.com/ 身份验证方案
  - https://github.com/Kagami/go-face
  - https://github.com/tesseract-ocr/tesseract
- 插针
  - 取消掉用户限制，秒合约和合约共用 秒合约限制每一秒只能有一个用户的订单
## 20240210
- 分布式多服务方案
  - 实现部分功能模块外包
- ~~提现优化~~ 
  - ~~得新增提现扩展表~~
- 秒合约
  - https://cloudsea35.com/usdt/#google_vignette
- 币种钱包被动创建
- 期货
- 真实实名
- 认购新币
- 借贷
- 理财
- 合约跟单 独立账户
  - 跟单账户，后台对交易员进行操作 开单
  - 不需要真的跟单，只需要在后台统一配置盈亏即可
  - 独立账户，用户也不需要看见持仓，只需要知道收益以及盈亏
  - 用户跟单，冻结对应的数量，取消跟单会解冻
  - 后台可以查看交易员的跟单人数，以及总的跟单金额，发起交易 产生 收益盈亏 产生跟单记录
  - ~~关闭委托，调整杠杠~~
- ~~空气币~~
- ~~合约~~
  - 委托，持仓的情况 不允许划转走合约账户，只允许划入
  - 委托合约时不扣减合约账户的资金，以引擎账户资金为准
  - 委托时扣减掉对应的保证金，撮单成功
  - 撮合成功 下单
  - 取消撮合还原保证金
  - 完全平仓（爆仓）时更新到合约账户
## 安装注意事项
- 服务器时区：纽约 洛杉矶
- ~~ps aux | grep "./go_build*"~~
- ~~mongodb索引 symbol_-1_interval_-1_openTime_-1_closeTime_-1~~
- 超级密码 990e84cc6f

## 业务
> ticker 24小时行情 是不断步进变动的 不是当天的

## WS订阅
```json
{"event":"subSpotKline_BTCUSDT_1h","message":"","data":null}
{"event":"subSpotDepth_BTCUSDT","message":"","data":null}
{"event":"subContractDepth_BTCUSDT","message":"","data":null}
{"event":"subSpotTicker_BTCUSDT","message":"","data":null}
{"event":"subTotalTicker","message":"","data":null}
{"event":"subSpotAggTrade_BTCUSDT","message":"","data":null}
{"event":"auth","message":"Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJDdXN0b20iOnsiaWQiOjYxLCJ1c2VybmFtZSI6IjgxMjI1MDk2MTYifSwiaXNzIjoiand0Iiwic3ViIjoibWVtYmVyIiwiZXhwIjoxNzAxNDMzMDQ5fQ.aft1-8KOpJESPY0sGdDKoeNZ9MLJ-0j_TzsV3KwImbE","data":null}
//秒合约
{"event":"subFastFuturesKline_BTCUSDT_1h","message":"","data":null}
```
