API接口对比
==================
基本概念
------------------
* 交易所 -> 市场/平台



The Open Group Base Specifications
------------------
http://pubs.opengroup.org/onlinepubs/9699919799/


宏汇API
------------------


中泰API
------------------
https://xtp.zts.com.cn/docs/quote/index.html
XTPMarketDataStruct  各种类型的字段都集成在一个结构中

附录
-------------------
<pre>
MSC_VER是微软的预编译控制。

_MSC_VER可以分解为：

MS：Microsoft的简写。

C:MSC就是Microsoft的C编译器。

VER：Version的简写。

_MSC_VER的意思就是：Microsoft的C编译器的版本。

微软不同时期，编译器有不同的版本：

MS VC++10.0 _MSC_VER=1600

MS VC++9.0 _MSC_VER=1500

MS VC++8.0 _MSC_VER=1400

......

其中MS VC++10.0就是Visual C++ 2010，MS VC++9.0就是Visual C++2008，MS VC++8.0就是Visual C++2005

在程序中加入_MSC_VER宏可以根据编译器版本让不同版本的编译器选择性地编译一段程序。

查看编译的版本信息，可以在Command line里敲 cl /?

 

文章二

_MSC_VER定义编译器的版本。常见编译器版本_MSC_VER值：

MSVC++ 11.0 _MSC_VER = 1700 (Visual Studio 2011) 
MSVC++ 10.0 _MSC_VER = 1600 (Visual Studio 2010) 
MSVC++ 9.0  _MSC_VER = 1500 (Visual Studio 2008) 
MSVC++ 8.0  _MSC_VER = 1400 (Visual Studio 2005) 
MSVC++ 7.1  _MSC_VER = 1310 (Visual Studio 2003) 
MSVC++ 7.0  _MSC_VER = 1300 
MSVC++ 6.0  _MSC_VER = 1200 
MSVC++ 5.0  _MSC_VER = 1100

 

在程序中加入_MSC_VER宏可以根据编译器版本让编译器选择性地编译一段程序。例如一个版本编译器产生的lib文件可能不能被另一个版本的编译器调用，那么在开发应用程序的时候，在该程序的lib调用库中放入多个版本编译器产生的lib文件。在程序中加入_MSC_VER宏，编译器就能够在调用的时根据其版本自动选择可以链接的lib库版本，如下所示。

 
　

复制代码
　#if _MSC_VER >= 1400 // for vc8, or vc9 

　　#ifdef _DEBUG 

　　#pragma comment( lib, "SomeLib-vc8-d.lib" ) 

　　#else if 

　　#pragma comment( lib, "SomeLib-vc8-r.lib" ) 

　　#endif 

　　#else if _MSC_VER >= 1310 // for vc71 

　　#ifdef _DEBUG 

　　#pragma comment( lib, "SomeLib-vc71-d.lib" ) 

　　#else if 

　　#pragma comment( lib, "SomeLib-vc71-r.lib" ) 

　　#endif 

　　#else if _MSC_VER >=1200 // for vc6 

　　#ifdef _DEBUG 

　　#pragma comment( lib, "SomeLib-vc6-d.lib" ) 

　　#else if 

　　#pragma comment( lib, "SomeLib-vc6-r.lib" ) 

　　#endif 

　　#endif
</pre>
