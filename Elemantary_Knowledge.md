# 1 主函数基础知识
main函数前int或者void作为函数返回值，对应return 0，或者不写，为int时C++会默认最后添加return 0。
main是程序入口但不一定第一条执行的就是main()语句，也有可能是全局语句，类似于python中在if __name__=="__main__"前写的语句。
main函数执行之前，主要是初始化系统相关资源
- 设置栈指针
- 初始化静态static变量和global全局变量，即.data段的内容
- 将未初始化部分的全局变量赋初值：数值型short,int,long等为0，bool为FALSE，指针为null等，即.bss段的内容。
- 全局对象初始化，在main之前调用构造函数
- 将main函数的参数argc,argc等传递给main函数，然后才真正运行main函数
atexit()用于对main执行结束后继续执行的定义，可以理解为栈的方式调用，后进先出，先进后出。
# 2 语法基础
"\n"与endl都表示换行，但是endl会刷新缓冲区，使得栈中的内容刷新一次，建议用endl换行。
头文件""与<>，<>默认去系统目录中找文件，""首先在当前目录下去寻找，找不到再去系统目录下找。
命名空间std，尽量避免直接使用using namespace std，等直接引入整个命名空间，否则会因为命名空间污染导致很多不必要的问题。
system("pause")不能在Linux系统下使用，因为Linux不会弹出命令框。
