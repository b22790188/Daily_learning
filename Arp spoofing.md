---
date : 2022-11-8 20:42
alias : []
---

---

今天的網路通訊協定課程, 主要在介紹arp協定, 助教也用code讓我們對arp進行一些實做. 雖說主要的部份就只是改改source protocol address, source mac address, defalut gateway address, 但確實也讓我對arp有更進一步的理解. 

arp spoofing最主要運用的就是arp中`stateless的特點`, 由於只要收到arp封包, 就幾乎是來者不拒, 將送封包來的對象當成是`真的對象`. 會這樣說的原因在於, 若今天發出arp請求的對象IP被假冒, 則自己的電腦則依舊不會識別, 便將對方放在自己的arp cache裡, 造成訊息被監聽或竄改. 若是惡意人士假冒了default gateway, 則區網內的對外的封包則都會到達有心人士的機器, 造成極大危險.