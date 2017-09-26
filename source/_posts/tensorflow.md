---
title: tensorflow踩的坑
date: 2017-09-14 16:27:04
categories:
- Tensorflow
tags:
- Tensorflow 
- MachineLearning
---
## install
具体详见源码安装吧，cpu-only，一是自己小破本不支持gpu( If I hit five million in the lottery, I would buy a GTX1080ti to play a game first. :)，二是先跑起来再说吧。  
[教程](https://www.tensorflow.org/install/install_sources)  
[github源码](https://github.com/tensorflow/tensorflow)   
run demo可能会出现一些warning，试试下面方法解决。
> mkdir _python_build  
> cd _python_build  
> ln -s ../bazel-bin/tensorflow/tools/pip_package/build_pip_package.runfiles/org_tensorflow/* .  
> ln -s ../tensorflow/tools/pip_package/* .  
> python setup.py develop

　　之后每次修改C++文件, 或者添加, 删除, 移动或修改任何Python文件之后, 都需要运行
`bazel build -c opt //tensorflow/tools/pip_package:build_pip_package`  
重新构建（参数根据情况设置，参考教程吧）。

## 理解图计算
***先构建图，再执行图。***  

* 使用`图  graph` 来表示计算任务.* 在被称之为 `会话 session`的上下文 (context) 中执行图.* 使用 `tensor` 表示数据，看作是一个 n 维的数组或列表，包含`Rank``Shape``Type`* 通过 `变量 Variable`维护状态信息.* 使用` feed` 和` fetch `可以为任意的操作(arbitrary operation) 赋值或者从其中获取数据.

## 交互式的使用
为了便于使用诸如 IPython 之类的 Python 交互环境, 可以使用 `InteractiveSession` 代替 `Session `类, 使用 `Tensor.eval()` 和 `Operation.run()` 方法代替 `Session.run()` . 这样可以避免使用一个变量来持有会话.

## Feed
　　`feed` 机制可以临时替代图中的任意操作中的` tensor `, 可以对图中任何操作提交补丁, 直接插入一个 `tensor`.  
　　`feed` 使用一个 `tensor `值临时替换一个操作的输出结果. 你可以提供 `feed` 数据作为 `run()` 调用的参数. `feed `只在调用它的方法内有效, 方法结束, `feed `就会消失. 最常见的用例是将某些特殊的操作指定为`feed`操作, 标记的方法是使用 `tf.placeholder()` 为这些操作创建占位符.

