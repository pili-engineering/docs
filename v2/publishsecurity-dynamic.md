## Dynamic动态推流

鉴权方式的一种。
由nonce/token共同参与签算合法的URL，形如`rtmp://<HubPublishDomain>/<StreamKey>?nonce=<Nonce>&token=<PublishToken>&<OtherKey>=<OtherValue>`

### 参数说明：

| 名称     | 类型   | 必填 | 默认值 | 描述 |                                      
|----------|--------|------|--------|---------|
| nonce    | int    | 是   | none   | 比上次推流使用的Nonce大的任意值。推荐使用推流时刻的UNIX Timestamp。时间为秒。|
| token | string | 是   | none | 查看[token计算方式](#token) |
| otherkey | string | 否   | none   | 任意key名及任意符合URL规范的字符串值。当otherkey参与了token计算时，构造推流地址时需将otherkey包括在内。 |

### <a name="token"></a>TOKEN计算方式

`sign = hmac_sha1("/<StreamKey>?nonce=<Nonce>&<OtherKey>=<OtherValue>", "<PublishKey>")`
`publishToken = url_base64(sign)`

### 使用方式：

1. 生成nonce值
2. 获得PublishKey
3. 通过[token计算方式](#token)计算出token
4. 获得推流地址`rtmp://<HubPublishDomain>/<StreamKey>?nonce=<Nonce>&token=<PublishToken>&<OtherKey>=<OtherValue>`

### 参考：

* [UNIX Timestamp](http://tool.chinaz.com/Tools/unixtime.aspx)
* [PublishKey](publishkey.md)
* [Static静态推流](publishsecurity-static.md)
* [Expiry限时推流](publishsecurity-expiry.md)
* [None无鉴权推流](publishsecurity-none.md)