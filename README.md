#从《游戏人工智能编程》学到的状态机

采用状态模式，与传统不同的是，所有状态都是单例，优点是频繁切换状态时不用重复申请内存，非常高效。缺点是无法保存非共享的数据，数据需要保存在Context实体中。

除了保存当前状态，还保存着上一个状态和一个全局状态，这样方便恢复到上一个状态，全局状态表示一个一直需要检查的状态。

所有的状态由exit，enter，execute三个函数控制执行和切换。

状态机支持消息功能，调用MessageDispatcher中的函数可以在不同的Context间发送消息。

State类是所有状态的基类，写成模板类方便复用。

typeid是C++ RTTI的知识，使用前需要头文件 typeinfo。

hpp文件包含了类的声明和定义，写模板类的时候比较方便，适合用来编写开源库。

