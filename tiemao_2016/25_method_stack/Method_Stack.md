
# 方法-栈

2016年6月7日



方法的定义，叫做 CODE，是固定死的。


方法的参数，内部的变量，叫 var， 存放在 stack 之中，叫方法栈。


方法的调用栈，也是在stack之中，每个方法的变量栈，叫做 frame，简称栈帧


你理解了反射，就理解了方法区


method.invoke(thisArg, otherParams);


所有语言的方法调用，本质都是这样的。
this.setXXX(ccc)


编译之后，执行的时候，实际执行的是 setXXXMethod.invoke(this, ccc)


所以，方法就是固定死的，每个线程都可用来取用，等价于一串指令模板，放在内存之中。 执行的时候，依次将这串指令，传输给CPU,各个内核什么的(实际上是CPU自己来取)。


需要什么参数，就去相对于当前线程的地址去取(也就是stack)


所以，只要编译器将这些东西规定好，约定好，那么后面的流程就是很简单的


堆内存中的对象，其实在stack之中存放了一个地址。 
例如 Object obj = new Object();
那么，在当前方法的stack之中，就有一个符号，叫 obj, 占用了4个字节(一般是4个)，类型是指针，里面的内容就是 那个对象的相对地址值。


当然，stack之中还有很多额外的信息，比如标记着 obj 是一个指针，还是一个int值，还是什么。。。看具体情况。


如果经过优化，那么可能会有一些出入。优化之后，什么东西都不是绝对的了。 但大致道哩是这样


有时候多思考一下。 看得多了你就想明白了，不一定是看JVM


理解C语言，你也会理解这些



这些基础就是内功。 各种技能就是武功。 各种工具就是兵器

武功和兵器不行，那么内功深厚，战斗力也是不行的


