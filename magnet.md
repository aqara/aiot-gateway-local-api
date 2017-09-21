# 窗磁传感器

(~60分钟每次),窗磁传感器贴在窗户上或门上感知窗户的状态，每动作一次发送一次report。

| 属性 | 说明 |
| -- | -- |
| status | open/close  (开/关) |
| voltage | 纽扣式电池电压值，单位mv，范围0~3300mv，一般情况下，小于2800mv时表示低电量 |

##属性上报

```{"cmd":"report","model":"magnet","sid":"89234324","short_id":4343,"data":"{\"status\":\"open\"}" }```

##心跳上报

```{"cmd":"report","model":"motion","sid":"89234324","short_id":4345,"data":"{\"voltage\":\"3000\"}" }```

magnet代码是窗磁， 89234324代表的设备的ID（64位的长16进制字符串），status 是窗磁的开关状态。





