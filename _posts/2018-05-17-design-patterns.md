---
layout: post
title:  "Design Patterns"
date:   2018-05-17 20:00:00 +0800
tags: GOF23 GRASP OODP
---

## Overview
谈到设计模式，C++ guys 首先就会想到 GOF23.  
23种模式分为创建模式，结构模式和行为模式三大类．  

如何合理创建对象，对象间的关系以及过象在协作中解决问题. 面向对象的软件设计需要解决的也正是这三大类问题．

## GOF23

Purpose | Desgin Pettern | Aspect(s) that can vary
--------|----------------|------------------------
Creational | Abstract Factory(87) | families of product object
           | Builder(97) | how a composite object gets created
           | Factory Method(107) | subclass of object that is instantiated
           | Prototype(117) | clsss of object that is instantiated
           | Singleton(127) | the sole instance of a class
 Structural | Adapter(139) | interface to an object
            | Bridge(151) | implementation of an object
            | Composite(163) | structure and composition of an object
            | Decorator(173) | responsibility of and object without subclass
            | Facade(185) | interface to a subsystem
            | Flyweight(195) | storage costs of objects
            | Proxy(207) | how an object is accessed; its location
Behavioral | Chain of Responsibility(223) | object that can fulfill a request
           | Command(233) | when and how a request is fulfilled
           | Interpreter(243) | grammar and interpretation of a language
           | Iterator(257) | how an aggregate's elements are accessed, traversed
           | Mediator(273) | how and which objects interact with each other
           | Memento(283) | what private information is stored outside an object, and when
           | Observer(293) | number of objects that depend on another object; how the dependent objects stay up to date
           | State(305) | states of an object
           | Strategy(315) | an algorithm
           | Template Method(325) | steps of an algorithm
           | Visitor(331) | operations that can be applied to object(s) without changing their class(es)


## GRASP
Information Expert  
Creator  
High cohesion  
Low Coupling  
Controller

Indriection  
Polymorphism  
Pure Frabrication  
Proected variation  

## OODP
### OCP - 开闭原则
### SRP - 单一职责原则
### DIP - 依赖倒原则
### LSP - 里氏替换原则
### ISP - 接口隔离原则
### LoD - 迪米特法则
### CARP - 合成/聚集复用原则

