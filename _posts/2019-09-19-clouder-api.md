---
layout: post
title: Clouder api认证
date: 2019-09-17
Author: chinaxjk
tags: [clouder,aliyun]
comments: true
toc: true
pinned: true
---

## 调用Api  
### api概念  
	* api 是一些预先定义的函数，目的是提供应用程序与开发人员基于某软件或硬件得以访问一组历程的能力，而又无需访问源码或者内部工作机制的细节。
### api 特点  
	* 明确定义接口，可以为其他软件提供服务
	* 小到单独函数,大到可以包含数以百计的类和方法，全局函数，数据类型，枚举类型和常量
	* api可以是私有的也可以是开源的
### api的分类  
	1. 面向对象语言 javaApi列表
	2. 库与框架 windows api
	3. api与协议 ldap应用程序接口
	4. api 与设备接口 bios调用接口
	5. webapi google地图api ，新浪微博api ，阿里云api市场
### 为什么要使用api  
	1. 快速扩展功能
	2. 避免造轮子 ，提高开发效率
	3. 降低模块耦合度
### 阿里云市场api专区  
	1. 1000 + api
	2. 云市场 api
## api请求与认证
### webapi协议
	1. 解耦
	2. http协议，包含四部分url，method，headers，body
### api请求方式
	1. get
	2. post
	3. put 
	4. delete
### 状态返回码
	1. 2xx 请求成功
	2. 5xx 服务错误，解决方式 重试
	...   
### api数据格式
	1. JSON格式 简洁，轻量级数据交换格式
	+ 表示对象
	-json最常用格式对象的键值对
	+ 表示数组
	- 和普通js数组一样，表示方式[]
	2. XML格式
### api身份认证及签名认证
	1. APPCODE 简单认证
	+ 请求Header中添加Authorization
	+ 配置Authorization字段为 “APPCODE + 半角空格 +ＡＰＰＣＯＤＥ值
	2. AppKey & AppSecret

## API 调试与调用
### api调试
### Api调用步骤
	1. api文档
	2. 创建应用
	3. 获取授权
	4. 调用ＡＰＩ
### 调用ＡＰＩ
	00
### API调用注意事项
	1. 每个账号下app个数上限１０个，app名称对应账号下唯一
	2. 调用ＡＰＩ的流控制限制为，单个ＩＰ，ＱＰＳ不超过１００
	3. 你有权购买ａｐｉ与ａｐｐ的授权和解除授权，服务提供方授权给你的ａｐｐ的ａｐｉ，你无权操作解除
	4. 您的请求需要包括签名信息

