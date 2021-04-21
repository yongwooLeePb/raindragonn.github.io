---
layout:     post
title:      "[Android] Adb 이용하여 Doze Mode 진입"
subtitle:   "Doze Mode 명령어"
date:       2021-03-15
author:     "raindragon"
header-style: text
catalog: true
lang: ko
tags:
    - TIP
    - Android
    - ADB
---

<br>

# Android 6.0(23)버전 부터 [Doze mode][Doze_link]가 도입 되었다.

<br>

## Doze 모드 진입

1. adb shell dumpsys battery unplug - `베터리 충전 중지(ACTIVE 상태에서 넘어가기위함1)`
2. 해당 기기의 스크린을 끈다 - `ACTIVE 상태에서 넘어가기위함2`
3. `4번이 계속 안먹힐경우입력`- adb shell dumpsys deviceidle enable
4. 상태가 IDLE이 될때까지 adb shell dumpsys deviceidle step 입력
   - 혹은 adb shell dumpsys deviceidle force-idle 한번


## Doze 모드 해제

1. adb shell dumpsys deviceidle unforce
2. adb shell dumpsys battery reset




[Doze_link]: https://developer.android.com/training/monitoring-device-state/doze-standby

