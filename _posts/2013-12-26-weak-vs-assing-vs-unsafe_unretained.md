---
layout: post
title: "weak vs assing vs unsafe_unretained"
categories: 
tags: [iOS]


---

 A weak reference does not extend the lifetime of the object it points to, and automatically becomes nil when there are no strong references to the object
 [Apple Doc](https://developer.apple.com/library/mac/releasenotes/ObjectiveC/RN-TransitioningToARC/Introduction/Introduction.html)
