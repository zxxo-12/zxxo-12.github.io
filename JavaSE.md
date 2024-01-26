

# JavaSE笔记

## 	1.java的注释

1. 单行注释：

   ```java
   //双斜线表示单行注释
   ```

2. 多行注释：以／＊开头，以＊／结束即可，中间的＊可有可无

   ```java
   /*
   *多行注释
   *多行注释
   */
   ```

3. 文档注释：以／＊开头，以＊／结束即可，中间的＊可有可无

   ```java
   /**
   *文档注释
   @ author 作者
   @ date 日期
   */
   ```

## 2.包的概念

* Java 开发中，我们使用包来对代码进行分类处理，包实际上就是文件夹。在同个包内 Java 文件可以直接相互引用，不在同个包内的则需要导包。

  导包快捷键Alt+?并且选择到java.util项目

  > 特殊的：Java.lang这个包内的所有类无需导包，直接使用
  >
  > 常用`String``System`

* 包名的命名规范：一般使用公司域名倒写的方式，包名中的每个．都是一个独立的文件夹

  * 百度的官网是www.baidu.com，那么百度的项目的包就会设置为 `com.baidu.www` 。
  * 百度地图的官网是`map.baidu.com`，包设置为 `com.baidu.map`。
  * 百度贴吧`tieba.baidu.com`，包设置为 `com.baidu.tieba `。

## 3.变量命名规范

1. ​	变量由英文大小写、数字、下划线、和美元符组成。
2. 变量首字母不是数字。
3. 变量命名不能与java关键字相同

## 4.变量名推荐使用

* 使用驼峰命名法（首单词首字母小写，后续单词首字母大写）例getInfoByCarId
* 变量中数字要求在末尾
* 常量变量要求全部大写，多单词组合成要求用 _ 隔开
* 必须使用关键字表示变量，前面加_
* 布尔型禁止使用is开头

## 5.Java的数据类型

### 5.1基本数据类型（首字母小写）

|  数据类型   | 含义                    | 范围                   | 默认值 |
| :---------: | ----------------------- | ---------------------- | ------ |
|    short    | 短整型                  | -32768~32767           | 0      |
|   **int**   | 整型（默认）            | -2147483648~2147483648 | 0      |
|    long     | 长整型                  | -2^63~2^63-1           | 0      |
|    float    | 单精度浮点型            | -3.403E38~3.403E38     | 0.0    |
| **double**  | 双精度浮点型（默认）    | -1.798E308~1.798E308   | 0.0    |
|    byte     | 字节型                  | -128~127               | 0      |
|    char     | 字符型                  | 只表示一个字符         | ''     |
| **boolean** | 布尔型（只有ture,false) | 只有ture,false两个值   | false  |

自动类型转换：小到大

byte->short->int->long->float->double

char->int->long->float->double

手机号，学号，身份证号使用类型为：String

### 5.2引用数据类型

* Java中引用数据类型无数个，默认值**null**
* 常用的内置引用数据类型
  * `string`字符串
  * `scanner`输入控制类(需要**导包**)使用的类和当前类不在同一包内
* **首字母基本大写** ，但不强制

## 6.输出语句

* `System.out.println`表示整行输出，默认占据一行，且可以输出空内容
* `System.out.print`表示内容输出，多次输出内容合并在一行，且不可以输出空内容
* 在字符串的内容中，用\n,\t表示换行符和制表符。需要显示\n,\t时，使用\转义符进行转义。转义符只转义\后第一个字符。

## 7.数据类型转换

> 在Java中关于数值类型，还存在一个Number类，属于所有数值的父类

* 范围大的转向范围小的，强制转换，丢失精度
* 范围小到范围大，直接转换(自动转)

## 8.表达式和运算符

Java开发中最小单位是类，类中最小单位是运算符

### 8.1算术运算符(+-*/%)

1. 加号两边一边是字符串，结果一定是字符串
   加号两边有字符串的拼接则表示字符串拼接符

* `System.out.println(num1+"+"+num2+"="+(num1+num2));`num1+ ，num2+  string类型 "=" 后面才是最终运算结果前面""中的加减只是作为标识，前面num1未加""原因：num1不是字符串，是所要输出的数字

* **算术运算符号中左右两边类型相同，则结果一定为该类型**
* **算术运算符号中左右两边类型不相同，则结果一定为范围更大的那个类型**

### 8.2一元运算符++和--

* **++在前表示先计算后执行其他操作**

* **++在后表示先执行其他操作后计算结果**

```java
int num3 =10;
int num4 =num3++;//num4=10，num3=11
int num5 =++num3;//num5=12,num3=12
System.out.println(num4);//10
System.out.println(num5);//12
System.out.println(num3++);//12
System.out.println(++num3);//14
```

### 8.3比较运算符

| 运算符 | 运算规则 |
| ------ | -------- |
| `==`   | 等于     |
| `!=`   | 不等于   |
| `<`    | 小于     |
| `>`    | 大于     |
| `<=`   | 小于等于 |
| `>=`   | 大于等于 |

### 8.4逻辑运算符

| 运算符 | 运算规则 | 方法                                                         |
| ------ | -------- | ------------------------------------------------------------ |
| &      | 与       | 左右两边都为ture,结果为ture                                  |
| \|     | 或       | 左右两边都为flase,结果为flase                                |
| ^      | 异或     | 左右两边结果必须相反,结果为ture                              |
| !      | 非       | 取反                                                         |
| &&     | 短路与   | 左右两边都为ture,结果为ture，若左边为flase,右边则不会继续执行 |
| \|\|   | 短路或   | 左右两边都为false,结果为flase，若左边为ture,右边则不会继续执行 |

### 8.5位运算(只作用于整数运算)

| 运算符 | 运算规则   | 方法                                          |
| ------ | ---------- | --------------------------------------------- |
| &      | 位与运算   | 左右两边都为1,结果为1，反之为0                |
| \|     | 位或运算   | 左右两边都为0,结果为0，反之为1                |
| ^      | 位异或运算 | 左右两边不一致,结果为1，反之为0               |
| ~      | 位非运算   | 取反                                          |
| <<     | 左移运算   | 向左移指定位置，左边溢出，右边补0，符号位不变 |
| `>>`   | 右移运算   | 向右移指定位置，右边溢出，左边补符号位的值    |
| `>>>`  | 无符号右移 | 向右移指定位置，右边溢出，左边补0             |

十进制整数->二进制表示->原码->反码->补码

正数的原码，反码，补码一致

负数反码：除符号位全部取反

负数补码：除符号位全部取反末位加一

**运算时逢负取补，结果是逢负取原**

`任何整数和1进行&位运算，结果为1则是奇数，否则为偶数`

`任何值和本身进行异或操作，结果都是0`

`任何值和0进行异或操作，结果都是自身`

`异或操作符合交换律：a^b=b^a`

### 8.6注意事项

java.lang.NullPointerException:空指针异常 

所以尽量使用不为Null的对象调用方法，若必须使用则

``` java
Scanner scanner =new Scanner (System.in);
System.out.println("请输入字母a:");
String str =null;
System.out.println("a".equals(str));
```

用后面这种形式

out不是蓝色则少大括号了

## 9.条件语句

### 9.1if 语句

```java
	 /* if-else-if-else
	 * 在java的语法习惯中，开始的大括号{}一般都和代码放在一行
	 * 结束的大括号单独一行*/
```
```java
	/*
	 * 三元运算符
	 * 表达式？true:false
	 */
```
交换变量的常见两个方法

```java
		//临时变量法
		//int temp=a;
		//a=b;
		//b=temp;
		//异或运算
		a=a^b;
		b=b^a;
		a=a^b;
```
### 9.2 Switch语句

```java
	 /*
     * 在jdk1.8之前的版本中，Switch中的变量类型，只允许使用基本数据类型
     * 在jdk1.8中新增了Switch对string类型的支持
     *switch(变量){
	 * case1 值1:
	 * 		break;
	 * case2 值2:
	 * 		break;
	 * case3 值:
	 * 		break;
	 * default:
	 * 		break;
	 */
```
事例

```java
	Scanner scanner=new Scanner(System.in);
	System.out.println("请输入1-7");
	String str="";
	int week=scanner.nextInt();
	switch(week){
		case 1:
			str="周一";
			break;
		case 2:
			str="周二";
			break;
		case 3:
			str="周三";
			break;
		case 4:
			str="周四";
			break;
		case 5:
			str="周五";
			break;
		case 6:
		case 7:
			str="周末";
			default:
			str="内容有误";
			break;
	}
	System.out.println(str);
```
## 10.循环语句

Java中的循环的必要条件:循环次数（循环如何结束）

### 10.1while循环：只要表达式为ture，结果一直运行

​		 while(表达式){
​		  //循环体
​		 }

### 10.2do-while循环：先执行一次操作，再判断条件

​		do{
​		 //循环体
​		}while(表达式)

### 10.3for循环：针对确定次数的循环使用的。是while循环的简化版

for(1计数器;2循环条件;3计数器自增){

//4循环体

}

执行顺序：首次执行：1234				后续执行：234

## 11.快捷键

在错误处使用Ctrl+1可以快速已知错误在哪方面并提供修改选项

导包scanner快捷键Alt+?并且选择到java.util项目

Ctrl+E快速删除/Ctrl+

Ctrl+/	注释当前行,再按则取消注释



| 快捷键           | 描述                                                         |
| ---------------- | ------------------------------------------------------------ |
| Ctrl+1           | 快速修复(最经典的快捷键,就不用多说了)                        |
| Ctrl+D           | 删除当前行                                                   |
| Ctrl+Alt+↓       | 复制当前行到下一行(复制增加)                                 |
| Ctrl+Alt+↑       | 复制当前行到上一行(复制增加)                                 |
| Alt+↓            | 当前行和下面一行交互位置(特别实用,可以省去先剪切,再粘贴了)   |
| Alt+↑            | 当前行和上面一行交互位置(同上)                               |
| Alt+←            | 前一个编辑的页面                                             |
| Alt+→            | 下一个编辑的页面(当然是针对上面那条来说了)                   |
| Alt+Enter        | 显示当前选择资源(工程,or 文件 or文件)的属性                  |
| Alt+/            | 补全当前所输入代码                                           |
| Shift+Enter      | 在当前行的下一行插入空行(这时鼠标可以在当前行的任一位置,不一定是最后) |
| Shift+Ctrl+Enter | 在当前行插入空行(原理同上条)                                 |
| Ctrl+Q           | 定位到最后编辑的地方                                         |
| Ctrl+L           | 定位在某行 (对于程序超过100的人就有福音了)                   |
| Ctrl+M           | 最大化当前的Edit或View (再按则反之)                          |
| Ctrl+O           | 快速显示 OutLine                                             |
| Ctrl+T           | 快速显示当前类的继承结构                                     |
| Ctrl+W           | 关闭当前Editer                                               |
| Ctrl+K           | 参照选中的Word快速定位到下一个                               |
| Ctrl+E           | 快速显示当前Editer的下拉列表(如果当前页面没有显示的用黑体表示) |
| Ctrl+/(小键盘)   | 折叠当前类中的所有代码                                       |
| Ctrl+×(小键盘)   | 展开当前类中的所有代码                                       |
| Ctrl+Space       | 代码助手完成一些代码的插入(但一般和输入法有冲突,可以修改输入法的热键,也可以暂用Alt+/来代替) |
| Ctrl+Shift+E     | 显示管理当前打开的所有的View的管理器(可以选择关闭,激活等操作) |
| Ctrl+J           | 正向增量查找(按下Ctrl+J后,你所输入的每个字母编辑器都提供快速匹配定位到某个单词,如果没有,则在stutes line中显示没有找到了,查一个单词时,特别实用,这个功能Idea两年前就有了) |
| Ctrl+Shift+J     | 反向增量查找(和上条相同,只不过是从后往前查)                  |
| Ctrl+Shift+F4    | 关闭所有打开的Editer                                         |
| Ctrl+Shift+X     | 把当前选中的文本全部变为大写                                 |
| Ctrl+Shift+Y     | 把当前选中的文本全部变为小写                                 |
| Ctrl+Shift+F     | 格式化当前代码                                               |
| Ctrl+Shift+P     | 定位到对于的匹配符(譬如{}) (从前面定位后面时,光标要在匹配符里面,后面到前面,则反之) |

下面的快捷键是重构里面常用的,本人就自己喜欢且常用的整理一下(注:一般重构的快捷键都是Alt+Shift开头的了)

快捷键	描述
Alt+Shift+R	重命名 (是我自己最爱用的一个了,尤其是变量和类的Rename,比手工方法能节省很多劳动力)
Alt+Shift+M	抽取方法 (这是重构里面最常用的方法之一了,尤其是对一大堆泥团代码有用)
Alt+Shift+C	修改函数结构(比较实用,有N个函数调用了这个方法,修改一次搞定)
Alt+Shift+L	抽取本地变量( 可以直接把一些魔法数字和字符串抽取成一个变量,尤其是多处调用的时候)
Alt+Shift+F	把Class中的local变量变为field变量 (比较实用的功能)
Alt+Shift+I	合并变量(可能这样说有点不妥Inline)
Alt+Shift+V	移动函数和变量(不怎么常用)
Alt+Shift+Z	重构的后悔药(Undo)

## 12.数组

概念：存储一组数据的数据格式

java的数组长度是固定的，声明或初始化后，不得更改！

### 12.1数据类型

* 数据类型	[] 数组名=new 数据类型[数组长度]；//声明数组
  * 初始化数组时，数组内有多少内容，长度就是多少
* 数据类型	[] 数组名=new 数据类型{内容1，内容2，内容3}；//声明即初始化数组
  * 数据类型	[] 数组名=new 数据类型{内容1，内容2，内容3}；
* 数据类型	[] 数组名=new 数据类型[数组长度]；//上述的三种声明数组的方式中，[]写在数组名后依然正确
* 数组通过下标的形式进行操作，下标是从0开始的自然数，下标的最大值一定是长度-1
* 获取数组值：数组名[下标]
* 数组赋值：数组名[下标]=数组类型的值
* 获取数组长度使用length属性
* 当下标志不合法时报错（数组/下标越界） java.lang.ArraryIndexOutOfBoundException

### 12.2二维数组

二维数组：数组中的每一项的值也都是一个数组

声明二维数组时，第二个中括号就是长度

在声明数组时就给长度赋值，那么这个二维数组的内部数组长度就被固定了，并且是每一项都被固定了

# 12.3冒泡排序	*精

重点须背

```java 
for(int i=0;i<arr.length-1;i++){//控制比较次数
			for(int j=0;j<arr.length-1-i;j++) {
				if(arr[j]>arr[j+1]) {
					int temp=arr[j];
					arr[j]=arr[j+1];
					arr[j+1]=temp;
				}
			}
			
		}
```

冒泡排序
每次比较都会找到最大值或最小追放到末尾或开头的位置，因此后续每次比较都可以比上次少比较一次
第一次比较l-1次
第二次比较l-1-1次
第三次比较l-1-1-1次
第n次比较l-1-（n-1）次

n个数字来排序，两两比较大靠后
外层循环n-1，内层循环再减i

### 12.4选择排序*熟

```java
int minIndex=0;//假定最小值的下标为0
		for(int i=0;i<arr.length-1;i++) {
			minIndex=i;
			for(int j=i+1;j<arr.length;j++) {
				if(arr[minIndex]>arr[j]) {
					minIndex=j;
				}//break;寻找的是第一个的，没有则是最后一个的下标
			}//寻找最小下标
			
			if(minIndex !=i) {
				int temp=arr[minIndex];
				arr[minIndex]=arr[i];
				arr[i]=temp;
			}
		}
```

假定首位为最小值

通过内部循环找完整数组中，是否存在更小值进行交换

每次完成也同样可以确定前面的值

### 12.5插入排序*了解

```java
for(int i=1;i<arr.length;i++) {
			int j=i;
			int num=arr[j];//目标值
			while(j>0&&num<arr[j-1]){
				arr[j]=arr[j-1];
				j--; 
			}
			arr[j]=num;
		}
		
```

### 12.6二分查找法

 二分查找法(折半

要求数组是必须排序过的，且没有重复值

```java
int[] arr= {5,2,4,6,8,9,1};
		
		for(int i=0;i<arr.length-1;i++){//控制比较次数
			for(int j=0;j<arr.length-1-i;j++) {
				if(arr[j]>arr[j+1]) {
					int temp=arr[j];
					arr[j]=arr[j+1];
					arr[j+1]=temp;
				}
			}
		}	
			System.out.println("排序后数组："+Arrays.toString(arr));
			
			int n=6;
			int min=0;//查找范围最小下标
			int max=arr.length-1;//查找范围最大下标
			int index=-1;
			while(min<=max) {
				//找中间下标
				int mid=(max+min)/2;
				if(arr[mid]==n) {
					index=mid;
					break;
				}
				if(arr[mid]>n) {
					max=mid-1;
				}
				if(arr[mid]<n) {
					min=mid+1;
				}
			}
			System.out.println(n+"的下标是："+index);
```

### 12.7Arrays工具类

在二分查找法中的应用

```java
//1.sort(arr)方法，对数组排序，没有返回值，改变原数组
		int[] arr= {5,2,4,6,8,9,1};
		System.out.println("原数组为"+Arrays.toString(arr));
		Arrays.sort(arr);
		System.out.println("排序后："+Arrays.toString(arr));
		/*
		 * 二分查找的值若不在，则返回结果算法为
		 * （假设存在时的下标+1）*-1
		 */
		
		
		System.out.println("6在数组中的下标是"+Arrays.binarySearch(arr, 6));
		System.out.println("7在数组中的下标是"+Arrays.binarySearch(arr, 7));//应该存在的下标加一添负号比如7应该是5
		System.out.println("8在数组中的下标是"+Arrays.binarySearch(arr, 8));
		System.out.println("24在数组中的下标是"+Arrays.binarySearch(arr, 24));
		System.out.println("76在数组中的下标是"+Arrays.binarySearch(arr, 76));//应该存在的下标加一添负号比如24应该是7加一为8
		
		//int binarySearch(type[] a,int frontIndex,int toIndex, type key);
		System.out.println("1在数组下标2-5的范围内的下标是:"+Arrays.binarySearch(arr, 2,5,1));
		/*复制数组，第二个参数的长度确定arr2的长度
		 * 输入长度大于arr2则会自动填充默认值
		 * 输入长度小于arr2则会自动裁剪存入
		 */
		
		int[] arr2=Arrays.copyOf(arr, arr.length);
		//若多出来则多出来的值为其默认值
		System.out.println(Arrays.toString(arr2));
		/*
		 * 拷贝下标2-6之间的值到新的数组中，新数组的长度为6-2
		 * 若超出拷贝数组的范围，则补充其默认值
		 */
		int[] arr3=Arrays.copyOfRange(arr, 2, 6);
		System.out.println(Arrays.toString(arr3));
		/*
		 * equals先比较长度，在比较内容
		 */
		System.out.println(Arrays.equals(arr, arr2));
```

## 13.随机数random

```java 
 //  例如：生成 [6, 23) 的随机数
 double t2 = Math.random() * (23 - 6) + 6;

 //  生成 [min, max] 的随机数
 Math.random() * (max - min + 1) + min;
 //  例如：生成 [8, 24] 的随机数
 double t3 = Math.random() * (24 - 8 + 1) + 8;
```

随机产生0-9的数字

int num =(int)	(Math.random()*10);

## 14.方法

概念：将一组代码整合到一起，提供使用的方式

作用：只需要知道方法名进行调用，就可以执行该方法内的代码，已达到代码的重复利用的效果

### 14.1普通方法(最基础

* [访问修饰符] 返回值类型 方法名 ([形参1,形参2,……,形参n]){

  ​							//方法体

  ​							}

[]语法在说明文档中[]一般可以省略

* 调用方法：对象名.方法名([实参1,实参2,……,实参n]);的方式进行调用

* 方法的返回值使用return关键字返回，return会直接终止代码剩余部分的执行，return关键字必须为它所在分支的最后一行有效代码

  #### 14.1.1无参无返回值的方法

  使用void关键字表示方法没有具体的返回类型

  该方法适用于过程处理或直接内部可以处理完毕的行为

  ```java 
  public void getRandom() {
  //		Random random =new Random();
  //		int r= random.nextInt(6)+5;
  //		System.out.println(r);
  		
  		int r=getRandom4(5,10);
  		System.out.println(r);
  	}
  ```

  

  #### 14.1.2有参无返回的方法

  无返回值有参数的方法
  带参数的方法，可实现动态功能

  生成n-m之间的随机数并输出打印

  ```java
  public void getRandom2(int n,int m) {
  //		Random random =new Random();
  //		if(n>m) {
  //			int temp=n;
  //			n=m;
  //			m=temp;
  //		}
  //		int r= random.nextInt(m-n)+n;
  //		System.out.println(r);
  		
  		int r=getRandom4(n,m);
  		System.out.println(r);
  	}
  	
  ```

  #### 14.1.3调用普通方法：对象名.方法名()

  ```java
  public static void main(String[] args) {
  		Demo01 d1 = new Demo01();
  		d1.getRandom();
  	}
  ```

  #### 14.1.4有返回值有参数的方法

  ```java
  	public int getRandom4(int n,int m) {
  		Random random =new Random();
  		if(n>m) {
  			int temp=n;
  			n=m;
  			m=temp;
  		}
  		return random.nextInt(m-n+1)+n;
  }
  ```

  

### 14.2静态方法(类方法)

### 14.3构造方法

### 14代码

```java
package day06;

import java.util.Arrays;
import java.util.Random;

public class Demo01 {
	/*
	 * 方法
	 */
	
	public void getRandom() {
//		Random random =new Random();
//		int r= random.nextInt(6)+5;
//		System.out.println(r);
		
		int r=getRandom4(5,10);
		System.out.println(r);
	}

	/*
	 * 无返回值有参数的方法
	 * 带参数的方法，可实现动态功能
	 * 生成n-m之间的随机数并输出打印
	*/
	public void getRandom2(int n,int m) {
//		Random random =new Random();
//		if(n>m) {
//			int temp=n;
//			n=m;
//			m=temp;
//		}
//		int r= random.nextInt(m-n)+n;
//		System.out.println(r);
		
		int r=getRandom4(n,m);
		System.out.println(r);
	}
	

/*
 * 有返回值无参数的方法
 * 
 * 一般，有返回值的方法都需要使用其返回值的类型变量来进行接收，不接收也可以
 * 
 * 生成1-9的随机数并返回
*/

	public int getRandom3() {
		Random random =new Random();
		return random.nextInt(9)+1;
}
	/*
	 * 有返回值有参数的方法
	 * 
	 */
	public int getRandom4(int n,int m) {
		Random random =new Random();
		if(n>m) {
			int temp=n;
			n=m;
			m=temp;
		}
		return random.nextInt(m-n+1)+n;
}
	
	
	/**
	 * 获取两个参数中的最大值
	 * @param n参数1
	 * @param m参数2
	 * @return
	 */
	public int getMax(int n,int m) {
		if(n>m) {
			return n;
		}/*else {*/
			return m;
		//}
	}
	/**
	 * 获取输入参数最小值
	 * @param nums 按照正常赋值的方式进行调用。
	 * 			会自动变成数组,也可以直接传递数组
	 * ...表示的参数必须只能是方法形参的最后一个
	 * @return 最小值
	 */
	public int getMin(int ...nums) {
		if(nums.length>0) {
			int min=nums[0];
			for(int i=0;i<nums.length;i++) {
				if(nums[i]<min) {
					min =nums[i];
				}
			}
			return min;
		}//else {
		//}
		//	System.out.println(Arrays.toString(nums));
			return 0;
	}
	
	/**
	 * 如果参数要求传递的是数组时。就必须只能把多个参数先封装为数组，在进行传达
	 * @param arr
	 * @return
	 */
	
	
	
	public int getMin2(int [] arr) {
		System.out.println(Arrays.toString(arr));
		return 0;
	}
	


	public static void main(String[] args) {
		//调用普通方法：对象名.方法名();
		Demo01 d1 = new Demo01();//初始化
		d1.getRandom();
		d1.getRandom2(5,2);
		d1.getRandom3();//有返回值的方法只执行不接收
		
		int num1=d1.getRandom3();
		System.out.println(num1);
		System.out.println(d1.getRandom3());
		
		/*
		 *生成1-9之间的长度为5的数组
		*/

		int[] arr =new int [5];
		for(int i=0;i<arr.length;i++) {
				arr[i]=d1.getRandom3();
		}
		System.out.println(Arrays.toString(arr));
		
		for(int i=0;i<arr.length;i++) {
			arr[i]=d1.getRandom4(20, 30);
		}
		System.out.println(Arrays.toString(arr));
		
		
		
		int max=d1.getMax(5, 10);
		System.out.println(max);
		
		
		d1.getMin(5);
		d1.getMin();
		d1.getMin(5,6,8);
		d1.getMin(arr);
		System.out.println(d1.getMin(5,10));
		System.out.println(d1.getMin(arr));
		
	}

}
```

## 15.装箱和拆箱

calendar.set(Calendar.DATE, 05);//前面是修改内容，后面是修改为的值

不能根据时间戳来规定的

带（）的是方法，不带的是属性



不需要返回值的情况：

* 可能意义不大，对于结果来说不需要返回值的。
* 代码是用于格式化操作

## 16.面对对象

```java
		 /*面向对象（OOP）
		 * 三大特性：
		 * 封装：封装内部实现细节，保护数据安全
		 * Java中的类也需要封装，我们需要把属性私有化，提供公开的方法进行访问或设置。
		 * 面向对象的封装是包括Java的包装
		 * 
		 * 
		 * 
		 * 继承：A类继承B类继承，那么A类继承为B类的子类，B类为A类的父类
		 * Java中使用extends关键字来表示继承关系，写作A extends B
		 * Java中的继承是单继承，具有传递性。在Java中所有类都直接或间接的继承自Object类
		 * 一个类没有明确指定父类，那么它的父类就是Object类。
		 * Object自带的方法中我们要记住的是：equals和toString。
		 * 一个类如果不想被别人继承，那么需要使用final关键字来修饰。这样的类称为太监类。代表是String类型
		 * Java中可以继承所有的非私有属性和非私有方法
		 * 子类可以重写父类的方法
		 * 
		 * 
		 * 方法重写：(打印子类中，特有的属性，父类的方法不能满足子类需求)
		 * 发生在继承关系中，子类重写父类的方法
		 * 要求子类的方法名必须和父类的方法名一致，返回类型、参数个数和参数类型一致
		 * 子类方法的访问修饰符权限要大于或等于父类方法的访问修饰符。
		 *父类需要实例化
		 * 
		 * 
		 * final关键字：
		 * 修饰类表示这个类不能被继承
		 * 修饰方法表示这个方法不能够被重写
		 * 修饰变量表示这个变量不能被改变  例如常量，声明必须赋值不能被更改
		 * 
		 * 
		 * 继承关系中的构造函数
		 * 子类的构造函数必须先调用父类的构造函数，如果没有显式调用，那么jdk在编译时就会自动调用父类的无参构造函数的代码。
		 * 使用super();表示父类构造函数的调用。该函数的调用必须是子类构造函数的第一行！！
		 * 
		 * 调用当前类的构造函数使用this();
		 * 
		 * super关键字：1父类对象的引用 2区分它们的属性
		 * 
		 * 
		 * 多态：
		 * 抽象（被官方否定
		 */
```

关键字this，super，final，extends，static

```java
/*
		 * 方法重载
		 * 发生在同一个类中
		 * 方法名相同，方法的参数个数和参数类型各不相同
		 * 
		 * 方法重载可以发生在普通方法，构造方法，静态方法中
		 * 
		 */
		
		
		
		/*
		 * 多态：同个对象在不同场景内的多种形态。
		 * Java中多态的前提：必须有继承发生，必须有子类重写父类的方法
		 * Java中多态的表现：
		 * 父类的声明指向子类，调用重写的方法，子类执行，称为向上转型，反之为向下转型(强制类型转换来实现)
		 * 
		 * 
		 * 多态执行中，属性调用执行父级，重写的方法调用子级，未重写方法调用父级
		 * 
		 */
```

```java
/*
		 * static 关键字
		 * 
		 * static修饰的属性或方法称为类属性和类方法，实例化出的所有对象中的值，都是一致的
		 * 
		 * 1static修饰属性称为静态属性，静态属性无需实例化，直接通过类名.属性名的方法调用
		 * 静态属性只要改了都会变，普通属性针对对象
		 * 
		 * 2static修饰方法称为静态方法，静态方法中只能使用静态属性，静态方法也只能调用静态方法
		 * 
		 * 3static修饰代码块称为静态代码块，该块中的代码会在类加载中首先被执行。
		 * 
		 *///Demo静态方法执行new构造方法执行
```

```java
public static  String RANDOM_STR="gdhjsahxbZXahs432787";
	//使用方法重载的场景
	private static final String DAT_FORMATTER="yyyy-MM-dd HH:mm:ss";
	
	public static String getStringDate(Date date,String formatter) {
		SimpleDateFormat sdf=new SimpleDateFormat(formatter);
		return sdf.format(date);
	}
	

	public static String getStringDate(Date date) {
		return getStringDate(new Date(),DAT_FORMATTER);
	}
	
	public static String getStringDate(String formatter) {
		return getStringDate(new Date(),formatter);
	}
	

	public static String getStringDate() {
		return getStringDate(new Date(),DAT_FORMATTER);
	}
	
	
	public static Date getNow() {
		return new Date();
	}
	
	public static int getRandom(int n,int m) {
		if(n==m) {
			return n;
		}
		if(n>m) {
			int temp=n;
			n=m;
			m=temp;
		}
		
		
		return (int)(Math.random()*(m-n+1)+n);
	}
	
	
	
	public static int getRandom() {
	//	return (int)(Math.random()*(9-0+1)+0);
		return getRandom(0,9);
		
	}
	
		public static String smsCode(int len) {
			String code="";
			for(int i=0;i<len;i++) {
				code+=getRandom(0,9);
			}
			return code;
		}
		
		public static String imageCode(int len) {
			String code="";
			for(int i=0;i<len;i++) {
				code+=RANDOM_STR.charAt(getRandom(0,RANDOM_STR.length()-1));
			}
			return code;
		}
```

## 17.抽象

```java 
/*
		 *抽象的关键字：abstract
		 *abstract标记在类上表示抽象类
		 *抽象类不能被实例化，可以被抽象类和普通类继承
		 *继承抽象类的类，依然是抽象类，但是该子类不能实例化
		 *abstract标记在方法上表示抽象方法
		 *抽象方法没有方法体
		 *抽象方法只能存在抽象类中，抽象类中不能只是抽象方法
		 * 
		 */

```

## 18.接口

接口就是只有一个方法的抽象类，（可以不用属性）关键字使用interface代替class，接口和类不同的概念，但是平级

* 接口中只存在静态常量和抽象方法
* 静态常量默认就是公开的静态方法，没有static和final
* 方法不加修饰符就是public默认，被default修饰的也是普通方法（可以有自己的内容），其余均为抽象方法（但是可以省略abstract
* 接口不能被实例化，但是类（extends）单一继承，接口（implements）多继承；
* 抽象类的概念：属于不属于，接口的概念：有没有。

面向接口编程

show被default修饰

## 19.多态

打断点：检查哪里有错误，鼠标移至该位置可以显示具体对象的信息，若无则只显示类的信息

多态：一个事物有多种表现形态 ；作用：可以提高代码的可扩展性，可维护性

* 必须要有`继承`关系，才能进行调用以及向下/向上转型
* 定义方法参数为父类，调用方法，传子类数据类型的参数
* 定义方法时，返回值为父类，调用方法时，用子类接收
  * 将父类引用指向子类
* 方法重写是多态的基础

使用多态时，父类只需要方法的声明，不关注具体的实现，因为，会被子类重写覆盖

抽象方法：只声明不实现（没有方法体{}） abstract--抽象方法，例如只写：public abstract void hospital();		实现：子类通过重写来实现

抽象类：一个类中存在抽象方法，那么该类就是抽象类即添加abstract

* 若父类为抽象类，则子类也必须实现抽象方法，或者是子类也为抽象类
* 抽象类中一定有抽象方法，非抽象方法可有可无
* 普通类中一定不能有抽象方法

```java
public void cure(Animal animal){
    if(anmial.getHealth()<60);
        anmial.hospital();
}//简化后就不用再写Dog dog和Cat cat 类，使用它们的父类Anmial，这就是多态
```

anmial instanceof Dog : instanceof 是否--类型判断

方法重载：(与返回值无关，关注于方法名和参数列表，若相同则报错，修改其一可行)

向下转型：父类转子类，强制转换

向上转型：子类转父类，自动转换(可以理解为继承)

## 20. 抽象方法

抽象类中可以包含抽象方法还有普通方法。普通方法一定不包含抽象方法。

抽象类不能被实例化(通过该类创建对象-->类名 对象名=new 类名 )

抽象类实例化的方法--->创建一个普通类，继承抽象类，实现抽象方法，最后实例化普通类。(实现子类)

修改类名：在导航栏需要修改的类处右击Refactor-->Rename

接口：由抽象类延伸出----可以降低程序之间的耦合性

面向接口编程：有利于程序的扩展性，维护性，降低了程序的耦合性。应该具备**低耦合高内聚**。

```Java
public class Test{
    public static void main(String[] args){
     USB usb=new FengShan();//只用改后面的接口类型
        usb.doit();
 }
}//一个完整的面向接口编程

```



耦合性：指模块和模块之间的松散程度，模块之间尽量松散，联系不紧密(低耦合)

 接口的使用

* 创建接口，接口是一个特殊的抽象类，使用interface来标识

创建类:

```java
  public  class{
  }
```

创建接口 :

```java
public interface 接口名{

定义接口方法

}
```



* Java程序中，除非调用静态方法或者访问静态属性可以不创建对象，直接通过类去访问。除此之外，必须创建对象才能使用。
  * 如何在接口中创建对象(实例化)
    * 接口本身不能被实例化，同抽象类-----接口是不能被普通类继承，只能被接口继承
    * 接口方法的实现不能使用继承，使用实现(implement)----创建一个普通类，让该类实现接口。

接口与抽象类的区别：

* 抽象类中可以存在普通方法，接口必须全部为抽象方法
*  接口中的抽象方法可以不添加abstract关键字
* 抽象还是接着使用class

接口定义了一个功能，定义类具体执行该功能。

public class Test {
	public static void main(String[] args) {
//		Lock lock =new ThefPoorDoor();
//		lock.close();
//		lock.open();
//		Picture picture=new ThefPoorDoor();
//		picture.takePicture();
		ThefPoorDoor  door1=new ThefPoorDoor();
		door1.close();
		door1.open();
		door1.takePicture();
		WoodDoor door2=new WoodDoor();
		door2.close();
		door2.open();
	} 

注意事项：

* 接口不能被实例化，只能实现化
* 实现类必须实现接口的全部方法----接口就是一个特殊的抽象类，重写
* 实现类可以实现多个接口(Java只支持单继承，多实现)
* 接口中的变量都是静态--static.常量--final.(可以不加)---必须赋值(初始化且后续不能修改)

main方法里面不能有实现体

## 21. 集合

使用集合的原因：

* 当需要保存多个数据时，可以用数组保存，但是数组存在弊端
  * 数组长度不可变
  * 动态给数组的具体位置添加元素十分麻烦
* 数据的个数不确定时，使用集合最好

Java中的集合(类和接口)体系结构---------Collection 、Map(都是接口)

* Collection:有两个子接口

  * List：有两个实现类----存储一组唯一的(不能重复)，有序(索引/下标)的对象---超市存包的
    * *ArrayList*常：实现了长度可变的动态数组，在内存分配一串连续的空间，基于索引的数组，查询数据效率更高，增删元素效率变低。
    * LinkeList：采用链表的形式存储，查询效率低，增删效率高，集合中的每个元素。除了记录数据外还要保存前后节点的位置信息，所以他需要更大的内存空间
  * Set：有两个实现类----存储一组唯一的(不能重复)，无序(无索引/无下标)的对象---超市购物袋
    * *HashSet*常
    * TreeSet

* Map：有两个实现类----存储以键值对(key-value)的形式存储，key不可重复，value可重复user为例--

  'user1'--user			'user2'--user

  * *HashMap*常
  * TreeMap

### 21.1 **ArrayList**

常用方法如下：

* boolean add(Object obj)	//添加，向集合尾部添加对象
* boolean add(int index,Object obj)	//向指定的位置插入对象
* int size()	//返回集合类型
* Object get (int index)	//通过索引返回具体数据
* boolean contains(Object obj)		//判断obj对象是否在集合中
* Object remove(int index)	//根据索引删除对象，并且将被删除的对象返回
* boolean remove(Object obj)	 //通过传入的对象进行删除

 凡是返回一个对象，其数据类型均为Object类型(Object 所有类的父类----体现了多态)

快捷键Alt+Shift+S----- Gteters and Setters

快捷键Alt+Shift+S----- Construction from Superclass---带参构造

```java
import java.util.ArrayList;

public class Test {

	public static void main(String[] args) {
		// 创建新闻对象
		News news1 =new News(1,"体育新闻","张三"); 
		News news2 =new News(2,"娱乐新闻","李四"); 
		News news3 =new News(3,"科技新闻","王五"); 
		//创建集合对象
		ArrayList list = new ArrayList();
		//将新闻对象存入集合
		list.add(news1);
		list.add(news2);//只能取1
		list.add(news3);//前面可以取0,1,2
        //集合长度越长所取得值就能越大
       System.out.println(list);
	}

}
```

### 21.2 **LinkeList**

除ArrayList常用方法外其他方法如下：

* void addFirs(Object obj)	//在集合的首部添加元素
* void addLast(Object obj)	//在集合的尾部添加元素
* Object getFirst()	//返回集合中第一个元素
* Object getLast()	//返回集合中最后一个元素
* Object removeFirst()	//删除并返回集合中的第一个元素
* Object removeLast()	//删除并返回集合中最后一个元素

```java
list.add(0,news3);//list.addFirst(news3);
list.add(4,news1);//list.addLast(news1);
list.remove(0);//list.removeFirst();//删后重新排序
list.remove(1);//list.removeLast();//长度一旦动态变化，索引必须变化减一
```

循环的第四种形式(增强型for循环)-----foreach

for(数据类型 变量名:遍历的目标集合){

若数据类型不同，在此进行强转换

方法体

}

```java 
		for(Object obj:list) {
			Dog dog5=(Dog) obj;	System.out.println(dog5.getName()+"\t"+dog5.getStrain());---增强型for循环
//		for(int i=0;i<list.size();i++) {
//			Dog dog=(Dog) list.get(i);
//			System.out.println(dog.getName()+"\t"+dog.getStrain());
//		}---普通for循环
```

**以上类是可以存储重复的元素的(对List实现的接口),而对Set接口实现的类是不能存储重复的元素**

### 21.3 **TreeSet**

(对Set接口的实现,底层是有TreeMap实现的)
注:TreeSet实际是利用TreeMap的key来存储元素,而TreeMap中的Value是位null,底层都是树结构，TreeSet可以给Set集合中的元素进行指定方式的排序。存储的对象必须实现Comparable接口。

* 底层:是树形结构

* 添加进来的元素可以进行排序(有序的 不是添加的顺序,是元素的自然顺序)

* 添加顺序是大的元素向右放,小的元素向左放;

  ```java 
  创建对象方法:
  	TreeSet set = new TreeSet();//指存储任意类型元素
  	TreeSet<Integer> set = new TreeSet<>();//指存储Integer元素(不仅可以是Integer可以是其他类,<>里面的也称为 java中的泛型)
  ```

常用方法：

* boolean add(E,e)	//对集合添加元素，对应E类型
* void clear()	//删除集合内所有的元素
* boolean contains(Object obj)	//判断元素是否在集合中存在
* boolean isEmpty()	//判断集合是否为空
* boolean remove(Object obj)	//删除集合中指定的元素
* Object pollLast()	//删除集合中最后一个元素并返回
* Object first()	//返回集合第一个位置的元素
* Object pollFirst()	//删除并返回集合第一个位置的元素
* Object last()	//返回集合最后一个位置的元素

### 21.4 **HashSet**

(对Set接口的实现,底层是HashMap实现的)
Set接口

不能存储重复元素

无序的(既不是添加顺序,也不是按元素自然顺序)

不会重复的原因:

* 底层使用hashCode()和equals()方法;
* 用内存计算一个hash值(整数),用hash值比较速度块(hash是不安全的,有可能两个内容不一样,hash值一样)

当hash值相同时,调用equals()方法,
这样效率提高,也保证安全了

构造方法

```java
HashSet<String> stringHashSet = new HashSet<>();//存储String类型的HashSet,不止可以是String可以是其他类型,Integer对象
HashSet stringHashSet = new HashSet();//存储任意类型
```

常用方法：

* boolean add(E,e)	//对集合添加元素，对应E类型
* boolean contains(Object obj)	//判断元素是否在集合中存在
* boolean remove(Object obj)	//删除集合中指定的元素
* boolean isEmpty()	//判断集合是否为空
* void clear()	//删除集合内所有的元素

当HashSet中的泛型为 自己写的类创建的对象时

```java
import java.util.Objects;
//定义Student类
public class Student implements Comparable{
    private int id;
    private String name;
public Student(int id, String name) {
    this.id = id;
    this.name = name;
}

@Override
public String toString() {
    return id+name;
}

@Override
public boolean equals(Object o) {
    if (this == o) return true;
    if (o == null || getClass() != o.getClass()) return false;
    Student student = (Student) o;
    return id==id&&name.equals(student.name);
}    }
//如果我们想要对象中内容相同的元素判断为重复元素,就必须在我们类中重写hashCode()与equals()方法
    @Override
    public int hashCode() {
        return Objects.hash(id, name);
    }

    @Override
    public int compareTo(Object o) {
        return this.id-((Student)o).id;
    }
}
```
```java
HashSet<Student> studentHashSet = new HashSet<>();
        Student student = new Student(101, "cwy");
        Student student1 = new Student(102, "dqw");
        Student student2 = new Student(103, "wyn");
        Student student3 = new Student(101, "cwy");

        studentHashSet.add(student);
        studentHashSet.add(student1);
        studentHashSet.add(student2);
        studentHashSet.add(student3);
        System.out.println(studentHashSet);

```


如果Student类中没有重写**hashCode()**与**equals()**方法,则运行结果会发现存在重复项,这是因为判断重复项时会调用类中的hashCode()计算hash值，类中若是没有hashCode()会调用父类的hashCode()，即Object类中的public native int hashCode()；(native本地方法,由操作系统提供的)。所以，只要是new出来的，调用Object值，是内存地址，肯定不同

***如果我们想要对象中内容相同的元素判断为重复元素,就必须在我们类中重写hashCode()与equals()方法***

对单列集合的遍历
使用for循环

```java
ArrayList<String> stringArrayList = new ArrayList<>();
//1.for循环遍历
        for (int i=0;i<stringArrayList.size();i++){
            if(stringArrayList.get(i).equals("2")){
                stringArrayList.remove(i);
                //for循环的时候,是支持从元素中删除元素的,但是删除后,后面的元素会前移,需要控制索引
            i--;
            }
        }
        System.out.println(stringArrayList);
//2.增强for循环    不支持删除元素
        for(String s:stringArrayList){
            System.out.println(s);
        }

```

使用迭代器

```java
//3.使用迭代器1.0遍历Iterator 支持删除方法,且不会漏掉元素
       Iterator<String> iterator = stringArrayList.iterator();
       while(iterator.hasNext()){
           String s = iterator.next();
           if(s.equals("2")){
               iterator.remove();//迭代器中删除的方法
           }
           System.out.println(s);
       }
       //迭代器2.0 只能遍历List
       ListIterator<String> stringListIterator = stringArrayList.listIterator();
       while(stringListIterator.hasNext()){
           String s = stringListIterator.next();
           System.out.println(s);
       }
       //从指定位置索引
       ListIterator<String> stringListIterator2 = 			`			           stringArrayList.listIterator(stringArrayList.size());//size=最大索引+1
       //逆序
       while(stringListIterator2.hasPrevious()){
           String s = stringListIterator2.previous();
           System.out.println(s);
       }

```

### 21.5HashMap

(对Map接口的实现)

HashMap 底层使用了三种结构

* hash数字定位（锁定元素的位置）
* 链表存储多个元素
* 红黑树存储多个元素

添加元素时：

* 首先用元素计算出 hash 值，用 hash 值％数组长度，得到元素位置，将数据<key,Value> 加到 hash 表指定位置
* 后面添加元素时，如果有相同的位置，那么将后来的元素添加到第一个元素的 next 结达一定条件时，链表会转为红黑树，提高查询效率

构造方法

```java
HashMap<String,String> stringHashMap = new HashMap<>();//创建HashMap对象,键值分别是String与String  当然也可以是其他的类
```

常用方法:

* public V put(K key, V value)	//对图进行添加新的元素(必须对应你预定的类型)
* boolean containsKey(Object key)	//判断指定的Key键是否存在
* boolean containsValue(Object value)	//判断指定的Value键是否存在
* boolean remove(Object key)	//删除指定键的元素，并返回对应的值
* boolean isEmpty()	//判断集合是否为空
* void clear()	//删除所有的元素
* boolean add(E,e)	//对集合添加元素，对应E类型
* int size	//返回元素个数即元素长度
* Object get(Object key)	//通过Key键返回对应的Value值

HashMap的键值遍历
对值的遍历

```java 
Collection<String> collection = stringHashMap.values();//获取值 System.out.println(collection);
```

对键的遍历

```java 
Set<String> set =stringHashMap.keySet();//获取键的集合
 System.out.println(set);
```

结合public V get(Object key)可以遍历对应的Value

对整体的遍历(使用迭代器)

```java
       //通过entrySet()  获取到Entry类型的集合,Entry中放有键值对
        Set<Map.Entry<String,String>>entries = stringHashMap.entrySet();
        for(Map.Entry<String,String> empty:entries){
            System.out.println(empty);
            System.out.println(empty.getKey());//获取键
            System.out.println(empty.getValue());//获取值
        }
```

### 21.6 Hashtable

(底层与HashMap一样,只不过方法修饰符不同)
底层结构与HashMap相同,但是线程安全的,方法被synchronized关键字修饰

### 21.7 TreeMap

(实现SortedMap接口)
有序性:TreeMap 存储的键值对是有序的。具体来说，键的插入顺序和自然排序顺序或者自定义的比较器排序顺序是一致的，**其余方法都与TreeMap一样**



**小总结：**

集合分为：**Collection **和 **Map**

Collection：**List (ArrayList有下标  LinkedList无下标)和 Set(HashSet TreeSet)**

Map：**<key,Value>  HashMap TreeMap (key中保存Set value中保存Collection )**

## 22. 泛型

为什么使用泛型?

数组中只能保存相同数据类型的数据，集合中可以保存不同数据类型的对象，但是可能会给开发带来问题。为了避免这一问题，让集合中只能保存一种数据类型的对象，就要使用泛型。

泛型：规范集合所保存的数据类型，使集合只能保存泛型规定的数据类型。(不能写基本数据类型，要写成其包装类)

添加完泛型之后，从集合中取值就不需要添加强转。迭代器中不属于集合仍需要强转。

**List: **List<规定类型> list = new LinkedList<规定类型>();

**Set: **Set<规定类型> set = new HashSet<规定类型>();

**Map: **Map<规定类型,规定类型> map = new HashMap<规定类型,规定类型>();

Collection：接口，两者区别要注意有无s。

Collections：工具类，定义了一系列对集合的操作。

升序：sort();		反序：reverse();	获取集合中的最大值：max();	获取集合中的最小值min();

若要让其按照某一类型排序，可以使用接口比较，排序。

```java 
//添加接口implements Comparable<Employee>
public int compareTo(Employee o)//通过id排序
{
	if(this.id==o.id){
        return 0;
    }else if(this.id>o.id){
        return 1;
    }else if(this.id<o.id){
        return -1;
    }
    return 0;
}
```



## 23. 实用类

### 23.1 枚举

在描述对象的某些属性时，这些值是在固定范围内取得。描述一种特定的数据类型。

枚举由一组固定的常量组成。

语法：Modifier(私有访问修饰符) enum (枚举)

Modifier enum enumName{

​	enum1;

​	enum2;

}//和类的结构很像

### 23.2 包装类

**装箱和拆箱补充**

对应的是8种基本数据类型，将基本数据类型转化为类。

使用集合的泛型时，无法设置基本数据类型，泛型必须是一个类，所以就需要将基本数据类型包装为一个类。

每一个基本数据类型在java.lang中都有对应的包装类。

包装的作用：提供了操作对应基本数据类型的一系列实用方法。

基本数据类型的包装类：

| 基本数据类型 | 包装类                               |
| ------------ | ------------------------------------ |
| Object       | Boolean,Number,Character             |
| Number       | Integer,Short,Long,Double,Float,Byte |
| int          | Integer                              |
| short        | Short                                |
| long         | Long                                 |
| double       | Double                               |
| float        | Float                                |
| byte         | Byte                                 |
| boolean      | Boolean                              |
| char         | Character                            |

基本数据类型--->>包装类	装箱

* 通过包装类的构造函数
* 通过包装类的静态方法valueOf

包装类--->>基本数据类型	拆箱

- xxxxxValue()-------包装类	基本数据类型Value()

  Integer intValue()

  Boolean booleanValue()

- parsexxxx()

  把字符串转化为基本数据类型（Character类型除外）

  包装类.parse基本数据类型

  ```java
  int num1 =Integer.parseInt("123");
  double num2 =Double.parseDouble("6.6");
  ```

## 24. IO流

### 24.1 File 类

* File类是java.io包中很重要的一个类

* File类的对象可以表示文件,还可以表示目录,在程序中的一个File类对象可以代表一个文件或目录
* File对象可以对文件或目录的属性进行操作,如:文件名,最后修改日期,文件大小等
* File对象无法操作文件的具体数据,即不能对文件进行读或写的操作

常用方法：

* boolean exists()	//判断文件是否存在 存在-true 不存在-false
* boolean isFile()	//判断是否为文件,是---true 不是---false
* boolean isDirectory()	//判断是否为目录,是目录---true 不是---false
* String getName()	//获取文件名称
* long length()	//获取文件长度(字节数)
* boolean creatNewFile()throws IOException	//创建新文件,成功---true 失败---false,有可能抛出IOException异常,必须捕捉
* boolean delete()	//删除文件,成功---true 失败---false
* public String[] list()	//将目录下的子目录以及文件的名字,返回到String数组
* public Flie[] listFiles()	//将目录下的子目录以及文件的实例返回到File数组

### 24.2 IO流

IO流：Java程序通过IO流完成文件的读写(文件的复制粘贴)

读取：InputStream----将文件读取到Java程序中

写出：OutputStream----从Java程序中将文件写入本地硬盘

流是一种有序的数据序列，以先进先出的方式发送数据的通道。

Java流的分类：

* 按方向

  * 输入流	InputStream
  * 输出流	OutputStream

* 按单位(每次处理的数据单元)

  * 字节流：以字节为单位处理(byte)

    字节是计算机能识别的基本单位，1字节=8位二进制数Byte

  * 字符流：以字符为单位处理

    1字符=2字节，16位二进制数

* 按功能

  * 节点流(字节流，字符流)
  * 处理流(字节流----字符流)

### 24.3 字节流   输入流

*InputStream OutputStream*   抽象类

实例化的是子类：FileInputStream FileOutputStream

FileInputStream实例化：

FileInputStream(File file)

FileInputStream(String path)

FileOutputStream实例化：

FileOutputStream(File file)

FileOutputStream(String path)

FileOutputStream(String path,boolean append)

append为ture，表示在原文件基础之上技能型追加

append为flase，表示覆盖原文件，默认值

InputStream 常用方法：

*  int read() 	//将文件中的数据以字节为单位进行读取
* int read(byte[] b) 	//将文件中的数据以字节为单位进行读取，保存到byte数组中
* int read(byte[] b,int start,int length) 	//将文件中的数据以字节为单位进行读取，保存到byte数组中。从Start开始，保存长度为length的数据
* void close();	//关闭流,释放内存资源
* int available()	//返回当前文件中可读取的数据个数

OutputStream 常用方法：

* void writer(int temp);	//向输出写入一个字节数据,该字节数据位参数b的低8位
* void writer(byte[] bs);	//将bs中的数据写出去
* void writer(byte[] bs,int start,int length) 	///将bs中的数据写出去从off开始，保存长度为length的这段数据写出，不是全部写出
* void close() ;	//关闭流，释放内存资源
* void flush();	//强制将缓冲区的数据写出

### 24.4 字符流   输出流

原理和字节流一样，每次处理数据的单位不同。

**Reader**	抽象类，不能实例化，实例化子类FileReader

Reader常用方法：

* int read()	//以字符为单位读取数据
* int read(char[ ] c)	//将数据以字符为单位读取，保存在c中
* int read(char[] c,int start,int length)	//同上，从start开始，长度为length的数据
* int close()	//关闭流

**Writer**	抽象类，不能被实例化，实例化其子类FileWriter

Writer常用方法：

实例化：

FileWriter(String path)

FileWriter(File file)

OutputStreamWriter(String path)

OutputStreamWriter(File file)

void writer();

如果取的是中文，一定不能使用字节流，会出现编码格式错误，要使用字符流

原因：一个汉字是由两个字节组成，必须同时读取，不能拆分。

如果是英文，字符流和字节流没有区别

原因：一个字母字符就是一个字节

###   24.5 缓冲流

为了提高效率，直接读取一行字符串

BufferedReader是Reader的子类，**BufferedReader**类带有缓冲区

BufferedReader直接按行读取内容的方法String readLine();

BufferedWriter是Writer的子类，**BufferedWriter**类带有缓冲区



p2p：(电驴)损伤硬盘，使用字节流，每次读取一个字节，都要访问一次硬盘。

解决方法：在内存中开辟一个缓冲区，访问一次硬盘，将缓冲区的内存填满，再从缓冲区中读取资源。

flush(); 强制将缓冲区的数据写出到硬盘。一般在执行close方法之前，需要先调用flush。

os.fulsh();

os.close();

读取二进制文件(图片视频音频)

DataInputStream是FileInputStream的子类

DataOutputStream是FileOutputStream的子类

也可以使用字节流，不能使用字符流

### 24.6 序列化	反序列化

序列化：将内存中的对象写入到流中

​			将Java对象保存到硬盘中

反序列化：从流中获取数据

重新在内存中构建对象

​			从硬盘中读取数据，还原成Java对象

序列化步骤：

* 实体类实现序列化接口Serializable
* 创建对象输出流
* 调用writeObject方法将对象写入硬盘
* 关闭资源

```java 
import java.io.FileOutputStream;
import java.io.ObjectOutputStream;
import java.io.OutputStream;
import com.southwind.entity.User;
public class Test3{
    public static void main(String[] args){
        User user=new User();
        user.setId(1);
        user.setName("张三");
        OutputStream os;
        try{
            os=new FileOutputStream("d:user.txt");
            ObjectOutputStream oos=new ObjectOutputStream(os);
            oos.writeObject(user);
            oos.flush();
            oos.close();
            os.close();
        }catch(Expcetion e){
            //TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
}
```



反序列步骤：

* 创建对象数据流
* 调用readObject方法读取数据并且在内存中重新构建对象
* 关闭资源

```java
 try{
     InputStream is=new FileInputStream("d:user.txt");
     ObjectInputStream ois=new ObjectInputStream(is);
     User user=(User) ois.readObject();
     System.out.println(user.getId()+"-----"+user.getName());
     ois.close();
     is.close();
     catch(Expcetion e){
         //TODO Auto-generated catch block
         e.printStackTrace();
        }
 }
```

## 25. 多线程

进程：应用程序执行的实例，有独立的内存空间和系统资源

线程：进程中执行运算的最小单位，CPU调度和分派的基本单位

一个进程是有多个线程组成。

多线程：一个进程中同时进行多个线程，完成不同的工作中。(同时运行不是真正意义上的同时运行)实际是在交替占用CPU资源，CPU运算速度特别快，虽然说是在交替运行，看上去感觉是多个线程在同时执行。

优点：	充分利用CPU资源	简化编程模式	带来良好的用户体验

Java中的main方法是主线程，在main方法中，可以产生多个子线程。

如何使用多线程：

Thread类来描述线程。

* 创建线程

  * ----->自定义一个子线程类，继承Thread类
  * ------>自定义一个子线程类，实现Runnable接口

* run方法中定义该线程要执行的程序

  启动一个子线程，必须调用start()方法，不能调用run()方法，调用run方法相当于在主线程中调用普通对象的普通方法，还是只有一个主线程。

  //创建子线程MyThread mt =new MyThread();

  //启动子线程mt.start(); 

线程的状态

* 创建状态(实例化线程对象)
* 就绪状态(调用了start方法，进入争夺CPU资源的序列)
* 运行状态(此刻线程占用了CPU资源，进行计算)
* 阻塞状态(设置该线程暂时停止，排除在争夺CPU资源的序列之外)
* 死亡状态(线程执行完毕，外部强制干预)

![image-20240125230832170](E:\Topora\JavaSE.md)

线程调度

按照某种机制为多个线程分配CPU的使用权

具体操作，使用Thread的各种方法来完成线程调度。

* 设置线程的优先级，一个线程的优先级越高，抢占到CPU资源的概率越大。

  set Priority (int value)优先级范围1-10，默认值5

* 设置线程休眠，在指定的毫秒数内让当前正在执行的线程休眠，进入阻塞状态，不在参与CPU资源的争夺，休眠结束后，再进入就绪状态。

  static void sleep(long millis)

* 使当前正在执行的线程暂停，执行调用了jion方法的线程(Thread2)。当Thread2执行完成之后，再来执行该线程。让其他线程暂停，执行调佣了jion()方法的线程。

  void jion();

* 线程礼让，暂停调用yield()方法的线程，让其他线程执行，优先执行其他线程，在下一个抢占CPU资源的时刻，两者又回到竞争关系。

  void yield();

  jion类似sleep

  sleep：通过时间段来划分是否放弃抢占资源

  yield是某一时刻，线程礼让，放弃抢占资源。

习题练习：

1.要求每个线程代表一个人可以设置每个人的爬山速度，每爬100米显示信息，爬到终点给出提示

```java 
public class Climb implements Runnable{
	//每爬100米时间
	private int time;
	//爬了多少个100米
	private int num;
	
	public Climb(int time,int meter) {
		this.time =time;
		this.num =meter/100;
	}
	
	@Override
	public void run() {
		// TODO Auto-generated method stub
		while(num>0) {
			try {
				Thread.sleep(time);
			}catch(InterruptedException e) {
				e.printStackTrace();
			}
			System.out.println(Thread.currentThread().getName()+"爬了100米");
			num--;
		}
		System.out.println(Thread.currentThread().getName()+"爬上了山顶");
	}

}

public class Test {
	public static void main(String[] args) {
		//创建一个爬山者
		Climb cr =new Climb(2000,2000);
		Thread th =new Thread(cr,"张三");
		th.start();
		//创建二个爬山者
		Climb cr2 =new Climb(5000,2000);
		Thread th2 =new Thread(cr,"李四");		
		th2.start();
	}
}
```

2.叫号看病 某科室一天需要看50个普通号，10个特需号，特需号时间是普通号的2倍，开始的时候普通号和特需号并行叫号，叫到普通号的概率比特需号小，当普通号叫完10号时，要求先看完所有的特需号，再看普通号。

```java 
public class Special  implements Runnable{

	@Override
	public void run() {
		// TODO Auto-generated method stub
		for(int i=0;i<10;i++) {
			try {
				Thread.sleep(2000);
			} catch (Exception e) {
				// TODO: handle exception
				e.printStackTrace();
			}
			System.out.println("特需号"+(i+1)+"在看病");
		}
	}

}


public class Test2 {

	public static void main(String[] args) {
		Special sr=new Special();
		Thread th =new Thread(sr);
		th.start();
		//开启普通号线程
		for(int i=0;i<50;i++) {
			if(i==10) {
				try {
					th.join();
				} catch (Exception e) {
					// TODO: handle exception
				}
			}
			try {
				Thread.sleep(1000);
			} catch (Exception e) {
				// TODO: handle exception
				e.printStackTrace();
			}
			System.out.println("普通号"+(i+1)+"在看病");
	}
		Thread.currentThread().setPriority(1);
}
}
```



多个线程同时访问共享数据引发的数据安全问题，通过给线程加锁的方式，避免这种数据安全的问题。当一个线程访问资源时，给该资源上锁，该资源被当前线程锁定，其他线程就无法访问该资源。当前线程执行完毕之后，释放锁，其他线程就可以访问资源。

如何实现上述过程：(用synchronized关键字修饰资源)

* 直接在使用资源的方法声明处添加synchronized
* 在方法体中，具体使用资源的代码处，添加synchronized

## 26. 异常

异常处理机制

* 默认处理机制
  * java中默认的异常处理机制：
    当程序出现异常后,会将异常包装在一个对应的对象中，并抛出此对象。并终止程序的运行。
* 手动处理
  * Java中提供一套异常处理机制，在程序发生异常时，可以执行预先设定好的处理程序，执行完成后，程序不会停止，可以继续向后执行。
* 异常处理:
  * 遇到异常就终止程序运行(不想要的)
  * 遇到程序异常时,进行处理

在写代码的时候,就要根据不同的情况设定好处理程序

运行程序

* 如果程序执行时,出现问题,执行异常处理程序
* 如果程序执行时,没有出现问题,不需要执行异常处理程序(语法错误 并非异常)

| 关键字                          | 分析                                                         |
| ------------------------------- | ------------------------------------------------------------ |
| NullPointerException            | 当应用程序试图在需要对象的地方使用 null 时，会抛出此异常。例如，调用空对象的方法或访问空对象的成员变量。 |
| IndexOutOfBoundsException       | 此异常通常发生在尝试访问数组、字符串或其他类型的集合时，索引超出了其实际范围 |
| ArithmeticException             | 当出现异常的算术条件时，例如除以零，会抛出此异常。           |
| ClassCastException              | 当尝试将对象强制转换为不是实例的子类时，会抛出此异常。       |
| llegalArgumentException         | 当向方法传递了一个非法或不适当的参数时，会抛出此异常。       |
| ConcurrentModificationException | 当程序在迭代一个集合的同时，另一个线程试图修改这个集合，就会抛出这个异常。 |
| FileNotFoundException           | 当试图打开一个不存在的文件时，会抛出此异常。                 |
| IOException                     | 这是一个一般性的I/O错误，通常用于指示输入/输出操作失败或中断的异常。 |
| ClassNotFoundException          | 当JVM试图通过其字符串名称加载类，但在已加载的类中找不到相应的类定义时，会抛出此异常 |
| ArrayIndexOutOfBoundsException  | 当应用程序试图访问数组的非法索引时（即负数或大于等于数组大小的数）时，会抛出此异常。 |
| NullPointerException            | 当一个应用程序试图在需要对象的地方使用 null 时，会抛出此异常。 |
| NumberFormatException           | 当一个应用程序试图在需要对象的地方使用 null 时，会抛出此异常。 |
| InterruptedException            | 当线程正在等待、休眠或占用，并且线程的中断优先级被设置为InterruptedException时，会抛出此异常。 |

异常处理中的几个常用关键字(try catch finally throw throws)------------如果出现多个错误,则会抛出共同的父类

```java 
异常处理
   java中提供一套异常处理机制,在程序发生异常时,可以执行预先设定好的处理程序,
   执行完成后,程序不会停止,可以继续向后执行.
   
   在写代码的时候,就要根据不同的情况设定好处理程序,
   运行程序
   如果程序执行时,出现问题,执行异常处理程序
   如果程序执行时,没有出现问题, 不需要执行异常处理程序
   
   关键字
     try{
	    写代码,可能会出现异常
	 }catch(异常类型 a){ 捕获指定类型的异常
	    
	 }finally{
	     最终必须要执行的代码
	 }
	try{
            int[] a = {1,2,3};
            int b = a[4];
        }catch (ArrayIndexOutOfBoundsException a){
            a.printStackTrace();
        }catch (Exception e){
            e.printStackTrace();
        }
        System.out.println("666");
    }
```

**throw 与 throws区别**
在Java中，throws和throw是两个不同的关键字，它们在异常处理中起着不同的作用。

* *throws关键字*
  * throws用于声明一个方法可能会抛出的异常。当一个方法可能会抛出异常时，我们需要使用throws关键字在方法签名中声明这些异常。这样，调用该方法的代码就需要处理这些异常，或者继续向上抛出。
  * 例如，如果一个方法可能会抛出IOException，我们可以这样声明：public void readFile() throws IOException。
* *throw关键字*
  * throw用于手动抛出异常。我们可以使用throw关键字在代码中直接抛出一个异常对象。
  * 例如，我们可以这样手动抛出一个IOException：throw new IOException("File not found");。

总结：throws用于声明方法可能抛出的异常，而throw用于手动抛出异常。这两个关键字在异常处理中是相辅相成的，它们一起处理和传递异常。

**编译期异常和运行期异常的区别**

* **异常处理要求不同：**编译期异常（也称为检测异常checked Exception）要求在代码中显式地处理（使用try-catch或者throws）。运行时异常（也称为unchecked Exception）不要求显式地处理。
* **异常检测时机不同：**编译期异常在代码编译阶段就可以被检测到。运行时异常在代码运行过程中才能被检测到。
* **异常必要性不同：**编译期异常通常表示外部环境或者业务逻辑上的问题，需要通过异常处理来解决。运行时异常通常表示程序中的错误或者编程错误，可以通过代码改进避免。

自定义异常
JavaAPI中定义的标准异常类,都是与语法有关的(例如索引越界,空指针…),

 但是我们的程序有可能不满足某种业务条件时,想以抛出异常的形式处理,此时就需要自定义一个与

 业务相关的异常类来表示(如 分数不合法,提供scoreException);

在Java中，您可以通过继承Exception或RuntimeException类来创建自定义异常。这些异常可以具有您需要的任何特定格式。以下是一个创建自定义异常的简单示例

```java 
// 创建一个自定义异常类
class MyException extends Exception {
    public MyException(String message) {
        super(message);
    }
}

// 在代码中抛出这个异常
public class Test {
    public static void main(String[] args) {
        try {
            throwException();
        } catch (MyException e) {
            e.printStackTrace();
        }
    }

    public static void throwException() throws MyException {
        throw new MyException("这是我的异常");
    }
}
```

```java 
//自定义异常
public class ScoreException  extends Exception{
    public ScoreException(){

    }
    public ScoreException(String message){
        super(message);//直接调用父类的构造方法
    }
}
```

```java 
public class TestScoreException {
    public static void main(String[] args) {
        try {
            System.out.println(scoreClass(1000));
        } catch (ScoreException e) {
            e.printStackTrace();
        }
    }
    public static char scoreClass(int score) throws ScoreException {
        if(score<0||score>100){
            throw new ScoreException("输入非法分数");
        }
        if(score>=90){
            return 'A';
        }else if(score>=80){
            return 'B';
        }else if(score>=70){
            return 'C';
        }else{
            return 'D';
        }
    }
}
```

## 27. 网络编程

计算机网络：

把分布在不同地理区域的，具有独立功能的计算机，通过通信设备与线路连接起来，由功能完善的软件实现资源共享和信息传递的系统。(简单来说就是把不同地区的计算机通过设备连接起来，实现不同地区之前的数据传输)

网络编程是借助计算机网络，实现我们所写的程序，在不同电脑上，可进行数据的传输。

java是支持网络间的数据传输的，降低层细节封装起来了，给程序员提供了一套标准的类库，很方便使用java语言开发可以进行网络通信的软件。

**网络编程的核心问题**

-  如何找到网络世界中的恶目标主机,以及目标软件
-  在终端 使用 ipconfig 指令查看ip
-  如何安全可靠的进行数据传输 协议 规则

**网络：**

- 网络模型
-  OSI参考模型 是一个理想化的标准模型
  -  分成七层
-  TCP/IP参考模型
  -  分成四层
  -  应用层(http)
  -  运输层(协议)
  -  网络层(ip)
  -  物理链路层(硬件设备)

通信要素 ip 端口 协议

* IP：在网络世界中,是计算机的地址
*  局域网地址： 192.168.1.20 连接到路由器，会自动分配IP
*  广域网地址：家里的宽带 与外界连接
*  本机地址：本地回环地址 127.0.0.1
* 端口：计算机中运行中的程序的编号，对应的是程序
  * 端口号0-65535之间 由于0-1024被一些系统程序使用,所以我们开发的程序可以从1024-655335区设定端口，但是不能与已有的发生冲突
* ip+端口 找到目标计算机 以及你想要的程序

Java中分为两种编程协议

- TCP( **TCP是可靠的安全的,相对于UDP效率低**)
- UDP( **不用建立连接,直接发送**)



### 27.1 TCP

#### 27.1.1**TCP协议通信原理**

先检测网络是否通畅,客户端是否能连接到服务器端
如果能连接到,则进行数据的传输,如果连接不到,就会报错
**采用3次握手的机制 (连接请求)**

* 第一次客户端给服务器发送一个信息
* 服务器收到客户端的请求后,需要给客户端做出一个反馈(表示服务器端收到客户端消息)
* 客户端收到服务器端确认反馈后,再一次向服务器发送一个反馈,以确保服务器知道他的反馈,客户端是收到 (表示客户端成功收到服务器端消息)

**四次挥手(端来请求)**

- 客户端 向服务器端发送一个断开请求
- 服务器端 向客服发出一个反馈
- 服务器端把没有发完的数据全部发送
- 客户端再向服务器端发送最终断开的信号

#### 27.1.2TCP编程

**服务端**

`ServerSocket`常用的方法

- ```
  Socket accept() throws IOException
  ```

  - 等待客户端的连接请求,返回与该客户端进行通信的Socket对象

- ```
  void close() throws IOException
  ```

  - 关闭监听Socket

```java 
import java.io.*;
import java.net.ServerSocket;
import java.net.Socket;
/*
服务器端
 */
public class Server {
    public static void main(String[] args) {
        //创建并启动服务器
        try{
            ServerSocket serverSocket = new ServerSocket(9999);
            System.out.println("服务器启动成功");

            while(true) {
                Socket socket = serverSocket.accept();//监听有没有客户端连接到服务器,监听时,会阻塞程序
                System.out.println("有傻逼端连接到服务器");
                //接收客户端发送的数据
                InputStream inputStream = socket.getInputStream();
                //下面过于复杂,可以调用DataInputStream  但是必须对应DataOutputStream
//                byte[] bytes = new byte[100];
//                int size = inputStream.read(bytes);
//                String s = new String(bytes, 0, size);
//                System.out.println(s);
                DataInputStream dataInputStream = new DataInputStream(inputStream);
                String s= dataInputStream.readUTF();
                System.out.println(s);


                //服务器向客户端发送消息
                OutputStream outputStream =socket.getOutputStream();
                DataOutputStream dataOutputStream = new DataOutputStream(outputStream);
                dataOutputStream.writeUTF("已经收到");

                // 确保数据被发送出去，并释放资源
                dataOutputStream.flush();
                dataOutputStream.close();
                socket.close();
            }
        } catch (IOException e) {
            e.printStackTrace();
            System.out.println("服务器启动失败,端口被占用");
        }
    }
}
```

**客户端**

常用方法

* void close() throws IOException	//关闭Socket 不可以在以后得网络连接中使用 除非创建新的套接字
* InputStream getInputStream() throws IOException	//获取与Socket相关联的字节输入流,用于从Socket中读入数据
* OutputStream getOutputStream() throws IOException	//获取与Socket相关联的字节输出流 ,用于向Socket中写入数据

```java 
import java.io.*;
import java.net.Socket;
/*
客户端
 */
public class Client {
    public static void main(String[] args)  {

        //创建客户端
        //127.0.0.1自己地址
       try {

               //向服务器发送
               Socket socket = new Socket("127.0.0.1", 9999);
               //在客户端向服务器端发送一句话
               OutputStream outputStream = socket.getOutputStream();//获取输出流
               DataOutputStream dataOutputStream =new DataOutputStream(outputStream);

               String s = "你好";
               dataOutputStream.writeUTF(s);

               //接受服务器
               InputStream inputStream = socket.getInputStream();
               DataInputStream dataInputStream = new DataInputStream(inputStream);
               System.out.println(dataInputStream.readUTF());


       } catch (IOException e) {
           e.printStackTrace();
           System.out.println("连接服务器失败");
       }
    }
}
```



### 27.2 UDP协议通信原理

#### 27.2.1UDP协议通信原理

-  将数据分装成一个一个数据报
-  包含 数据 源(自己电脑ip) 目标(接受ip 端口)
-  只管发送 是否成功,不知道
-  是不安全的,但是效率高

#### 27.2.2UDP编程

**服务端**

```java 
import java.io.IOException;
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.SocketException;

public class UDPReceive {
    public static void main(String[] args) {
        try {
            while(true){
                //接受数据的对象
                DatagramSocket datagramSocket = new DatagramSocket(9999);

                byte[] bytes = new byte[100];
                //接受数据包
                DatagramPacket datagramPacket = new DatagramPacket(bytes,0, bytes.length);
                datagramSocket.receive(datagramPacket);
                String s = new String(bytes,0,datagramPacket.getLength());
                System.out.println(s);
                datagramSocket.close();
            }
        } catch (SocketException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        }

    }
}
```

**客户端**

```java 
import java.io.IOException;
import java.net.*;

//发送端
public class UDPSendDemo {

    public static void main(String[] args) {
        try {
            DatagramSocket datagramSocket = new DatagramSocket();//负责发送数据报
            byte[] bytes = "你好sb邓钦文".getBytes();
            DatagramPacket datagramPacket = new DatagramPacket(bytes,0, bytes.length, InetAddress.getByName("127.0.0.1"),9999);

            //发送(datagramSocket方法)
            datagramSocket.send(datagramPacket);
            datagramSocket.close();
        } catch (SocketException e) {
            e.printStackTrace();
        } catch (UnknownHostException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

}

```



### 27.3 TCP 与 UDP的区别

TCP（传输控制协议）和UDP（用户数据报协议）都是网络传输层协议，用于在网络中传输数据。它们之间的主要区别在于连接方式、可靠性、数据流方式和功能。

* *连接方式：*
  TCP是面向连接的协议，发送方和接收方在发送数据之前，必须通过三次握手建立连接。这个过程确保了双方都已准备好进行数据传输。
  UDP是无连接的协议，发送方在向接收方发送数据时不需要建立连接。这意味着UDP可以更快地发送数据，但也可能导致数据的丢失或乱序。
* *可靠性：*
  TCP通过序号机制、确认机制、超时重传机制和数据校验来保证传输的可靠性。如果数据在传输过程中丢失或损坏，TCP会重新发送数据，直到接收方成功接收为止。
  UDP只添加了端口和差错检查的功能，不提供数据的可靠性保证。因此，UDP在传输过程中可能会出现数据丢失或乱序的情况。
* *数据流方式：*
  TCP是面向字节流的协议，将应用层传递下来的数据当做无结构的数据流进行处理。TCP不知道所传数据的具体含义，只是将数据块拼接成一个段进行发送。
  UDP是面向报文的协议，发送方的UDP对应用程序交下来的报文添加首部后直接向下交付IP层。每个报文都是独立发送的，不需要进行拼接。
* *功能：*
  TCP支持单播、多播和广播的功能，可以实现一对一、一对多、多对多和多对一的数据传输。
  UDP同样支持这些传输方式，但由于其无连接的特性，使得UDP在实时性要求较高的场景中更为适用，如视频流、音频流等。