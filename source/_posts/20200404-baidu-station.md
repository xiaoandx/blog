---
title: 百度收录网站，主动推送(Python)
date: 20200404 15:50:03
tags: [baidu, Python]
categories: 技巧分享
---

### 说明：

> 当自己创建网站后，在百度上搜索自己德网站时，会显示魏找到内容或者显示无关的内容。如何提交自己的网站让百度快速收录。

下面将演示如何主动提交的网站链接

### 1. 需要将自己的网站链接编辑成Sitemap（即站点地图）

> 就是您网站上各网页的列表。创建并提交Sitemap有助于百度发现并了解您网站上的所有网页。您还可以使用Sitemap提供有关您网站的其他信息，如上次更新日期、Sitemap文件的更新频率等，供百度Spider参考。

1) 手动编辑Sitemap文件命名为：Sitemap.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  
  <url>
      <!-- 网站链接-->
    <loc>https://blog.xiaoandx.wang/2020/04/03/git-reset-hard.html</loc>
    <!-- 时间-->
    <lastmod>2020-04-03T02:54:01.562Z</lastmod>
    
  </url>
  
  <url>
    <loc>https://blog.xiaoandx.wang/2020/04/02/git-how-to-ignore-tracked-files.html</loc>
    
    <lastmod>2020-04-03T02:31:40.303Z</lastmod>
    
  </url>
  
  <url>
    <loc>https://blog.xiaoandx.wang/2020/04/02/git-rewrite-history.html</loc>
    
    <lastmod>2020-04-01T10:41:59.662Z</lastmod>
    
  </url>
  
  <url>
    <loc>https://blog.xiaoandx.wang/2020/03/29/git-basic.html</loc>
    
    <lastmod>2020-03-29T08:59:41.417Z</lastmod>
    
  </url>
  
  <url>
    <loc>https://blog.xiaoandx.wang/tags/index.html</loc>
    
    <lastmod>2020-02-23T14:23:11.000Z</lastmod>
    
  </url>
  
  <url>
    <loc>https://blog.xiaoandx.wang/categories/index.html</loc>
    
    <lastmod>2020-02-23T14:23:11.000Z</lastmod>
    
  </url>
  
</urlset>

```



### 2.搭建python语言运行环境

#### 2.1以下为在 Window 平台上安装 Python 的简单步骤：

- 打开 WEB 浏览器访问https://www.python.org/downloads/windows/

  ![img](https://www.runoob.com/wp-content/uploads/2013/11/721E917D-CCA5-4F37-8FD6-486315EC8CF8.png)

- 在下载列表中选择Window平台安装包，包格式为：*python-XYZ.msi* 文件 ， XYZ 为你要安装的版本号。

- 要使用安装程序 *python-XYZ.msi*, Windows 系统必须支持 Microsoft Installer 2.0 搭配使用。只要保存安装文件到本地计算机，然后运行它，看看你的机器支持 MSI。Windows XP 和更高版本已经有 MSI，很多老机器也可以安装 MSI。

  ![img](https://www.runoob.com/wp-content/uploads/2013/11/20180711-160607.png)

  

- 下载后，双击下载包，进入 Python 安装向导，安装非常简单，你只需要使用默认的设置一直点击"下一步"直到安装完成即可。



#### 2.2在 Windows 设置环境变量

在环境变量中添加Python目录：

**在命令提示框中(cmd) :** 输入

```
path=%path%;C:\Python 
```

按下"Enter"。



**注意:** C:\Python 是Python的安装目录。

也可以通过以下方式设置：

- 右键点击"计算机"，然后点击"属性"
- 然后点击"高级系统设置"
- 选择"系统变量"窗口下面的"Path",双击即可！
- 
- 然后在"Path"行，添加python安装路径即可(我的D:\Python32)，所以在后面，添加该路径即可。 **ps：记住，路径直接用分号"；"隔开！**
- 最后设置成功以后，在cmd命令行，输入命令"python"，就可以有相关显示。

![img](https://www.runoob.com/wp-content/uploads/2013/11/201209201707594792.png)

#### 2.3运行Python

有三种方式可以运行Python：

##### 1、交互式解释器：

你可以通过命令行窗口进入 Python，并在交互式解释器中开始编写 Python 代码。

你可以在 Unix、DOS 或任何其他提供了命令行或者 shell 的系统进行 Python 编码工作。

```
$ python # Unix/Linux
```

或者

```
C:>python # Windows/DOS
```

以下为Python命令行参数：

| 选项   | 描述                                                   |
| :----- | :----------------------------------------------------- |
| -d     | 在解析时显示调试信息                                   |
| -O     | 生成优化代码 ( .pyo 文件 )                             |
| -S     | 启动时不引入查找Python路径的位置                       |
| -V     | 输出Python版本号                                       |
| -X     | 从 1.6版本之后基于内建的异常（仅仅用于字符串）已过时。 |
| -c cmd | 执行 Python 脚本，并将运行结果作为 cmd 字符串。        |
| file   | 在给定的python文件执行python脚本。                     |

##### 2、命令行脚本

在你的应用程序中通过引入解释器可以在命令行中执行Python脚本，如下所示：

```
$ python script.py # Unix/Linux
```

或者

```
C:>python script.py # Windows/DOS
```

**注意：**在执行脚本时，请检查脚本是否有可执行权限。

##### 3、集成开发环境（IDE：Integrated Development Environment）: PyCharm

PyCharm 是由 JetBrains 打造的一款 Python IDE，支持 macOS、 Windows、 Linux 系统。

PyCharm 功能 : 调试、语法高亮、Project管理、代码跳转、智能提示、自动完成、单元测试、版本控制……

PyCharm 下载地址 : https://www.jetbrains.com/pycharm/download/

PyCharm 安装地址：[http://www.runoob.com/w3cnote/pycharm-windows-install.html](https://www.runoob.com/w3cnote/pycharm-windows-install.html)

![img](https://www.runoob.com/wp-content/uploads/2014/06/pycharm_ui_darcula.png)



### 3.编写提交代码

```python
#coding:utf-8
import requests
import time
from bs4 import BeautifulSoup as bp

print ('自动推送开启....','utf-8')
time.sleep(0.5)
# your sitemap file url
site_url = 'https://xiaoandx.icu/links/icu/baidusitemap.xml'

try:
    print ('正在获取sitemap链接....','utf-8')
    data_ = bp(requests.get(site_url).content,'lxml')
except Exception.e:
    print (e)

list_url=[]

def get_(data):
    headers={'User-Agent':'curl/7.12.1 ',
             'Content-Type':'text/plain '}
    try:
        r = requests.post(url='http://data.zz.baidu.com/urls?site=https://xiaoandx.icu&token=XXXXXXXXXXXXXXXXXXXXXXXX',data=data)
        print (r.status_code)
        print (r.content)
    except Exception as e:
        print (e)

print ('---------------------------------')
for x,y in enumerate(data_.find_all('loc')):
    print ( x,y.string)
    list_url.append(y.string.replace('http://','http://'))

print ('---------------------------------')

print ('链接开始推送....','utf-8')

for x in list_url:
    print ('当前推送条目为:',x)
    get_(x)
```

代码说明：

> http://data.zz.baidu.com/urls?site=https://xiaoandx.icu&token=XXXXXXXXXXXXXXXXXXXXXXXX
>
> 1. 登录百度站长然后，点击站点管理![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404160558.png)
> 2. 点击添加站点后进行验证（验证过程跳过）
> 3. 验证通过后点击对应网站获取对应网站的提交API 和 token![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404160832.png)
> 4. 将地址替换代码中的提交api地址

### 4.安装代码需要的运行库

> 因为已经配置了环境变量所以打开cmd 冰切换到python安装路径下的Scripts文件夹下![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404161313.png)

#### 4.1安装requests支持库

```
pip install requests
```

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404161339.png)

当出现以上显示说明安装成功



#### 4.2安装bs4支持库

1. 下载bs4：
   https://www.crummy.com/software/BeautifulSoup/bs4/download/  python若比较新，就下载最新版本即可

 ![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404161658.png)

2. 下载完成后，将其解压到你放置python安装包的地方，存放在beautifulsoup.**文件下

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404161753.png)



3. 打开电脑的命令提示行，即以管理员身份打开，具体步骤如下：按快捷键win+R，在框中输入cmd，回车，进入命令提示行，运用cd命令进入你、第二步放置安装包的位置

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404161819.png)



4. 安装bs4:使用命令：python setup.py install

#### 4.3 安装lxml支持库

> 注意：安装lxml前需要先安装一下wheel

```
pip install wheel
```

安装成功后安装lxml支持库

```
pip install lxml
# 等待下载安装
```

### 5.运行代码

```
python   xx.py（完整路径）
```

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404162629.png)

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404162548.png)

 出现以下提示则提交成功

### 6.等待3-10天，百度就会收录

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200404162755.png)