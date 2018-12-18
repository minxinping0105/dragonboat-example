# 示例3 - C++ Hello World #

## 关于 ##
本示例将给您一个C++使用Dragonboat库的概览。

如果您计划在Golang项目中使用Dragonboat，您可以跳过本示例。

## 编译 ##
为了编译helloworld示例可执行文件，首先编译Dragonboat C++支持库。在Dragonboat的顶层目录：
```
cd $GOPATH/src/github.com/lni/dragonboat
make clean
make binding
```
然后编译helloworld程序：
```
cd example/cpphelloworld
make
```

## 运行 ##
在同一主机上三个不同的终端terminals上启动三个cpphelloworld进程：

```
./cpphelloworld 1
```
```
./cpphelloworld 2
```
```
./cpphelloworld 3
```
这将组建了一个三节点的Raft集群。本示例程序的行为和Go版本的[示例1 - Hello World](../helloworld/README.CHS.md)十分相似。

## 代码 ##
[datastore.h](datastore.h)和[datastore.cpp](datastore.cpp)实现本应用所使用的Data Store. 和[plugin.h](plugin.h)以及[plugin.cpp](plugin.cpp)一起, 它们可以用来编译产生一个名为dragonboat-cpp-plugin-cpphelloworld.so的插件。

[helloworld.cpp](helloworld.cpp)含main函数，它将启动一个Raft节点并实现本程序的功能与行为。[helloworld.cpp](helloworld.cpp)含详细注释，以解读各细节。