---
date : 2022-10-27 00:39 Thu
alias : []
---
因為目前還不熟悉vim, 但因為想學習kali,所以也所以也決定在kali上安裝vscode, 簡單紀錄一下安裝過程

1. 使用dpkg -i(`i參數代表安裝`)至下載deb的地方 安裝vscode
```
dpkg -i code_1.72.2-1665614327_amd63.deb
```
2. 在已經有一個cpp檔的情況下進入到vscode內之後先按下右上角的執行,行vscode會列出系統上偵測到的編譯器, 選擇完後, vscode會自動產生task.json,也就是將剛剛所選的編譯器設定為預設編譯器,之後就不用再選擇了.
3. debug : 在右上角按鈕旁選擇齒輪( 新增偵錯設定,英文為Add debug configuration), 之後在產生launch.json檔. 設定至此完成

目前因為對於這些json檔內的參數都不熟悉,所以中間出問題的時候也不知道怎樣去修改, 日後有時間再來去對這些參數做研究, 這次最大主問題是`一開始沒裝到gdb!!`原本以j為kali有內建,後來才發現原來是需要自己裝,被自己蠢了一波.


參考 : https://code.visualstudio.com/docs/cpp/config-linux