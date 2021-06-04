# Git Graph Cheatsheet

รวมสูตรโกงสำหรับการใช้งาน Git Graph

## ❤️ ศัพท์และความหมาย (1)

|ศัพท์|ความหมาย|
|-|-|
|Git|โปรแกรมควบคุมการพัฒนาโปรแกรม|
|GUI|Graphic User Interface โปรแกรมแบบมีหน้าตา และดำเนินการได้ง่ายกว่า|
|CLI|Command-line Interface โปรแกรมแบบใช้คำสั่ง ดำเนินการยากกว่า|
|Repository|แหล่งเก็บโปรเจคการพัฒนาที่ใช้ Git|
|GitHub|ผู้ให้บริการ Repository แบบออนไลน์|
|GitLab|ผู้ให้บริการ Repository แบบออนไลน์|
|BitBucket|ผู้ให้บริการ Repository แบบออนไลน์|
|Local|การใช้ Repository แบบออฟไลน์|
|Initilize|เริ่มต้นโปรเจคการพัฒนากับ Git|
|Changes|โค้ดที่มีการเปลี่ยนแปลง|
|Unstaged|โค้ดที่มีการเปลี่ยนแปลง และยังไม่ได้รับการยืนยันเตรียม Commit|
|Staged|โค้ดที่มีการเปลี่ยนแปลง และได้รับการยืนยันพร้อม Commit|
|Commit|บันทึกกิจกรรมเปลี่ยนแปลงบน Repository จากเนื้อหาที่ได้รับการ Staged|
|Hash|การเข้ารหัสพิเศษ เพื่อยืนยันตำแหน่งของ Commit เป็นเสมือน ID สำหรับระบุตัวตน|
|Push|อัปโหลด Commit ทั้งหมดไปยังผู้ให้บริการ Repository|
|Pull|นำ Commit จากผู้ให้บริการ Repository มายัง Local|
|Fetch|เรียกดูการเปลี่ยนแปลง Commit จากผู้ให้บริการ Repository มายัง Local|
|Clone|ดาวน์โหลด Repository ที่ต้องการ|
|Tag|แท็กเวอร์ชั่นโปรแกรมบน Repositry|

## ❤️ ศัพท์และความหมาย (2)

|ศัพท์|ความหมาย|
|-|-|
|Branch|สาขาการพัฒนาโปรแกรมบน Repository สำหรับการแบ่งงาน|
|Branch `main`|สาขาหลักของการพัฒนาที่เสถียรภาพ|
|Branch `master`|สาขาหลักของการพัฒนาที่เสถียรภาพ (ถูกประกาศเลิกใช้ในปัจจุบัน)|
|Branch `develop`|สาขารองของการพัฒนา เป็นรอยต่อของสาขาย่อยอื่นๆ ก่อนเข้าที่สาขาหลัก|
|Branch `feature/*`|สาขาย่อยของการพัฒนา สำหรับคุณสมบัติใหม่|
|Branch `hotfix/*`|สาขาย่อยของการพัฒนา สำหรับการเร่งรีบแก้ไขโปรแกรม|
|Branch `release/*`|สาขาย่อยของการพัฒนา สำหรับการเตรียมเปิดใช้งานโปรแกรม|
|Checkout|การเลือก Commit หรือ Branch หรือ Tag สำหรับเรียกดูโปรแกรมช่วงเวลานั้นๆ หรือใช้ก่อนดำเนินการ Merge และอื่นๆ|
|Merge|รวมเนื้อหาการเปลี่ยนแปลง Commit ใน Branch รวมเข้าด้วยกันกับ Branch อื่น|
|Fork|การคัดลอกเนื้อหา Repository ผู้อื่นบนผู้ให้บริการต่างๆ มาเป็นของเราเองพร้อมกับอ้างอิงต้นฉบับ|
|Pull Request|การขอเนื้อหาเปลี่ยนแปลงบน Fork ทำการอัปเดตเนื้อหาบน Repository หลัก|
|Merge Request|การขอเนื้อหาเปลี่ยนแปลงบน Fork ทำการอัปเดตเนื้อหาบน Repository หลัก|
|Conflict|ปัญหาจากการ Merge เนื้อหา แล้วพบการกระทบระหว่าง Commit ที่แก้ไขบรรทัดเดียวกัน|
|Reset Hard|การยกเลิกเปลี่ยนแปลงล่าสุด แบบไม่เก็บการเปลี่ยนแปลง|
|Reset Mixed|การยกเลิกเปลี่ยนแปลงล่าสุด แบบเก็บการเปลี่ยนแปลงไว้บน Unstaged|
|Reset Soft|การยกเลิกเปลี่ยนแปลงล่าสุด แบบเก็บการเปลี่ยนแปลงไว้บน Staged|
|Revert|การยกเลิกการเปลี่ยนแปลง Commit ที่เลือกทั้งหมด|
|Rebase|การปรับรากฐานสำหรับ Branch ที่ตามหลังเนื้อหามากเกินไป คล้าย Merge แต่ทำเพื่อปรับเส้นโครงสร้างเท่านั้น|
|Cherry Pick|เลือก Commit ที่ต้องการ เพื่อคัดลอกการเปลี่ยนแปลงมาใช้งานกับสถานที่ได้ Checkout ไว้|
|Stash|การเก็บพักการเปลี่ยนแปลงชั่วคราว ใช้เพื่อต้องการ Checkout ขณะที่มีการ Changes เกิดขึ้น|
|Apply Stash|เรียกคืนการเปลี่ยนแปลงชั่วคราว|
|Pop Stash|เรียกคืนการเปลี่ยนแปลงชั่วคราว พร้อมกับลบข้อมูลการพัก|
|Drop Stash|ลบข้อมูลการพักการเปลี่ยนแปลง|
|Issues|การแจ้งและติดตามปัญหาของโปรแกรม|
|Automate|ระบบจัดการอัตโนมัติ ตามค่าที่ได้กำหนดไว้ โดยแต่ล่ะผู้ให้บริการ Git Repository จะมีไม่เหมือนกัน|
|Actions|ระบบ Automate ของ GitHub|

## 👍 เว็บไซต์รวบรวมการใช้ Git แบบ GUI

- [https://git-scm.com/downloads](https://git-scm.com/downloads)
- [https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)
- [https://www.sourcetreeapp.com/](https://www.sourcetreeapp.com/)

## 👨‍💻 ตั้งค่าชื่อและที่อยู่อีเมลเพื่อเริ่มต้น

> ใช้คำสั่งผ่าน `cmd` เพื่อตั้งชื่อและอีเมล หรือใช้ผ่าน Setup name & email บน Git Graph

```bash
git config --global user.name "John Doe"
git config --global user.email "john12@example.com"
```

## 💾 บันทึกการเปลี่ยนแปลงพื้นฐาน

<div class="has-text-centered">
  <img src="https://i.imgur.com/CZWv8dj.jpg" alt="flow-common">
</div>

## 🌐 บันทึกการเปลี่ยนแปลงไปยัง GitHub

<div class="has-text-centered">
  <img src="https://i.imgur.com/AjgDxTr.jpg" alt="flow-github">
</div>

## 🔀 การแบ่ง Branch และการรวม Branch

<div class="has-text-centered">
  <img src="https://i.imgur.com/Y31BLkS.jpg" alt="flow-branch">
</div>

## ➕ Initialize

![git-init](https://i.imgur.com/xmQR0uM.jpg)

## 🧰 Git Graph

![git-graph-button](https://i.imgur.com/qKQ1y1O.jpg)

## ⚙️ Git Graph settings

![git-graph-settings](https://i.imgur.com/CGnQRGN.jpg)

## 👨‍💻 Setup name & email

![git-graph-set-user](https://i.imgur.com/N4jSKB1.jpg)

## ✅ Stage

![git-stage](https://i.imgur.com/G7zCptH.jpg)

## 💾 Commit

![git-commit](https://i.imgur.com/l978v66.jpg)

## ☑️ Checkout

![git-checkout](https://i.imgur.com/IuZcCpQ.jpg)

## ⏭ Rebase

![git-rebase](https://i.imgur.com/aRIYr0K.jpg)

## ⤵️ Merge

![git-merge](https://i.imgur.com/YNKsWvc.jpg)

## 📥 Stash

![git-stash](https://i.imgur.com/TbkGkw2.jpg)

## 📤 Pop Stash

![git-pop](https://i.imgur.com/RUBMZ82.jpg)
