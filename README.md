# -Javascript03
偷个懒。。。明天再传了
### 语句  
 在 JavaScript 中，语句使用分号（;）进行分隔  
 JavaScript解释器按照语句的编写顺序依次执行。但也可以编写一些复杂的语句块,就如下  
 ![流程控制语句](http://a3.qpic.cn/psb?/V118JuTr0BKcy7/Kuqs7spk.nvnKjjzE3y9A9F6GUsAXRYYCASXd5kLBEU!/m/dPIAAAAAAAAA&bo=dgL4AAAAAAADB64!&rf=photolist)  
 **流程控制语句**
>- 语句有
>   - 条件语句: JavaScript 解释器根据一个值判断是执行还是跳过指定语句。
>   - 循环语句: JavaScript 解释器根据一个值判断是否重复执行指定语句。
>   - 跳转语句: 使 JavaScript 解释器跳转到指定语句。
#### 空语句
- 空语句允许包含 0 条语句
- JavaScript 解释器执行空语句时，不会执行任何动作。
```js
    ;
```
#### 语句块
JavaScript 中使用一对花括号（{}）表示一个语句块。  
语句块的作用是为语句进行分组，使语句的结构清晰明了
```js
{
    var str = 'string';
    console.log(str);
}
```
>- 语句块的结尾不需要分号。 
>- 语句块中的行都有缩进，但并不是必需的。 
>- 语句中声明变量是全局变量
#### 条件语句
>条件语句就是指通过判断指定的计算结果，来决定是执行还是跳过指定的语句块。  
>如果说 JavaScript 解释器是按照代码的“路径”执行的话，那条件语句就是这条路径上的分叉点，代码执行到这里时必须选择其中一条路径继续执行。  
>JavaScript 提供了两种条件语句：if else 语句和 switch case 语句。
1. if语句  
 ```js
 var num = 100;
 if (num >= 100) {
     console.log(num);// 根据表达式`num >= 100`是true还是false来打印结果
 };//如果在if语句最后添加分号时 - 执行不会报错：1. 将分号解析为空语句；2. 性能下降
 ```
>* if关键字后的表达式的小括号不能被省略  
>   * 包含语句的语句块的大括号允许被省略的 - 一般不建议,降低可读性 
>* JavaScript解析器默认认为表达式后的第一条语句就是被控制的语句  
>   * 被条件语句所控制的语句只能是一条   
>- if 关键字后面的条件判断的结果必须是布尔值。如果结果为非布尔值的话，JavaScript 会自动转换为布尔值。

![条件语句的执行流程图](http://a4.qpic.cn/psb?/V118JuTr0BKcy7/rjQa.tDjTMyH6gmBDGt7RTXfLKkXvPfk0yI2dJv7xCE!/m/dD8BAAAAAAAA&bo=GwWAAgAAAAADB74!&rf=photolist)

2. if...else语句  
```js
var num = 100;
if (num > 100) {
    console.log('语句块一');
} else {
    console.log('语句块二');//在if的基础上给了flase可显示的结果
}
```
![if...else执行流程图](http://a3.qpic.cn/psb?/V118JuTr0BKcy7/1wIbeoct5fbS8iXJ0RWmETmE3bYudDlQ*flunLcE8PQ!/m/dPIAAAAAAAAA&bo=GwWAAgAAAAADB74!&rf=photolist) 
>if...else语句允许嵌套的,但是建议不超过3层
>- 嵌套的层级过多时
>   - 性能下降
>   - 可读性降低
```js
//if..else的嵌套操作
var score = 85;
if ( score > 90 ) {
    console.log('优秀');
} else {
    if ( score > 80 ) {
        console.log('良好');
    } else {
        console.log('其他');
    }
}
```

3.if语句与条件运算符的比较  
```js
var num = 100;
//条件语句 
if ( num > 100 ) {
    console.log('语句块一');
}  else {
    console.log('语句块二');
}
//条件运算符 
num >= 100 ? console.log('语句块一') ：console.log('语句块二');
```
>* 条件语句
>      * 优点 - 代码的可读性更高
>      * 缺点 - 执行的效率相对不高
>* 条件运算符
>      * 优点 - 执行的效率相对比较高
>      * 缺点 - 代码的可读性不高
>* 在实际开发中
>      * 完成功能(需求) - 首选语句实现
>      * 代码优化 - 将语句改写为运算符表达式
 
4. else..if语句  
```js
var score = 45;
if ( score > 90 ) {
    console.log('优秀');
} else if ( score > 80 ) {
    console.log('良好');
} else if ( score > 60 ) {
    console.log('及格');
} else {
    console.log('不及格');
}
```
![else..if语句的执行流程](http://a4.qpic.cn/psb?/V118JuTr0BKcy7/6u6*HqU4KJ9Gkmn0x.nPkFvobLZLUaAyQ8gcRw0Y4PM!/m/dPMAAAAAAAAA&bo=GwWAAgAAAAADB74!&rf=photolist)

5. switch...case语句  
`switch case 语句是开关语句，但整体执行流程要比 if else 语句复杂的多`
```js
var num = 0;
// 枚举 
switch ( num ) {
    /*default:
        console.log('错误');
        break; - 若是放在开头要写*/
    case 0:
        console.log(0);
        break;
    case 1:
        console.log(1);
        break;
    case 2:
        console.log(2);
        break;
    case 3:
        console.log(3);
        break;
    case 4:
        console.log(4);
        break;
    case 5:
        console.log(5);
        break;
    default:
        console.log('错误');
        /*break; - 将default语句放置在了 switch 语句的最后面,所以不用写 */
}
```
![执行流程图](http://a4.qpic.cn/psb?/V118JuTr0BKcy7/ZZGif8YrMMoLWXzuSwXOb9E3xaIEyVpjg9Pb0JjDR4E!/m/dPMAAAAAAAAA&bo=GwWAAgAAAAADB74!&rf=photolist)    
>- 在实际开发中，switch case 语句与 break 语句同时使用。
>- switch case 语句相对于 if else 语句执行性能更优，但也有很多需要注意的地方。
>    - switch 关键字后面的小括号、case 关键字后面的冒号都不能被省略的。 
>    - default 关键字只能出现在 switch case 语句的最后面（default 关键字后面不能再出现 case 关键字）。 
>    - break 语句是跳出语句，一旦被执行，表示后面所有的 case 和 default 语句都不会被执行。
#### 循环语句  
- 循环语句是一系列反复执行到复合特定条件的语句。   
- 为了更好地理解循环语句，可以将 JavaScript 代码想象成一条条的分支路径。    
- 循环语句就是代码路径中的一个回路，可以让一段代码重复执行。   
1. while语句  
- while 语句是一个基本循环语句，语法结构与 if 语句很类似。
```js
var num = 100;
while ( num >= 90 ) {
    console.log(num);
    num--;
}
console.log('这是while语句执行之后');
```
![执行图](http://a4.qpic.cn/psb?/V118JuTr0BKcy7/tc4B.ylKF7uymdmmfBSuk8utGJYxEtQrBZ4Q4Rn6bh8!/m/dPMAAAAAAAAA&bo=GwWAAgAAAAADB74!&rf=photolist)   
>- while 关键字后面的小括号不能被省略。 
>- while 关键字后面的条件判断的结果必须是布尔值。如果结果为非布尔值的话，JavaScript 会自动转换为布尔值。 
>- while 语句中的大括号（{}）可以被省略，但建议编写，以提高代码阅读性。

2. do..while语句  
- do while 语句也是一个基本循环语句，执行流程与 while 语句很类似。
```js
var num = 0;
do {
    console.log(num);
    num++;
} while ( num < 10 );
```
![执行图](http://a3.qpic.cn/psb?/V118JuTr0BKcy7/3cKAoFK6hOpApyGRJefL1ZYkJZ1h.R6.NvwMFLfcxQ8!/m/dPIAAAAAAAAA&bo=GwWAAgAAAAADB74!&rf=photolist)   
>- while 关键字后面的小括号不能被省略。 
>- while 关键字后面的条件判断的结果必须是布尔值。如果结果为非布尔值的话，JavaScript 会自动转换为布尔值。 
>- do while语句中的大括号（{}）可以被省略，但建议编写，以提高代码阅读性。

3. while语句和do..while语句的区别  
```js
var num = 0,num2 = 1;
// 第一次执行条件判断表达式时 - 结果为false，一次循环都没有
while ( num < 0 ) {
    console.log(num);
}
// 第一次执行语句块，再执行条件判断表达式是 - 结果为false，结束循环
do {
    console.log(num2);
} while ( num2 < 0 );
```
* while语句 - 先判断，再执行  
    * 可能一次循环都不执行
* do..while语句 - 先执行，再判断   
    * 至少循环执行一次
4. for语句  
- for语句是一种最简洁的循环语句，其中包含三个重要部分:  
    - 初始化表达式: 初始化一个计数器，在循环开始前计算初始状态。
    - 条件判断表达式: 判断给定的状态是否为true。如果条件为true，则执行语句块，否则跳出循环。
    - 循环操作表达式: 改变循环条件，修改计数器的值。       
![语法结构图](http://a4.qpic.cn/psb?/V118JuTr0BKcy7/l*PIW*FNLMzphQTKxNwxf1rTV4Nd3h3LQow2hEkum20!/m/dGsBAAAAAAAA&bo=GwWAAgAAAAADB74!&rf=photolist)     
```js
var num = 0;
while ( num < 10 ) {
    console.log(num);
    num++;
}
// 代码的可读性 - for语句更高
for ( var num = 0; num < 10; num++ ) {
    console.log(num);
}
```
![执行流程图](http://a3.qpic.cn/psb?/V118JuTr0BKcy7/azhRE6*TaBaPGYRf85F70wbBWcJXmZsvBWk.PC3IsYE!/m/dPIAAAAAAAAA&bo=GwWAAgAAAAADB74!&rf=photolist) 

5. for语句的特殊用法  
`for语句的特殊用法 - 表达式具有三个`
- 默认完整for语句的结构 
```js
for ( var num = 0; num < 10; num++ ) {
    console.log(num);
}
```

- 将`初始化表达式`省略
```js
var num = 0;
for ( ; num < 10; num++ ) {
    console.log(num);
}
```

- 将`循环操作表达式`省略
```js
var num = 0;
for ( ; num < 10;  ) {
    console.log(num);

    num++;
}
```

- 将`条件判断表达式`省略 - 循环结构中没有`条件判断表达式`,循环没有意义（一定是死循环）
```js
var num = 0;
for ( ; /*num < 10*/;  ) {
    console.log(num);

    num++;
}
```
>在`for()`里面，分号`;`不可以省略

6. 循环嵌套  
`JavaScript 中对循环嵌套的层级没有任何限制。但一般建议循环嵌套三层，不然执行的性能会下降。`
```js
for (var i=0;i<10;i++) {
    for (var j=0;j<10;j++){
        // i = 0,j = 0
        console.log('i = ' + i + ',j = ' + j);
    }
}
```
![流程图](http://a3.qpic.cn/psb?/V118JuTr0BKcy7/KzJgdS255YQDd7CYXGH*9kFe6j1vd*wfzrlVCp3yqqg!/m/dPIAAAAAAAAA&bo=CQSAAgAAAAADB60!&rf=photolist)

#### 跳转语句
- JavaScript 中另一种语句就是跳转语句。从名称就可以看出，它使得 JavaScript 代码的执行可以从一个位置到另一个位置。    
- 跳转语句提供了 break 和 continue 两种，用于跳出当前的循环或开始下一次的循环等。  
* 注意 - 跳转语句不能被用在条件语句中
    * switch 条件语句中使用 break 语句除外
* 用法 - 跳转语句是被用在循环语句中
1. break语句  

>错误的写法

```js
var num = 0;
if (num >= 0) {
    break;// 在这个地方跳出循环就没有下面的事了
    console.log(num);
}
```
>break语句 - 跳转整个循环体
```js
for (var i=0;i<10;i++){
    if (i > 4){
        break;
    }
    console.log(i);// 0,1,2,3,4
}
```
2. continue语句 
`continue语句 - 跳出当前循环`
```js
for (var i=0;i<10;i++){
    if (i == 4){
        continue;
    }
    console.log(i);// 除了 4 之外的 0——9
}
```


 






