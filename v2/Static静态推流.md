## Static静态推流

鉴权方式的一种。
直接使用PublishKey获得鉴权许可，来实现推流的方式。

### 使用方式：

1. 查看[应用属性] →鉴权方式。将鉴权方式设定为Static。修改后，所有流的鉴权方式都使用Static。
2. 获得PublishKey(密匙)
3. 构造推流地址 `rtmp://<HubPublishDomain>/<StreamKey>?key=<PublishKey>`
4. 进行推流。

### 参考
* [Expiry限时推流](Expiry限时推流)
* [Dynamic动态推流](Dynamic动态推流)
* [None无鉴权推流](None无鉴权推流)

