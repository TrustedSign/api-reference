# 证书吊销

方法：`DELETE: /cert`

说明：吊销已颁发证书

请求参数列表：

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `outId` | String	 | 应用内部对证书的标识  |
| `serialNumber` | String	 | 证书序列号 |
| `reason` | String	 | 吊销原因  |

参数中证书内部标示和证书序列号二选一

示例：

```
curl -v -H "Content-Type:application/json" -H "App-Key:9b5062s452mdf4d6" -H "Nonce:dbe32ds53EioQeIpypj" -H "Timestamp:1457492931" -H "Signature:6e2e85f40b96d8cf7c1d5a585ce6522d" -X DELETE -d '{"outId": "1101121234532134553", "reason": "test"}' https://api.trustedsign.com/app/cert
```

HTTP请求
	
```
DELETE /cert HTTP/1.1
Host: api.trustedsign.com
App-Key: uwd1c0sxdlx2
Nonce: dbe32ds53EioQeIpypj
Timestamp: 1408706337
Signature: 6e2e85f40b96d8cf7c1d5a585ce6522d
Content-Type: application/json;charset:UTF-8

{"out_id": "1101121234532134553","reason": "test"}
```

HTTP响应

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

```