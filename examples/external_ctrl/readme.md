# 指南：编写一个从外部与 MC 通信的程序

## 概述
当我们使用 FB 导出导出服务器建筑时，我们不禁思考：如果 FB 可以与 MC 交互，我们自己编写的程序是否可以呢？   
一项有益的尝试是 FastBuilder.JS(介绍在隔壁目录中), 然而 FastBuilder.JS 是使用一个脚本 "从内部驱动" FB  
那么，是否有办法 "从外部控制" FB呢？  
这，就是本指南的目的 。  

## robot.json
显然，如果希望从外部控制 FB， 控制程序和 FB 必须做好相应的准备，并建立起通信的桥梁  
而 FB 中已经做好了建立连接一侧的全部工作，自动登录，屏蔽更新，打开端口，自动重启 
使用这一切只需要配置 一份 robot.json 文件即可
在这个目录中，已经放置了一份示例的 robot.json 它包括以下字段
- "token": 用户的 fb token，可以从 fb 官网获得
- "server_number": 服务器号  
- "server_passwd": 服务器密码  
- "transfer_port": 端口打开的位置 (TCP)  
- "ignore_update": 屏蔽更新
- "auto_restart": 自动重启  

robot.json 必须和fastbuilder 放置在同一目录下，且不能改名！  

## 通信
在 robot.json 指定的端口上，FB 会作为服务器接受 TCP 连接，完成连接后，FB 将向客户端发送其收到的 __所有__ 数据包   
当客户端向 FB 发送数据包时，FB 将把它转发到 MC 中，或者作为 FB 的一条指令执行  

目前，我们使用一种很简单通信格式:
对于 MC -> FB 的数据包 msg，假设 msg 有 n 字节，FB 在转发时，首先按小端序发送4个字节表示 msg 的长度 n，
接着将 msg 的 n 个字节全部发送   
类似的，控制程序发给 FB 数据包时，也需要先使用4个字节表示数据的长度，紧接着发送对应的数据   

未完待续... -CMA2401PT   

## 例子?
由于这真的不是一个 readme 就能写清所有的东西，所以你们还是自己读 Python 例子吧。
注：例子并没有覆盖提供的全部 Api！  

- example00   
最简单的例子，仅解析收到的数据，看看游戏里发生了什么

- example01  
 有两个子线程，一个负责停的解析数据，并通过 Queue 将解析结果在线程之间传递
 另一个子线程的目仅仅负责发送指令
 主线程每隔一段时间检查连接状态 
 提供了一个功能，用户可以输入指令，指令被发给 MC，紧接着显示收到的结果

- example02  
 在example01上，当任意子线程死亡时，主线程尝试重连

- example03  
  high api, 并非可复用的形式出现，而是以类似模版的方式出现，功能是作为参数传入的
  所以才叫 high_level_api, 可以更专注的实现功能
  当 high_level_api 不能实现某个功能时，应该参考源码写另一个模版   
  在这个 example03 中，当检测到用户输入 "菜单" 时，弹出一条提示

## 还有问题？
那是当然的，或许你可以找我？ -CMA2401PT   