---
date : 2022-10-27 Thu 22:49
alias : []
---

---
## Lab - username enumeration via subtly different response

這個lab的原理很好理解,  因為網站對於不同的狀況會有不同的回應. 所以可以加以利用這點來破解. 像是這個lab中, 當`使用者名稱錯誤,密碼錯誤時,`網頁的回應是`invalid username`,然而當`username正確, 密碼錯誤時`,網頁的回應會是`invalid password`. 再加上lab有給candidate payload, 所以可以先試username, 再試password, 很快就可以解出lab

---

## lab 2-FA simple bypass
這個lab的問題在於, 網頁對於第二步驗證沒有做其他檢查, 因此可以直接透過網址列修改登錄頁面.

像這個lab中, 只要先創建好自己的帳號, 並且進入到網站內部後, 更改url, 便可以使得駭客不需要輸入驗證碼就可以進入某使用者的帳號.(在已知帳號密碼的情況下)

---
## lab 2-FA broken logic



