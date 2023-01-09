# LED-panel

## LED选型

1. [国星金线小间距P1.25P 1.5 P1.6P2室内户外高清防水会议LED显示屏-淘宝网 (taobao.com)](https://item.taobao.com/item.htm?id=562968559313)

   介绍页面有P1.667 200*150 30扫 大于1920HZ

2. 



## LED驱动

### 75驱动及代码

- [(95条消息) 一文搞懂HUB75接口（附带LED单元板驱动介绍）_ReCclay的博客-CSDN博客_hub75e](https://recclay.blog.csdn.net/article/details/115307011?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-115307011-blog-106658193.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-115307011-blog-106658193.pc_relevant_vip_default&utm_relevant_index=1)

  - [Everything You Didn't Want to Know About RGB Matrix Panels - News - SparkFun Electronics](https://www.sparkfun.com/news/2650)
  - [rpi-rgb-led-matrix - Support group for https://github.com/hzeller/rpi-rgb-led-matrix](https://rpi-rgb-led-matrix.discourse.group/)
  - [64x128 LED Matrix with HUB75 (not HUB75E) interface not working · Issue #956 · hzeller/rpi-rgb-led-matrix (github.com)](https://github.com/hzeller/rpi-rgb-led-matrix/issues/956)
  - [hzeller/rpi-rgb-led-matrix: Controlling up to three chains of 64x64, 32x32, 16x32 or similar RGB LED displays using Raspberry Pi GPIO (github.com)](https://github.com/hzeller/rpi-rgb-led-matrix)
  - [adafruit/RGB-matrix-Panel: Arduino library and example code for the 16x32 RGB matrix panels in the shop (github.com)](https://github.com/adafruit/RGB-matrix-Panel)
  - [Driving a 64*64 RGB LED panel with an FPGA. - jaeblog jaeblog (justanotherelectronicsblog.com)](https://justanotherelectronicsblog.com/?p=636)

- [(95条消息) LED单元板驱动(HUB75接口)_爱FC的捷哥的博客-CSDN博客_hub75](https://blog.csdn.net/a3748622/article/details/106658193)

  含具体代码

- [HUB75 LED显示驱动器 (stmicroelectronics.cn)](https://shequ.stmicroelectronics.cn/thread-619835-1-1.html)

- [(95条消息) hub75点屏（32扫）_乐易198的博客-CSDN博客_hub75e](https://blog.csdn.net/li18438605823/article/details/124385224?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-2-124385224-blog-115307011.pc_relevant_vip_default&spm=1001.2101.3001.4242.2&utm_relevant_index=5)

  64*64的138驱动代码

- [(95条消息) Arduino驱动RGB点阵彩屏（Led matrix）--显示数字，字母，汉字，学习经历，供大家参考，少走弯路_veteran412的博客-CSDN博客_rgb点阵屏驱动](https://blog.csdn.net/veteran412/article/details/86670082?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-86670082-blog-124385224.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-86670082-blog-124385224.pc_relevant_vip_default&utm_relevant_index=3)

- [nadyrshin_ryu / icn2053_esp32_demo — Bitbucket](https://bitbucket.org/nadyrshin_ryu/icn2053_esp32_demo/src/master/) icdn2053

- [vamoosebbf/hub75e: hub75e 64*64 rgb 点阵屏 (github.com)](https://github.com/vamoosebbf/hub75e)


### 串行驱动

- [求助 HUB75的P3(2121)64X64-32-V4.1全彩LED屏 芯片驱动 - 我爱单片机 数码之家 (mydigit.cn)](https://www.mydigit.cn/thread-244700-1-1.html)

  *2021-3-24 11:18:44*  [crazy0qwer](https://www.mydigit.cn/space-uid-2984404.html)写了一版驱动代码

  ```
  int i,j,row ;
     
     while(1)
  {
  /*以下变量绑定对应引脚
  scan_A
  scan_B
  scan_C
  data_RD1
  data_GD1
  data_BD1
  data_RD2
  data_GD2
  data_BD2
  control_CLK
  control_LAT
  control_OE
  */
  
   //行————————————————————————————————————————
      if(row>31) { row=0; }
      control_OE=1;   //换行        
      scan_B=1;            //使能信号，不行试试=0
      temp=1<< row ;
      for(j=0;j<2;j++)        //CLK(A)  BK(B) DIN(C)
      {
         for(i=0;i<32;i++)        
                  {
              scan_C=temp & (1<<i);
              scan_A=1;   scan_A=0;   //clk
          }
      }
      //列——————————————————————————————————————
      for(i=0;i<16;i++)        
      {
          for(j=0;j<4;j++)                 
          {
              //红色
              data_RD1=1;                data_RD2=0;
              data_GD1=0;                data_GD2=0;
              data_BD1=0;                data_BD2=1;                
              control_CLK=1;                        control_CLK=0;                //输出一个脉冲
          }
      }
      control_LAT=1;        control_LAT=0;        //一个LAT脉冲，锁存数据
      control_OE=0;                                        //点亮
      row++;                                                        //切换到下一行
      //delay();
  }
  ```

- [jaygreco/TLC5958: C++/Arduino driver for TI TLC5958x multiplexed LED driver (github.com)](https://github.com/jaygreco/TLC5958)



### 320接口

[20200115190856.pdf (kystar.com.cn)](http://www.kystar.com.cn/filespath/files/pdf/20200115190856.pdf) 320接收卡凯视达G628

[小间距专用接收卡HD-R320T_深圳市灰度科技有限公司 (huidu.cn)](https://www.huidu.cn/product_16.html)

[卡莱特-下载专区-软件下载-产品规格书-操作说明 (lednets.com)](https://www.lednets.com/zh/Support/Specification/index.html)

[2021081420231185.pdf (lednets.com)](https://www.lednets.com/upload/Support/Specification/2021081420231185.pdf) E320接收卡卡莱特



## 驱动芯片

[ICND2163_datasheet_EN_2020_V1.1.pdf](file:///E:/项目/全息显示/屏幕方向/LED模组资料/ICND2163_datasheet_EN_2020_V1.1.pdf)

[ICN20531~32扫PWM恒流输出LED显示屏驱动芯片.pdf-文档在线预览 (book118.com)](https://max.book118.com/html/2019/0609/6231210122002035.shtm)



# Motor

## 电机设置

电压：24V

### 脉冲细分

200个脉冲走一圈360°

[(95条消息) 什么是步进电机的细分？ 什么是细分？是不是细分越高精度越高？_小白study的博客-CSDN博客_步进电机细分和转速的关系](https://blog.csdn.net/android_lover2014/article/details/53462089)

## zynq资料

[Part2_Z7-Lite系列教程之SDK篇 V1.1.pdf](file:///E:/项目/全息显示/电机方向/zynq/Part2_Z7-Lite系列教程之SDK篇 V1.1.pdf)

[Part1_Z7_Lite系列教程之逻辑篇 V1.1.pdf](file:///E:/项目/全息显示/电机方向/zynq/Part1_Z7_Lite系列教程之逻辑篇 V1.1.pdf)

[Z7-LITE_Rev1_1_引脚图.pdf](file:///E:/项目/全息显示/电机方向/zynq/Z7-LITE_Rev1_1_引脚图.pdf)



## zynq online例程

1. [【FPGA ZYNQ Ultrascale+ MPSOC教程】30.自定义IP实验 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/346124527)
   - 可调节PWM和占空比的例程
   - 封装IP实际上就是写寄存器值（我理解的）

## zynq在SDK中计算某段程序的执行时间

#include "xtime_l.h"  包含这个头文件
int main() 
{
 XTime tEnd, tbegin;
 u32 tused;

	 XTime_GetTime(&tbegin);
	 *******test_code*****************
	 *******test_code*****************
	 *******test_code*****************
	 XTime_GetTime(&tEnd);
	tused = ((tEnd-tbegin)*1000000)/(COUNTS_PER_SECOND);
	 xil_printf("time elapsed is %d us\r\n",tused);
}
[(100条消息) 如何在xilinx sdk中捕获调试某段代码需要运行的时间_Nina_小哥的博客-CSDN博客_xilinx sdk查询函数执行时间](https://blog.csdn.net/weixin_38931060/article/details/109090710?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-109090710-blog-93783921.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-109090710-blog-93783921.pc_relevant_vip_default&utm_relevant_index=3)



## zynq代码知识

### uart

[(117条消息) ZYNQ基础----串口中断_black_pigeon的博客-CSDN博客_zynq串口中断](https://blog.csdn.net/qq_41332806/article/details/107100381)

[(117条消息) ZYNQ进阶之路14--PS端uart串口接收不定长数据_鹏哥DIY的博客-CSDN博客_zynq串口](https://blog.csdn.net/WP_FD/article/details/92442468)

[(117条消息) 学会Zynq（25）UART的基本使用方法_FPGADesigner的博客-CSDN博客_zynq中ps单独运行串口](https://bestfpga.blog.csdn.net/article/details/88852990?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-88852990-blog-92442468.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-88852990-blog-92442468.pc_relevant_vip_default&utm_relevant_index=3)

[(113条消息) ZynqMP Vitis2021.1 PS UART接收中断及IDLE（超时）中断_sudaroot的博客-CSDN博客_xuartps_setopermode](https://blog.csdn.net/sudaroot/article/details/121015393)

[(113条消息) 学会Zynq（27）UART中断驱动模式示例_FPGADesigner的博客-CSDN博客](https://bestfpga.blog.csdn.net/article/details/88910848?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-88910848-blog-110840478.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-88910848-blog-110840478.pc_relevant_vip_default&utm_relevant_index=2)



### print相关 print vs printf vs xil_printf

[(95条消息) ZYNQ开发系列——SDK输出串口选择以及打印函数print、printf、xil_printf的差别_十年老鸟的博客-CSDN博客_xil_printf](https://blog.csdn.net/gzy0506/article/details/124085448)

- printf 是调用C标准库，使用printf的时候需要加头文件 #include <stdio.h>

- print 和 xil_printf是使用xilinx自己的库 #include “xil_printf.h”
- print只能打印字符串
- xil_printf和printf，可以带参量打印，但是xil_printf不支持打印浮点数

**需要打印字符串就使用print函数，需要打印浮点数就使用printf，需要打印整点数就使用xil_printf就没错了。可能的话最好所有打印都不要出现printf，只要有一个都会使内存增加不少**

**%s是打印一个字符串，%c是打印一个字符**

### printf 浮点数 有效数字 小数部分

- %3.0f表明待打印的[浮点](https://so.csdn.net/so/search?q=浮点&spm=1001.2101.3001.7020)数（floatNum）至少占3个字符宽，且不带小数点和小数部分，整数部分至少占3个位宽；

- %6.2f 表明待打印的数（floatNum）至少占6个字符宽度（包括两位小数和一个小数点），且小数点后面有2位小数，小数点占一位，所以整数部分至少占3位。

  **前面的数，表示了即将输出的这个数占多少位数后面的数，表示了即将输出的这个数将保留多少位小数** 前面的数是一个正数，则说明它是向右对齐的，即补位补在前面，如果是负数，则相反

  **保留0位小数的时候，只要小数点后第一位>=5，就可以进位，但是保留1位或者2位等等，保留小数的后一位要>5才可以进位，否则就舍去**

### create_clock

-period 表示时钟周期，单位为ns

[(98条消息) SDC时序约束(1)- create_clock_limanjihe的博客-CSDN博客_sdc约束](https://blog.csdn.net/limanjihe/article/details/52325218)





## znyq代码错误

### xil_printf没有输出

串口通信端口设置错误，去看引脚图，我的是UART0（14，15）

### AP transaction error, DAP status f0000021

把FPGA复位一次就好了