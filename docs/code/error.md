# 格式类
1. UnicodedecodeError:gbk codec can't decode
	原因：编码方式不对
	解决：二进制读取；或者改变编码方式（在open相关的地方加上`encoding='utf-8'`)
	[https://blog.csdn.net/qq_31267769/article/details/109128882](https://blog.csdn.net/qq_31267769/article/details/109128882)转载

2. 