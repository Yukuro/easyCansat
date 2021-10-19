---
sidebar_position: 2

---
# 1. Remote Control
In this mission, you will learn how to add a remote control to Cansat.

## Story
You are a student aiming to participate in the Cansat competition.

The name of the tournament is Challengers Space Event.

The winner of the competition will receive a highly functional CanSat as a prize!

But you've never built a CanSat before.

So you found easyCanSat and assembled it.

You've built it, but you don't know how to program it, and you don't know how to make it run.

By trial and error, you decide to try to find a way to make your CanSat run.

## Success Criteria
- Success level : Minimum
  - Purpose
    - Using UIFlow, just run a servo motor
  - Objectives
    - Confirm by video or visual inspection.
- Successs level : Full
  - Purpose
    - Using UIFlow, run servo motors remotely
  - Objectives
    - Confirm by video or visual inspection.
- Success level : Advanced
  - Purpose
    - Using remote control with UIFlow, move Cansat back and forth, left and right.
  - Objectives
    - Confirm by video or visual inspection.

## Implementation Example
m5f file is [here](https://raw.githubusercontent.com/Yukuro/easyCansat/main/website/static/files/missions/Remote_Cotrol.m5f)

```python
from m5stack import *
from m5ui import *
from uiflow import *
import module

import time
remoteInit()
setScreenColor(0x222222)

servo2 = module.get(module.SERVO2)

def _remote_forward():
  rgb.setColorAll(0xff0000)
  servo2.position(0, 120)
  servo2.position(1, 80)

def _remote_back():
  rgb.setColorAll(0x000099)
  servo2.position(0, 80)
  servo2.position(1, 120)

def _remote_stop():
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