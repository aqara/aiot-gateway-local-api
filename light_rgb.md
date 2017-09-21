# 智能彩灯

##属性上报

温湿度传感器如果温度变化达到0.5度或者湿度变化达到6%上报一个报文。

| 属性 | 说明 |
| -- | -- |
| status  | on/off        (开/关) |
| level | 亮度 |
| color_temperature  | Color Temperature Mired |
| x | Current X |
| y  | Current Y |
| saturation | Current Saturation |
| hue | Current Hue |

**开关状态上报**

```{"cmd":"report","model":"rgbw_light","sid":" 158d0000f2ac34","short_id":"8390","token":"7","data":"{\"status\":\"on\"}" }```

**亮度上报**

```{"cmd":"report","model":"rgbw_light","sid":" 158d0000f2ac34","short_id":"8390","token":"7","data":"{\"level\":\"126\"}" }```

**颜色上报**

```{"cmd":"report","model":"rgbw_light","sid":"158d0000f2ac34","short_id":"26033","token":"2","data":"{\"hue\":\"170\",\"saturation\":\"254\", \"color_temperature\":\"65279\", \"x\":\"10\", \"y\":\"10\"}"}```

