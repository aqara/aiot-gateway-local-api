# 温湿度传感器

##属性上报

温湿度传感器如果温度变化达到0.5度或者湿度变化达到6%上报一个报文。

| 属性 | 说明 |
| -- | -- |
| temperature | 温度 |
| humidity | 湿度 |

```{"cmd":"report","model":"sensor_ht","sid":"112316","short_id":4343,"data":"{\" temperature \":”2333”}" }```

```{"cmd":"report","model":"sensor_ht","sid":"112316","short_id":4343,"data":"{\" humidity \":”6678”}" }```

以上例子对应的温度为23.33,湿度为66.78%
