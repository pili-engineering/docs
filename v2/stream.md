## Stream 流
流。最小的播放内容的单位，一个流对应一个应用，一个应用对应多个流。

* `StreamTitle`,流名称,是签算推流地址和构成播放地址的重要组成部分。
* `StreamKey`,组成`PublishURL`的部分。每个`PublishURL`推流地址形如 `rtmp://<Domain>/<StreamKey>?token=<publishToken>`,`StreamKey`参与签算生成`token`。
* （此概念已过期）`StreamID`标识,流在系统中的唯一索引，形如 `<Zone>.<hubname>.<StreamTitle>`。可流属性中查看流标识。