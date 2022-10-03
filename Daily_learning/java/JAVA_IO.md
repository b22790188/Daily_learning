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
	![[image/Java_處理流.png]]


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
`待寫入`

---
## 轉換流

轉換流，如其名 ，可以將bytestream轉換為characterstrea。
ex. InputStreamReader即是將InputStream轉為Reader(`bytestream -> characterstream`)

在使用轉換流建構子時也可以指定編碼型式
```java
InputStream isr = new InputStreamReader(System.in, "big5");
```


---
## 資料流

有針對JAVA基礎型別(ex : double , int)的轉換，與電腦本身無關。但須注意`先寫先讀`問題
，因為DataStream是依照順序讀取。(......`待寫入`)


---
## 打印流

主要都屬於輸出流，有PrintWriter , PrintStream。
+ 兩者皆`提供` overload 的 print() method
+ 兩者都沒有throw exception，使用者需要透過錯誤狀態來了解錯誤的相關訊息
+ 兩者都`自帶flush` ，會自動清除緩衝區。

---
## 補充 

常用函數 : 
+ *getByte( ) : 若`無` 參數傳入時，預設以作業系統的編碼將字串以該編碼生成Byte陣列 ，若有指定編碼則以該編碼生成
ex :
```java
String linebuf = "test";
Byte[] bytearray = linebuf.getByte("big5");
//以big5編碼方式生成byte陣列
```
