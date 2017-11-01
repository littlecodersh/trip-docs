# 简介

## 初衷

协程已经是出现很久的技术了，也常常有人问到我有没有简单易用的协程网络库推荐。
不像在推荐普通网络库，我可以不假思索的说出Requests，这件事情需要好好考虑怎么回答。

爬虫框架不适合入门也不够灵活，协程网络库都复杂需要重学大部分代码，协程插件又让结果有时变的不可控制也难以和其他协程配合。

后来有一天，有人私聊了我这么一个问题。为什么这样不是协程：

```python
import requests
from tornado import gen, ioloop

@gen.coroutine
def main():
    r = yield requests.get('http://httpbin.org/get/')
    print(r)

ioloop.IOLoop.current().run_sync(main)
```

答案很简单，`requests.get`返回的不是一个`Future`，自然无法运行。

但是，为什么不呢？

所以就有了这个库：

```bash
TRIP: Tornado & Requests In Pair
```

## Apache2 License

本项目中使用了Requests与Tornado的部分源码，故按照其开源协议的要求使用Apache2协议。

简而言之，在将该软件或衍生作品使用Apache2协议发布时，该软件作者及各贡献者仅保留署名权，
用户及二次开发者可以自由修改、复制、发行、翻译、以各种方式向公众提供该软件。
另外，应当注意，对于任何可能由于本软件使用产生的直接、间接的损失，
该软件作者与各贡献者不承担相应的责任。

## 开源协议

```
Copyright 2017 LittleCoder

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```
