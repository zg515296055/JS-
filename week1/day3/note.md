变量提升：
在当前作用域下，代码执行之前，对带var和function关键字的进行提前声明和定义

函数执行的步骤：
1.开辟一个私有的作用域
2.形参赋值
3.变量提升
4.代码从上往下执行

全局作用域：浏览器加载页面时形式  全局变量 谁都可以可以访问
私有作用域: 函数运行时形成  私有变量（形参和带var关键字）在函数内部才能访问得到
变量查找的顺序：
1.先确定是否是私有的，若是则用私有的变量即可
2.若不是，往上级作用域查找，若没有找到，继续往上级作用域查找，直到找到window,若window下也没找到，则报错
上级作用域：函数在哪定义的，上级作用域就是谁 跟函数执行没有关系

## 闭包
在函数运行时形成一个保护里面变量不受外界污染的私有作用域，这就成为闭包，闭包是一种机制
- 封装性
- 保护的作用
闭包的形式：
1.自执行函数 
    window.xxx = xxx;
2.函数内部返回一个函数
   预处理机制（柯里化函数思想）：
   - 有些内容现在先提前处理下，但还有部分逻辑现在不需要处理，等你自己执行返回的函数再处理  例如 bind方法就是利用这种思想
   - 在返回小函数之前，先提前把公有的内容定义好，小函数执行时就能获得这些公有的内容
3.函数的内部返回一个对象
   解决公有和私有的问题
   把需要暴露给外界的内容，放在对象中给返回
   
   
## let 和 var  
 - let定义的变量没有变量提升
 - 不会是window的属性
 - 在当前作用域里，变量不能重名

const 
- 没有变量提升
- 不会是window的属性
- 在当前作用域里，变量不能重名
- 不能重复赋值

## 作用域销毁
 全局作用域：关闭页面时销毁
 私有作用域：通常情况下，函数运行完后就销毁了 
 不销毁：函数内部的内容被外界给占用了，这时作用域就不销毁了
 不立即销毁：函数运行完后返回一个需要被执行的小函数，只有等小函数运行完后，这个函数运行产生的作用域才能被销毁
 
 堆内存销毁
 堆内存的引用地址赋值给变量了，这时堆内存就销毁不了了，解决办法，把变量设成null,变成空指针，浏览器在空闲时会释放堆内存，这就是垃圾回收机制

## this
 指调用的主体
 - 方法运行时，方法名前面有没有.,若有点，点前面是谁this就是谁，若没有则this是window
 - 自执行函数的this是window
 - 事件驱动函数运行里的this是绑定的元素
 oBtns[0].onclick = function(){
        console.log(this);//绑定的元素
 }
