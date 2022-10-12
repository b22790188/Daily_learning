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
2.  query中對應columns需擁有相同的`資料型態` (意即需要依照想要攻擊的型態去測試`不同欄位`)

## 尋找行數的辦法
1. order by語法在SQL中做為`順序排序`的語法，可以使用如
	order by 1--
	order by 2--
	order by 3--
	
	等方式來判斷行數。
	因為排序是依照現有的行數下去做排序，當超過行數時便會報錯，因此可以得知query的行數。
	
2. Union+SELECT+NULL--
	跟第一點提到的方式相同，因為需要行數相同，否則會報錯。
	當NULL個數與行數匹配時，會額外多出一列NULL。
	
	這裡比較特別的是選擇`NULL`作為測試值。原因為`NULL`是可以被轉換成常見的datatype的，因此使用NULL作為payload是可以增加測試成功的機率。


### 資料型別的測試(使用Union+Select+Null)
1. 若要查找字串類型的資料，則將該行的`NULL`轉換成字串形式如`UNION+SELECT+NULL,'a',NULL--`等，若是資料型別失敗的話則會報錯。


### Additional
若是在單行中讀取多個數據時，可以使用如 `~` 的符號來區別，增加辨識度。

