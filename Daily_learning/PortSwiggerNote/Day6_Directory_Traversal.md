---
date : 2022-11-7 Mon 14:47
alias :[]
---
---

## Directory_Traversal

漏洞問題主要是因為在server端沒有對檔名進行檢查而產生.
舉例來說, 如網站要向server請求特定特定檔案 (ex:`image`), 所做的請求如:
`filename?filename=abc.jpg`

這時如果沒有對filename進行檢查的話, 會造成攻擊者可以在filename上進行竄改, 可以將檔名改成如`../../../../../etc/paaswd`則會將檔案到回到root, 我們再從root到passwd目錄, 就可找到在這台server上有紀錄的使用者,相當的危險.

後面還有其他如`..//..//..//`來對防禦系統做規避等.

---
## How to prevent it
最有效的避免方式就是避免將這些user-supplied輸入傳到檔案系統api中, 若非得要直接將這些輸入傳遞到filesystem api中, 則也應該對這些輸入進行過濾,例如只允許某些特定的value, 或規定參數的開頭必須從某些目錄開始, 來避免漏洞被利用.