# 接口返回值状态码


## HTTP状态码

| code        | 描述        | 详细解释  |
| ------------- |-------------| -----|
| `200` | 成功	 | 成功  |
| `400` | 错误请求	 | 该请求是无效的，详细的错误信息会说明原因  |
| `401` | 验证错误	 | 验证失败，详细的错误信息会说明原因  |
| `403` | 被拒绝	 | 被拒绝调用，详细的错误信息会说明原因  |
| `404` | 无法找到	 | 资源不存在  |
| `429` | 过多的请求	 | 超出了调用频率限制，详细的错误信息会说明原因  |
| `500` | 内部服务错误	 | 服务器内部出错了，请联系我们尽快解决问题  |
| `504` | 内部服务响应超时	 | 服务器在运行，本次请求响应超时，请稍后重试  |


## 业务状态码

| code        | 描述        | 详细解释  | HTTP 状态码|
| ------------- |-------------| -----|----|
| `1000` | 服务内部错误	 | 服务器端内部逻辑错误,请稍后重试  |  500|
| `1001` | 缺少鉴权头部信息	 | 缺少API鉴权需要的http header信息  |  401|
| `1002` | AppKey不存在	 | AppKey不存在|  401|
| `1003` | App账户被锁定或删除	 | App 账户被锁定或删除 |  401|
| `1004` | 验证签名错误	 | 验证签名错误 |  401|
| `1005` | 参数错误	 | 参数数量或类型错误 |  400|
| `1006` | 参数长度超限	 | 参数长度超限，详细的描述信息会说明 |  400|
| `1007` | 调用频率超限	 | 调用频率超限，详细的描述信息会说明 |  429|
| `2000` | 文件验证失败	 | 文件验证失败，详细的描述信息会说明 |  200|