---
layout: post
title: "UIImageView drawRect"
categories: iOS小坑
tags: iOS


---

由于排版问题，需要在UIImageView上添加分割线。最开始的想法是在继承它，并在子类的drawRect:方法中用CoreGraphic API手动画上线条。
尝试过后发现完全不起作用，查了相关资料，发现UIImageView不支持重写drawRect:，文档提示如下

        Subclassing Notes
		Special Considerations

		The UIImageView class is optimized to draw its images to the display.
	 UIImageView will not call the drawRect: method of a subclass. If your 
	 subclass needs custom drawing code, it is recommended you use UIView as 
	 the base class.

最后解决方式是在UIImageView添加CALayer，在CALayer把线条画出来