##关于dms
dms 是杭州奥点科技提供的一个双向消息推送服务，提供了js,php,c++,nodejs,shell，java，python，android,ios之间相互通
信的功能，是市面上唯一支持低版本ie消息推送的服务

###php sdk
php sdk 提供了向dms推送消息的功能，由于常规php一般运行在http模式，只有很短的生存周期，所以只提供了发布功能。

###使用条件
* php版本>5.3
* 能连通dms服务器(公网)

###安装
* 使用composer 安装 引入库4lan/dms-php-sdk ，命名空间dms
* 或者直接下载文件,放在调用代码目录下
```php
include(".dms_php_sdk/phpMQTT.php");
include(".dms_php_sdk/Pusher.php");
```

###使用
新建pusher对象，传入dms的publish key 和subscribe key
```php
use dms;//at head
$pusher= new Pusher('your pub key','your sub key');
```
推送数据
```php
$data=["user"=>"wangdachui","message"=>"can you hear me?"];//这里用了php5.4的语法，如果使用5.3请用array替换。
$pusher->trigger('a_topic',json_encode($data));
```


