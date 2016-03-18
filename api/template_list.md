# 获取模板列表


方法： `GET: /template`

说明：获取用户所有模板列表

请求参数列表：

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `name` | String	 | 按名称过滤  |


响应数据为template对象的数组:

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `name` | String	 |   模板调用名称    |
| `type` | String	 |   模板类型    |
| `isActive` | Bool	 |   是否启用    |
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
	{"name": "test", "type":"test", "is_active": true, "created_at": 2016-01-01T08:00:00+08:00},
	{"name": "test1", "type":"test", "is_active": true, "created_at": 2016-01-01T08:00:00+08:00}
]
```

