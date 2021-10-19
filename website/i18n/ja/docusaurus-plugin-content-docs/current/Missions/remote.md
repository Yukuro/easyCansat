---
sidebar_position: 2

---
# 1. リモートコントロール
このミッションではCansatにリモートコントロール機能をつける方法を学ぶことが出来ます

## ストーリー
あなたはCansatの大会に出場することを目指す学生です

大会の名前はチャレンジャーズ宇宙イベント

大会の優勝賞品として高機能なCanSatがもらえます

でも、あなたはCanSatなんて作った経験はありません

そこで、easyCanSatを見つけて組み立ててみました

組み立てたは良いのですが、プログラミングの方法もわからないし、走らせる方法もわかりません

試行錯誤してCanSatを走らせる方法を模索してみることにしました

## サクセスクライテリア
- サクセスレベル：Minimum
  - 内容
    - UIFlowを用いて、サーボモーターを動かす
  - 検証方法
    - 映像 または 目視により確認する
- サクセスレベル：Full
  - 内容
    - UIFlowを用いて、遠隔からサーボモーターを動かす
  - 検証方法
    - 映像 または 目視により確認する
- サクセスレベル：Advanced
  - 内容
    - UIFlowを使った遠隔操作を用いて、Cansatを前後左右に動かす
  - 検証方法
    - 映像 または 目視により確認する

## 実装例
- m5fファイルは[こちら](https://raw.githubusercontent.com/Yukuro/easyCansat/main/website/static/files/missions/Remote_Cotrol.m5f)

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time
remoteInit()
setScreenColor(0x222222)

servo2 = module.get(module.SERVO2)

def _remote_前進():
  rgb.setColorAll(0xff0000)
  servo2.position(0, 120)
  servo2.position(1, 80)

def _remote_後退():
  rgb.setColorAll(0x000099)
  servo2.position(0, 80)
  servo2.position(1, 120)

def _remote_停止():
  rgb.setColorAll(0xffffff)
  servo2.position(0, 100)
  servo2.position(1, 100)


servo2.position(0, 100)
wait_ms(100)
servo2.position(1, 100)
wait_ms(100)
lcd.qrcode('http://flow-remote.m5stack.com/?remote=undefined', 72, 32, 176)

# Describe this function...

# Describe this function...

# Describe this function...
```

