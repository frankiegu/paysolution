# 个人收款支付免签项目

### 测试站点

测试站点 http://103.200.29.108:996/

### 优点

* 可以直接使用直接测试。
* 没有中间商赚差价，买家扫多少，商家收多少。
* 支持 微  信 收款
* 支持 支付宝 收款
* 支持 Q   Q 收款
* 支持 Q   Q 收款
* 不用 注册微信商家
* 不用 注册支付宝商家
* 不用 营业执照
* 不用 Root
* 适合几乎所有安卓手机
* 使用方便,原理简单,demo简单开源。
* 不需要生成收款码,只要你把你的验证码上传,对方扫码直接付款就可以了。
### 流程说明 (2步超级简单)

* 1 下载app,根据提示给app通知权限,app和微信/支付宝/qq后台运行,微信/支付宝/qq需要收款的时候发送通知。
* 2 下载服务器端demo，根据提示直接使用。

### 原理说明(原理是按照服务器端为python来说明的,如果难懂请看我的python服务器端代码)

* 基于监听安卓手机收款通知,来进行回调,没有xposed,没有hook,账户不会有任何的风险,适合几乎所有安卓手机,也没有这个或那个的bug,只要给通知权限即可。
* 手机安卓端: 当手机监听到收款消息的时候,将会发送带有金额的http post消息给服务器。
* 服务器端(网站端): 第一步-创建订单(订单号由金额转化而来(去掉小数点前面再加两个0)),订单保存在类似python的字典变量中,值为wait。
* 服务器端(网站端): 第二步-支付,如果支付成功,服务器端收到手机安卓端发来的http post消息,将python的字典变量改为,值为payed,然后在这里执行支付成功发送商品的逻辑。
* 服务器端(网站端): 第三步-与web交互,开一个接口给其访问订单的类似python的字典变量,如果结果是payed就删除这个字典的键值对。

### 测试

### 下载(下载不了clone到gitee上然后下载速度快很多)

安卓端 https://github.com/MarsDiplomatToEarth/paysolution/blob/master/getpayment.apk?raw=true

服务器端(python flask版本) https://github.com/MarsDiplomatToEarth/-python-paysolution/tree/master

### 联系我们（热烈欢迎有想法的开发者加入我们项目一起开发）

邮箱 mr3317952@gmail.com

QQ 1908215058

telegram @AutoServer

QQ群 783129197

telegram group @AutoServergroup
