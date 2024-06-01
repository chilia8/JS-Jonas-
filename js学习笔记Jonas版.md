# SECTION 1: JS Fundamentals - Part 1

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



# SECTION 2: JS Fundamentals - Part 2

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
const newLength = friends.push('Jay')
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



# SECTION 3:Develop Skills & Editor Setup



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































## 三.数字(Numers)/日期(Dates)/计时器(Timers)

## 四.进阶Dom

## 五.面向对象 JS

## 六.丰富项目

## 七.异步 JS

## 八.现代JS程序应用

## 九.部署&Git

## *语法

```
console.log(参数)               //在控制台(console)显示日志(log)
```























































