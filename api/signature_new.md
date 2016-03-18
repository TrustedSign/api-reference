# 签章制作


方法：`POST: /signature`

说明：上传印章图样，支持格式bmp/png/jpg

请求参数列表：

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `outId` | String	 | 应用内部对印章图样的标识，小于64位  |
| `displayName` | String	 | 签章显示名称  |
| `attach` | String 	 |   应用附加的数据，透传，小于128k        |

响应数据列表:

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `id` | String	 |   成功创建的印章唯一内部ID标识，32位    |

示例：

HTTP请求
	
```
POST /signature HTTP/1.1
Host: api.trustedsign.com
App-Key: uwd1c0sxdlx2
Nonce: dbe32ds53EioQeIpypj
Timestamp: 1408706337
Signature: 890b422b75c1c5cb706e4f7921df1d94e69c17f4
Content-Type: multipart/form-data; boundary=----1294919323195  

-----------------------------1294919323195
Content-Disposition: form-data; name="out_id"

12345678
-----------------------------1294919323195
Content-Disposition: form-data; name="attach"

test
-----------------------------1294919323195
Content-Disposition: form-data; name="upload_file"; filename="xxxx.png"
Content-Type: application/octet-stream
```

HTTP响应

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{"signature_id": "56249bbc7fc54e4d9ee9b664"}
```