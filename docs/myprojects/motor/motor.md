# zynq资料

[Part2_Z7-Lite系列教程之SDK篇 V1.1.pdf](file:///E:/项目/全息显示/电机方向/zynq/Part2_Z7-Lite系列教程之SDK篇 V1.1.pdf)

[Part1_Z7_Lite系列教程之逻辑篇 V1.1.pdf](file:///E:/项目/全息显示/电机方向/zynq/Part1_Z7_Lite系列教程之逻辑篇 V1.1.pdf)

[Z7-LITE_Rev1_1_引脚图.pdf](file:///E:/项目/全息显示/电机方向/zynq/Z7-LITE_Rev1_1_引脚图.pdf)



# zynq online例程

1. [【FPGA ZYNQ Ultrascale+ MPSOC教程】30.自定义IP实验 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/346124527)
   - 可调节PWM和占空比的例程
   - 封装IP实际上就是写寄存器值（我理解的）

# zynq代码知识

1. print相关 print vs printf vs xil_printf

   [(95条消息) ZYNQ开发系列——SDK输出串口选择以及打印函数print、printf、xil_printf的差别_十年老鸟的博客-CSDN博客_xil_printf](https://blog.csdn.net/gzy0506/article/details/124085448)

   - printf 是调用C标准库，使用printf的时候需要加头文件 #include <stdio.h>

   - print 和 xil_printf是使用xilinx自己的库 #include “xil_printf.h”
   - print只能打印字符串
   - xil_printf和printf，可以带参量打印，但是xil_printf不支持打印浮点数

   **需要打印字符串就使用print函数，需要打印浮点数就使用printf，需要打印整点数就使用xil_printf就没错了。可能的话最好所有打印都不要出现printf，只要有一个都会使内存增加不少**

2. printf 浮点数 有效数字 小数部分

   - %3.0f表明待打印的[浮点](https://so.csdn.net/so/search?q=浮点&spm=1001.2101.3001.7020)数（floatNum）至少占3个字符宽，且不带小数点和小数部分，整数部分至少占3个位宽；
   - %6.2f 表明待打印的数（floatNum）至少占6个字符宽度（包括两位小数和一个小数点），且小数点后面有2位小数，小数点占一位，所以整数部分至少占3位。

   **前面的数，表示了即将输出的这个数占多少位数后面的数，表示了即将输出的这个数将保留多少位小数** 前面的数是一个正数，则说明它是向右对齐的，即补位补在前面，如果是负数，则相反

   **保留0位小数的时候，只要小数点后第一位>=5，就可以进位，但是保留1位或者2位等等，保留小数的后一位要>5才可以进位，否则就舍去**

3. 

# znyq代码错误

1. xil_printf没有输出

   串口通信端口设置错误，去看引脚图，我的是UART0（14，15）

   