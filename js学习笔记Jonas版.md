







# 01 SECTION : JS Fundamentals - Part 1

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

**严格相等运算符**判断类型和值是否一致
**松散相等运算符**,如果类型不一致,进行类型转换后比较值是否相等

```
const age = '18'
if (age === 18) console.log('你刚刚成年啦!strict')
if (age == 18) console.log('你刚刚成年啦!loose')

//如果if只有一条线,可以不写{}
//===返回的是一个bool值
//==会数值强制为数字,===不会数值强制
//尽量使用===,避免代码错误,假装==不存在
//'18'==18  ->true
//'18'===18 ->false

```

```
const favourate = Number(prompt('what is your favourate number?'));
console.log(favourate);
console.log(typeof favourate);
if (favourate === 23) {//'23'==23
	console.log('23 is a great number!')
} else if (favourate === 7) {
	console.log('7 is also a great number!')
} else if (favourate === 50) {
	console.log('50 is the best number!')
} else {
	console.log('Number is not 27/23/50.')
}

if (favourate !== 23) {
	console.log('why not 23?')
}

//因为要严格使用===,所以必须在变量中将字符串转化为数字
//不要依赖==强制转化
/*
prompt:v:引发,激起,促使;提示
			 adj:立即的;准时的
			 n:提示符
			 adv:准时地
*/

```



## 十三.bool值逻辑



true when **All** true

|    AND    |  true  | false |
| :-------: | :----: | :---: |
| **true**  | *true* | false |
| **false** | false  | false |

true when **ONE** true

|    OR     | true |  false  |
| :-------: | :--: | :-----: |
| **true**  | true |  true   |
| **false** | true | *false* |

**NOT**:仅作用于bool值,改变true/false



## 十四.逻辑运算符的工作原理

### 1.if语句

```
const hasDriverLicense = true
const hasGoodVision = false

console.log(hasDriverLicense && hasGoodVision);
console.log(hasDriverLicense || hasGoodVision);
console.log(!hasDriverLicense)

if (hasDriverLicense && hasGoodVision) {
	console.log('Sarah is able to drive!')
} else {
	console.log('someone else should drive...')
}


const isTired = false
console.log(hasDriverLicense && hasGoodVision && isTired)


if (hasDriverLicense && hasGoodVision && !isTired) {
	console.log('Sarah is able to drive!')
} else {
	console.log('someone else should drive...')
}
```



### 2.switch 语句

**与if语句相似**,可相互转化,按照喜好选择

```
const day = 'monday'

switch (day) {
	case 'monday'://day === monday
		console.log('Plan course structure')
		console.log('Go to coding meetup')
	break
	case 'tuesday':
		console.log('prepare theory videos')
		break
	case 'wedsday':
	case 'thursday':
		console.log('write code examples')
		break
	case 'friday':
		console.log('record videos')
		break
	case 'saturday':
	case 'sunday':
		console.log('enjoy the weekend')
		break
	default:
		console.log('not a valid day')
}





//const 变量 = 参数

switch(变量){
  case 参数1:
    执行
    break
  case 参数2:
    执行
    break
  case 参数3:
    执行
    break
  default:
    执行默认语句
}

//重点别忘了break,若不break,将继续执行下一行代码
//别忘了:
//default可设置默认情况类似else
```



### 3.三元运算符?:

**本质是表达式**

```
//三元运算符,本质是if/else
//格式: 条件?结果1:结果2
const age = 23
age >= 18 ? console.log('I like to drink wine🍷') :console.log('I like to drink water💧')


//运算符是一个表达式,可以产生值,所以将产生的值赋予变量
const drink=age>=18 ? 'wine🍷':'water💧'


//需要快速做判断用三元运算符,条件复杂用if/else
//例
const bill = 430
let tip = bill >= 50 && bill <= 300 ? bill * 0.15 : bill * 0.2

console.log(`The bill was ${bill},the tip was ${tip},and the total value was ${bill + tip}.`)

```

















## 十五.语句和表达式



```
if(23>14){
  const str='23 is bigger';
}

//'23 is bigger'是表达式,产生值
//if语句是语句,不产生值,语句结束后最好加;表示语句结束
//某些地方只能插入表达式,不能插入语句,例如:

const me ='Jonas'
console.log(`I'm ${2037 - 1991} years old.${me}`)

//以上内容不能插入if语句,但能插入三元运算符作为表达式代替
console.log(`I like drink ${age >= 18 ? 'wine🍷' : 'water💧'}`)
```







## 十六.现代操作(ES5/ES6/ESNEXT)

ES5:2009

ES6:2015

JS开发仅10天,主要用于网页互动

JS能向后兼容,但不能向前兼容,所以浏览器尽量更新到最新,JS尽量用旧的代码库,以免浏览器不能理解最新JS



# 02 SECTION : JS Fundamentals - Part 2

```
'use strict';//激活严格模式,可以让产生的错误更直观,最好开头就用,错误会反馈在控制台
```





## 一.函数(Functions)

```
//return返回一个变量,调用函数后,会得到该变量,就像水果处理器处理后得到的果汁


function fruitProcessor(apples, oranges) {
	const juice = `Juice with ${apples} apples and ${oranges} oranges.`;
	return juice;
}

const appleJuice = fruitProcessor(5, 0);
console.log(fruitProcessor(5, 0));


//在方程式中参数可以不被调用
function logger() {
	console.log('My name is Jonas');
}
logger(23);
logger();
```



### 1.函数声明

```
//函数声明

function calcAge1(birthYear) {
	const age = 2037 - birthYear;
	return age;//课直接return 2037-birthYear
}
const age1 = calcAge1(1991);

//格式:
function 函数名(参数){
  表达式;
  return 变量(或表达式);
}
```

1.函数声明可以在定义该函数前调用,函数表达式不可以

2.声明和表达式可以按照喜好选择

### 2.函数表达式

```
//函数表达式(匿名函数),是一个值,不是类型,可以存储在变量中

const calcAge2 = function (birthYear) {
	return 2037 - birthYear
}
const age2 = calcAge2(1991)

console.log(age1, age2)

//格式:
const 函数名 = function (参数){
  return 表达式;
}
```



### 3.箭头函数

一种更短的函数表达式,是特殊的函数表达式

```
const yearsUntilRetirement = (birthYear, firstName) => {
	const age = 2037 - birthYear;
	const retirement = 65 - age;
	return `${firstName} retires in ${retirement} years.`;
}

//格式:
const 函数名 =参数 =>表达式

```

1.更简短,可以不用return

2.如果表达式复杂,要用{}和return



### 4.函数中调用其他函数

```
function cutFruitPieces(fruit) {
	return fruit * 4;
}


function fruitProcessor(apples, oranges) {
	const applePieces = cutFruitPieces(apples);
	const orangePieces = cutFruitPieces(oranges);
	const juice = `Juice with ${applePieces} pieces of apples and ${orangePieces} pieces of oranges.`;
	return juice;
}

console.log(fruitProcessor(2, 3));
```



### 5.回顾复习

1.函数中的参数是局部变量,不同函数的参数无关联

2.函数进行到return后终止,可以定义一个变量来储存返回值

3.函数声明可以在声明前使用

4.函数表达式可以作为一个值储存在变量中

5.箭头函数是特殊的更便捷的函数表达式

6.函数的参数是局部变量,与外部变量同名不会冲突

7.调用函数时带上(),不带()则表示一个值,带()表示调用函数

8.写完函数别忘了调用





## 二.数组(Arrays)

### 1.创造数组的两种方式

```
//[a,b,c]
const friends = ['Michael', 'Steven', 'Peter']
console.log(friends)
//new Array(a,b,c)
const years = new Array(1991, 1984, 2008, 2020)
console.log(years)
```



### 2.取用数组

```
//取用数组
console.log(friends[0]);
console.log(friends[2]);
//查看数组数量
console.log(friends.length)
//查看数组最后一个数值
console.log(friends[friends.length - 1])
//改变数组内容
friends[2] = 'Jay'
console.log(friends)
```

1.const 定义常量,不能改变,但不能改变保护的是原始值,数组不是原始值

2.const定义的数组不可以重新赋值,但数组元素不再保护范围内,例:

可以friends[2]='Jay'

不可以friends=['a','b','c']

### 3.数组存储的数据类型

```
//储存不同数据类型:变量/字符串/数字/表达式/数组
const firstName = 'Jonas'
const Jonas = [firstName, 'Waterhouse', 2037 - 1991, 'teacher', friends];
console.log(Jonas)
console.log(Jonas.length)

//数组元素做运算后成立新数组
const calcAge = function (birthYear) {
	return 2037 - birthYear
}

const years = [1990, 1967, 2002, 2010, 2018];
const ages = [calcAge(years[0]), calcAge(years[1]), calcAge(years[years.length - 1])]
console.log(ages)
```

### 4.基础数组函数/方法

#### 1..push/unshift:添加元素

```
//push:在数组最后新加元素,并产生一个关于新数组长度的返回值
const newLength = friends.push('Jay',1,2,3,4)
console.log(friends)
console.log(newLength)

//unshift:在数组开头新加元素,并产生一个关于新数组长度的返回值
friends.unshift('John')
console.log(friends)
```

#### 2..pop/shift:删除元素

```
//pop:删除最后一个元素,无需参数,返回删除的元素
friends.pop()
const popped = friends.pop()
console.log(popped)
console.log(friends)

//shift:删除第一个元素,返回删除的元素
friends.shift()
console.log(friends)
```

#### 3..indexOf/includes:索引

```
//indexOf:索引元素在数组的顺序,返回数值
console.log(friends.indexOf('Steven'));
console.log(friends.indexOf('Bob'));

//includes:判断元素是否在数组内,返回布尔值,采用严格相等
console.log(friends.includes('Steven'));
console.log(friends.includes('Bob'))
```

includes实例:

```
if (friends.includes('Steven')) {
	console.log('You have a friend called Steven.')
} else {
	console.log('Who is that?')
}
```

#### 4..数组实例

```
//----------------------编码挑战2-----------------------

const calcTip = bill => bill >= 50 && bill <= 300 ? bill * 0.15 : bill * 0.2;

const bills = [125, 555, 44];
const tips = [calcTip(bills[0]), calcTip(bills[1]), calcTip(bills[2])]

const calctotal = a => bills[a] + tips[a]
const total = [calctotal(0), calctotal(1), calctotal(2)]

console.log(bills, tips, total)

```

#### 5..Array1.contact()：合并数组

```
const a=[1,2,3];
const b=[4,5,6];
const c=a.contact(b)
console.log(c)
//结果:c[1,2,3,4,5,6]
```

#### 6..Math.min()&Math.max():最小/大值



### 5.数组文档

见[MDN数组](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array)

## 三.对象(Objects)

```
const Jonas = {
	firstName: 'Jonas',
	lastName: 'Waterhouse',
	age: 2037 - 1991,
	job: 'teacher',
	friends:['Michael','Peter','Steven']
}
```

1.数组中无法对值命名,对象可以,job是属性,'teacher'是值

2.数组适合有序数据,对象适合非结构性数据

3.数组用[],对象用{}

### 1.对象的使用方法

```
//对象[属性]:[]里面什么都能装,一般需要属性名称运算时用,其余情况用.更方便
//对象.属性:不能什么都装
console.log(jonas)
console.log(jonas.lastName)
console.log(jonas['lastName'])
const nameKey = 'Name'
console.log(jonas['first' + nameKey])
console.log(jonas['last' + nameKey])

```



```
//关于[]的用法
const interestedIn = prompt('what do you want to know about Jonas?Chooose between firstName,lastName,age,job,and friends');
if (jonas[interestedIn]) {
	console.log(jonas[interestedIn])
} else {
	console.log('Wrong quests! What do you want to know about Jonas? Chooose between firstName,lastName,age,job,and friends')
}
```

```
//关于.的用法:添加新属性
jonas.location = 'Portugal'
jonas['twitter'] = '@jonasschmedtman'
console.log(jonas)
```

```
//challenge:[]和.的混合用法
//优先级:从左到右

console.log(`${jonas.firstName} has ${jonas.friends.length} friends, and his best friend is called ${jonas.friends[0]}.`)
//Jonas has 3 friends, and his best friend is called Michael.
```

### 2.对象函数/方法

**写在对象里的函数称为方法,只能是函数表达式(匿名函数),函数名作为属性存在,因为函数表达式返回值,函数声明不返回值**

```
const jonas = {
	firstName: 'Jonas',
	lastName: 'Waterhouse',
	birthYear: 1991,
	job: 'teacher',
	friends: ['Michael', 'Peter', 'Steven'],
	hasDriversLicense: true,

	calcAge: function (birthYear) {
		return 2037 - birthYear;
	}
}

console.log(jonas.calcAge(1991));
console.log(jonas['calcAge'](1991));
```

### 3.this:面向对象

**方法中用this取代对象名称,保持代码不重复原则**

```
const jonas = {
	firstName: 'Jonas',
	lastName: 'Waterhouse',
	birthYear: 1991,
	job: 'teacher',
	friends: ['Michael', 'Peter', 'Steven'],
	hasDriversLicense: true,

	calcAge: function () {
		console.log(this)
		return 2037 - this.birthYear;
	}
}

console.log(jonas.calcAge())
console.log(jonas.calcAge())
console.log(jonas.calcAge())
//calcAge运算3次
```

**调用属性时避免多次运算,将含方法的属性储存为新变量**

```
const jonas = {
	firstName: 'Jonas',
	lastName: 'Waterhouse',
	birthYear: 1991,
	job: 'teacher',
	friends: ['Michael', 'Peter', 'Steven'],
	hasDriversLicense: true,

	calcAge: function () {
		this.age = 2037 - this.birthYear;
		return this.age
	}
}

console.log(jonas.calcAge());
console.log(jonas.age);
console.log(jonas.age);
//calcAge仅且必须运算1次
```

### 4.challenge:

```
const jonas = {
	firstName: 'Jonas',
	lastName: 'Waterhouse',
	birthYear: 1991,
	job: 'teacher',
	friends: ['Michael', 'Peter', 'Steven'],
	hasDriversLicense: true,
	
	calcAge: function () {
		this.age = 2037 - this.birthYear;
		return this.age
	},

	getSummary: function () {
		return `${this.firstName} is a ${this.calcAge()}-year old ${this.job}, and he has ${this.hasDriversLicense ? 'a' : 'no'} driver's license.`
	}
}

console.log(jonas.getSummary())
```

1.别忘记,

2.活用三元运算符

3.调用方法而非变量,因为不能保证该方法一定被运算过

4.数组是特殊的对象,



### 5.对象实例

```

const mark = {
	fullName: 'Mark Miller',
	mass: 78,
	height: 1.69,

	calcBMI: function () {
		this.bmi = this.mass / this.height ** 2
		return this.bmi
	}
}

const john = {
	fullName: 'John Smith',
	mass: 92,
	height: 1.95,

	calcBMI: function () {
		this.bmi = this.mass / this.height ** 2
		return this.bmi
	}
}

mark.calcBMI()
john.calcBMI()
console.log(mark.bmi, john.bmi)

if (mark.bmi > john.bmi) {
	console.log(`${mark.fullName}'s bmi(${mark.bmi}) is higher than ${john.fullName}'s bmi(${john.bmi})!`)
} else if (mark.bmi < john.bmi) {
	console.log(`${john.fullName}'s bmi(${john.bmi}) is higher than ${mark.fullName}'s bmi(${mark.bmi})!`)
} else {
	console.log(`${john.fullName}'s bmi(${john.bmi}) equals ${mark.fullName}'s bmi(${mark.bmi})!`)
}
```



## 四.循环语句

### 1.for循环

```
//rep是局部变量,仅在for循环内使用
//若用var定义rep,则rep称为全局变量
//定义rep=5;判断条件;进入循环,rep+1;

for (let rep = 5; rep <= 10; rep++) {
	console.log(`Lifting weights reptition ${rep} 🏋🏻`)
}
```

### 2.array循环

```
const jonas = [
	'Jonas',
	'Waterhouse',
	2037 - 1991,
	'teacher',
	['Michael', 'Peter', 'Steven'],
	true
];

const types = [];
for (let i = 0; i < jonas.length; i++) {
	//读取jonas数组
	console.log(jonas[i], typeof jonas[i]);
	//填充types数组1
	// types[i] = typeof jonas[i];
	//填充types数组2,更易读
	types.push(typeof jonas[i]);
}
console.log(types);



const years = [1991, 2007, 1969, 2020]
const ages = []
for (let i = 0; i < years.length; i++) {
	ages.push(2037 - years[i]);
}
console.log(ages)
```

### 3.continue:符合条件的记录后继续循环

```
console.log('--- ONLY STRINGS ---')
for (let i = 0; i < jonas.length; i++) {
	if (typeof jonas[i] !== 'string') continue;

	console.log(jonas[i], typeof jonas[i]);
}
```

for循环中加上if/continue,给循环加上筛选条件,只有符合条件的可以continue,其他的不被记录

### 4.breaak:符合条件后终止循环

```
console.log('--- BREAK WITH NUMBER ---')
for (let i = 0; i < jonas.length; i++) {
	if (typeof jonas[i] === 'number') break;

	console.log(jonas[i], typeof jonas[i]);
}
```

for循环中加上if/break,给循环加上终止条件,遇到符合条件的break循环,之后的不被记录

### 5.倒着遍历数组

```
const jonas = [
	'Jonas',
	'Waterhouse',
	2037 - 1991,
	'teacher',
	['Michael', 'Peter', 'Steven'],
	true
];

for (let i = jonas.length - 1; i >= 0; i--) {
	console.log(i, jonas[i])
}
```





### 6.循环中循环

```
for (let exercise = 1; exercise < 4; exercise++) {
	console.log(`-------Starting exercise ${exercise}`);
	for (let rep = 1; rep < 6; rep++) {
		console.log(`Lifting weight repetition ${rep}🏋🏻`)
	}
}
```

### 7.while循环

```
let dice = Math.trunc(Math.random() * 6) + 1

while (dice !== 6) {
	console.log(`You rolled a ${dice}`)
	dice = Math.trunc(Math.random() * 6) + 1
	if (dice === 6) { console.log('Loop is about to end...') }
}

```

1..while循环不必依靠计数器,()中可装任何条件,也仅可装一个条件,但可以以在循环语句中插if

2..不知道要循环多少次可以用while

### 8.循环实例

```
//-----------------编码挑战4--------------------

const bills = [22, 295, 176, 440, 37, 105, 10, 1100, 86, 52]
const tips = []
const totals = []

const calcTip = function (bill) { bill >= 50 && bill <= 300 ? bill * 0.15 : bill * 0.2 }

for (let a = 0; a < bills.length; a++) {
	tips.push(calcTip(bills[a]));
	totals.push(bills[a] + tips[a]);
}
console.log(bills, tips, totals)

//计算数组内数值的平均数
const calcAverage = function (arr) {
	let a = 0
	let sum = 0
	while (a < arr.length) {
		// sum = sum + arr[a];
		sum += arr[a];
		a++
	}
	return sum / arr.length
}
console.log(calcAverage(bills), calcAverage(tips), calcAverage(totals));
```



# 03 SECTION : Develop Skills & Editor Setup



## 一.vscode配置

prettier,设置方法见[prettier官方文档](https://prettier.io/docs/en/options.html)

看不懂看jonas视频p50

## 二.安装NODE.JS&安装一个dev环境

有live serve就不装node.js了,相撞看视频p51

## 三.怎样学习编程

**错误示例:**

1.不做做笔记,不完成挑战,不能只是复制别人的代码

2.追求极致简洁高效,失去信心

3.孤立学习无交流

**正确做法:**

1.有一个目标

2.复制代码时要理解,不明白不要继续

3.强化记忆,多做练习:codewars.com

4.课程之外也要多练习

5.不要因写不出完美代码而沮丧

6.代码学习中永远会有自己不知道的新知识,不要沮丧

7.不要拿自己和顶尖人员比较

8.最好一起学习,不要孤立学习

9.光学习几门课并不能称为程序员,只能先打下基础

**程序员工作的需求**

1.开始学习信心倍增

2.自己上手逐渐迷茫

3.挑战自我不要放弃大量练习

4.真正熟练灵活运用--可以接单

5.学习新的技术并灵活应用

6.获得工作的资本

## 四.像一个开发者思考:成为问题的解决者

1.保持冷静

2.按照逻辑思考

**3.四步解决法:**

 **1.确保百分百理解需求**

 **2.拆分大需求**

 **3.遇到问题可以研究文档,可以google或stack overflow或者MDN JS文档**

 **4.在解决大问题前可以写一些伪代码(打草稿)**

## 五.使用google/stack overflow/MDN

[MDN官网](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)

实例:

```
//problem1:设计一个温度计，计算温度的升幅，并且记录下错误
const temperatures = [3, -2, -6, -1, 'error', 9, 13, 17, 15, 14, 9, 5];
//1)解题步骤：
//1.什么是温度的升幅？最高温和最低温之间的差距
//2.怎样计算最高温和最低温？
//3.传感器错误是怎样的？怎样解决?'error'.
//4.怎样忽略错误?

//2)拆分步骤
//1.忽略错误
//2.提取最大值
//3.提取最小值
//4.计算升幅,并返回

const calcTempAmplitude = function (temps) {
  let max = 0;
  let min = 0;
  for (let i = 0; i < temps.length; i++) {
    const curTemp = temps[i];
    if (typeof curTemp !== 'number') continue;
    if (curTemp > max) max = curTemp;
    if (curTemp < min) min = curTemp;
  }
  console.log(max, min);
  return max - min;
};

console.log(calcTempAmplitude(temperatures));
```

```
//problem2:
//输入两个数组
//问题解析:合并两个数组

const calcTempAmplitude = function (a, b) {
  // let c = [];
  // for (let i = 0; i < a.length; i++) c.push(a[i]);
  // for (let i = 0; i < b.length; i++) c.push(b[i]);
  let c = a.concat(b);
  console.log(c);

  let max = 0;
  let min = 0;
  for (let i = 0; i < c.length; i++) {
    const curTemp = c[i];
    if (typeof curTemp !== 'number') continue;
    if (curTemp > max) max = curTemp;
    if (curTemp < min) min = curTemp;
  }
  console.log(max, min);
  return max - min;
};

const shiyan = [-10, 20];
console.log(calcTempAmplitude(temperatures, shiyan));
```

## 六.debug(调试)

1.意识到有bug

2.找bug:console.table()

3.修bug

4.预防bug

```
const measureKelvin = function () {
  const measurement = {
    type: 'temp',
    unit: 'celsius',
//C)修复错误
    value: Number(prompt('Degrees celsius:')),
  };

//B)发现错误
  console.table(measurement);

  // console.log(measurement.value);
  // console.warn(measurement.value);
  // console.error(measurement.value);

  const kelvin = measurement.value + 273;
  return kelvin;
};
//A)意识到错误
console.log(measureKelvin());

```

在代码中插入debugger,实现断点功能,,后续内容不运行

```
//-------------------编程挑战1-----------------------
const printForecast = function (arr) {
  let sentence = `...`;
  for (let i = 0; i < arr.length; i++) {
    sentence += `${arr[i]}C in ${i + 1} days...`;
  }
  return sentence;
};
const a = [17, 21, 23];
const b = [12, 5, -5, 0, 4];
console.log(printForecast(a));
console.log(printForecast(b));

```



# 04 SECTION : HTML-CSS

## 一.html的基本结构和元素

```
//输入!,按Tab键,自动生成

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

```
<html>//html文件
  <head>//这里是标题
    <title>标题名称</title>
    <meta>格式图标等</meta>
  </head>
  <body>//这里是网页上的具体内容
    <h1></h1>//这里是网页内容的标题,从h1-6
    <p></p>//这里是段落内容
  </body>
</html>
```

完整的html有<html><head><body>

所有文件的主文件都叫index.html

## 二.属性/类class/ID

```
//元素
<a href="链接">文字</a>     //anchor对文字进行链接
<img src="链接" />          //插入图片

//用类/ID命名元素
//每个id是唯一的,每个页面只能用一次
//class可以反复使用
//多用class,少用id
<p class="first">...</p>
<img id="..." src="..."/>


```

### **命名规则**:

**a)**用-连接名字.

**b)**class可以有多个名字,不同名字用空格连接

例如: aaa class="a b-c d"   bbb class="a e-f g"

**c)**调用时.代表and:

document.querySelector('.a')调用aaa和bbb

document.querySelector('.a.d')调用aaa

document.querySelector('.a.g)调用bbb

document.querySelector('e-f')调用bbb

**d)**调用时空格表内部,[:]表示该元素的属性的值:

```
//一个 class 属性为"user-panel main"的 div 元素<div>(<div class="user-panel main">) 内包含一个 name 属性为"login"的 input 元素<input> (<input name="login"/>) ，如何选择，如下所示：

var el = document.querySelector("div.user-panel.main input[name='login']");
```



div是个通用盒子,没有实际意义,form是名叫表单的div,有语义

输入框:

```
    <form id="your-name">
      <h2>Your name here</h2>
      <p>Please fill in this form:)</p>

      <input type="text" placeholder="Your name" />
      <button>OK!</button>
    </form>
```

## 三.CSS基础style

style算一种设置,仅在head内生效,不进入body

```
<head>
  <style>                        //style在<head>内
    body{background-color:green} //声明//元素{属性:值}
  </style>                       //声明块

//或者用link,link基本只链接样式表
    <link href="style.css" rel="stylesheet" />


</head>
```

```
* {         //初始化全局空间,方便后续为每个盒子设置样式
  margin: 0;
  padding: 0;
  box-sizing: border-box;  //将盒子大小固定为盒子的边框范围
}


body{  
  background-color:green     //背景颜色
  font-family:Arial          //字体
  font-size:20px             //字体颜色            
  border:5px solid #444      //边框线:尺寸 实线 颜色
  
}

//规则

元素{属性:值}
.类{属性:值}
#ID{属性:值}

#ID h2 {属性:值}    //这个ID内的h2设置
```

## 四.CSS盒子模型的介绍

```
content:文本/图像/或者指定内容
width:宽度
height:高度     //宽+高组成content
border:边框
padding:填充/在盒子内部创造空白     //content到边框的空间
margin:盒子外

text-align:center    //文本位置
```





# 05 SECTION : DOM&EVENTS fundermentals

## 001--项目1:guess my number--

```
console.log(document.querySelector('.message').textContent);
//文档搜索"message"的类,并提取文本内容,在log上显示
```

### 一.DOM是什么/操作:document object model

dom相当于html文档的节点树,关于dom的操作和方法等不是JS的内容,JS 仅仅是ecma的方言

DOM是Web API的一部分,web api相当于一个巨大浏览器可以实现的巨大的库,可以看作是js写的(但并不是),JS可以在代码中进行访问并自动使用



document->html->1.head

​                                  2.body

### 二.选择和操作元素

```
document.querySelector('.message').textContent = '🎉 Correct Number!';

document.querySelector('.number').textContent = 13;
document.querySelector('.score').textContent = 10;
document.querySelector('.guess').value = 23;
console.log(document.querySelector('.guess').value);

//document.querySelector('.类名').textContent
```



### 三.点击事件(鼠标)

```
document.querySelector('.check').addEventListener('click', function () {
  let guess = Number(document.querySelector('.guess').value);
  console.log(guess, typeof guess);

  if (!guess) {
    document.querySelector('.message').textContent = '😅 No Number!';
  } 
});

//对check类添加监听事件:点击,进行funtion
//ps:0是false
```

### 四.实现游戏逻辑

```
//math.trunc()去除小数
//math.random()在0-1取值,开区间

let secretNumber = Math.trunc(Math.random() * 20) + 1;
let score = 20;
document.querySelector('.number').textContent = secretNumber;

document.querySelector('.check').addEventListener('click', function () {
  let guess = Number(document.querySelector('.guess').value);
  console.log(guess, typeof guess);

  if (!guess) {
    document.querySelector('.message').textContent = '😅 No Number !';
  } else if (guess === secretNumber) {
    document.querySelector('.message').textContent = '🎉 Correct Number !';
  } else if (guess > secretNumber) {
    if (score > 1) {
      document.querySelector('.message').textContent = '😭 Too High !';
      score--;
      document.querySelector('.score').textContent = score;
    } else {
      document.querySelector('.message').textContent = '💥 You Lose The Game !';
      document.querySelector('.score').textContent = 0;
    }
  } else if (guess < secretNumber) {
    if (score > 1) {
      document.querySelector('.message').textContent = '😭 Too Low !';
      score--;
      document.querySelector('.score').textContent = score;
    } else {
      document.querySelector('.message').textContent = '💥 You Lose The Game !';
      document.querySelector('.score').textContent = 0;
    }
  }
});
```

### 五.CSS Style操作

```
//body前不用加.
// 改css用.style
//css的-命名改为驼峰命名法

 document.querySelector('body').style.backgroundColor = '#60b347';
document.querySelector('.number').style.width = '30rem';
```

### 六.again功能:代码挑战

```
//again功能:初始化功能,手动修正
document.querySelector('.again').addEventListener('click', function () {
  secretNumber = Math.trunc(Math.random() * 20) + 1;
  score = 20;
  document.querySelector('.guess').value = '';
  document.querySelector('.score').textContent = score;
  document.querySelector('.number').textContent = `?`;
  document.querySelector('.number').style.width = '15rem';
  document.querySelector('.message').textContent = 'Start guessing...';
  document.querySelector('body').style.backgroundColor = '#222';
});
```

### 七.最高分操作

```
let highScore = 0;

if (score > highScore) {
  highScore=score;       document.querySelector('.highscore').textContent=highScore;
    }
```

### 八.重构代码

```
//不重复原则

    //猜错了
    else if (guess !== secretNumber) {
      if (score > 1) {
        document.querySelector('.message').textContent =
          guess > secretNumber ? '😭 Too High !' : '😭 Too Low !';
        score--;
        document.querySelector('.score').textContent = score;
      } else {
        document.querySelector('.message').textContent =
          '💥 You Lose The Game !';
        document.querySelector('.score').textContent = 0;
      }
    }


//将复杂代码写作function调用
```

## 002--项目2:Modal Window--

### 0001)Modal Window

```
//querySelectorAll可以提取所有含相同名字的类,并按顺序返回一个nodelist
const btnsOpenModal = document.querySelectorAll('.show-modal');
console.log(btnsOpenModal);

//qsa返回的nodelist具有和数组相同的功能
for (let i = 0; i < btnsOpenModal.length; i++)
  console.log(btnsOpenModal[i].textContent);
```



### 0002)classes操作

```
const modal = document.querySelector('.modal');
const overlay = document.querySelector('.overlay');
const btnCloseModal = document.querySelector('.close-modal');
const btnsOpenModal = document.querySelectorAll('.show-modal');
//点击关闭弹窗
const closeModal = function () {
  modal.classList.add('hidden');
  overlay.classList.add('hidden');
};
//点击出现弹窗
const showModal = function () {
  console.log('Button clicked !');
  modal.classList.remove('hidden');
  overlay.classList.remove('hidden');
};

for (let i = 0; i < btnsOpenModal.length; i++)
  btnsOpenModal[i].addEventListener('click', showModal);

btnCloseModal.addEventListener('click', closeModal);
overlay.addEventListener('click', closeModal);
```

==//若要实现click事件后调用函数,监听事件中应传递函数本身,即不带()==

//**==classlist==**:

aaa.classlist.add

aaa.classlist.remove

//添加监听事件时,函数不带(),仅传递函数本身,若带(),则传递函数的返回值(如果有),但函数在closeModal前已被调用,该返回值不是我们需要的.

### 0003)按键事件

```
document.addEventListener('keydown', function (e) {
  console.log(e.key);
  if (e.key === 'Escape' && !modal.classList.contains('hidden')) closeModal();
});
```

esc对全局起作用,所以对document起作用

善用classlist,例:classlist.contains

## 003--项目3:Pig Game

### 0001)获取id

```
const score1EL = document.getElementById('score--1');

//比querySelector快速,不用加#
```

### 0002)骰子系统

```
const current0EL = document.querySelector('#current--0');
const current1EL = document.querySelector('#current--1');

//设定当前回合分数,不能再函数里,否则会被不停定义
let currentScore = 0;

//骰子功能
btnRoll.addEventListener('click', function () {
  if (playing) {
    //1.生成随机骰子
    const dice = Math.trunc(Math.random() * 6) + 1;
    console.log(dice);
    //2.展示骰子
    diceEL.classList.remove('hidden');
    diceEL.src = `dice-${dice}.png`;
    //3.骰子=1?换人:加到current score
    if (dice !== 1) {
      //把dice加到current上
      currentScore += dice;
      document.getElementById(`current--${activePlayer}`).textContent =
        currentScore;
    } else {
      //换人
      switchPlayer();
    }
  }
});
```

### 0003)换人系统

```
const player0EL = document.querySelector('.player--0');
const player1EL = document.querySelector('.player--1');
let activePlayer = 0

//换人功能
const switchPlayer = function () {
  currentScore = 0;
  document.getElementById(`current--${activePlayer}`).textContent = 0;
  activePlayer = activePlayer === 0 ? 1 : 0;
  player0EL.classList.toggle('player--active');
  player1EL.classList.toggle('player--active');
};
```

### 0004)保存分数系统

```
//加分功能
btnHold.addEventListener('click', function () {
  if (playing) {
    //1)把当前玩家的current加到score
    scores[activePlayer] += currentScore;
    document.getElementById(`score--${activePlayer}`).textContent =
      scores[activePlayer];
    //2)check if score>=100
    if (scores[activePlayer] >= 20) {
      //3)finish the game
      playing = false;
      document
        .querySelector(`.player--${activePlayer}`)
        .classList.add('player--winner');
      document
        .querySelector(`.player--${activePlayer}`)
        .classList.remove('player--active');
      diceEL.classList.add('hidden');
    } else {
      //4)switch player
      switchPlayer();
    }
  }
});

```



### 0005)重置游戏

```
//游戏开始前定义变量
let scores,currentScore,activePlayer,playing

//开始条件
const init = function () {
  player0EL.classList.remove('player--winner');
  player1EL.classList.remove('player--winner');
  player0EL.classList.remove('player--active');
  player0EL.classList.add('player--active');
  player1EL.classList.remove('player--active');
  diceEL.classList.remove('hidden');
  diceEL.classList.add('hidden');

  score0EL.textContent = 0;
  score1EL.textContent = 0;
  current0EL.textContent = 0;
  current1EL.textContent = 0;

  scores = [0, 0];
  currentScore = 0;
  activePlayer = 0;
  playing = true;
};
init();

//重开功能
btnNew.addEventListener('click', init);
```

函数内部定义的变量只能作用域函数内,是**局部变量**



# 06 SECTION : JS工作原理

## 一.高度概括

高级/面向对象/基于原型的/多范式编程语言

### 1)高级

### 2)垃圾收集

随时清除无用信息

### 3)解释型/即时编译

人类语言<->机器语言

### 4)多范式

三种范式:(三种都有)

​	程序化的

​	面向对象的

​	函数式编程

两种范式:

​	命令式

​	声明式

### 5)基于原型&面向对象

js中除了原始值,都是对象,例如数组继承自一个巨大的原型

### 6)具有一流功能

函数可以被视作变量传递给其他函数,甚至可以从函数中返回函数->可以函数式编程

### 7)动态语言

变量定义不需要类型,且后续可变

### 8)单线程



### 9)非阻塞事件循环并发模型

并发模型:同时处理多个任务

JS本身是在单线程中,但有任务需要同时进行,把阻塞事件放入循环中,完成后放入主线程,形成**非阻塞事件循环并发模型**



## 二.JS引擎&runtime

**即时编译**:同时编译和解释(过去被认为是解释语言),一般情况source code需要编译成文件再解释给机器,即时编译可以省去文件的步骤,编译后直接解释,并且进行**优化**



JS可以存在与浏览器之外,但不能用**Web API**,因为提供Web API的是浏览器,Web API是dom的一部分,不属于JS.相反,JS有多个C++绑定,和一个所谓的线程池



调用栈/heap + web API + 回调函数(事情发生后的第一件事,例如点击) :

事情发生后的第一件事,例如点击(**回调函数**,进入回调队列)

若**栈**是空的,放入堆栈处理(通过事件循环进行)

## 三.执行内容&调用堆栈

1编译后的代码(01)

-->2唯一的全局执行上下文(顶级代码)(函数除外)

​	1)**执行上下文**:类似于一个环境,JS在其中执行,储存所有必要的待执行的信息,例如传给函数的参数

​	2)执行上下文里有什么:

​	1.))**变量环境**:**变量**和**函数**的声明(let/const/var/function)+一个特殊的**参数**对象(包含所有传递进入执行上下文的函数的参数)

​	2.))==**区块链**:==函数产生的区块链,函数可以在内部定义变量并进行访问

​	3.))**关键字**(this keyword):发生在执行前

​	4.))tips:**箭头函数**无参数和关键字,相反可以从最近的常规函数母级使用参数对象和this关键字

-->3执行顶级代码:计算机处理收到的机器码



```
const name = 'Jonas';

const first = () => {
  let a = 1;
  const b = second(7, 9);
  a = a + b;
  return a;
};

function second(x, y) {
  var c = 2;
  return c;
}

const x = first();
```

```
//先Global
name = 'Jonas'
first = <function>
first = <function>
x =<unknow>

//然后first
a=1
b=<unknow>

//最后second
c=2
arguments=[7,9]
```



-->4函数被执行,并等待调用

  1)调用堆栈:执行上下文的地方,栈顶的代码是正在运行的,调用完成后将从堆栈删除,执行并返回到上一个执行上下文(单线程一次只能处理一个)

  global->first->second->(删除se



cond)first->(删除first)global->删除global

  2)存放堆栈

-->5事件循环提供回调函数,调用函数



## 四.区块&区块链

1.==全局作用域==

​	在任何函数和区块外

​	此处声明的变量任何地方可调用

2==.函数作用域==

​	局部作用域

​	变量仅在函数内部起效

3==.块作用域==

​	局部作用域

​	变量仅在区块内部起效,区块表示{}的内容,例如if,for

​	==只适用**let/const**声明的变量(**var**创造全局变量)==

​	ES6开始,所有function作用域都是block作用域

4.区块链中,子区块链可以访问所有的母区块链

5**.只有函数声明的位置影响作用域链,调用函数的位置不影响,**例:



```
//词法作用域

function second(){
  c=0
third()
}

function third(){
  d=2
  console.log(c+d)
}

//因为second和third的母区块都是全局区块,不在同一条区块链上,所以third读取不到变量c,即使third被second调用,作用域链也不受影响:调用函数的位置不影响作用域链
```



## 五.变量环境:提升&TDZ

TDZ(时空死区,被定义前不能使用)

```
if (myname==='Jonas'){
//------以下内容是job变量的TDZ(时空死区)
//所以下列第一行代码将报错
  console.log(`Jonas is a ${job}`)
  const age=2037-1989
  console.log(age)
//-----------------------
  const job='teacher'
//x未定义
  console.log(x)
}
```

函数声明可以随意调用

函数表达式/箭头函数被定义前不能调用

|                         | 提升                         | 初始值            | 作用域/区块链 |
| ----------------------- | ---------------------------- | ----------------- | ------------- |
| var                     | 可以                         | undefined         | function      |
| const/let               | 不                           | <uninitiated>,TDZ | block         |
| function声明            | 可以                         | 实际函数          | block         |
| function表达式/箭头函数 | 取决于用var还是const/let定义 |                   |               |

**提升**存在的原因:1)使函数在实际声明前可被调用2)var是时代的眼泪

```
console.log(addDecl(2, 3));
//addExpr被var提升为undefined,undefined(2,3)不是函数所以错误
console.log(addExpr(2, 3));
//addExpr被var提升为undefined,能够读取
console.log(addExpr);
//addArrow是const的uninitiated,所以错误
console.log(addArrow(2, 3));

function addDecl(a, b) {
  return a + b;
}

var addExpr = function (a, b) {
  return a + b;
};

const addArrow = (a, b) => a + b;

//var 将在全局窗口(window)创建一个x的变量
var x = 1;
let y = 2;
const z = 3;

```



## ==六.this 关键字==

**1.非静态**,取决于函数的调用

**2.this 不会指向函数本身,也不会指向它的变量环境,只会指向调用函数的对象**



|                          | this=                                         | 备注                                                     |
| ------------------------ | --------------------------------------------- | -------------------------------------------------------- |
| 方法(附加到对象的函数)   | **调用**该方法的对象(不是声明)                |                                                          |
| 简单的函数调用/变量****  | **undefined**                                 | 只对**严格模式**生效,否则指向global scope的对象,即window |
| 箭头函数(无论是不是方法) | **没有自己的this关键字**,会指向母作用域的对象 |                                                          |
| Event Listener           | 处理程序函数所附加的DOM Element(**元素)**     |                                                          |
| new/call/apply/bind      |                                               |                                                          |

```
//this本身在全局变量,指向window
console.log(this);

//简单函数,this指向undefined,如果不是严格模式,也会指向window
const calcAge = function (birthYear) {
  console.log(2037 - birthYear);
  console.log(this);
};
calcAge(1991);

//简单箭头函数没有this,this指向本身的母作用域,此种情况即window
const calcAgeArrow = birthYear => {
  console.log(2037 - birthYear);
  console.log(this);
};
calcAgeArrow(1980);

//方法,this指向调用方法的对象,即jonas
const jonas = {
  year: 1991,
  calcAge: function (birthYear) {
    console.log(this);
    console.log(2037 - this.year);
  },
};
jonas.calcAge();

//方法借用,this指向了matilda
const matilda = {
  year: 2017,
};
matilda.calcAge = jonas.calcAge;
matilda.calcAge();

//f()只是一个变量,this没有附着到object上,变为默认绑定关系,strict模式下是undefined,然后读取不到undefined的year,会导致error
//与简单的函数调用有微妙区别,简单函数调用只有undefined
const f = jonas.calcAge;
f();

```





## ==七.常规函数VS箭头函数==

1.==**简单函数/变量**的this=**undefined**,其属性不存在会**error**==

==**箭头函数**的this=母作用域的对象=**window**,其属性不存在会**undefined**==

**==2.箭头函数不要当方法用,但可以在方法内用!也不要使用var!!!!!!!!!!==**(方法内的箭头函数的this将指向方法的对象)

==3.方法仅限**函数表达式**用,可以避免许多问题!==

```
//箭头函数不是方法,没有自己的this关键字,会指向自己(greet)的母作用域(全局区块)的对象(window)
//jonas是对象,不是代码块,没有形成作用域,其属性不是被围在作用域内,只是一种字面定义对象的方式,所以greet仍在全局作用域内
//window没有firstName的属性,所以是undefined,如果用var声明变量会在window创建属性,输出结果不会是undefined,会彻底混乱
const jonas = {
  firstName: 'Jonas',
  year: 1991,
  //calcAge附着在对象jonas上,是方法
  calcAge: function (birthYear) {
    console.log(this);
    console.log(2037 - this.year);

    // //解决方案1(旧版):
    // //this此时还是jonas,将其赋值给self/that
    // //=是赋值,不是直接等于self
    // const self = this;
    // //isMillennial不是方法,没有附着在对象上,是函数,
    // const isMillenial = function () {
    //   console.log(self);
    //   //如果使用&,true返回1,false返回0
    //   console.log(self.year >= 1981 && self.year <= 1996);
    //   // console.log((this.year >= 1981) & (this.year <= 1996));
    // };

    //解决方案2:
    //方法内使用箭头函数,将this指向方法的对象
    const isMillenial = () => {
      console.log(this);
      console.log(this.year >= 1981 && this.year <= 1996);
    };

    // 这只是一个简单函数的调用,不是方法,this=undefined,没有year属性,会报错
    isMillenial();
  },

  greet: function () {
    console.log(`Hey ${this.firstName}`);
  },
};
jonas.greet();
jonas.calcAge();
```



## 八.arguments(参数)关键字

**参数只存在于常规函数中**

```
//argument(参数)关键字
const addExpr = function (a, b) {
  console.log(arguments);
  return a + b;
};
//可以传入很多参数,除了a,b其他都可以存在,只是未命名罢了
addExpr(2, 5);
addExpr(2, 5, 8, 12);

var addArrow = (a, b) => {
	//参数只存在于常规函数中,所以此处页面会报错
  console.log(arguments);
  return a + b;
};
addArrow(2, 5);

```



## 九.原始类型VS对象

const声明的变量不可变仅限于原始值,对象可以变来变去

**==const不变的是栈中的value==**

堆中value改变与const/let无关

![71744277753](C:\Users\86153\AppData\Local\Temp\1717442777530.png)

==三大问题,日后讨论:==

1.原型继承:面向对象编程

2.事件循环:异步JS

3.DOM的工作原理



**object.assign({},本体)**

```
//原始值
let lastName = 'Williams';
let oldLastName = lastName;
lastName = 'Davis';
console.log(lastName, oldLastName);

//对象
const jessica = {
  firstName: 'Jessica',
  lastName: 'Williams',
  age: 27,
};

const marriedJessica = jessica;
marriedJessica.lastName = 'Davis';
console.log('Before marriage:', jessica);
console.log('After marriage:', marriedJessica);

//marriedJessica={}

//复制对象
const jessica2 = {
  firstName: 'Jessica',
  lastName: 'Williams',
  age: 27,
  family: ['Alice', 'Bob'],
};
//改变复制体的lastName
const jessicaCopy = Object.assign({}, jessica2);
jessicaCopy.lastName = 'Davis';
//object.assign只能浅拷贝,复制第一层改变,深度嵌套内容无法复制,改动会影响到原型
jessicaCopy.family.push('Mary');
jessicaCopy.family.push('John');

console.log('Before marriage:', jessica2);
console.log('After marriage:', jessicaCopy);
```





# 07 SECTION : 数据结构&现代操作&字符串



## 一.数组解构



```
//空格表示跳过该值
let [main, , secondery] = restaurant.categories;
console.log(main, secondery);
```

```
const restaurant = {
  name: 'Classico Italiano',
  location: 'Via Angelo Tavanti 23, Firenze, Italy',
  categories: ['Italian', 'Pizzeria', 'Vegetarian', 'Organic'],
  starterMenu: ['Focaccia', 'Bruschetta', 'Garlic Bread', 'Caprese Salad'],
  mainMenu: ['Pizza', 'Pasta', 'Risotto'],

  order: function (starterIndex, mainIndex) {
    return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];
  },
```



```
//交换值2
[main, secondery] = [secondery, main];
console.log(main, secondery);

//接收一个函数的两个返回值
const [starter, mainCourse] = restaurant.order(2, 0);
console.log(starter, mainCourse);

//nested解构
const nested = [2, 4, [5, 6]];
// const [i, , j] = nested;
const [i, , [j, k]] = nested;
console.log(i, j, k);

//默认值
const [p = 1, q = 1, r = 1] = [8, 9];
console.log(p, q, r);

```



## 二.对象解构

```
const restaurant = {
  name: 'Classico Italiano',
  location: 'Via Angelo Tavanti 23, Firenze, Italy',
  categories: ['Italian', 'Pizzeria', 'Vegetarian', 'Organic'],
  starterMenu: ['Focaccia', 'Bruschetta', 'Garlic Bread', 'Caprese Salad'],
  mainMenu: ['Pizza', 'Pasta', 'Risotto'],

  openingHours: {
    thu: {
      open: 12,
      close: 22,
    },
    fri: {
      open: 11,
      close: 23,
    },
    sat: {
      open: 0, // Open 24 hours
      close: 24,
    },
  },

  order: function (starterIndex, mainIndex) {
    return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];
  },

  orderDelivery: function ({
    starterIndex = 1,
    mainIndex = 1,
    time = '20:00',
    address,
  }) {
    console.log(
      `Order recieved! ${this.starterMenu[starterIndex]} and ${this.mainMenu[mainIndex]} will be delivered to ${address} at ${time}.`
    );
  },
};

restaurant.orderDelivery({
  time: '22:30',
  address: 'Via del Sola, 21',
  mainIndex: 2,
  starterIndex: 2,
});

restaurant.orderDelivery({
  address: 'Via del Sola, 21',
  starterIndex: 1,
});
//对象解构

const { name, openingHours, categories } = restaurant;
console.log(name, openingHours, categories);
//属性改名
const {
  name: restaurantName,
  openingHours: hours,
  categories: tags,
} = restaurant;
console.log(restaurantName, hours, tags);

//默认值
const { menu = [], starterMenu: starters = [] } = restaurant;
console.log(menu, starters);

//变异变量
let a = 111;
let b = 999;
const obj = { a: 23, b: 7, c: 14 };
({ a, b } = obj);
console.log(a, b);
//对象解构

const {
  fri: { open, close },
} = openingHours;
console.log(open, close);
```

## 三.spread运算符









# 08 SECTION :

# 09 SECTION :数字(NumBers)/日期(Dates)/计时器(Timers)



# 10 SECTION :

# 11 SECTION :

# 12 SECTION :

# 13 SECTION :

# 14 SECTION :

# 15 SECTION :

# 16 SECTION :

# 17 SECTION :现代JS程序应用



# *语法



### 1.console.log():控制台显示

```
console.log(参数)               
//在控制台(console)显示日志(log)
```

















































