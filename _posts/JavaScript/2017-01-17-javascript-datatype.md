---
layout: post
comments: true
categories: JavaScript
title: JavaScript의 데이터타입
---

### 1. 원시데이터 유형 ( 복사가 되는 값 )

#### 1.1 숫자형(Number) : 36, -9, 3.141592, 0.07

추가적으로 세가지 의미있는 기호적인 값들도 표현할 수 있다.

* +/- Infinity
* NaN (not-a-number)

{% highlight lua %}
var x = 10;    // 정수
var y = 10.12; // 실수
var z = -20;   // 음의 정수

var foo = 42 / -0;
console.log(foo);        // -Infinity
console.log(typeof foo); // number

var bar = 1 * 'string';
console.log(bar);        // NaN
console.log(typeof bar); // number
{% endhighlight %}

<br>

#### 1.2 문자형(String) : "자바스크립트 언어", 'JavaScrpt !!!'
String(문자열) 타입은 텍스트 데이터를 나타내는데 사용한다. 이는 0개 또는 그 이상의 유니코드(16비트 부호없는 정수 값) 문자들의 집합이다. 문자열은 작은 따옴표(‘’) 또는 큰 따옴표(“”) 안에 텍스트를 넣어 생성한다.

* 문자 데이터 간에는 산술(사칙)연산이 이루어지지 않는다.
* 하지만 문자 간 접합(용접)은 + 기호로 가능하다.
* '\n' 개행문자
*  \", \' 이스케이핑 처리하여 화면에 노출  

<br>

#### 1.3 논리형(Boolean) : 0 이외의 값은 모두 true.

<br>

#### 1.4 undefined : undefined > 값이 할당(대입)되지 않았다. 정의안됨

<br>

#### 1.5 null : 비어있음

<br>

#### 1.6 Symbol (New in ECMAScript 6)

<br>

### 2. 참조(Reference) 가 되는 데이터는 모두 객체(Object)
* Plain Object '{}'
* Function Object 'function(){}'
* Array Object '[]'
