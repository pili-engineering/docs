## PublishSecurity 鉴权方式
即鉴权方式。决定了推流地址的有效性和合法性。
是应用(Hub)的属性,可以在控制台应用属性中进行修改。
推流时，使用`rtmp://<HubPublishDomain>/<StreamKey>?<鉴权方式中的publishKey或token>`这样带有鉴权参数的地址，可获得推流能力。
包括四种鉴权方式，`static 静态推流地址`/`expiry限时推流地址`/`dynamic动态推流地址`/`none无鉴权方式`。


### 参考：

* [Static静态推流](publishsecurity-static.md)
* [Expiry限时推流](publishsecurity-expiry.md)
* [Dynamic动态推流](publishsecurity-dynamic.md)
* [None无鉴权推流](publishsecurity-none.md)