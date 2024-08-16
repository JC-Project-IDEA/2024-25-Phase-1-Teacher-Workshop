
<h1 align="center">🎵 共融藝術 ✕ 科技 教師工作坊 🎵</h1>
<p align="center"> 2024/25 Phase 1: Teacher Workshop </p>
<p align="center">👨‍🏫 Lazarus Chan&emsp;&emsp;👩‍🏫 Fiona Lee&emsp;&emsp;🧑‍🏫 Cat Fung;&emsp;👨‍🏫 Andio Lai</p>


## 🎨 工作坊內容簡介：
「賽馬會科藝共融計劃」由香港賽馬會慈善信託基金捐助和城大主辦，旨在提升本地中學教師及學生對藝術科技的認識和能力，透過工作坊讓他們掌握如何應用數碼科技進行藝術創作，為傳統創作方式注入新元素，創造更多別樹一格的表現方式。同時，本計劃將透過分享和體驗活動提升學生對共融藝術的意識，啟發他們反思如何讓殘疾人士欣賞藝術及參與藝術活動，透過藝術科技建立共融的社會。


## 📖 學習資料下載：


<li>
   <a href="https://github.com/JC-Project-IDEA/2023-24-PHASE-2-Teacher-Workshop/blob/main/Day%201%20-%20AM.pdf"> 教師工作坊課堂筆記 Day 1 AM </a>
</li>
<li>
   <a href="https://github.com/JC-Project-IDEA/2023-24-PHASE-2-Teacher-Workshop/blob/main/Day%201%20-%20PM.pdf"> 教師工作坊課堂筆記 Day 1 PM </a>
</li>
<li>
   <a href="https://github.com/JC-Project-IDEA/2023-24-PHASE-2-Teacher-Workshop/blob/main/Day%202%20-%20AM.pdf"> 教師工作坊課堂筆記 Day 2 AM </a>
</li>
<li>
   <a href="https://github.com/JC-Project-IDEA/2023-24-PHASE-2-Teacher-Workshop/blob/main/Day%202%20-%20PM.pdf"> 教師工作坊課堂筆記 Day 2 PM </a>
</li>
<li>
   <a href="https://github.com/JC-Project-IDEA/2023-24-PHASE-2-Teacher-Workshop/blob/main/SnapSound-Hardware Assembling Instructions.pdf"> SnapSound 組裝步驟 </a>
</li>
<li>
   <a href="https://github.com/JC-Project-IDEA/2023-24-PHASE-2-Teacher-Workshop/blob/main/JC-Project-IDEA-phase-2/JC-Project-IDEA-phase-2.ino"> SnapSound編碼： </a>
</li>

```sh
#include "SerialMP3Player.h"// 使用MP3板的編碼庫library

#include <CapacitiveSensor.h>// 使用可感應導電物料的CAP SENSE編碼庫library

#define TX 10 //to MP3 board RX //定義ARDUINO TX到MP3 RX引腳連接
#define RX 11  //to MP3 board TX //定義ARDUINO RX到MP3 TX引腳連接

SerialMP3Player mp3(RX, TX);// 定義起動MP3相關的TX， RX

CapacitiveSensor sensor = CapacitiveSensor(3, 4);
//定義CAP SENSE導電感應引腳連接，兩者使用ARDUINO的DIGITAL引腳，並配合電阻達到感應運作 
//前者為SEND PIN,後者為RECIEVE PIN要連接到紙上


//設定：有電源起動時執行一次的程序
void setup() {
  Serial.begin(9600);     // 起動serial介面
  mp3.begin(9600);        // 開始MP3板的連接
  delay(500);             // 等待起動
  mp3.sendCommand(CMD_SEL_DEV, 0, 2);   //選取 sd-card
  delay(500);             // 等待起動
  mp3.setVol(50);// 設定音量
}


//迴圈: 處理器不停執行的程序
void loop() {

  long measurement =  sensor.capacitiveSensor(10);//讀取SENSOR的數值


  Serial.print(measurement);//SERIAL PRINT SENSOR的數值以方便MAPPING
  Serial.println("\t");

  if (measurement >= 100){//決定觸發起動歌曲的條件(值)
    mp3.play(1);     //歌曲於SD CARD內的次序
  }
  delay(50);//迴圈再執行的中間位
}
```

## 👂🏻 SnapSound 🎞｜留聲影像 – 用光影呈現聲音場景（聲音視覺化動能藝術作品）


導師將帶領學員以「聲音視覺化」作為創作主題，從聆聽到聲音採集，由聯想到通感呈現，學習不同 Software、Hardware的操作，讓聲音以形象化被看得見，從中學習到： 


1.	聲音的概念與採集，藉著不同聆聽練習，重新認識聲音，學習捕捉聲音的不同器材運用與技巧；


2.	感官訊號轉化，探索聲音與視覺符號的關連，配合形體表達，以攝影記錄及簡易程式編碼，將聲音視覺化，創作出不同能力人士都能欣賞的藝術作品；


3.	電子線路和機械零件（如摩打）的操作原理及裝嵌，以程式編碼配合電子零件的創作實踐，並探索利用生活中常見物品（熱敏紙）化為創作工具的可能性；


4.	Audacity 聲音編輯軟件和 Arduino 軟硬件的運用；

  
5.	結合以上技巧，創作出獨一無二的聲音＋視覺藝術作品，優秀作品亦有機會於年度展覽中展出。


## 相關連結（聲音）
1. 音頻檔案轉換 (.m4a to .mp3) https://cloudconvert.com/m4a-to-mp3 or https://convertio.co/m4a-mp3/

2. Big Sound Bank https://bigsoundbank.com/

3. Free Sound https://freesound.org/

4. Internet Archive https://archive.org/details/opensource_audio


## 相關連結（影像）
1. https://perchance.org/ai-icon-generator
2. Online Photo Editor https://www.photopea.com/


## 相關連結（器材／資源）
1. RS Components 零件 https://hkcn.rs-online.com/web/c/?sra=oss&r=t&searchTerm=arduino

2. SparkFun 零件 https://www.sparkfun.com/

3. adafruit 零件 https://www.adafruit.com/

4. Arduino https://www.arduino.cc/

5. Processing https://processing.org/

6. Serial MP3 Player Library https://github.com/MajicDesigns/MD_YX5300

   Documentation https://majicdesigns.github.io/MD_YX5300/

7. Capacitive Sensing Library https://playground.arduino.cc/Main/CapacitiveSensor/


## 延伸學習
1. p5.js https://p5js.org/
