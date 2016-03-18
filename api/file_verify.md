# 文件验证

方法：`POST: /file/verify`

说明：上传合同文件进行安全验证


响应数据列表:

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `code` | Int	 |   业务状态码   |
| `message` | String	 |   业务状态信息    |
| `fileId` | String	 |   平台内部文件id    |
| `outId` | String	 |   应用内部文件id    |
| `signInfo` | Object	 |   签名信息    |

示例：

HTTP请求
	
```
POST /file/upload HTTP/1.1
Host: api.trustedsign.com
App-Key: uwd1c0sxdlx2
Nonce: dbe32ds53EioQeIpypj
Timestamp: 1408706337
Signature: 890b422b75c1c5cb706e4f7921df1d94e69c17f4
Content-Type: multipart/form-data; boundary=----1294919323195  

-----------------------------1294919323195
Content-Disposition: form-data; name="upload_file"; filename="xxxx.pdf"
Content-Type: application/octet-stream
```