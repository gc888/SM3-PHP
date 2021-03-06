# SM3-PHP

国密标准SM3的原生PHP实现。

## 前言

在开发本库的过程中，发现了 *PHP* 的三个**痛点**，敬请各位**务必**要有所了解:

1. **PHP本身对其他进制转换为二进制，由于浮点数的长度特性，会造成数据丢失**，这样就会造成运算结果的错误，需要自己重写；
2. **PHP的位运算符没法直接进行二进制变量的与或非运算**，必须得自己重写；
3. 碍于PHP本身的解释型、弱类型语言特点，**运行速度没有C快**，所以并不是最优选择。

但我们常说，看问题要有两面性。 

尽管 **PHP** 本身有诸多问题，唱衰之声不断，但仍然发展到今天的生态规模， 
很多时候，我们的实际性能需求并没有严格到要求我们去考量语言之间的速度差异，而重在功能的实现。 

况且，上面提到的诸多痛点都已经被我封装在了这个库里， 
性能的优化交给我来做，大家只要负责调用，来实现业务逻辑即可。

也希望大家来都来了，点个 **Watch** 和 **Star** ，持续关注一下。在此拜谢！

## 特点

1. 纯原生 *PHP* 代码，不额外依赖扩展项；
2. *OOP* + *Composer* ，更优雅，安装更简单；
3. 使用命名空间，防止变量名、方法名污染；
4. 引入了 *Composer* 的 *PSR-4* 规范，进行类的自动加载；
5. 代码注释完整，

可配合《[SM3密码杂凑算法](http://www.sca.gov.cn/sca/xwdt/2010-12/17/1002389/files/302a3ada057c4a73830536d03e683110.pdf)》食用，
方便进一步学习和研究本算法。


## 要求

* *php* >= 5.3
* 已安装 *composer*


## 安装

本类库仅支持 *composer* 安装

1. 安装 *composer*

    详见 《[如何安装 Composer](https://pkg.phpcomposer.com/#how-to-install-composer)》
2. 安装慢可更换中文镜像

    由于大量先前的镜像失效，所以目前(2019-11-25)推荐使用阿里云镜像
    
    更换阿里云镜像方式详见拙笔 《[向先行者致敬,迎接 Composer 的未来！](https://blog.doylee.cn/composer-chinese-mirror/)》
3. `composer require ch4o5/sm3-php`
4. `composer install`
5. `composer update`


## 快速开始

在根目录中的 *demo.php* 中，进行了简单的调用示范：

```php
<?php
/**
 * demo @ sm3-php
 *
 * Code BY ch4o5
 * 10月. 12th 2019
 * Powered by PhpStorm
 */

require 'vendor/autoload.php';

$sm3 = sm3('abc');
echo $sm3;
``` 
你也可以在 *examples/* 目录下找到更多的使用示例。

## 目录结构

- *src/*
    源码目录，命名空间为`SM3`

- *demo.php*
    演示代码
    
- *composer.json*
    *Composer* 配置文件
    

## 开源许可

本项目遵从 *Mozilla* 许可：

* 修改源码后不可以闭源；
* 新增代码无需采用相同许可证；
* 需要对源码的修改之处，提供说明文档
    
