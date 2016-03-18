# 接口列表

接口调用地址统一为 `https://api.trustedsign.com/app`

下列接口中涉及的接口调用地址为 接口基础地址+接口方法名，例如：
https://api.trustedsign.com/app/file/upload

* [证书颁发](api/cert_new.md)
* [证书吊销](api/cert_revoke.md)
* [文件生成](api/file_new.md)
* [文件嵌入](api/file_embed.md)
* [文件签名](api/file_sign.md)
* [文件查询](api/file_query.md)
* [文件验证](api/file_verify.md)
* [模板列表](api/template_list.md)
* [签章制作](api/signature_new.md)
* [签章列表](api/signature_list.md)
* [获取令牌](api/token.md)

**所有接口建议使用[curl](http://curl.haxx.se)或者[postman](https://www.getpostman.com)进行调试开发**