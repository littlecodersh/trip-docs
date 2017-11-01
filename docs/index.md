# Trip: 让协程与网络服务人类

[![pypi][pypi-image]][pypi]
[![][pyversion-image]][pypi]
[![][thanks-image]][thanks]
[![][english-image]][english]

Trip 是一个协程的网络库，使用如Requests一般简单的操作就可以让网络延时不再阻塞你的程序。

Python的协程可以这么简单（兼容Python 2.7-3.7）：

```python
import trip

@trip.coroutine
def main():
    r = yield trip.get('https://httpbin.org/get', auth=('user', 'pass'))
    print(r.content)

trip.run(main)
```

有了协程，同样的代码量，[一百份请求一份时间][demo]。

Trip的名字来源于其两个依赖包，也旨在将两个包的内容融合起来：'Tornado & Requests Is Paired'。
在兼容中使用了大量上述两个包结构和处理的代码，我只是做了一些简单的整合工作，感谢
[Tornado][tornado]与[Requests][requests]让我能如此轻易的完成本项目的编写。


通过使用Trip，你可以充分使用Requests的各种特性，包括但不限于：带持久 Cookie 的会话、
浏览器式的 SSL 认证、自动内容解码、 基本/摘要式的身份认证、 优雅的 key/value Cookie。
同时你的请求又和使用Tornado的AsyncHTTPClient一般是协程的，网络延时不再会阻塞你的
程序，在程序正常运行的时候你可以同时等待多项任务的完成。

爬虫耗时太久优化困难吗？各种协程网络框架难以使用吗？大型爬虫框架臃肿无法灵活定制吗？
试试Trip，你不会后悔的！

无论你是使用的2.7，3.3，3.7，Trip都可以完美运行。

## 用户手册

这部分内容是最基础的使用说明，如果你有Requests的使用基础，那么这部分完全可以快速浏览甚至
跳过。我不会怪你不好好看这部分文档的，当然也别因为这里的问题来问我哦。

* [简介](user/intro.md)
    * [初衷](user/intro/#_2)
    * [Apache2 License](user/intro.md#apache2-license)
    * [开源协议](user/intro.md#_3)
* [安装Trip](user/install.md)
    * [使用pip安装](user/install.md#pip)
    * [获得源码](user/install.md#_1)
* [快速上手](user/quickstart.md)
    * [发送请求](user/quickstart.md#_2)
    * [传递URL参数](user/quickstart.md#url)
    * [响应内容](user/quickstart.md#_3)
    * [二进制响应内容](user/quickstart.md#_4)
    * [JSON响应内容](user/quickstart.md#json)
    * [原始响应内容](user/quickstart.md#_5)
    * [定制请求头](user/quickstart.md#_6)
    * [更加复杂的POST请求](user/quickstart.md#post)
    * [响应状态码](user/quickstart.md#_7)
    * [响应头](user/quickstart.md#_8)
    * [Cookie](user/quickstart.md#cookie)
    * [重定向与请求历史](user/quickstart.md#_9)
    * [超时](user/quickstart.md#_10)
    * [错误与异常](user/quickstart.md#_11)

[pyversion-image]: https://img.shields.io/pypi/pyversions/trip.svg
[pypi]: https://pypi.python.org/pypi/trip
[pypi-image]: https://img.shields.io/pypi/v/trip.svg
[english]: https://github.com/littlecodersh/trip/blob/master/README_EN.md
[english-image]: https://img.shields.io/badge/english---%3E-yellow.svg
[thanks]: https://saythanks.io/to/littlecodersh
[thanks-image]: https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg
[demo]: https://gist.github.com/littlecodersh/6803d2c3382de9a7793a0189db72f538
[tornado]: https://github.com/tornadoweb/tornado
[requests]: https://github.com/requests/requests
[document]: http://trip.readthedocs.io/zh/latest/
[homepage]: http://github.com/littlecodersh/trip
