## 协议规范


用户调用可信签API必须遵循以下规则：

* 传输方式:
	
	为保证接口安全性，采用HTTPS传输
* 提交方式:	
	
	采用HTTP GET或POST方法提交
	
	带有文件传输:Content-Type:multipart/form-data; boundary=xxx
	
	无文件传输:Content-Type:application/json
* 数据格式:	

	请求和响应数据均采用JSON格式
* 字符编码:	
	
	统一采用UTF-8字符编码
* 签名算法	
	
	MD5，后续会兼容SHA1、SHA256、HMAC等。
* 签名要求	
	
	请求和接收数据均需要校验签名，详细方法请参考安全-签名算法