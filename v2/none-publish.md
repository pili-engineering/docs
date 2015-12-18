## None无鉴权推流
在鉴权方式中，None不使用任何鉴权标记。形态如`rtmp://<HubPublishDomain>/<StreamKey>`

如何获得None方式的推流地址：

* 查看控制台： 登录控制台，查看流属性
* 自行构造：在应用中绑定域名后，可自行构造StreamKey，自动创建流并实现推送功能。

### 参考：

* [Static静态推流](publishsecurity-static.md)
* [Expiry限时推流](publishsecurity-expiry.md)
* [Dynamix动态推流](publishsecurity-dynamix.md)