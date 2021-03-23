---
layout:     post
title:      "[TIL] Android - View 성능 올리기"
subtitle:   "Android 성능 개선"
date:       2021-03-04
author:     "raindragon"
header-style: text
catalog: true
lang: ko
tags:
    - TIL
    - Android
    - View
---


# View 성능 개선 방안

## 1. `오버드로우` 줄이기

- `오버드로우(OverDraw)`란?
    - 같은 픽셀에 여려번 덧 칠하는 것을 의미한다.

> 오버드로우를 줄이면 불필요한 GPU리소스를 줄이고 <br>퍼포먼스를 끌어올릴 수 있다.


<br>
부모뷰와 자식뷰간의 불필요한 배경 중첩이 일어나는 경우
<br>

```xml
    <LinearLayout
        android:id="@+id/ll_parent"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:background="@color/black"
        android:orientation="vertical">

        <LinearLayout
            android:id="@+id/ll_child"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="@color/black"
            android:orientation="vertical" >
            ...
        </LinearLayout>
        
    </LinearLayout>
```

## 2. `투명도 사용 삼가`하기

> 가능한 투명두가 들어가지 않은 컬러 사용하기


## 3. 레이아웃 계층 구조를 가능한 `간단하게` 하기

> ConstraintLayout 최대한 활용