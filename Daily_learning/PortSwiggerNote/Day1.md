---
date : 2022-10-12 Wed 23:11
alias : []
---

## SQL Injection

use -- to comment remainder of query

### Union attack 
利用SQL中Union的語法，來將injection合併到其他query中。
要使用Union attack的方式須至少滿足以下兩點 : 
1.  各個不同的query需具備相同的column數 (意即需要`判斷該query的column數`)
2.  query中對應columns需擁有相同的`資料型態` (意即需要依照ㄒㄧㄤ)


1. order by
	order by語法在SQL中做為`順序排序`的語法，可以使用如`order by 1--`的方式來確定
1. Union+SELECT+NULL
	1. why use null
	2. 
