# web-chat
## 前言
  前段时间由于项目需要，匆匆忙忙完成了websocket的消息订阅发送，后来发现订阅还不能满足我们项目的需要，因为很多场景
   是需要点对点的进行通信，就像微信聊天一样，有群聊（可以认为是广播），私聊（认为是点对点通信），所以我才有了自己
   用websocket实现一个简单的chat功能的想法，目前可以实现群聊，私聊，界面简陋，还有很多功能待完善，不过这不是重点，重点是清楚了它的实现原理，
   以方便用在真实的项目上。了解其原理后，可以实现更多个性化的功能，比如本聊天系统中还可以实现用户输入的时候，对方可以知道其输入状态等。时间有限，
   等以后有时间了再完善吧，本程序花了我周末两天时间，哈哈。
   目前服务端是nodejs版本的，以后我会开发java版本的，因为我们项目后端用的java spring boot，只要遵从websocket协议标准，用什么语言都可以的，
   由于前后端是分离的，所以
   前我用的vue，启动的时候先需要进入server目录启动服务端，再启动客户端
   用到的技术栈为：
   * 1 websocet.io
   * 2 nodejs(express)
   * 3 vue
   * 4 vue-router
   * 5 elementUI
   * 6 vue-material
   * 7 webpack
   
   总结一下，用websocket.io库实现websocket通信非常简单，主要分为几步：
   1. 服务器上需要io.on('connection', function (socket) {}，只要客户端有连接就会走进这个回调
   2. 客户端connect('ws://ip:port');
   3. 如果你的需求是实现双向通信，比如聊天程序，那么在服务和客户端都要监听事件和广播事件，如果
   不理解这点的话可以自行看代码尝试
   
   # 欢迎访问我的个人主页，目前在开发中  https://wflin.github.io/
   博客主页 https://my.oschina.net/martin123/blog
   
   # web-chat截图
   ## 服务端
   * 每个客户端连接后，在服务器会维持这个连接，同时可以将客户端信息保存下来，当客户端断开时，服务器能及时知晓。  
   ![image](https://github.com/wflin/web-chat/raw/master/docs/server.png)
   
   ## 客户端
   * 群聊和私聊，在前台界面上同时用了elementUI和VueMaterial两种ui组件库。
   * 可以实现更多功能，如当张三在输入时，对方可以显示“张三正在输入”,类似微信的聊天功能。
   * 如果要运行此示例，要将socket.js中的export default io.connect('ws://172.31.59.59:8000');中的ip改成自己server的ip。  
   ![image](https://github.com/wflin/web-chat/raw/master/docs/login.png)
   ![image](https://github.com/wflin/web-chat/raw/master/docs/chat.png)
## 启动方法：
    npm install
    
    修改 socket.js中的ip和端口
    
    cd server
    
    node index.js
    
    npm run dev

## 前端常用编译方法

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```
