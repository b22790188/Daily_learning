---
date : 2022-11-19 Sat 16:33
alias : []
---

----

ps  : process status
其中顯示出來的結果, pid代表的是`process id`, tty代表運行的`terminal`, time代表`process從啟動到現在佔用的cpu time`, command代表`執行的命令`.

systemctl : 
用來啟動service 主要參數有`start, stop, enable, disable` ,start及stop就是字面上的開啟跟中止, 而enable,disable指的則是, 是否要在開機時啟動該service.

&
會將要執行的命令放到background中, 不會佔用著終端機.`ex: 在終端機複製檔案時, 如果檔案很大, 則在終端機必須等待複製完成後, 才能夠繼續執行其他命令, 但在cp後使用＆, 則會使得命令跑到背景去執行, 我們也可以繼續執行其他的命令`

fg
`與&相反` , 會將命令從背景帶到前景, 並將結果輸出在前景終端機中

crontab