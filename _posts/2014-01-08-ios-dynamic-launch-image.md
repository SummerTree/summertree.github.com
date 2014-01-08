---
layout: post
title: "iOS dynamic launch image"
categories: iOS
tags:


---

# iOS动态启动页
我们会碰到这样的场景，需要动态变化启动页，比如根据季节来使用不同的图片，但是又不想要重新发布版本。解决方案是动态更换Defualt.png，可以通过NSBundle来获取app的启动页路径，再在程序运行时替换它。