今天主要讲一下找发消息的call，首先分析，正常发消息，至少需要两个参数：一个是wxid，一个是要发送的内容。需要用到的工具，OD和CE。找发消息要点：可以从这个发消息的内容入手，还有一点，我发给谁。比如我发给文件助手，文件助手的wxid是：filehelper，
用CE找，如下图：当前聊天窗口是文件助手，然后再切换到某个好友的微信聊天窗口，搜索：wxid_，然后再切换回去文件助手聊天窗口，

![image](https://user-images.githubusercontent.com/96330669/162386972-959c38e2-0b8f-4105-bcaf-67416b834a70.png)
将搜到的信息，移到最下面，切换不同的聊天窗口，双击下面的value值，可以看到不同的wxid，然后把value值里面的wxid修改成其他好友的wxid，这个时候发消息，看到消息没有发送到当前人的，而是发送给被修改wxid的那个好友了。也就是说，wxid是谁，就发给谁了，不管当天聊天窗口是谁。
![image](https://user-images.githubusercontent.com/96330669/162387282-639edffb-a41e-4c3b-8e5b-d328199e55b4.png)
然后从上面的找到地址，去OD里面下一个内存访问断点，然后在微信发送一条消息，这时就断下来了；
![image](https://user-images.githubusercontent.com/96330669/162387465-3e565157-8dff-4dbf-9925-c76322912192.png)
然后把刚才的断点删除，找传两个或者以上参数的汇编的地方，下一个断点，再发消息，看断下来。最终找到这个发消息call的地址。
现在最新版已实现很多有趣的功能，比如群管，发各种消息，加好友，接收各种消息等等，可提供接口二次开发，欢迎技术交流。

![image](https://user-images.githubusercontent.com/96330669/162387802-46f3061c-d829-44a6-9126-e07681ed1872.png)
企业微信也实现了类似的功能，如下图：
![image](https://user-images.githubusercontent.com/96330669/162388199-3c3ec65f-d3ec-477c-b7a7-e5b5ed037b9f.png)

QQ：2645542961
欢迎技术交流
