# 智能插座

##属性上报

| 属性 | 说明 |
| -- | -- |
| status | on/off        (开/关) |
| load_voltage | 负载电压，单位是毫伏 mV |
| load_power | 负载功率，单位是瓦 W |
| power_consumed | 负载消耗电量, 单位是千瓦时kWh |

```{"cmd":"report","model":"plug","sid":"112316","short_id":4343,"data":"{\"status\":\"on\"}" }```

##心跳上报(~10分钟每次)

```{"cmd":"heartbeat","model":"plug","sid":"112316","short_id":4343,"data":"{\" load_voltage \":\" 234300 \"}" , \" load_power \":\"9.57\",  \" power_consumed \":\"0.57\"}"}```

```{"cmd":"write","model":"plug","sid":"112316","short_id":4343,"data":"{\"status\":\"on\"}" }```
