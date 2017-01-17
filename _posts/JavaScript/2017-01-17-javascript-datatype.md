---
layout: post
comments: true
categories: JavaScript
title: JavaScript의 데이터타입
---

### 1. 원시데이터 유형 ( 복사가 되는 값 )

#### 1.1 숫자형(Number) : 36, -9, 3.141592, 0.07

* 8진수 : 숫자앞에 '0'
* 16진수 : 숫자앞에 '0x'

#### 1.2 문자형(String) : "자바스크립트 언어", 'JavaScrpt !!!'

* 문자 데이터 간에는 산술(사칙)연산이 이루어지지 않는다.
* 하지만 문자 간 접합(용접)은 + 기호로 가능하다.
* '\n' 개행문자
*  \", \' 이스케이핑 처리하여 화면에 노출  

#### 1.3 논리형(Boolean) : 0 이외의 값은 모두 true.

#### 1.4 undefined : undefined > 값이 할당(대입)되지 않았다. 정의안됨

#### 1.5 null : 비어있음

<br>

### 2. 참조(Reference) 가 되는 데이터는 모두 객체(Object)
* Plain Object '{}'
* Function Object 'function(){}'
* Array Object '[]'
