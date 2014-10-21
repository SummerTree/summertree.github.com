---
layout: post
title: "sqlite time function"
categories:
tags:
---

-------
1. 本周
	strftime('%W', tastings.date) = strftime('%W', 'now')
2. 当天
	strftime('%Y%W', createTime, 'unixepoch'), strftime('%Y%W', 'now', 'utc')

3. define kLastDate @"date(createTime, 'unixepoch') = date('now', '-1 day')"
4. define kThisWeek @"strftime('%%Y%%W', createTime, 'unixepoch') = strftime('%%Y%%W', 'now', 'utc')"
5. define kLastWeek @"strftime('%%Y%%W', createTime, 'unixepoch') = strftime('%%Y%%W', 'now', '-7 day', 'utc')"

