---
date : 2022-10-20 Thu 10:34
alias :[]
---

## Brute-force






---
## About Burp Intruder
### Attack type (這裡都是使用Simple list的狀況)
1. Sniper : Sniper只有一個payload set，每一次的變動都是針對同一個變數進行替換，直到將payload內的結果換完，才會開始換下一個變數。`ex:若是有pos1,pos2,pos3，3種變數，則是pos1先換，pos2,pos3維持不變，直到3個變數都被換完。`

2. Battering ram : 不管Position中有多少變數，都只有一個payload set，且在替換時，每一個變數位置的值都會相同。`ex : payload為aa,bb,cc，共有兩個變數，則替換方式為aa : aa , bb : bb , cc:cc`
3. Pitchfork : 每一個變數都會有自己的payload set，基本上會使set內的payload個數一樣，因為多出來的payload也不會被替換到。`ex : pos1的payload為aa,bb,cc。 pos2的payload為11,22,33，則嘗試的組合只有aa:11,bb:22,cc:33等組合`
4. Cluster bomb : Cluster bomb也是需要每一個變數都有自己的payload set，但替換方式並不是一對一的，而是一對多。`ex:pos1的payload set為aa,bb,cc。pos2的payload set為11,22,33。則嘗試組合有aa:11,aa:22,aa:33,bb:11,bb:22....等`

### Payload type

1. Simple list
2. Runtime file : 跟使用Simplist 效果相同，但若是因為檔案payload的很大，需要顯示的時候會使得simple list跑很久，若直接匯入檔案則可以解決這個問題。

3. Custom iterator : 共有1~8個position，每一個postion都會有各自的payload，最終，出現的組合會是position1+position2+position3，`也就是pos後方的payload不會跑到前面`

