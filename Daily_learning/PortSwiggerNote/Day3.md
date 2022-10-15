---
date : 2022-10-15 Sat 15:45
alias : []
---

---
## Blind SQLi

大多數的SQLi，都屬於這個類型。像前幾天的UNION attack，可以很容易的看到錯誤原因，是因為網頁的response會直接將這些漏洞或錯誤給顯示出來，讓我們可以直接從response去竊取到資料，然而現今大多的SQLi都屬於Blind SQLi，差異性在於`Blind SQLi的response中，並不會直接的包含資料庫內的一些資料(ex : 使用者帳密 , 資料庫版本等等)。 所以在使用SQLi的攻擊上，會是需要一步一步去嘗試我們所要取得的資料。

---
## 如何判斷是不是SQLi

對Request中的變數做一些true vs false的SQL query時，網頁的表現是否有差異性，若是有的話，則高機率是SQLi，如PortSwigger SQLi的lab11, 當query有回傳任何row時，response的內容中就會出現"Welcome back"的字串，反之則否，我們便可以利用這個漏洞來進行Blind SQLi。

---
## Summary



