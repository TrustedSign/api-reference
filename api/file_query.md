# 文件查询

方法： `GET: /file/search`

说明：按条件获取文件列表

请求参数列表：

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `name` | String	 | 文件名检索条件  |
| `outId` | String	 |   应用内部文件标识检索条件    |
| `模板属性字段` | String	 | 模板属性检索条件  |


响应数据为file对象的数组:

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `id` | String	 |   平台内部文件标识    |
| `outId` | String	 |   应用内部文件标识    |
| `name` | String	 |   文件名称    |
| `status` | Int	 |   文件状态,0签署中;1完成    |
| `createdAt` | Date(UTC)	 |   创建时间    |
| `signedInfo` | Date(UTC)	 |   签署信息    |




HTTP请求
	
```
GET /file/search HTTP/1.1
Host: api.trustedsign.com
App-Key: uwd1c0sxdlx2
Nonce: dbe32ds53EioQeIpypj
Timestamp: 1408706337
Signature: 890b422b75c1c5cb706e4f7921df1d94e69c17f4
Content-Type: application/json;charset:UTF-8

{"name": "test", "field_1": "111"}
```

HTTP响应

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
	{"id": "5421ba2231badas2d2", "outId":"2011239202", "name": "test", "status":0, "createdAt": 2016-01-01T08:00:00+08:00},
]
```

