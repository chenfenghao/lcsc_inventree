# lcsc_inventree
Inventree import bom from lcsc with python

## 前言
### [Inventree](https://inventree.org/) Introduction
InvenTree is an open-source inventory management system which provides intuitive parts management and stock control. A wide range of features makes InvenTree the perfect choice for businesses and hobbyists alike. InvenTree is designed to be extensible, and provides multiple options for integration with external applications or addition of custom plugins.

### 立创商城 [LCSC](https://www.szlcsc.com/)

这个程序是基于中国大陆版的LCSC，对于海外版本的LCSC的BOM导入未验证
> :warning: This program is based on the Chinese mainland version of LCSC, and the BOM import of the overseas version of LCSC has not been verified

## Let’s start
* 请允许我使用中文
* 新手程序员，多有不足，欢迎提出宝贵意见
* 欢迎帮忙维护代码
* 欢迎再issue中提出问题

### 程序使用环境以及工具
* Python 3.11
* juypter notebook （我猜python ide同样可以运行）
### 所需要的 python lib
* inventree 0.12.1 官方给的库，在inventree docs中有基本的教程
* pandas 1.5.3
* beautifulsoup 4.12.2
* requests 2.13.0
### 程序思路/框架
实在忍受不了一个接一个手动输元器件信息入到inventre中，一直想着用省时省力的方法。还好，官方提供了python api。
怎么获取LCSC的订单里的元器件的具体信息？这让我想到了爬虫，采用爬虫程序对网页信息进行分析。但是LCSC自动获取订单信息需要登录信息等等原因，
技术难度挺大的，也没有必要，所以选择了更简单高效的方法：“手动”，只需要Ctrl+C Ctrl+V就完美避开这个技术难点，只是不优雅。<br>
然后通过Beautifulsoup库对网页信息进行解析，解析完使用pandas采用dataframe形式储存，再使用requests下载图片，最后调用inventree进行创建零件、上传等操作。
### 具体操作
![alt 属性文本](login.png)
