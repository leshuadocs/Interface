# 查询用户openid

**简要描述：** 
- openid：用户在公众号内的身份标识，不同公众号拥有不同的openid。商户后台系统通过登录授权、支付通知、查询订单等API可获取到用户的openid。主要用途是判断同一个用户，对用户发送客服消息、模版消息等。可通过如下链接查看微信官方相关释义 https://pay.weixin.qq.com/wiki/doc/api/micropay_sl.php?chapter=2_2
- 注: 此接口需要上送户付款码和对应的微信公众号appid才能查询到用户openid

**参数:**

- 请求参数

| 参数名     | 变量名      | 必填 | 限制 | 类型   | 说明                        |
| ---------- | ----------- | ---- | ---- | ------ | --------------------------- |
| 接口名     | service     | 是   | 无   | string | query_openid 注：此为固定值 |
| 商户号     | merchant_id | 是   | 10   | string | 由乐刷分配                  |
| 授权码     | auth_code   | 是   | 32   | string | 微信授权码                  |
| 微信appid  | appid       | 是   | 32   | string | 微信公众号ID                |
| 随机字符串 | nonce_str   | 是   | 32   | string | 随机字符串                  |
| 签名       | sign        | 是   | 32   | string | MD5签名结果                 |



- 返回参数

| 参数名       | 变量名         | 必填 | 限制 | 类型   | 说明                                                         |
| ------------ | -------------- | ---- | ---- | ------ | ------------------------------------------------------------ |
| 返回状态码   | resp_code      | 是   | 无   | string | 0 - 成功，非0 - 失败。注：此字段是通信标识，业务状态要看result_code |
| 返回错误信息 | resp_msg       | 否   | 无   | string | 错误描述：resp_code非0时返回                                 |
| 业务结果     | result_code    | 是   | 1    | string | 0 - 成功，非0 - 失败                                         |
| 错误码       | error_code     | 否   | 无   | string | 参考错误码                                                   |
| 错误码描述   | error_msg      | 否   | 无   | string | 错误信息描述                                                 |
| 商户号       | merchant_id    | 是   | 10   | string | 由乐刷分配                                                   |
| 商户订单号   | third_order_id | 是   | 64   | string | 商户内部订单号                                               |
| 随机字符串   | nonce_str      | 是   | 32   | string | 随机字符串                                                   |
| 签名         | sign           | 是   | 32   | string | MD5签名结果                                                  |
| 用户子标识   | sub_openid     | 是   | 无   | string |                                                              |
| 商户号       | merchant_id    | 是   | 10   | string | 由乐刷分配                                                   |
