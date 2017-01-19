---
layout: post
comments: true
categories: JavaScript
title: JavaScript의 데이터 타입
---

### 1. 원시데이터 유형 (복사가 되는 값)

#### 1.1 숫자형(Number)
배정밀도 64비트 형식 IEEE 754 값 (-(2^53 -1) 와 2^53 -1 사이의 숫자값)을 나타내며, 추가적으로 세가지 의미있는 기호적인 값들도 표현할 수 있다.

* +/- Infinity 
* NaN (not-a-number)

ES6 부터는 숫자가 배정밀도 부동소수점 숫자인지 확인하는 용도로 `Number.isSafeInteger()` 과 `Number.MAX_SAFE_INTEGER`, `Number.MIN_SAFE_INTEGER` 
을 사용할 수 있다. 이 범위를 넘어서면 숫자는 더 이상 안전하지 않다.

<br>

#### 1.2 문자형(String)
String(문자열) 타입은 텍스트 데이터를 나타내는데 사용한다. 이는 0개 또는 그 이상의 유니코드(16비트 부호없는 정수 값) 문자들의 집합이다. 문자열은 작은 따옴표(‘’) 또는 큰 따옴표(“”) 안에 텍스트를 넣어 생성한다.

* 문자 데이터 간에는 산술(사칙)연산이 이루어지지 않는다.
* 하지만 문자 간 접합(용접)은 + 기호로 가능하다.

<br>

#### 1.3 논리형(Boolean) : 
Boolean 은 논리적인 요소를 나타내고, `true` 와 `false` 의 두 가지 값을 가질 수 있다.  
0 이외의 값은 모두 `true`.

<br>

#### 1.4 undefined
값을 할당하지 않은 변수는 `undefined` 값을 가진다

<br>

#### 1.5 null
Null 타입은 딱 한 가지 값, `null` 을 가질 수 있다

<br>

#### 1.6 [Symbol(New in ES6)](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Symbol)
Symbol은 유일하고 변경 불가능한 (immutable) 기본값 (primitive value) 이다.

<br>

### 2. 객체(Object) (참조가 되는 값)
* Plain Object '{}'
* Function Object 'function(){}'
* Array Object '[]'


참고사이트)
- [[MDN]자바스크립트의 자료형](https://developer.mozilla.org/ko/docs/Web/JavaScript/Data_structures)