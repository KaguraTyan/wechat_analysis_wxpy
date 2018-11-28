# wechat_analysis_wxpy
通过python，连接到微信账号，收集好友性别、城市、个性签名等公开信息，使用 Python 进行数据统计与分析，得到你专属的朋友圈的分析报告！

博客地址：https://blog.csdn.net/m511655654/article/details/82752396 

# 1、准备工作
# 1.1 环境配置
- 编译环境：Windows10

- 编程语言：Python3.6

- 编译器IDE：Pycharm

- 浏览器工具：Chrome浏览器

# 1.2 wxpy库介绍
采用第三方库wxpy进行微信登录和信息获取。

具体细节文档参考https://wxpy.readthedocs.io/zh/latest/

wxpy的一些常见的场景

> 控制路由器、智能家居等具有开放接口的玩意儿
> 运行脚本时自动把日志发送到你的微信
> 加群主为好友，自动拉进群中
> 跨号或跨群转发消息
> 自动陪人聊天
> 逗人玩
...
总而言之，可用来实现各种微信个人号的自动化操作

# 1.3 wxpy库安装
wxpy 支持 Python 3.4-3.6，以及 2.7 版本

将下方命令中的 “pip” 替换为 “pip3” 或 “pip2”，可确保安装到对应的 Python 版本中

1、从 PYPI 官方源下载安装 (在国内可能比较慢或不稳定):
```sh
$ pip install -U wxpy
```

2、从豆瓣 PYPI 镜像源下载安装 (推荐国内用户选用):
```sh
$ pip install -U wxpy -i "https://pypi.doubanio.com/simple/"
```
# 1.4 登录微信
使用bot()登录微信
```sh
# 导入模块
$ from wxpy import *
# 初始化机器人，扫码登陆
$ bot = Bot()
# 获取所有好友
$ my_friends = bot.friends()
$ print(type(my_friends))
```
输出结果
```sh
Getting uuid of QR code.
Downloading QR code.
Please scan the QR code to log in.
```
弹出二维码进行扫描，扫描后输出
```sh
Please press confirm on your phone.
Loading the contact, this may take a little while.
Login successfully as XXXX
<class 'wxpy.api.chats.chats.Chats'>
```
# 2.2 数据展示
采用 ECharts饼图 进行数据展示。

# 3、微信好友城市统计
# 3.1 数据统计
统计城市，此处只统计全国范围内的城市，如果写了国外，则记为“其他”。

# 3.2 数据展示
本想采用ECharts地图 来进行好友分布的数据呈现，结果网站在维护，无法打开，故通过下载echarts相关组件和js文件进行展示。

echarts官网下载  http://echarts.baidu.com/download.html

echarts源代码压缩包、jquery.js、echarts.min.js、china.js下载
链接：https://pan.baidu.com/s/1EIN4j0Avjut46Ljku1_SMQ 密码：9dtm

# 4、微信好友个性签名统计
# 4.1 数据统计
统计个性签名，并存至本地'signatures.txt'

# 4.2 数据展示
# 4.2.1 安装库
对个性签名文档做文本处理，需要安装以下第三方库文件

# 4.2.2 读取文本
# 4.2.3 加载停用词
百度“停用词表”，网上资源有很多可以下载，此处由于个性签名的文本较小，故只剔除了部分常见停用词，如的、了、啦、于、都、一、而、就、之等。
# 4.2.4 词频统计
# 4.2.5 词云展示

# 5、总结与展望
通过wxpy获取微信好友的性别、地区、个性签名等信息分析朋友圈好友基本属性，也可通过wxpy的其他功能进行微信分析，具体拓展可以根据兴趣继续实现https://wxpy.readthedocs.io/zh/latest/。
