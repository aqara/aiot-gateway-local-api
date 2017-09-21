# 对设备进行读写操作

## 1. 读设备

命令以**单播**方式发送给网关的udp 9898端口。

* 用户可以主动读取墙壁开关，插座的属性状态，网关返回设备的全部属性信息: `{"cmd":"read","sid":"158d0000123456"}`
* 网关以单播方式回复格式： `{"cmd":"read_ack","model":"ctrl_neutral2","sid":"158d0000123456","short_id":4343,"data":"{\"channel_0\":\"on\",\"channel_1\":\"off\"}"}`
* 读取网关的状态：`{"cmd":"read","sid":"1022780"}`
* 网关以单播方式回复格式：`{"cmd":"read_ack","model":"gateway","sid":1022780","short_id":0,"data":"{\"rgb\":0,\"illumination\":350,\"proto_version\":\"1.0.6\"}"}`，其中，rgb是网关夜灯的颜色值，illumination是光照度，proto_version是网关所用的本通信协议的版本号。

## 2. 写设备

命令以单播方式发送给网关的udp 9898端口。当用户需要控制墙壁开关，插座等设备时使用write命令。

`{"cmd":"write","model":"ctrl_neutral1","sid":"158d0000123456","short_id":4343,"data":"{\"channel_0\":\"on\",\"key\":\"3EB43E37C20AFF4C5872CC0D04D81314\"}" }`

网关以单播方式回复格式：`{"cmd":"write_ack","model":"ctrl_neutral2","sid":"158d0000123456","short_id":4343,"data":"{\"channel_0\":\"on\",\"channel_1\":\"off\"}"}`

> 该write\_ack只是代表网关收到了write命令，data里的属性状态为当前的设备最新状态，不是write之后的最终设备状态。最终的设备状态靠report报文进行上报。

**注意**

其中的“key”为32个字节长度的字符串。当网关启用了加密模式时，会对该key进行解密并校验，以验证写命令的合法性。该“key”的生成规则是：用户收到“heartbeat”里的16个字节的“token”字符串之后，对该字符串进行AES-CBC 128加密，生成16个字节的密文后，再转换为32个字节的ASCII码字符串。

比如：用户配置16个字符长度的密钥为“0987654321qwerty“, ”token”为”1234567890abcdef”,加密后密文是：0x3E,0xB4,0x3E,0x37,0xC2,0x0A,0xFF,0x4C,0x58,0x72,0xCC,0x0D,0x04,0xD8,0x13,0x14。那么，”key”为：”3EB43E37C20AFF4C5872CC0D04D81314”。

