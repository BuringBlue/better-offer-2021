## Java集合

![清晰uml图](https://camo.githubusercontent.com/5f1947d51a8b2f9589a004ebe1ff06ce25bf5ceb1f8ef7e2bf51b9d979492d94/68747470733a2f2f7777772e706461692e746563682f5f696d616765732f6a6176615f636f6c6c656374696f6e735f6f766572766965772e706e67)



![Java集合](/Users/wenzhuowang/Desktop/框图/Java集合.png)



### 1. ArrayList和LinkedList的区别

|          | ArrayList                                                    | LinkedList                                                   |
| -------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 数据结构 | 基于**动态数组**                                             | 基于**链表**                                                 |
| 特点     | 查找速度快，添加和删除慢                                     | 查找慢，添加和删除快                                         |
| 适用场景 | 频繁访问列表中的某一个元素。 <br />只需要在列表末尾进行添加和删除元素操作。 | 需要通过循环迭代来访问列表中的某些元素。<br />需要频繁的在列表开头、中间、末尾等位置进行添加和删除元素操作。 |



```java
import java.util.LinkedList;
import java.util.ArrayList;
import java.util.Collections;

LinkedList<E> list1 = new LinkedList<E>(); // 链表  
ArrayList<E> list2 =new ArrayList<E>();  //数组
Collections.sort(list2); //排序

```



| ArrayList                                                    | 功能                                          | LinkedList                                  | 功能                                                         |
| ------------------------------------------------------------ | --------------------------------------------- | ------------------------------------------- | ------------------------------------------------------------ |
| [add()](https://www.runoob.com/java/java-arraylist-add.html) | 将元素插入到指定位置的 arraylist 中           | boolean **add**(E e)                        | 链表末尾添加元素，返回是否成功。<br />若在满队列加新项，则抛异常 |
| [addAll()](https://www.runoob.com/java/java-arraylist-addall.html) | 添加集合中的所有元素到 arraylist 中           | void **add**(int index, E element)          | 向指定位置插入元素。                                         |
| [clear()](https://www.runoob.com/java/java-arraylist-clear.html) | 删除 arraylist 中的所有元素                   | boolean **addAll**(Collection c)            | 将一个集合的所有元素添加到链表后面，返回是否成功             |
| [clone()](https://www.runoob.com/java/java-arraylist-clone.html) | 复制一份 arraylist                            | boolean **addAll**(int index, Collection c) | 将一个集合的所有元素添加到链表的指定位置后面，返回是否成功   |
| [contains()](https://www.runoob.com/java/java-arraylist-contains.html) | 判断元素是否在 arraylist                      | void **addFirst**(E e)                      | 元素添加到头部。                                             |
| [get()](https://www.runoob.com/java/java-arraylist-get.html) | 通过索引值获取 arraylist 中的元素             | void **addLast**(E e)                       | 元素添加到尾部。                                             |
| [indexOf()](https://www.runoob.com/java/java-arraylist-indexof.html) | 返回 arraylist 中元素的索引值                 | boolean **offer**(E e)                      | 向链表末尾添加元素，返回是否成功<br />若在满队列加新项，则返false |
| [removeAll()](https://www.runoob.com/java/java-arraylist-removeall.html) | 删除存在于指定集合中的 arraylist 里的所有元素 | boolean **offerFirst**(E e)                 | 头部插入元素，返回是否成功                                   |
| [remove()](https://www.runoob.com/java/java-arraylist-remove.html) | 删除 arraylist 里的单个元素                   | boolean **offerLast**(E e)                  | 尾部插入元素，返回是否成功                                   |
| [size()](https://www.runoob.com/java/java-arraylist-size.html) | 返回 arraylist 里元素数量                     | void **clear**()                            | 清空链表。                                                   |
| [isEmpty()](https://www.runoob.com/java/java-arraylist-isempty.html) | 判断 arraylist 是否为空                       | E **removeFirst**()                         | 删除并返回第一个元素。                                       |
| [subList()](https://www.runoob.com/java/java-arraylist-sublist.html) | 截取部分 arraylist 的元素                     | E **removeLast**()                          | 删除并返回最后一个元素。                                     |
| [set()](https://www.runoob.com/java/java-arraylist-set.html) | 替换 arraylist 中指定索引的元素               | boolean **remove**(Object o)                | 删除某一元素，返回是否成功                                   |
| [sort()](https://www.runoob.com/java/java-arraylist-sort.html) | 对 arraylist 元素进行排序                     | E **remove**(int index)                     | 删除指定位置的元素。                                         |
| [toArray()](https://www.runoob.com/java/java-arraylist-toarray.html) | 将 arraylist 转换为数组                       | E **poll**()                                | 删除并返回第一个元素，获取失败返空                           |
| [toString()](https://www.runoob.com/java/java-arraylist-tostring.html) | 将 arraylist 转换为字符串                     | E **remove**()                              | 删除并返回第一个元素，获取失败抛异常                         |
| [ensureCapacity()](https://www.runoob.com/java/java-arraylist-surecapacity.html) | 设置指定容量大小的 arraylist                  | boolean **contains**(Object o)              | 判断是否含有某一元素。                                       |
| [lastIndexOf()](https://www.runoob.com/java/java-arraylist-lastindexof.html) | 返回指定元素在 arraylist 中最后一次出现的位置 | E **get**(int index)                        | 返回指定位置的元素。                                         |
| [retainAll()](https://www.runoob.com/java/java-arraylist-retainall.html) | 保留 arraylist 中在指定集合中也存在的那些元素 | E **getFirst**()                            | 返回第一个元素。                                             |
| [containsAll()](https://www.runoob.com/java/java-arraylist-containsall.html) | 查看 arraylist 是否包含指定集合中的所有元素   | E **getLast**()                             | 返回最后一个元素。                                           |
| [trimToSize()](https://www.runoob.com/java/java-arraylist-trimtosize.html) | 将 arraylist 中的容量调整为数组中的元素个数   | int **indexOf**(Object o)                   | 查找指定元素从前往后第一次出现的索引。                       |
| [removeRange()](https://www.runoob.com/java/java-arraylist-removerange.html) | 删除 arraylist 中指定索引之间存在的元素       | int **lastIndexOf**(Object o)               | 查找指定元素最后一次出现的索引。                             |
| [replaceAll()](https://www.runoob.com/java/java-arraylist-replaceall.html) | 将给定的操作内容替换掉数组中每一个元素        | E **peek**()                                | 返回第一个元素。<br />list为空时，返回null                   |
| [removeIf()](https://www.runoob.com/java/java-arraylist-removeif.html) | 删除所有满足特定条件的 arraylist 元素         | E **element**()                             | 返回第一个元素。<br />list为空时，抛异常                     |
| [forEach()](https://www.runoob.com/java/java-arraylist-foreach.html) | 遍历 arraylist 中每一个元素并执行特定操作     | E **peekFirst**()                           | 返回头部元素。                                               |



### 2. HashMap和HashTable的区别

|                              | HashTable                                        | HashMap                                                      | ConcurrentHashMap                                            |
| ---------------------------- | ------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 继承的父类不同               | 继承自Dictionary类                               | HashMap继承自AbstractMap类                                   |                                                              |
| 底层实现不同                 | 底层是**数组+链表**                              | 1.7版本底层是 数组+链表（链式）<br />1.8版本底层是 **数组+链表or红黑树** | 1.7版本底层是 数组+链表<br />1.8版本底层是 **数组+链表or红黑树** |
| 线程安全性不同               | **线程安全**<br />每个方法前加了**synchronized** | **非线程安全**<br />在并发环境下使用HashMap必须要自己增加同步处理 | **线程安全**<br />1.7是分段锁<br />1.8是去掉分段锁改成cas+synchronized |
| **key和value是否允许null值** | key和value都不允许出现null值                     | null可以作为键，这样的键只有一个；可以有一个或多个键所对应的值为null |                                                              |
| **hash值不同**               | 直接使用对象的hashCode                           | 重新计算hash值：hashcode 的高 16 位和低 16 位进行异或操作    |                                                              |
|                              | contains（=）containsValue，containsKey          | 去掉contains<br />containsValue和containsKey                 |                                                              |



### 3. ArrayList有哪些并发问题

#### 发生位置

其实就是**size++** 这一步的问题

#### 可能引发的问题

1. **越界**：两个线程**临界值**去**扩容**都满足，于是一个线程size++导致的，另外一个线程就溢出了，
2. **null**：element[size] = e,第一个线程还没来得及size++，第二个线程就在原先的索引上把值给覆盖了，并且在下一个索引为null。



### 4. HashMap

1. 谈谈你理解的 HashMap，讲讲其中的 get put 过程。
2. 1.8 做了什么优化？
3. 是线程安全的嘛？
4. 不安全会导致哪些问题？
5. 如何解决？有没有线程安全的并发容器？
6. ConcurrentHashMap 是如何实现的？ 1.7、1.8 实现有何不同？为什么这么做？

![img](https://awps-assets.meituan.net/mit-x/blog-images-bundle-2016/e4a19398.png)



#### 4.1 参数

```java
static final int MAXIMUM_CAPACITY = 1 << 30;//初始化桶大小，因为底层是数组，所以这是数组默认的大小。

//桶最大值
 
static final float DEFAULT_LOAD_FACTOR = 0.75f;//填充比(负载因子)
 
//当add一个元素到某个位桶，其链表长度达到8时将链表转换为红黑树
static final int TREEIFY_THRESHOLD = 8;
//退化链表的阈值是6
static final int UNTREEIFY_THRESHOLD = 6;
 
static final int MIN_TREEIFY_CAPACITY = 64;
 
transient Node<k,v>[] table;//存储元素的数组
 
transient Set<map.entry<k,v>> entrySet;
 
transient int size;//存放元素的个数
 
transient int modCount;//被修改的次数fast-fail机制
 
int threshold;//临界值 当实际大小(容量*填充比)超过临界值时，会进行扩容
```



1. **为什么容量要是 2 的整数次幂？**

因为获取 key 在数组中对应的下标是通过 key 的哈希值与数组长度 -1 进行与运算，如：tab[i = (n - 1) & hash]

n 为 2 的整数次幂，这样 n-1 后之前为 1 的位后面全是 1，这样就能保证 (n-1) & hash 后相应的位数既可能是 0 又可能是 1，这取决于 hash 的值，这样能保证散列的均匀，同时与运算效率高。如果 n 不是 2 的整数次幂，会造成更多的 hash 冲突。



2. **为什么<u>红黑树的阈值</u>是8？**

在 hash 函数设计合理的情况下，发生 hash 碰撞 8 次的几率为百万分之 6，概率说话。(泊松分布)



3. **为什么<u>退化链表的阈值</u>是6？**

6是因为如果 hash 碰撞次数在 8 附近徘徊，会一直发生链表和红黑树的转化，为了预防这种情况的发生



4. **为什么<u>负载因子</u>是0.75？**

   临界值（threshold） = 负载因子（loadFactor） \* 容量（capacity）

负载因子过低，频繁扩容，扩容会重新哈希，性能下降；负载因子过高，容易浪费容量.（经验+概率）



5. **hash ** 扰动函数

hash 函数是先拿到通过 key 的 hashcode，**是 32 位的 int 值**，然后让 **hashcode 的高 16 位和低 16 位进行异或操作**。

```java
static final int hash(Object key) {
    int h;
    return (key == null) ? 0 : (h = key.hashCode()) ^ (h >>> 16);
}
```

**【目的】**尽可能降低 hash 碰撞，让散列分布地更加均匀。

【**why位运算**】算法一定要尽可能高效，因为这是高频操作, 因此采用位运算

![img](https://images2018.cnblogs.com/blog/1303695/201804/1303695-20180407220236171-1291169329.png)



#### 4.2 put

```java
hashmap.put(Object key, Object value);
```

![HashMap](/Users/wenzhuowang/Desktop/框图/HashMap.png)



#### 4.3 get

```java
hashmap.get(Object key)
```

1. 判断：是否为空，为空，返回null
2. 不为空，判断第一个位置是否为查询key，是，返回value
3. 不是，下一个节点继续判断是否为红黑树，是，按树查找
4. 不是，按链表查找



#### 4.4 扩容

1.8 HashMap的扩容使用的是2次幂的扩展(指长度扩为原来2倍)，所以，元素的位置要么是在原位置，要么是在原位置再移动2次幂的位置。也就是说省略了重新计算hash值的时间，而且新增的1位是0还是1机会是随机的，因此resize的过程，均匀的把之前的冲突的节点分散到新的bucket了。如果在新表的数组索引位置相同，则链表元素不会倒置。

##### 扩容引发的并发问题

- HashMap扩容的时候会调用resize()方法，就是这里的并发操作容易在一个桶上形成环形链表

  这样当获取一个不存在的key时，计算出的index正好是环形链表的下标就会出现死循环。

- **但是1.7的头插法造成的问题，1.8改变了插入顺序，就解决了这个问题，但是为了内存可见性等安全性，还是需要ConCurrentHashMap**

- HashTable 是直接在操作方法上加 synchronized 关键字，锁住整个数组，粒度比较大

- Collections.synchronizedMap 是使用 Collections 集合工具的内部类，通过传入 Map 封装出一个 SynchronizedMap 对象，内部定义了一个对象锁，方法内通过对象锁实现

- **ConcurrentHashMap 使用分段锁，降低了锁粒度，让并发度大大提高。**(jdk1.8 CAS+ synchronized)

  

### 5. 数组/链表/队列/...常用操作

#### 队列

add         增加一个元索                      如果队列已满，则抛出一个IIIegaISlabEepeplian异常
remove   移除并返回队列头部的元素     如果队列为空，则抛出一个NoSuchElementException异常
element  返回队列头部的元素              如果队列为空，则抛出一个NoSuchElementException异常
offer       添加一个元素并返回true        如果队列已满，则返回false
poll         移除并返问队列头部的元素     如果队列为空，则返回null
peek       返回队列头部的元素              如果队列为空，则返回null
put         添加一个元素                       如果队列满，则阻塞
take        移除并返回队列头部的元素     如果队列为空，则阻塞



### 6. ConcurrentHashMap

#### 6.1 目的

 JDK 推出了专项专用的 ConcurrentHashMap ，该类位于 `java.util.concurrent` 包下，专门用于解决并发问题。



#### 6.2 1.7版本

##### 6.2.1 get的流程

**首先需要将key通过hash之后定位到具体的segment，然后再知道hashentry的index，最后一次循环遍历该index下的元素.**

ConcurrentHashMap 的 get 方法是非常高效的，**因为整个过程都不需要加锁**。

```java
// 确定segment：
(h >>> segmentShift) & segmentMask。默认使用h的前4位，segmentMask为15
  
// 确定index：
(tab.length - 1) & h  hashentry的长度减1，用之前确定了segment的新h计算
  
// 循环：
for (HashEntry<K,V> e = (HashEntry<K,V>) UNSAFE.getObjectVolatile(tab, ((long)(((tab.length - 1) & h)) << TSHIFT) + TBASE);e != null; e = e.next)
  
// 比较：
if ((k = e.key) == key || (e.hash == h && key.equals(k)))
                 return e.value;
```

##### 6.2.2 put 的流程

1. 将当前的Segment中的table通过key的hashcode定位到HashEntry
2. 遍历该HashEntry，如果不为空则判断传入的key和当前遍历的key是否相等，相等则覆盖旧的value
3. 不为空则需要新建一个HashEntry并加入到Segment中，同时会先判断是否需要扩容
4. 最后会解除在1中所获取当前Segment的锁。

⚠️**注意**：

- 虽然HashEntry中的value是用volatile关键字修饰的，但是并不能保证并发的原子性，所以put操作仍然需要加锁处理。
- 首先第一步的时候会尝试获取锁，如果获取失败肯定就是其他线程存在竞争，则利用`scanAndLockForPut()`**自旋获取锁**：
  - 尝试获取自旋锁
  - 如果**重试的次数**达到了`MAX_SCAN_RETRIES` 则改为**阻塞锁**获取，保证能获取成功。

##### 6.2.3 size

第一种方案：**使用不加锁**的模式**去尝试多次计算 ConcurrentHashMap 的 size，最多**三次**，比较前后两次计算的结果，结果一致就认为当前没有元素加入，计算的结果是准确的。 **

第二种方案：**如果第一种方案不符合**，他就会**给每个 Segment 加上锁**，然后**计算** ConcurrentHashMap 的 size 返回



#### 6.3 1.8版本🌟

1.7 查询遍历链表效率太低（种种原因）。其中抛弃了原有的 Segment 分段锁，而采用了 `CAS + synchronized` 来保证并发安全性（会扯1.6对synchronized的优化）

##### 6.3.1 get的流程（与1.7相同）

1. 根据计算出来的 hashcode 寻址，如果就在桶上那么直接返回值。

2. 如果是红黑树那就按照树的方式获取值。

3. 就不满足那就按照链表的方式遍历获取值。



##### 6.3.2 put的流程

1. 根据key计算出hashcode

2. 判断table是否需要进行初始化

3. 根据key的hashcode定位到HashEntry的first

3. 🆕**如果first为null**，说明table中这个位置第一次插入元素，利用Unsafe.compareAndSwapObject方法插入Node节点。

​       （1）**如果CAS成功**，说明Node节点已经插入，随后addCount(1L, binCount)方法会检查当前容量是否需要进行扩容。

​       （2）**如果CAS失败**，说明有其它线程提前插入了节点，自旋重新尝试在这个位置插入节点。

5. **如果first的hash值为-1**，说明当前f是ForwardingNode节点，意味有其它线程正在扩容，则一起进行扩容操作。

6. **如果都不满足**，则利用`synchronized`锁写入数据🆕 （两个🆕中是1.8与1.7不同的地方）

7. 如果链表长度达到阈值8时将链表转换为红黑树



##### 6.3.3 size

ConcurrentHashMap 提供了 baseCount、counterCells 两个辅助变量和一个 CounterCell 辅助内部类。sumCount() 就是迭代 counterCells 来统计 sum 的过程。 put 操作时，肯定会影响 size()，在 put() 方法最后会调用 **addCount()** 方法。

在**addCount()**方法中：

- 如果 counterCells == null, 则对 baseCount 做 CAS 自增操作。

- 如果并发导致 baseCount CAS 失败了使用 counterCells。

- 如果counterCells CAS 失败了，在 fullAddCount 方法中，会继续死循环操作，直到成功。

- CounterCell使用了 @sun.misc.Contended 标记的类

  

#### 6.4 锁

##### 6.4.1**自旋锁**

特性：当线程尝试获取锁失败时（锁已经被其它线程占用了），它不会将线程切换为沉睡状态，而是开启无限循环，不断地轮询锁的状态，当锁状态被更改时，获取到锁并进入临界区.

自旋锁本身并没有关注公平性、可重入性等特性，另外，由于自旋锁的实现需要不断轮询锁的状态，因此需要占用CPU，**适用于临界区时间很短的场景.** 自旋锁又可进一步细分为**排队自旋锁(TicketLock)、MCS锁以及CLH锁**， 其中排队自旋锁解决的是公平性的问题



##### 6.4.2**阻塞锁**

特性：当线程尝试获取锁失败时，线程进入阻塞状态，直到接收信号后被唤醒.(线程的状态包括新建、就绪、运行、阻塞及死亡）在JAVA中，能够唤醒阻塞线程的操作包括Object.notify, Object.notifyAll, Condition.signal, LockSupport.unpark(JUC中引入）

优点：在线程获取锁失败后，不会一直处于运行状态（占用CPU）， 因此**在竞争激烈的情况下**， 阻塞锁的性能将明显优于自旋锁



##### 6.4.3 互斥锁

**相同**

1. 都是用来协调多线程对共享对象、变量的访问

2. 都是可重入锁，同一线程可以多次获得同一个锁

3. 都保证了可见性和互斥性

| 区别                 | ReentrantLock                               | Synchronized                       |
| -------------------- | ------------------------------------------- | ---------------------------------- |
| **获得、释放锁情形** | 显式获得、释放锁                            | 隐式获得、释放锁                   |
| **锁的级别**         | `API`层面的锁                               | `JVM`层面重量级锁                  |
| **锁的类型**         | 可重入、公平\非公平、可响应中断、异步锁     | 可重入、非公平、不可中断，强阻塞锁 |
| **锁状态**           | 可判断，可响应中断                          | 不可判断，不可响应中断             |
| **唤醒条件**         | condition绑定多个条件                       | notify、notifyall                  |
| **发生异常时**       | 必须在finally显式释放锁，否则，一直锁住资源 | 主动释放锁                         |
| 锁对象               | 通过AQS和CAS操作，实现线程锁的获取和释放    |                                    |



##### 6.4.4 Lock获取锁的方式

假如线程`A`和线程`B`使用同一个锁`LOCK`，此时线程A首先获取到锁`LOCK.lock()`，并且始终持有不释放。如果此时B要去获取锁，有四种方式：

| 序号 | 获取锁的方式                        | 特性                                                         |
| ---- | ----------------------------------- | ------------------------------------------------------------ |
| 1    | `LOCK.lock()`                       | **在等待获取锁的过程中休眠并禁止一切线程调度**<br />即使调用`B.interrupt()`也不能中断，除非线程A调用`LOCK.unlock()`释放锁。 |
| 2    | `LOCK.lockInterruptibly()`          | **在等待获取锁的过程中可被中断**<br />当调用`B.interrupt()`会被中断等待，并抛出`InterruptedException`异常，否则会与`lock()`一样始终处于等待中，直到线程A释放锁。 |
| 3    | `LOCK.tryLock()`                    | **不会等待，获取到锁并返回true**；<br />**获取不到锁直接返回false**，去执行下面的逻辑。 |
| 4    | `LOCK.tryLock(n, TimeUnit.SECONDS)` | **在指定时间内等待获取锁；过程中可被中断**<br />该处会在n秒时间内处于等待中，但当调用`B.interrupt()`会被中断等待，并抛出`InterruptedException`。<br />n秒时间内如果线程A释放锁，会获取到锁并返回true，否则10秒过后会获取不到锁并返回false，去执行下面的逻辑。 |



#### 6.5 区别HashMap & ConcurrentHashMap 1.7/1.8版本

|      | HashMap                              | ConcurrentHashMap 1.7                                        | ConcurrentHashMap 1.8                                        |
| ---- | ------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 区别 | 不管是put还是get操作都需要做同步处理 | 【与HashMap比】<br />1. 核心数据如 value ，链表都是 volatile 修饰的，保证了获取时的可见性<br />2. 采用Segment分段锁保证并发安全<br />其中 Segment 继承于 `ReentrantLock`<br />3. 支持 CurrencyLevel (Segment 数组数量)的线程并发。 | 【与1.7比】<br />1. 采用 `CAS + synchronized` 来保证并发安全性<br />2. 将 1.7 中存放数据的 HashEntry 改为 Node(（但作用相同）；其中val和next都用volatile修饰：<br />`volatile V val;`<br />`volatile Node<K, V> next;` |
| 好处 |                                      | 解决了并发问题，并且能支持 N 个 Segment 的并发               | 采用红黑树之后可以保证查询效率                               |
| 缺点 |                                      | 查询遍历链表效率太低                                         |                                                              |



### 7. TreeSet & TreeMap

实际上TreeSet还是用TreeMap来保存set元素。

TreeMap采用一种被称为“红黑树”的排序二叉树来保存Map中的的每个Entry——每个Entry都被当做红黑树的一个节点来对待；

TreeMap实现SortedMap接口，能够把它保存的记录根据键排序，默认是按键值的升序排序，也可以指定排序的比较器，当用Iterator遍历TreeMap时，得到的记录是排过序的。如果使用排序的映射，建议使用TreeMap。在使用TreeMap时，key必须实现Comparable接口或者在构造TreeMap传入自定义的Comparator，否则会在运行时抛出java.lang.ClassCastException类型的异常。



### 8. LinkedHashMap 

#### 8.1 目的

基于 `HashMap` 但具有顺序的双向链表所构成，来解决有排序需求的场景。

因为是继承与 `HashMap` 的，所以一些 `HashMap` 存在的问题 `LinkedHashMap` 也会存在，比如不支持并发等。

#### 8.2 两种排序方式

- 根据写入顺序排序。
- 根据访问顺序排序：每次 `get` 都会将访问的值移动到链表末尾，这样重复操作就能的到一个按照访问顺序排序的链表。

#### 8.3 手撸LRU

```java
// 双向链表+HashMap，Java中的LinkedHashMap就实现了该算法。
// get
public int get(int key) {
    if (map.containsKey(key)) {
        Node n = map.get(key); // 获取内存中存在的值，比如A
        remove(n); //使用链表的方法，移除该节点
        setHead(n); //依然使用链表的方法，将该节点放入头部
        return n.value;
    } 
    return -1;
}
// put
public void set(int key, int value) {
    if (map.containsKey(key)) {
        Node old = map.get(key);
        old.value = value;
        remove(old); // 移除旧节点
        setHead(old); // 放到队头
    } else {
        Node created = new Node(key, value);
        if (map.size() >= capacity) {
            map.remove(end.key); // clear该key
            remove(end); //链表也是依次
            setHead(created); // 将created放入队头
        } else {
            setHead(created); // 如果没满，直接放入队头
        }
        map.put(key,created);
    }
}

```



```java
//lc: 146. LRU缓存机制
class LRUCache {
    private int cap;
    private Map<Integer, Integer> map = new LinkedHashMap<>();
    public LRUCache(int capacity) {
        this.cap = capacity;
    }
    
    public int get(int key) {
        if (map.containsKey(key)) {
            int value = map.get(key);
            // 查一次，就将查到到仍在队尾
            map.remove(key);
            map.put(key,value);
            return value;
        }
        return -1;
    }
    
    public void put(int key, int value) {
        if (map.containsKey(key)) {
            map.remove(key);
        } else if (map.size() == cap) {
            // 满了
            Iterator<Map.Entry<Integer, Integer>> iterator = map.entrySet().iterator();
            iterator.next();
            iterator.remove();
        }
        map.put(key, value);
    }
}

```

