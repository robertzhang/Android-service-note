# Android Service笔记

Service是Android的四大控件之一。主要适用于需要常驻后台运行的进程，或者比较耗时的操作。

Android Service分为系统服务和应用程序服务。系统服务指的是开机后，由系统启动并维护的服务。这部分服务是为系统正常运行所必须的服务，并且也为应用程序提供了一个运行环境

在这里我主要讲解一下应用程序服务

* Local Service
* Remote Service

本地服务和远端服务的最大区别是Service运行的空间不同。本地服务和启动他的activity在同一个进程中，而远端服务和activity并不在同一个进程中，所以当主应用程序终止时，远端服务仍然会继续运行。

## Local Service（本地服务）

大多数情况下，我们使用的Service都是本地服务。activity通过bindService()方法来绑定和启动需要控制的Service。而LocalService通过onBind()方法将Service返回给activity供其使用。


## Remote Service（远端服务）

远端服务因为在单独的进程中，所以要和activity进行交互就必须要提到IPC机制。我们都知道IPC能使用，就需要AIDL的知识。AIDL就是Android Interface Definition Language，用于约束两个进程间的通信规则。我们在设计远端服务的时候，只需要编写好以.aidl为后缀的接口文件，Android SDK会帮我们自动在gen目录下生成对应的.java文件。这个部分的java文件不用我们过多的关注。
做好这些事情，接下来就是编写IService.stub这个类。这个类主要做的事情就是实现我们在.aidl中定义的接口方法。




### To be continuing .....
后续持续添加
