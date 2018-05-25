---
layout: post
title:  "Tornado Coroutine 实现理解"
date:   2018-05-24 20:00:30 +0800
categories: python tornado coroutine
tags: python tornado coroutine generator future
---

<ul>
{% for tag in page.tags %}
<li><a href="#">{{ tag }}</a></li>
{% endfor %}
</ul>

## Overview
在 coroutine 上下文中，将 generator 返回的 future 添加至 io_loop（through add_future with Runner.run as callback function invoked by Future.set_result），并在 Runner.run 中再以 gen.send(future.res) 或 gen.throw(future.exc) 方法获得下一个 future 并再添加至 io_loop。以这种方式达到循环调用 generator 的效果直至其返回(raise gen.Return)或运行结束(raise StopIteration)。接着在 coroutine 结束之前使用 result_future.set_result 方法通知本 coroutine 的 caller(如果有的话)，使其重新被调度运行。


这就是在 @coroutine decorator 包装下，python generator 被自动调度，完成系列 asynchronous IO operations 的全过程。整个过程，异步回调被很好的隐藏起来，使用同步的写法，实现异步逻辑。在这当中，future 发挥着重要作用，它做为 generator 与 io_loop 间的粘合剂，使 generator 在合适的时机被重新调度并带回中间处理的结果。


io_loop 可认为是 IO driven scheduler, generator 为 schedule unit, generator 中发起 async IO 请求的地方为 yield point, 在此让出 CPU 给其它 generators, 直到  IO complete interrupt(callback)发生，generator 重新得到调度，在 yield point 下一行继续执行。


整个调度过程不涉及操作系统级别的上下文切换，线程时间片内，可以发生 N 次这样的用户级别的，IO 事件驱动的调度，不浪费一点时间在等待上面，充分利用 CPU，非常适合做为高并发解决方案。


其实本质就是 wait-notify, 但 coroutine 的写法可以让我们不需要另外定义 callback handler, 直接在 yield point 下面接着写 IO 后处理即可。
写法上面的转变其实还蛮容易接受，但要基于这套机制做一些扩展或改造，还是需要深入其内部。源码面前，了无秘密：）
