# 获取签章列表


方法： `GET: /signature`

说明：获取签章列表

请求参数列表：

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `keywords` | String	 | 关键词过滤(根据out_id和display_name匹配)  |


响应数据为signature对象的数组:

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `id` | String	 |   签章唯一标识    |
| `outId` | String	 |   应用平台内签章标识    |
| `displayName` | String	 |   签章显示名称    |
| `type` | String	 |   签章类型    |
| `createdAt` | Date(UTC)	 |   创建时间    |




HTTP请求
	
```
GET /template HTTP/1.1
Host: api.trustedsign.com
App-Key: uwd1c0sxdlx2
Nonce: dbe32ds53EioQeIpypj
Timestamp: 1408706337
Signature: 890b422b75c1c5cb706e4f7921df1d94e69c17f4
Content-Type: application/json;charset:UTF-8

{"name": "test"}
```

HTTP响应

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
	{"id":"890b422b75c1c5cb7","out_id": "110112112342121", "type":"test", "display_name": "测试签章", "created_at": 2016-01-01T08:00:00+08:00}
]
```

