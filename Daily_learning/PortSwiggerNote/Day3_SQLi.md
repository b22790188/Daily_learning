---
date : 2022-10-15 Sat 15:45
alias : []
---

---
## Blind SQLi

大多數的SQLi，都屬於這個類型。像前幾天的UNION attack，可以很容易的看到錯誤原因，是因為網頁的response會直接將這些漏洞或錯誤給顯示出來，讓我們可以直接從response去竊取到資料，然而現今大多的SQLi都屬於Blind SQLi，差異性在於`Blind SQLi的response中，並不會直接的包含資料庫內的一些資料(ex : 使用者帳密 , 資料庫版本等等)。 所以在使用SQLi的攻擊上，會是需要一步一步去嘗試我們所要取得的資料。

---
## 如何判斷是不是Blinde SQLi

對Request中的變數做一些true vs false的SQL query時，網頁的表現是否有差異性，若是有的話，則高機率是SQLi，如PortSwigger SQLi的lab11, 當query有回傳任何row時，response的內容中就會出現"Welcome back"的字串，反之則否，我們便可以利用這個漏洞來進行Blind SQLi。

---
## Summary

今天主要是學習lab11的部分

在這個部分，因為會用到列舉等暴力破解的方式，因此手動輸入是相當不具備效率的。因此，善用BurpSuite的內建工具，或者是自己使用程式語言來解決這些事情都是效率更佳的方法。
BurpSuite在常使用之後就比較熟悉，但因為目前使用的是Community版本，所以在大量的payload上面速度也比較慢。所以`近期的目標是，要能夠使用程式語言來跑這些payload，讓破解這件事的效率提升。`


到這個部分，使用SQL語法的量就更大了，開始需要花更多的時間去了解各個SQL query背後的涵義，開始覺得這個邊查邊學SQL的狀況有一點沒效率，接下來可能會考慮先去學基礎部分的SQL語法，也正好因為碰上學校正在上資料庫的課程，也有可能會先將PortSwigger WebAcademy SQLi的部分先暫停，先轉往其他類型的攻擊學習，待到SQL較為熟悉之後再回來將SQLi的lab做完。


