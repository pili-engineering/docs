## StreamStatus 流状态
流状态指流在当下的状态描述。状态包括 connected:正在推流中；disconnected：推流终止。disconnected的状态产生：当流的状态为持续无数据的时间超过hub.DataTimeoutSecond(推流超时时间)，流的状态为disconnected推流终止。

### 参考
* [CallbackUrl](CallbackUrl推流状态回调.md)
