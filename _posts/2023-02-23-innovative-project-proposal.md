---
layout: post
title: 自適應眼鏡技術
author: [Jacques Wang]
category: [Lecture]
tags: [NTOUEE]
---

This homework is to propose an innovative project and describe the key features, list all Design Considerations and the required technologies, then draw the System Block Diagram.

---
## 自適應眼鏡

### 眼科醫生演示近視遠視散光
<iframe width="885" height="498" src="https://www.youtube.com/embed/frFwuF1fbM0" title="【你有視力問題嗎?】眼科醫生演示近視遠視散光" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

**各種眼鏡(近視、散光、遠視、老花):**<br>

![](https://media.gettyimages.com/vectors/various-black-silhouette-glasses-eyeglasses-frames-set-sunglasses-vector-id1003883462)

---
**近視比例:**<br>
![](https://www.taiwanpb.org/uploadfile/C01/images/%E6%9C%AA%E5%91%BD%E5%90%8D-1-2(1).jpg)


---
### Homework Report
**Contents:**<br>

### 應用功能說明
1. 判斷度數
2. 調整度數(定時、可關閉)

### 設計考量與相關技術
**系統設計考量：**<br>
1. 操作方式:可塑性透明鏡片及半流體填充
2. 動力方式:微型馬達
3. 供電方式:鋰電池及太陽能板
4. 聯網方式:WiFi或BT to 手機

**所需相關技術：**
1. 調整度數:軟式高透光鏡片、高透半流體
2. 度數判斷:超音波、光學判斷
3. 接收指令：APP設定

### 系統方塊圖
![](https://github.com/rkuo2000/MCU-course/blob/main/images/FutureHome_kitchen_robot.png?raw=true)

---
## Design Methodology (設計方法)
* Top-Down Design  ：由上層應用分析再區分出下層個別功能及所需軟硬體設計
* Bottom-Up Design ：由底層軟硬體元件往上組合出上層所需應用功能

---
## Market Analysis (市場分析)
![](https://www.modernmgz.com/wan2/upload/images/20180710154032.jpg)

---
### TAM of Future Home Products
目標客群為近視、遠視、散光、老花等人群(主要為近視).<br>

---
### Taiwan Households = 8.93M (台灣 9百萬戶）
* [Total number of households in Taiwan from 2010 to 2020(in 1,000s)](https://www.statista.com/statistics/330804/taiwan-national-total-number-of-households/#:~:text=By%20the%20end%20of%202020,households%20in%20the%20previous%20year.)

### Japan Households = 57.2M (日本 5千7百萬戶)
* [Number of Households in Japan](https://www.helgilibrary.com/indicators/number-of-households/japan/) 

### South Korea Households = 19.9M (南韓 2千萬戶)
* [Number of Households in South Korea](https://www.helgilibrary.com/indicators/number-of-households/south-korea/)

---
### American Households = 129.93M (美國 1.3億戶)
* [Number of households in the U.S. from 1960 to 2021(in millions)](https://www.statista.com/statistics/183635/number-of-households-in-the-us/)<br>
* [The average American household consisted of 2.51 people in 2021.](https://www.statista.com/statistics/183648/average-size-of-households-in-the-us/)<br>

---
### [Number of private households in selected European countries in 2020](https://www.statista.com/statistics/868008/number-of-private-households-in-the-eu/)
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Households_number_Europe2020.png?raw=true)
* Germany households = 40,120.9K **(德國 4千萬戶)**
* France households  = 30,304K **(法國 3千萬戶)**
* United Kingdom households = 27,792K **(英國 2千8百萬戶)**
* Italy households = 26,079K **(義大利 2千6百萬戶)**
* Turkey households = 24,920.1K **(土耳其 2千5百萬戶)**
* Spain households = 18,793.9K **(西班牙 1千9百萬戶)**
* Poland households = 14,723.6K **(波蘭 1千5百萬戶)**

---
### Germany Households = 40.546M (in 2020)
* [Number of households in Germany from 2000 to 2020, by size(in 1,000)](https://www.statista.com/statistics/464187/households-by-size-germany/) 
  - one person: 16,476K
  - two persons: 13,778K
  - three persons: 4,915K
  - four persons: 3,970K
  - five persons: 1,407K
  
---
### France Households = 29.7M 
* [Number of Households in France](https://www.helgilibrary.com/indicators/number-of-households/france/)
* The average household size in France in 2020 is **2.2** people per household.

---
### UK Households = 28.267M 
* [Number of Households in UK ](https://www.ibisworld.com/uk/bed/number-of-households/44090/)
* [Number of households in the United Kingdom in 2020, by type of household(in 1,000s)](https://www.statista.com/statistics/961002/households-in-the-united-kingdom-uk-by-type/)<br>

---
### Canada Households = 10.5M (加拿大 1千萬戶)
* [Number of families in Canada from 2006 to 2021(in millions)](https://www.statista.com/statistics/443323/families-in-canada/)

### Mexico Households = 34.8M (墨西哥 3千4百萬戶)
* [Number of Households in Mexico](https://www.helgilibrary.com/indicators/number-of-households/mexico/) 

---
### Brazil Households = 72.4M (巴西 7千2百萬戶)
* [Number of households in Brazil from 2012 to 2019(in 1,000s)](https://www.statista.com/statistics/870646/brazil-number-households/)

### Argentina Households = 13.8M (阿根廷 1千3百萬戶)
* [Number of Households in Argentina](https://www.helgilibrary.com/indicators/number-of-households/argentina/)

<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*


