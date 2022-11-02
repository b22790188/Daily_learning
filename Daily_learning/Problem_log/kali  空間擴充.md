---
date : 2022-10-29 Sat 15:15
alias : []
---

因為最一開始只有在kali上分配100G的空間, 在開始裝一些會用到的軟體後, 感覺之後的空間可能會不夠, 於是google了linux的容量擴充方式, 起初找到許多在windows上用`Easeus partition manager分割完後再進到linux內用 `gparted`來進行空間擴充. 但後來發現自己在用gparted擴充容量時, 自己硬碟的位置沒辦法擴充空間(在前方有unlocated空間的情況下), 後來在一些搜尋後, 在windows上用Ease partition manager將unlocated space 移動到安裝kali的硬碟的後方, 並將其擴充, 在重新進入kali就發現空間有得到擴充了.


但感覺不是一個很正規的擴充方式, 應該是自己在安裝系統時有些地方沒設定好, 才會在gparted上沒辦法擴充, 先將這個問題記錄下來, 等到對作業系統及磁碟部份更熟悉後再回來探討其中原因.



