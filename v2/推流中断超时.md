## 推流中断超时

正在推流中的Stream，因为网络原因或推流端源原因，造成Stream中无数据，当持续无数据的时间超过推流中断超时，则Stream状态变为disconnected，链接断开。
hub.DataTimeoutSecond，推流超时时间，用来描述Stream持续无数据的时间。