1.内存相关问题
---
（1）内存泄漏是什么

内存泄露是指：内存泄漏也称作"存储渗漏"，用动态存储分配函数动态开辟的空间，在使用完毕后未释放，结果导致一直占据该内存单元。直到程序结束。(其实说白了就是该内存空间使用完毕之后未回收)即所谓内存泄漏。

(2)如何检测内存泄露

第一：良好的编码习惯，尽量在涉及内存的程序段，检测出内存泄露。当程式稳定之后，在来检测内存泄露时，无疑增加了排除的困难和复杂度。使用了内存分配的函数，一旦使用完毕,要记得要使用其相应的函数释放掉。


第二：将分配的内存的指针以链表的形式自行管理，使用完毕之后从链表中删除，程序结束时可检查改链表。

第三：Boost 中的smart pointer。

第四：一些常见的工具插件，如ccmalloc、Dmalloc、Leaky等等。

(3)引起内存泄漏的原因

1、单例造成的内存泄漏

由于单例的静态特性使得其生命周期和应用的生命周期一样长，如果一个对象已经不再需要使用了，而单例对象还持有该对象的引用，就会使得该对象不能被正常回收，从而导致了内存泄漏。



（2）常见的数据结构在内存中存储的位置及其存储方式

