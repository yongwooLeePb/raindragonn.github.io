---
layout:     post
title:      "[TIL] Android DI"
subtitle:   "Dependency Injection"
date:       2021-01-22
author:     "raindragon"
header-style: text
catalog: true
lang: ko
tags:
    - TIL
    - DI
    - Dependency Injection
---

# 의존성 주입(Dependency Injenction)

의존성을 주입한다.. 라는게 뭘까요? 일단 의존성이 뭔지 알아야곘죠?

## 1. 의존성이란 무엇일까?

```kotlin
class Material{
    fun milk(){}
    fun espresso(){}
}


class Coffee{
    val material = Material()

    fun makeLatte(){
        material.apply{
            milk()
            espress()
        }
    }
}
```

해당 예제를 보면 Coffee클래스로 라떼를 만들수있습니다.   
Coffee 클래스 내부 에서 새로운 객체(Material)를 만들어 사용 하기때문에 `Material클래스에서 기능이 수정되거나 추가된다면 Coffee 클래스에서도 해당 기능에 영향을 받게 됩니다.` 따라서 Coffee 클래스는 Material 클래스에 의존성(결합도)이 높음을 알수있습니다.


## 2. 의존성 주입 이란?

위의 예제에서 Coffe클래스에서 필요로하는 객체(Material)를 내부에서 생성하는것이 아닌, `외부에서 생성하고 받아와서 사용을 한다면`(사용 방식을 정의한 인터페이스에 대해서 알고) 어디선가 만든 의존성을 주입한다고 볼수 있겠습니다.   

>한마디로 정의 하자면   
*`두개 이상의 모듈이나 클래스간의 결합도를 낮추기 위해 외부에서 객체를 생성하고 주입하는것`*

