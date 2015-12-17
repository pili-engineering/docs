## Expiry限时推流

鉴权方式的一种。
由`expire`/`token`/`otherkey` 共同参与签算合法URL，形如`rtmp://<HubPublishDomain>/<StreamKey>?expire=<ExpireAt>&token=<PublishToken>&<OtherKey>=<OtherValue>`

### 参数说明：


| 名称     | 类型   | 必填 | 默认值 | 描述 |
|----------|--------|------|--------|------------------|
| expire   | int    | 否   | <Now>+30s   | UNIX Timestamp。时间的单位精确到秒。预计推流动作发生的时间段，默认为当前时刻之后的30s。举例说明，当前时刻为12:00，预计12:20之前推流，超过时间后不可推流，时刻内可推流。将此刻12:20换算为UNIX Timestamp。 |
| token    | string | 是   | none   | 查看[token计算方式](#token) |                                                                                                              
| otherkey | string | 否   | none   | 任意key名及任意符合URL规范的字符串值。当otherkey参与了token计算时，构造推流地址时需将otherkey包括在内。|


### <a name="token"></a>token计算方式:

`sign = hmac_sha1("/<StreamKey>?expire=<ExpireAt>&<OtherKey>=<OtherValue>", "<PublishKey>")`
`publishToken = url_base64(sign)`

### 使用方式：

1. 转换有效时刻为UNIX Timestamp. 
2. 获得PublishKey
3. 通过[token计算方式](#token)计算出PublishToken
4. 获得推流地址`rtmp://<HubPublishDomain>/<StreamKey>?expire=<ExpireAt>&token=<PublishToken>&<OtherKey>=<OtherValue>`

### 参考：

* [UNIX Timestamp](http://tool.chinaz.com/Tools/unixtime.aspx)
* [PublishKey](PublishKey.md)
* [Static静态推流](Static静态推流.md)
* [Dynamic动态推流](Dynamic动态推流.md)
* [None无鉴权推流](None无鉴权推流.md)
