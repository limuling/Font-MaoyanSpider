## Font-MaoyanSpider
【转行三重奏】-字体反爬复习-利用KNN算法处理动态字体映射。

## [回到总目录](https://github.com/LeoLin9527/ZSpider)
## [KNN原理与实践](http://fishmoon.xyz/2019/12/22/%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0-KNN%E5%8E%9F%E7%90%86%E4%B8%8E%E5%AE%9E%E8%B7%B5/)

## 内容简述
1、一般字体反爬处理思路利用Python的fontTools模块建立字体对应关系。

2、猫眼字体可发现动态编码且相同文字带有随机形变，表现为动态字体坐标偏移量不一致。

3、应对策略：
- 限定对象的坐标值差值在一定阈值内就可以认为是两个相同的数字(已测试，效果差)，如下图很难全部匹配出来
- 利用KNN进行字体坐标处理

4、先用测试集得到每个数字的距离，然后在测试的时候我们对不同的输入（也就是数字）就是距离计算，距离最近的即为相同值。

5、所以此处K值取1，先进行缺失值处理，然后取出特征值和目标值。

6、最后用解析到编码与数字的字典替换原响应中的&#x部分。

![](/common/Pic/result.png)

## 使用说明
1、Python环境与依赖安装略过

2、启动爬虫
```
python run_the_spider.py
```
3、可视化界面
```
cd GUI
python callwindow.py
```
![](/common/Pic/gui.png)

## 欢迎关注
![](/common/Pic/wechat.png)