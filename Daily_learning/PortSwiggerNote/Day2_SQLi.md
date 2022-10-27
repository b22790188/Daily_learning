---
date : 2022-10-14 Fri 00:48
alias :[]
---

---
## Inspect Table name

因為所有SQL內都會有table，可以使用

SELECT table_name , NULL FROM information_schema.tables(在已知兩行的情況下)
來取得table_name名字

當找到之後，可以使用
`SELECT column_name , NULL FROM information.columns WHERE table_name=` '目標table'
+ `僅適用於非Oracle版本的database`

最後確定欄位即表格之後，使用
SELECT 目標欄位1 , 目標欄位2 , FROM 目標表格，即可查看到想看的資料。


---
## Summary
由於目前對於SQL的大致結構及語法還不是到很熟悉，所以使用burpsuite在forward封包的時候常常會因為語法打錯因而造成錯誤，目前還處於邊查邊學的狀況中。

另外，對於不同database系統，如oracle , microsoft等等，也需要能夠看懂portswigger內附的cheat sheet ，來增加可試性，像是不同類型的註解( `#`  ,  ` -- `,)就需要交互去嘗試。

對於今天的lab，自己需要在輸入SQL語法上需更加細心一點，才可以減少許多debug的時間。
