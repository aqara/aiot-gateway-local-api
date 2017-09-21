# 人体传感器

人体传感器探测到人会立即上报一次report信息。在一直有人的情况下为了省电人体传感器最快一分钟发送一次report。 

| 属性 | 说明 |
| -- | -- |
| voltage | 纽扣式电池电压值，单位mv，范围0~3300mv，一般情况下，小于2800mv时表示低电量 |
| status | motion探测到有人 |

##属性上报

```{"cmd":"report","model":"motion","sid":"112316","short_id":4343,"data":"{\"status\":\"motion\"}" }```

##心跳上报(~60分钟每次):

```{"cmd":"report","model":"motion","sid":"112316","short_id":4343,"data":"{\"voltage\":\"3000\"}" }```





