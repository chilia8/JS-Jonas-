# 基础部分

## 一.JS是什么

一个高级的面向对象的多范式编程语言

## 二.能做什么

html/css/js共同作用创建动态网站和程序



html负责文本,图像,按钮和网站上所有能看到的内容(名词):

```
<p></p>
//paragraph
```

css负责造型和布局(形容词)

```
p{color:red}
//该paragraph的color为red
```

js负责交互(动词)

```
p.hide()
//hide这个paragraph
```



## 三.基础操作

#### 1.内联脚本

```
//在html文件中的内联脚本

	<script>
		let js = 'amazing';
		if (js === 'amazing') alert('JavaScript is FUN!');
		40 + 8 + 23 - 10;
		console.log(40 + 8 + 23 - 10);
	</script>

//优势为不必加载另一个文件

```

#### 2.调用外部脚本

```
//在html中调用外部js文件

<script src="JS script.js"></script>

//js文件必须和html在同层文件夹
//确保正确拼写脚本名
//调用的js文件写在<script>里
//js脚本无差错
```



## 四.值(values),变量(variables)

### 1.值:

值是js中信息的最小单位,包括数值/字符串/......



### 2.变量

##### 1..最大优势:

改变变量值后,其他地方引用的变量随之改变

##### 2..命名原则:

  1...驼峰命名法(camecase):firstName

  2...下划线命名:first_name

  3...首字母不能:数字,最好不要大写(大写一般是函数)

  4...变量名只能包含:数字,字母,_,$

  5...变量名不能是保留关键字

  6...变量名全大写:一般写常量

## 五.数据类型

```
//object对象

let me = {
  name:'Jonas'
};
```

```
//primitive原始值

let firstName = 'Jonas';
let age = 30;
```

值不是对象时,就是原始值

### 1.七种原始数据类型

*JS是动态类型,值具有类型,而不是变量*

***字符串一定要带""或''***

```
//浮点数number,有小数
let age =20;

//字符串string,要带''或者"",与变量名区别
let firstName = 'Jonas';

//布尔值bool,只有true/false
let fullAge = true;
```

```
//未定义undifined,空的,未赋值
let children;

//不存在Null,也是空的

//常量symbol(ES2015),现在没用了,值唯一且不可改

//超大数字bigInt,比nuber更大的整数
```

查看数据类型

```
//在控制台记录(值的数据类型)
console.log(typeof 值)


console.log(typeof null)      //结果是object,是js历史遗留错误

```





## 六.变量的三种声明方式:let,var,const

let

```
let age = 30;
age = 31;

//let可以改变变量，重新赋值，或者称为数值变异
//变量取空值，后期填充


```

const

```
const birthYear = 1991;
//birthYear = 2001;//错误
//const job

//所以const不能声明空值
//const的变量不可以改变，会报错

```

var

```
var job = 'programmer';
job = 'teacher';

//var是旧方法
//var 如果不在function使用，会创建全局变量
//for 循环最好用let
```

*综上，变量用let，常量用const（const减少突变创建错误）*

**基本永远不用var*





## 七.JS的基本运算符

```
//数学运算符


const now = 2037;
const ageJonas = now - 1991;
const ageSarah = now - 2018;
console.log(ageJonas, ageSarah);

console.log(ageJonas * 2, ageJonas / 10, 2 ** 3);
//2**3 = 2的3次幂 = 2*2*2

const firsName = 'Jonas';
const lastName = 'Zhu';
console.log(firsName + ' ' + lastName);
```

```
//赋值运算符


let x = 10 + 5;  //15
x += 10;         //x=x+10=25
x *= 4;          //x=x*4=100
x++;            //x=x+1=101
x--;            //x=x-1=100
console.log(x);
```

```
//比较运算符


console.log(ageJonas > ageSarah);//>,<,>=,<=
console.log(ageSarah >= 18)

const isFullAge = ageSarah >= 18;

console.log(now - 1991 > now - 2018)
```

*注意运算符的左右方向*

```
//运算符的不同优先级

const now = 2037;
const ageJonas = now - 1991;
const ageSarah = now - 2018;

console.log(now - 1991 > now - 2018)


let x, y;
x = y = 25 - 10 - 5;//x=y=10,先y=10,再x=y=10，=赋值从右往左
console.log(x, y)

const averageAge = (ageJonas + ageSarah) / 2
console.log(ageJonas, ageSarah, averageAge)

```

优先级查看mdn web doc的[operator precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_precedence)的table



## 八.字符串和模板(template)

```
//字符串拼接

const firsName = 'Jonas';
const job = 'teacher';
const birthYear = 1991;
const year = 2037

const jonas = "I'm " + firsName + ',a ' + (year - birthYear) + ' years old ' + job + '!'

console.log(jonas)
```

```
//模板字符串
//用``表示模板字符串,点击Tab上面一个键,${}表示变量,里面什么都可以装
//好处是方便文字排版
const jonasNew = `I'm ${firsName},a ${year - birthYear} years old ${job}!`;
console.log(jonasNew)

//理论上可以用``代替任何不规则引号字符串,且更方便
console.log(`Just a regular string...`)

```

```
//用/n/表示换行
console.log('String with \n\
mutiple\n\
lines')

//用``换行不用带\n\
console.log(`String with
mutiple
lines`);
```

综上:``表示的模板字符串可以**方便排版文字**和**自动换行**

应用场景:对话/多行字符串

## 九.判断语句if,else

```
//if语句模板

if () {

} else if(){

} else{

}
```

## 十.数据类型(二)

```
//数值转化

//转换为数字
const inputYear = '1991'
console.log(Number(inputYear), inputYear)//->1991 '1991'
console.log(Number(inputYear) + 18)//->2019
//Number(a):变为数字输出,但a本身没变

console.log(Number('Jonas'))
console.log(typeof NaN)
//NaN:无效数字,但类型是number



//转化为字符
console.log(String(23), 23)

```

```
//数值强制

console.log('I am ' + 23 + ' years old.')
console.log('I am ' + '23' + ' years old.')
//两个相同,23被强制转化为字符串

console.log('23' - '10' - 3)
console.log('23' * '10')
console.log('23' / '10')
//(-*/)运算符触发了字符串到数字的转化

console.log('23' + '10' + 3)
//(+)运算符触发了数字到字符串的转化
```

## 十一. 真值(truthy),假值(falsy)

**假值**是非false的值,但是被转换时,会转化为布尔值false

JS中仅有5个假值

```
//5 falsy values:0,'',undifined,null,NaN
//其他一切转化后皆为true
```

```
//if(a),a将被强制转化为布尔值

const money = 0
if (money) {                          //money成立否->money是否true
	console.log('别把钱花光了')
} else {
	console.log('你该找份工作了!')
}
```

## 十二. == vs ===

# 通用技能

















































# Dom操作

# 工作原理

# 现代操作(ES6)

# 函数(Functions)

# 数组(Arrays)

# 数字(Numers)/日期(Dates)/计时器(Timers)

# 进阶Dom

# 面向对象 JS

# 丰富项目

# 异步 JS

# 现代JS程序应用

# 部署&Git

# *语法

```
console.log(参数)               //在控制台(console)显示日志(log)
```























































