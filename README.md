## 后续版本更新转到ETServer的分支 ETCore 下了 https://github.com/roubingcode/ETCore

## ETServer运行使用方法
1 安装.net sdk  
2 通过vs installer安装 .net framework (共享组件需要安装在C盘)  
3 安装vs code 和vs code c#扩展  
4 需要用uinty打开新下载的ES项目，使项目能正确加载unity引擎代码库   
5 NLog.config文件解决ES4,5版本log输出问题(\ET-Branch_V5.0\Server\App)  
6 设置launch.json文件，在vs code中对项目进行调试  
7 用global.json指定项目net sdk版本  
8 命令行编译Server/Hotfix/Server.Hotfix.csproj  
9 调试运行服务端，运行客户端 

### 框架作者：熊猫，社区参与者 哲学绅士，Justin沙特王子
### 框架地址：https://github.com/egametang/ET
__讨论QQ群 : 474643097__

# ET 3.2发布! 3.2变化不大修复了一些bug，进一步完善了ET
1.增加了ChangeSystem，可以订阅组件改变事件  
2.修复dbcache中查询数据库一定会cache的bug  
3.去掉了IEntityActorHandler接口，使用string来分发  

# ET 3.1发布!
1.进一步完善了entity component模型，去掉了Dispose层级，增加了ComponentWithId继承层级，Component增加了InstanceId，更好的实现了System机制  
2.增加了DestroySystem事件，在Component Dispose时调用  
3.actor实现代码进行了简化  
4.升级了默认Unity版本，修复了kcp协议中UdpClient无法接收udp消息的bug  

# ET 3.0发布啦! 3.0是ET非常完善的一个版本，在2.0的基础上增加了如下功能：
1.客户端全热更支持，逻辑，消息，事件，config，UI等等全部可以热更了  
2.System改成了事件机制，awake，update，start等system可以在不同模块多次订阅  
3.消息去掉了继承结构，其它客户端对接起来，更方便了。  
4.增加了初步的Module机制，目录结构更清晰，社区分享代码更方便了。  
5.优化了代码，3.0的代码更加清晰，结构更加合理，前后端代码几乎一模一样了  

## ETServer c#游戏服务器框架
这是肉饼负责维护的一个ET框架的纯服务器版本，同步原框架更新。  

ET框架使用C#做服务端，现在C#是完全可以跨平台的，在linux上安装.netcore，即可，不需要修改任何代码，就能跑起来。性能方面，现在.netcore的性能非常强，比lua，python，js什么快的多了，做游戏服务端完全不在话下。

ET框架不但支持TCP，而且支持可靠的UDP协议（ENET跟KCP），ENet是英雄联盟所使用的网络库，其特点是快速，并且网络丢包的情况下性能也非常好，这个我们做过测试TCP在丢包5%的情况下，moba游戏就卡的不行了，但是使用ENet，丢包20%仍然不会感到卡，非常强大。框架还支持使用KCP协议，KCP也是可靠UDP协议，据说比ENET性能更好，使用kcp请注意，需要自己加心跳机制，否则20秒没收到包，服务端将断开连接。三种协议可以无缝切换。

## 视频教程：  
[肉饼老师主讲：](http://www.taikr.com/course/972) http://www.taikr.com/course/972  
__讨论QQ群 : 474643097__
