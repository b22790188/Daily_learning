---
date : 2022-10-02 23:26 
alias :[]
---

---
## Stream
流 : 可想像成與檔案交流的一個`資料通道`，ex : 檔案是桶子，想要與檔案互動就需要用水管`(流)`將水`(資料)` 給取出來。

不同面向對應不同的流 :

*以Program的角度而言*
1. 輸入流 : 資料(ex: txt檔) -> program : 對`program`來說是輸入 ,因此為`輸入流`
2. 輸出流 : program -> 資料 : 對`program`來說是輸出, 因此為`輸出流`

1. 節點流 : 想成單一條水管連接在program與檔案間 , 單純以水管(stream)做傳輸。
	1. FileInputStream 
	2. FileOutputStream
	3. FileReader
	4. FileWriter

2. 處理流 : 想成在水管上的水質過濾器，處理不想要通過水管的東西。
	![[Java_處理流.png]]


參考 : https://ethan-imagination.blogspot.com/2018/12/javase-gettingstarted-019.html

---

## 緩衝流 

在讀取資料時，每次都以一個byte的方式讀取或寫入，因為是與disk進行互動，來回其實是會耗費相當多時間的，但若是有一個緩衝區將資料預先全部讀進來或寫入，在輸出時一次傳遞更多的資料，也可以減少與disk互動，進而減少時間。

### 用法
主要是套接在`對應的節點流上`，如
```java
BufferedReader br =  new BufferedReader(FileInputStream("test.txt"));
```


mark() 與 reset()
待寫入

---
## 轉換流

轉換流，如其名 ，可以將bytestream轉換為characterstrea。
ex. InputStreamReader即是將

