---

title: 快速改变网站为黑灰色调（css）
date: 20200405 11:46:03
tags: [Web, CSS]
categories: 技巧分享
---

### 说明：

> 通过在css全局中加入以下代码，可使网站整体色调改变

下面将演示改变前后的区别

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405115233.png)

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405115204.png)



### 1. 修改网站的全局CSS

> 如果只需要改变某一个页面色调，只用在该页面中加入css代码即可

#### 1.1 cs

```css
html,body{
 	filter: grayscale(100%);
	-webkit-filter:grayscale(100%);
	-moz-filter:grayscale(100%);
	-ms-filter:grayscale(100%) ;
	-o-filter:grayscale(100%);
}
```

#### 1.2 JavaScript

```javascript
document.documentElement.style.filter="grayscale(100%)"
```



### 2.查看效果

> 查看修改后的效果，显示效果无误后即修改成功



### 3.拓展想法

> 可以运用JavaScript来实现动态改变，设定指定时间区段来改变网站色调



### 4.大厂的代码

#### 4.1 百度

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405120417.png)

#### 4.2 淘宝

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405120510.png)

#### 4.3 网易云音乐

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405120551.png)

#### 4.4 360首页

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405120623.png)

#### 4.5 腾讯

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405121410.png)

#### 4.6 掘金

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405120723.png)

#### 4.7 CSDN

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405120753.png)

#### 4.8 中国中央政府网

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405120831.png)

#### 4.9国务院新闻办公室

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200405120849.png)