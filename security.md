# 安全


## 签名算法

每次请求 API 接口时，均需要提供 4 个 `HTTP Request Header`，具体如下：

| 名称        | 类型        | 说明  |
| ------------- |-------------| -----|
| `App-Key` | String	 |   可信签开发平台分配的App-Key。    |
| `Nonce` | String 	 |   随机字符串，最大长度32    |
| `Timestamp` | String	 |   时间戳，从 1970 年 1 月 1 日 0 点 0 分 0 秒开始到现在的秒数    |
| `Signature` | String  |  数据签名     |

Signature (数据签名)计算方法：将系统分配的App-Secret(秘钥)、Nonce (随机数)、Timestamp (时间戳)三个字符串按先后顺序拼接成一个字符串并进行 `MD5` 哈希计算。如果调用的数据签名验证失败，接口调用会返回 HTTP 状态码 401。其他状态码请参见状态码表。

```
md5(App-Secret + Nonce + Timestamp)
```

**关于App-Key 和 App-Secret请登录平台，企业管理->开发配置中查看和管理**

## 生成随机数算法
HTTP Request Header中加入的nonce随机字符串，主要保证签名不可预测。我们推荐生成随机数算法如下：调用随机数函数生成，将得到的值转换为字符串。