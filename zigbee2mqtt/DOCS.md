# Zigbee2MQTT 
官方Zigbee2MQTT家庭助理插件。



## 配置说明

### mqtt

​	如果不使用mosquito to broker插件，请填写MQTT详细信息(使用mosquito to broker插件时可不填写)。格式可参考下面的实例

```
server: mqtt://localhost:1883
user: Mqtt的账号
password: "Mqtt的密码"
```

注意:如果密码包含某些特殊字符(由yaml规范保留)，则需要加上引号。所以我们建议如果日志显示密码错误时，优先考虑加上引号。

### serial

​	填写串行详细信息(例如USB协调器的端口)。格式可参考下面的实例

```
port: /dev/ttyUSB0
```

如果您不知道详细的端口，并且只有一个USB设备连接到您的机器，请尝试/dev/ ttyUSB0。否则，请查看“配置 - 系统 - 硬件 - 全部硬件”，在搜索上输入“tty”查看。
