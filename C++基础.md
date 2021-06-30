1.	面试官看重的是代码的调试能力和编程习惯
2.	除了完成基本功能，还要考虑错误输入、边界处理，很重要。
3.	面试官给提问环节，最好问 和 求职部门相关的项目和技术，不要向非HR问工资，也不要问自己的面试表现怎么样？
4.	A a = 10; 执行了两步：先将10隐式转换为A(10)； 再调用拷贝构造函数将 A a = A（10）； https://blog.csdn.net/twdlll/article/details/78302349
5.	类A的复制构造函数为A(A other)这样是不行的，因为是传值调用，那么调用这个拷贝构造函数的时候：形参用拷贝构造函数给实参赋值，这样就会循环调用拷贝构造函数，导致栈溢出。 
6.	重载运算符：返回值 class::operator = ( const参数&),如果一个运算符函数是成员函数，那么它的左侧运算对象绑定到掩式的this指针上，因此，成员运算符函数的参数比运算符运算对象少一个。如重载赋值运算符：MyClass& MyClass::operator=( const MyClass&);
7.	复制构造函数和赋值运算符：
都是将一个对象的值复制给另一个对象。
赋值运算符是将对象的值复制给一个已经存在的实例；复制构造函数是用传入的对象构造一个新的对象。二者主要看是否有新对象产生。复制构造函数的定义：Class(const Class& );
复制构造函数：string str = “000”;
赋值运算符： str = str1; 

8.	C++规定：初始化只在进入构造函数体之前，进入构造函数体之后就是赋值了；
如：ClassA(int num, string str): age(num), name(string){} 是初始化，如果是ClassA(int num, string str){age = num; name = str;}就是赋值了。

9.	因为不能拷贝数组，所以数组形参会自动转化为指针。所以：
Void print（int *）；
Void print(int[]);
Void print(int[10]);  //这三个虽然形式不同，但是都是传入的指针类型

10.	数组和指针：当声明一个数组时，数组名也是一个指针，该指针指向数组的第一个元素。我们可以使用指针来访问数组。如：
Int data1[] = {1,2,3,4};
Int data2* = data1;
GetSize(data1);  //函数GetSize的声明为GetSize( int data[]);
如果sizeof（data1），等于16；而sizeof（data2），等于4； 将数组传入函数中，那么此时data1是指向数组第一个元素的指针。
上述例子访问数组的第三个元素可以：
1.	data1[2]
2.	data1 + 2;
3.	data2 + 2;

11.	从函数返回数组，返回的是数组的指针，局部变量需声明为static：
https://www.runoob.com/cplusplus/cpp-return-arrays-from-function.html

12.	Sizeof是关键字，用于获取类或数据类型的大小。

13.	为了节省内存，C/C++把常量字符串放到单独的一个内存区域，将此字符串赋值给不同的指针时，是指向相同的区域。用数组时则有所不同。
Char str1[] = “hello, world”; 
Char str2[] = “hello , world”;

Char * str3 = “hello,world”;
Char * str4 = “hello, world”;
Str1和str2是两个不同的数组， str3和str4指向相同的区域。

14.	
