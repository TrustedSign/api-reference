# 文件生成

## 直接上传
方法：`POST: /file/upload`

说明：直接上传本地文件生成合同, 支持的文件扩展名包括：（doc/docx/xls/xlsx/ppt/pptx/pdf/txt/tiff/html）

请求参数列表：

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `outId` | String	 | app内部对文件的标识  |
| `attach` | String 	 |   应用附加的数据，透传，小于128k        |
| `file` | File | 文件 |

响应数据列表:

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `id` | String	 |   成功创建的文件ID标识    |

示例：

```
curl -X POST -H "App-key: 9b5062s452mdf4d6" -H "Nonce: dbe32ds53EioQeIpypj" -H "Timestamp: 1457492931" -H "Signature: 6e2e85f40b96d8cf7c1d5a585ce6522d" -H "Cache-Control: no-cache" -H "Postman-Token: 376b3ed0-ec9f-3799-fad7-a1ad0b581c4b" -H "Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW" -F "outId=1101021234312453321" -F "file=@测试.pdf" "http://localhost:8080/app/file/upload"
```

HTTP请求
	
```
POST /app/file/upload HTTP/1.1
Host: localhost:8080
App-key: 9b5062s452mdf4d6
Nonce: dbe32ds53EioQeIpypj
Timestamp: 1457492931
Signature: 6e2e85f40b96d8cf7c1d5a585ce6522d
Cache-Control: no-cache
Postman-Token: 87b781b3-d240-fb2e-bb9b-43b482f555e6
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW

----WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="outId"

1101021234312453321
----WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="file"; filename="测试.pdf"
Content-Type: application/pdf


----WebKitFormBoundary7MA4YWxkTrZu0gW
```

HTTP响应

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{"id": "56249bbc7fc54e4d9ee9b664"}
```

## 通过模板生成
方法：`POST: /file/generate`

说明：直接上传本地文件生成合同
请求参数列表：

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `outId` | String	 | 应用内部对文件的标识，必须 |
| `name` | String	 | 文件名称， 必须  |
| `templateInvokeName` | String	 | 模板名称调用标识，必须  |
| `fields` | Object 	 |   应用附加的数据，可选        |
| `attach` | String 	 |   应用附加的数据，透传, 小于128k，可选        |

说明： fields记录了要替换模板中指定区域的的数据，例如{"field_1": "data1", "field_2": "data2"}

响应数据列表:

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `id` | String	 |   成功创建的文件ID标识    |

HTTP请求
	
```
POST /file/generate HTTP/1.1
Host: api.trustedsign.com
App-Key: uwd1c0sxdlx2
Nonce: dbe32ds53EioQeIpypj
Timestamp: 1408706337
Signature: 890b422b75c1c5cb706e4f7921df1d94e69c17f4
Content-Type: application/json;charset:UTF-8

{"out_id": "100020202","name":"测试合同", "attach": "11232444", "template_id": "56249bbc7fc54e4d9ee9b664", "fields": {"field_1": "data1", "field_2": "data2"}}
```

HTTP响应

```
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{"code": 0,"file_id": "56249bbc7fc54e4d9ee9b664"}
```


