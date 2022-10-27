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
3. debug : 