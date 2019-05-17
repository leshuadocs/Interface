    
**简要描述：** 

- 商户结算管理 -> 商户订单计费明细

**请求URL：** 
- ` http://***.***.cn/combine-pay-customer/new-agent-order/list-paybill `
  
**导出URL：** 
- ` http://***.****.cn/combine-pay-customer/new-agent-order/export-merchant-paybill `

**请求方式：**
- POST

**参数：** 

|参数名          |必选 |类型   |说明      |
|:----          |:---|:----- |-----     |
|startTime      |待确定  |String |开始时间   |
|endTime        |待确定  |String |结束时间   |
|searchType    |否  |Integer |查询类型 0-打款失败查询  1-商户打款记录查询   |
|merchantId    |否  |String |商户编号   |
|agentId  |是  |String |直属代理商编号（下拉框），与业务员二选一必填   |
|operatorAccount    |是  |String |发展业务员账号（下拉框），与直属代理商二选一必填|
|payBillFlag   |是  |Integer |打款类型  0 - t0    1 - t1 |
|state    |否  |Integer |打款状态（下拉框）,跟打款类型联动 |
|billId    |否  |String |打款单号 |
|pageNo         |否  |int    |页码 |
|pageSize       |否  |int    |分页大小 |

**T0打款状态：** 

 |ID |说明      |
 |:--- |-----     |
 |-1|打款失败   |
 |0|打款中   |
 |1|打款成功   |

**T1打款状态：** 

 |ID |说明      |
 |:--- |-----     |
 |-1|打款失败   |
 |0|打款中   |
 |1|打款成功   |
 |2|打款退票  |
 |3|冻结出款   |

 **返回示例**

``` 
  {
	"totalCount":2,
    "result_cde":"0",
	"result_msg":"成功",
    "list":{
	   "0" : {
	      "fCreateTime":"2018-08-08 00：00：00",
		  "fBillId":"00000012",
		  "fMerchantId":"87970980890",
		  "fMerchantName":"12345625354",
		  "fBankHolder":"XXXXXX",
		  "fBankName":"XXXX商户"，
		  "fBankAccount":"23247362773673647"，
		  "agentId":"123456",
		  "operatorId":"388904",
		  "payBillFlag":0,
		  "amountStr":"3432",
		  "stateStr":"打款成功",
		  "fRemark":"XXXXXXX",
		  "fUpdateTime":"2018-08-08 00：00：00"
		  },
	   "1" :  {
	      "fCreateTime":"2018-08-08 00：00：00",
		  "fBillId":"00000012",
		  "fMerchantId":"87970980890",
		  "fMerchantName":"12345625354",
		  "fBankHolder":"XXXXXX",
		  "fBankName":"XXXX商户"，
		  "fBankAccount":"23247362773673647"，
		  "agentId":"123456",
		  "operatorId":"388904",
		  "payBillFlag":0,
		  "amountStr":"3432",
		  "stateStr":"打款成功",
		  "fRemark":"XXXXXXX",
		  "fUpdateTime":"2018-08-08 00：00：00"
		  }
       }
    }

```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----|
|totalCount |int   |统计记录  |
|result_cde |String   |执行状态码  |
|result_msg |String   |执行结果说明  |
|fCreateTime |String   |创建时间  |
|fBillId |String   |打款单号  |
|fMerchantId |String   |商户编号  |
|fMerchantName |String   |商户名称(需单独查询其他库，无法导出) |
|fBankHolder |String   |银行开户名  |
|fBankAccount |String   |开户账号  |
|agentId |String   |直属代理商编号(需单独查询其他库，无法导出)  |
|operatorId |String   |发展业务员编号(需单独查询其他库，无法导出) |
|payBillFlag |Integer   |打款类型  |
|amountStr |String   |打款金额  |
|stateStr |String   |打款状态  |
|fRemark |String   |备注  |
|fUpdateTime |String   |更新时间  |

 **备注** 

- 更多返回错误代码请看首页的错误代码描述
