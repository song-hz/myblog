# LED选型

1. [国星金线小间距P1.25P 1.5 P1.6P2室内户外高清防水会议LED显示屏-淘宝网 (taobao.com)](https://item.taobao.com/item.htm?id=562968559313)

   介绍页面有P1.667 200*150 30扫 大于1920HZ

2. 



# LED驱动

## 75驱动及代码

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
- 

## 串行驱动

- [求助 HUB75的P3(2121)64X64-32-V4.1全彩LED屏 芯片驱动 - 我爱单片机 数码之家 (mydigit.cn)](https://www.mydigit.cn/thread-244700-1-1.html)

  *2021-3-24 11:18:44*  [crazy0qwer](https://www.mydigit.cn/space-uid-2984404.html)写了一版驱动代码

  ```bash
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



## 320接口

[20200115190856.pdf (kystar.com.cn)](http://www.kystar.com.cn/filespath/files/pdf/20200115190856.pdf) 320接收卡凯视达G628

[小间距专用接收卡HD-R320T_深圳市灰度科技有限公司 (huidu.cn)](https://www.huidu.cn/product_16.html)

[卡莱特-下载专区-软件下载-产品规格书-操作说明 (lednets.com)](https://www.lednets.com/zh/Support/Specification/index.html)

[2021081420231185.pdf (lednets.com)](https://www.lednets.com/upload/Support/Specification/2021081420231185.pdf) E320接收卡卡莱特





