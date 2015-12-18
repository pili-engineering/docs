## CallbackUrl 推流状态回调
当流的状态（StreamStatus）发生变化时，触发CallbackUrl。
触发的条件：

* 当StreamStatus从disconnected变成connected时，触发回调。
* 当StreamStatus从connected变成disconnected，触发回调。
* 当StreamStatus处于connected时，Stream的可用性变为了disabled，此时Stream中无数数据推送，当无数据持续时间超过hub.DataTimeoutSecond(推流超时时间)，StreamStatus变更为disconnected，触发回调。

### 参考
* [StreamStatus](streamstatus.md)
