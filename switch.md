# 无线开关传感器

无线开关传感器每按键一次上报一个报文。400ms内按两次上报的报文是双击。

| 属性 | 说明 |
| -- | -- |
| status | click/double_click    (单击/双击) |
| voltage | 纽扣式电池电压值，单位mv，范围0~3300mv，一般情况下，小于2800mv时表示低电量 |

##属性上报

```{"cmd":"report","model":"switch","sid":"112316","short_id":4343,"data":"{\"status\":\"click\"}" }```

```{"cmd":"report","model":"switch","sid":"112316","short_id":4343,"data":"{\"status\":\"double_click\"}" }```

##心跳上报(~60分钟每次)

```{"cmd":"report","model":"motion","sid":"112316","short_id":4343,"data":"{\"voltage\":\"3000\"}" }```



