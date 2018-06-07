---
layout: post
title:  "关于时间管理"
date:   2018-05-14 20:20:30 +0800
categories: effective time management
---

## Overview
Program = Data Structure + Algorithm  
Softwore = Program + Document  
:-)

## 查找素数(质数 prime)
### １不是素数
### 只能被１和自身整除的数
### 2^32 + 1 = 4294967297 不是素数，641×6700417=4294967297是合数(by 欧拉)
### 一个数，如果只有1和它本身两个因数，这样的数叫做质数（或素数）。例如 2，3，5，7 是质数，而 4，6，8，9 则不是，后者称为合成数或合数。从这个观点可将整数分为两种，一种叫质数，一种叫合成数。（1不是质数，也不是合数）著名的高斯「唯一分解定理」说，任何一个整数。可以写成一串质数相乘的积

## References
[管理时间是空话，集中精力吃青蛙](http://www.fortunechina.com/column/c/2014-01/24/content_192062.htm)


<img src='https://g.gravizo.com/svg?
abstract class AbstractList;
interface List;
List <|.. AbstractList;
'/>

![Alt text](https://g.gravizo.com/svg?
  digraph G {
    aize ="4,4";
    main [shape=box];
    main -> parse [weight=8];
    parse -> execute;
    main -> init [style=dotted];
    main -> cleanup;
    execute -> { make_string; printf}
    init -> make_string;
    edge [color=red];
    main -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
)

## Push Service Architechture

<img src='https://g.gravizo.com/svg?
digraph G {
    aize ="4,4";
    iOS [shape=box,style=filled];
    Android [shape=box,style=filled];
    Device [shape=box,style=filled];
    edge [color=blue];
    iOS -> RESTful_GW [label="appid, token, topics..."];
    RESTful_GW -> RESTful_GW [label="cache appid..."];
    RESTful_GW -> APNs_Client -> MQ;
    edge [color=black];
    Device -> MQ [label="publish topic"];
    MQ -> { Android; APNs_Client };
    APNs_Client -> APNs -> iOS;
  }
'/>