---
layout:     post
title:      "[Android] Tip - Mac에서 핸드폰 미러링 하기"
subtitle:   "Scrcpy"
date:       2021-03-23
author:     "raindragon"
header-style: text
catalog: true
lang: ko
tags:
    - TIP
    - Android
    - Scrcpy
---


나는 Mac으로 Android 앱개발을 하면서 에뮬레이터 보다는 실기기를 주로 사용을 하고있다.  
코딩을 하다가 핸드폰을 들고 기능 확인을 한다던가 하면 이리저리 움직이는게 너무 불편해서 미러링 프로그램을 찾아보다 설치와 사용도쉬운 [scrcpy][scrcpy]를 찾았다.

Mac OS 에서 설치법
===

패키지 관리자인 [homebrew][homebrew]가 필요하다.

없을경우 아래의 명령어를 iterm이나 터미널에서 입력해서 설치하자.

    
    $ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

`1. Scrcpy의 설치는 아래의 명령어 입력후`
   
   
    $ brew install scrcpy

`2. homebrew 버전에 맞게 아래와 같이 입력하면 된다.`


    # Homebrew >= 2.6.0
    $ brew install --cask android-platform-tools

    # Homebrew < 2.6.0
    $ brew cask install android-platform-tools


사용법
===


맥에 디바이스 연결후 iterm 이나 터미널에서 입력하면된다 :


    $ scrcpy

    (명령어 확인)
    $ scrcpy --help





[scrcpy]:"https://github.com/Genymobile/scrcpy"
[homebrew]:"https://brew.sh/index_ko"
