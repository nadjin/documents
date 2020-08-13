
为什么使用RxJS？业务的快速增长和变化，会伴随代码库的快速膨胀，为了快速迭代，提高代码的质量，控制代码的复杂度，提高代码的可维护性，我们需要引入一种新的方式，RxJS的出现为我们解决这些为题提供了有效的方式。

# RxJS

> RxJS使用了一种不同于传统的编程模式——函数响应式编程，并使用迭代器和观察者模式。
RxJS中有一种特殊的对象——“流”，或者说Observable对象。代表流的变量标识符都用$结尾，这种命名方式称为“芬兰式命名法（Finnish Notation）”

上面说过RxJS使用的是函数响应式编程，这里涉及两个重要的思想：
* 函数式
* 响应式

这两个思想会伴随RxJS的始终，请务必理解和掌握。


## 函数式编程(FP)

简单说，"函数式编程"是一种"编程范式"（programming paradigm），也就是如何编写程序的方法论。一种编程思想。

### 特点：
* 声明式
* 纯函数

### 声明式
和声明式编相对应的编程方式叫做命令式编程，也是我们最常见的一种编程方式。

* 命令式
先来说下什么是命令式。实现一个将数组中的每个元素变为原来的2倍，代码如下：

``` js
function double(arr){
  const results = [];
  for(let i=0, i<arr.length, i++){
    results.push(arr[i]*2);
  }
  return results;
 }
 ```
 这种程序猿们通过一步步代码指令告诉计算机如何操作，最终得到我们想要的结果就是命令式，这时有的朋友就会疑惑，我们的工作不就是通过计算机语言把我们的想法传递给计算机，告诉计算机我们想要做什么吗？
 没错我们的工作就是通过语言去和计算机交流，但是交流也有很多中方式，让我们换种交流方式再来看看声明式是如何交流的。
 
 * 声明式
 和上面命令式实现相同的功能，还是直接看代码：
 
 ``` js
 function double(arr){
  return arr.map(item=> item * 2);
 }
 ```
完了？没错哈拉少不哈拉少。现在如果我们的业务变了，要求每个元素在原来的基础上加1，如果是命令式我们又会怎么样？
对比之后我们发现完全两种风格，上面的一看就是个话痨，而下面的简直就是个高冷艳的小姐姐啊小姐姐。高在思想，冷在‘话’少，艳在结构。看完之后是不是有种马上想和小姐姐认识的冲动😍😍。

为了更好的理解声明式，说一下SQL，其实SQL就是一种声明式编程语言。
比如我们要查学号是1的同学姓名：

``` sql
SELECT name FROM student WHERE id=1;
```

不会SQL的英语稍微懂点，通过字面就大概知道这个代码是干嘛的。我们不需要去实现复杂的查询和筛选代码，只需要告诉计算机，我想要什么结果，具体怎么操作我们不需要关心。

> ps:
在js中函数有第一公民的身份，指的是函数与其他数据类型一样，处于平等地位，可以赋值给其他变量，也可以作为参数，传入另一个函数，或者作为别的函数的返回值。

* 总结：
命令式编程（Imperative）：详细的命令机器怎么（How）去处理一件事情以达到你想要的结果（What）；
声明式编程（ Declarative）：只告诉你想要的结果（What），机器自己摸索过程（How）；

声明式更加简洁和利于维护，让程序员能重重复的复杂工作中释放出来，更加集中精力在代码设计上。

### 纯函数

所谓纯函数指的是满足下面两个条件的函数：
* 函数的执行过程完全由输入参数决定，不会受除参数之外的任何数据影响。
* 函数不会修改任何外部状态，比如修改全局变量或传入的参数对象。

纯函数的要求，可能会让使用者感到失望，好像没有什么强大的地方，更多的感觉是束缚了手脚，其实纯函数的这种降级，是为了是函数回归原始，变得更加简单，我们不需要担心函数副作用带来潜在问题，通过这种最单纯的函数组装强大的功能。

* 总结：
满足纯函数的特性也叫做引用透明度，这是更加正确的说法。所谓纯函数就是输入参数到返回结果的一个映射，不要产生副作用。

### 函数式编程的缺点：
根据炼金术士的重要思想，等价交换原则：你想得到某样东西就要付出相同的代价。函数式的缺点是速度上会慢一点，如果你是个极度追求执行速度完美的人，那么他可能不适合你。，但是我们损失的这一点点性能，却换来了开发速度和维护成本。

### 函数式编程（FP）和面向对象编程(OOP)：
函数式编程中，倾向于数据就是数据，函数就是函数，函数可以处理数据，而面向对象的类概念是把数据和方法封装在一起，函数式是不修改原有数据，通过产生新的数据来作为运算结果。

## 响应式(RP)
和面向对象，函数式编程一样，响应式编程是一个编程范式，与其他编程范式不同的是它是基于数据流和变化传播的。

## 函数响应式编程：(FRP)
主要利用函数式编程的思想和方法来支持响应式编程就是函数响应式编程。

Rx诞生的主要目的虽然是解决异步处理问题，但并不表示Rx不适合处理同步的数据，实际上，使用RxJS之后大部分代码不需要关心自己是被同步执行还是异步执行，所以处理起来更加简单。





 
