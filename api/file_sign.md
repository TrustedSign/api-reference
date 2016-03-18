# 文件签名

说明：文件签名是对文件内容进行数字签名，为了考虑到兼容传统视觉习惯，在文档中插入图像标识并与签名数据关联。

---

方法：POST /file/sign

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `fileId` | String	 | 可信签文件的标识  |
| `outId` | String	 | 应用系统对文件的标识  |
| `signatureOutId` | String	 | 签章的调用名称  | 
| `signatureImage` | String	 | 签章的图像数据base64编码  |
| `signatureRule` | int	 | 签章规则  |
| `signatureByPosition` | []Object	 | 签章绝对位置，对应signature_rule==0  | 
| `signatureByText` | []string	 | 签章定位文字，对应signature_rule==1  |
| `signatureByBookmark` | []string	 | 签章定位书签名称，对应signature_rule==2  |  
| `certOutId` | String	 | 证书的外部标识  | 

其中签章规则包括：

* `0` 绝对定位，默认规则
* `1` 按文字查找定位
* `2` 按书签查找定位



其中,position数据结构如下

```
{
   	"page": 0, //页数，从0开始
   	"x": 2000, //坐标
   	"y": 2000, //坐标
}
```

说明： 

* fileId与outId二选一，优先使用fileId 
* signatrueOutId 和signatureImage二选一，优先使用signatrueOutId, 如果均无效，则使用证书信息生成默认图章


响应数据列表:

HTTP Status Code 200表示成功，其他则失败，失败返回错误信息

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `code` | String	 |   错误代码    |
| `error` | String	 |   错误信息    |

