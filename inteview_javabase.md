## 2. java 基础  

1. hashmap的底层实现，如何处理冲突，采用链表存储同一个hash值的元素，对于什么操作会有影响。

	底层实现是数组，数组中的对象是Entry类对象。  
	当存在冲突时，将具有相同hashcode的对象挂载在相同槽内，组成链。采用头插法，新插入对象放在链头，最先加入的对象放在链尾。  
	**hashcode()**  
	**indexFor()**  
	**put()**  
	**get()**  
	**addEntry()**  
	**loadfactor**  
	loadfactor=元素个数/表长  
	**hash算法**  

	```java
	int indexFor(int h, int length){
		return h&(length - 1)	
	}
	```
	**resize**  
	数组默认大小是16，负载因子默认未0.75  

2. 为何重写hashcode 和 equals方法  
	重写equals方法必然重写hashcode方法，这是java规范。  
	hashcode返回值是一个整数，代表两个对象是否相等。  


3. 异常种类有哪些
	
	![java中常见异常如下图所示](img/exception_1.jpg)  
	Throwable是所有异常的根，java.lang.Throwable  
	Error是错误，java.lang.Error  
	Exception是异常，java.lang.Exception  
	一般分为Checked异常和Runtime异常，所有RuntimeException类及其子类的实例被称为Runtime异常，不属于该范畴的异常则被称为CheckedException。


4. [java 排序算法代码实现](http://www.cnblogs.com/wolf-sun/p/4312475.html)，复杂度、稳定性

5. 浅拷贝 vs 深拷贝

	**浅拷贝**是指拷贝对象时仅仅拷贝对象本身（包括对象中的基本变量），而不拷贝对象包含的引用指向的对象。  
	**深拷贝**不仅拷贝对象本身，而且拷贝对象包含的引用指向的所有对象。  
	若不对clone()方法进行改写，则调用此方法得到的对象即为浅拷贝。  
	[详细解释浅拷贝与深拷贝](http://www.cnblogs.com/shuaiwhu/archive/2010/12/14/2065088.html)  
	当然我们还有一种深拷贝方法，就是将对象串行化。缺点耗时。

6. 怎么判断一个对象该被回收  
	计数法  
	根搜索法

7. hashMap 和 hashtable区别
8. hashtable原理
9. hashtable是怎么实现线程安全的
8. java的代理是怎么实现的
9. 抽象类和接口的区别
10. 接口和实现类的区别
10. java四种引用
11. 集合类介绍，各种集合类之间的区别
12. 继承和组合区别
13. lmbda表达式
14. java 8 新特性
15. java基础数据类型 
	- 整形 byte	short	int		long  
	- 浮点型	float	double  
	- 逻辑型 boolean  
	- 字符型	char  
16. java中的数据存储  

	- 寄存器：最快的存储区，编译器分配，程序无法控制
	- 栈：存放基础数据类型的变量数据 和 对象的引用  
	- 堆：new出来的对象存放位置
	- 静态域：静态成员变量存放位置  
	- 常量池：字符串变凉&基本数据类型变量 public static final  
	- 非rRAM存储：硬盘等永久存储空间
7. 内存溢出 和 内存泄漏
3. 内存敲代码优化，我们都用stringbuffer来代替+号，来减少建立的对象。那么问题来了，除了这个你还用过什么碼代码技巧来节省内存 