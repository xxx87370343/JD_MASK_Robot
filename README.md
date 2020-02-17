# JD_Robot

## 京东抢购
Python爬虫，扫码登录京东网站，查询商品库存，价格，显示购物车详情等。<br/>
可以指定抢购商品，自动购买下单，然后手动去京东付款就行。

## 注意事项
+ 下单前请清空购物车
+ area_id 在浏览器里复制出来是以'-'连接的，请手动换成'_'连接

## 版本历史
+ 2017-03-30 [Python2版实现二维码扫码登陆|开发者已经不维护](https://github.com/Adyzng/jd-autobuy)
+ 2019-07-26 重新实现自动购买下单，下单成功发送邮件提醒
+ 2019-08-08 1.修复了重复添加购物车的bug  2.修复了和别的商品一起提交订单的bug
+ 2019-09-27 去掉了不必要的异常捕捉
+ 2019-10-10 删掉了对golang版本的超链接,因为golang作者辱华
+ 2020-02-04 Super喵喵玄 增加了定时下单的功能
+ 2020-02-17 修复了下单成功却不结束程序的逻辑错误


## 运行环境
Python 3


## 第三方库
- [requests][1]: 简单好用，功能强大的Http请求库
- [bs4][2]: 从HTML或XML文件中提取数据的Python库
- [lxml][2]: lxml is a Pythonic, mature binding for the libxml2 and libxslt libraries



## 环境配置
``` Python
pip install requests
pip install bs4
pip install lxml
```


## 使用帮助
``` cmd
> python spider.py -h
usage: spider.py [-h] [-g GOOD] [-c COUNT]
                     [-w WAIT] [-f] [-s]

Simulate to login Jing Dong, and buy sepecified good

optional arguments:
  -h, --help            show this help message and exit
  -g GOOD, --good GOOD  Jing Dong good ID
  -c COUNT, --count COUNT
                        The count to buy
  -w WAIT, --wait WAIT  Flush time interval, unit MS
  -f, --flush           Continue flash if good out of stock
  -s, --submit          Submit the order to Jing Dong
```

## 实例输出
``` python3 spider.py
+++++++++++++++++++++++++++++++++++++++++++++++++++++++
Mon Feb 17 21:56:34 2020 > 自动登录中... 
登录成功!
+++++++++++++++++++++++++++++++++++++++++++++++++++++++
Mon Feb 17 21:56:39 2020 > 商品详情
编号：100010617232
库存：现货
价格：2299.00
名称：Redmi K30 5G双模 120Hz流速屏 骁龙765G 30W快充 6GB+128GB 深海微光 游戏智能手机 小米 红米
加入购物车链接：http://cart.jd.com/gate.action?pid=100010617232&pcount=1&ptype=1
商品已成功加入购物车！
+++++++++++++++++++++++++++++++++++++++++++++++++++++++
Mon Feb 17 21:56:44 2020 > 订单详情
应付款：￥2299.00
收货人：牟** 180****2551
寄送至： 浙江 台州市 温岭市 太平街道  ****
{"overSea":false,"orderXml":null,"noStockSkuIds":"","reqInfo":null,"hasJxj":false,"addedServiceList":null,"cartXml":null,"sign":null,"pin":"jd_5e7c70b95c7bb","needCheckCode":false,"success":true,"resultCode":0,"orderId":112390498799,"submitSkuNum":1,"deductMoneyFlag":0,"goJumpOrderCenter":false,"payInfo":null,"scaleSkuInfoListVO":null,"purchaseSkuInfoListVO":null,"noSupportHomeServiceSkuList":null,"msgMobile":null,"addressVO":null,"msgUuid":null,"message":null}
下单成功！订单号：112390498799
请前往京东官方商城付款
```

## 注
代码仅供学习之用，京东网页不断变化，代码并不一定总是能正常运行。<br/>
如果您发现有Bug，Welcome to Pull Request.
## 问题提交
请直接提issue或者加我微信:lly19980726.不解决不会使用python等问题.不接商业合作,薅羊毛的🐕勿扰.


[1]: http://docs.python-requests.org
[2]: https://www.crummy.com/software/BeautifulSoup

