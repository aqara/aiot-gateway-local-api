# 设备上报和控制报文格式


JSON报文格式如下：

```
{
	"cmd" : "write",           //命令类型
	"model" : "ctrl_neutral1",   //设备类型
	"sid" : "112316",          //设备的id
	"short_id" : 4343,         //zigbee设备的短id
	"data" : "{\" channel_0\":\"on\"}"    //设备状态等信息，再次解开字符串获取其中属性
}```

>其中data的内容是个字符串， 我们对这个字符串再次转成json，从中提取属性。