# Live Chatroom

A C++ Live Chatroom (version 0.2.0)

[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://opensource.org/licenses/MIT)

## Introduction 

* 本项目为C++11编写的基于epoll开发的即时聊天服务器，服务器采用I/O复用实现并发，客户端采用管道进行进程间通信，分别负责聊天消息的读写。

* 此聊天室具备客户端和服务端，服务端接受新的客户端连接，并将每个客户端发来的信息发给其他所有客户端。客户端接受服务端发来的消息，并且可以将信息广播给其他所有客户端。

## Environment
* OS: Ubuntu Linux release 18.04
* Compiler: g++ 7.5.0

# Build

```
$ make
$ make clean
```

# Run

```
$ ./chatroom_server
$ ./chatroom_client
```

# Technology

* 基于epoll的I/O复用机制，可选采用边缘触发(ET)或水平触发(LT)模式，配合非阻塞使用

* 使用list维护当前连接到服务器上的客户端列表，并动态将通过用户关闭的客户端剔除或插入新连接的客户端。

# To Do

