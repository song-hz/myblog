# Matlab

## 函数

### norm

n=norm(A,p) p-范数

[(98条消息) MATLAB中范数norm()函数精讲_爱趣无穷的博客-CSDN博客_matlab norm](https://blog.csdn.net/weixin_40857506/article/details/120436911)

### 左除右除

- 左除A\B=inv(A)*B
- 右除B/A=B*inv(A)

### vrho

求谱半径

### tril、triu

tril 矩阵下三角部分 triu举证上三角部分

### pgm读写

- cover=imread('1.pgm')

- stego=unit(stego);

  imwrite(stego,'stego.pgm')

### 获取文件夹下所有名称

coverPath = ‘E:\song_study\images’;

dirOutput=dir(fullfile(coverpath,'*.pgm'));

for i=1:size(dirOutput,1)

​	name=dirOutput(i).name;

​	pgmPath=fullfile(coverPath,name);

​	cover=imread(pgmPath);

end

### 字符串处理

str=['show_',num2str(i)];

str=fullfile('show','image.pgm');

fprintf(' %d- DONE\n',i);

### 既有数组又有字符

changerate=cell(size(dirOutput,1),2);

changerate{1,1}=name;

changerate{1,2}=sum(cover(:)~=stego(:))/numel(cover);

(或者考虑用struct，但是不知道如何动态赋值)

### 矩阵拼接

A=[];

A=[A [1,2]]; A=[A,[1,2]];行拼接  A=[A;[1;2]]；列拼接

### 保存变量

save('name.mat','variable1','variable2')

### 整除 求余

rem(a,b)==0  a整除b,结果符号与a相同

mod(a,b)==0  a整除b,结果符号与b相同

### single函数

一般来说，大矩阵计算，如果用single类型的数据能节省一半的内存空间,double数据类型占8个字节，single类型占4个字节，matlab在内部执行的时候是默认转换成double类型进行运算，据说可以从菜单里面改设置变成默认single 未尝试过，matlab里面有single命令可以转换数据格式

## 画图

### 均值加标准差

Average=[12,11,7,7,6,5];
Variance=[0.5,0.4,0.3,1,0.3,0.5];
Time=0:1:5;

errorbar(Time,Average,Variance,'-or')

### 坐标轴

xlim([0.05 0.55]);
ylim([0 0.5]);
xticks([0.1 0.2 0.3 0.4 0.5]);
yticks([0 0.1 0.2 0.3 0.4 0.5]);

### 网格

ax=gca;

ax.YGrid='on'

## 设置

### 设置打印精确度

- format long

```
>> str=['the value of pi=' num2str(pi)];
>> disp(str);
the value of pi=3.1416
```

[(98条消息) MATLAB 显示输出数据的三种方式_Anne033的博客-CSDN博客_matlab输出](