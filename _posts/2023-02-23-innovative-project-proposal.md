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
### Taiwan = 13M (台灣 1300萬人）

### global  = 1.5B (全球 15億)




<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*


