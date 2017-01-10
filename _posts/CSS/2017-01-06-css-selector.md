---
layout: post
comments: true
categories: CSS
title: CSS의 선택자, 가상클래스, 가상요소
---

### 1. [Class 선택자](https://developer.mozilla.org/ko/docs/Web/CSS/class_selectors)
{% highlight lua %}
.classname { style properties }
[class~=classname] { style properties }
{% endhighlight %}

<br>

### 2. [ID 선택자](https://developer.mozilla.org/ko/docs/Web/CSS/ID_selectors)
{% highlight lua %}
#id_value { style properties }
[id=id_value] { style properties }
{% endhighlight %}

<br>

### 3. [속성 선택자](https://developer.mozilla.org/ko/docs/Web/CSS/Attribute_selectors)

{% highlight lua %}
[attr]            : attr 이름의 속성을 가진 모든 요소
[attr="value"]    : 속성값이 정확히 "value"인 요소
[attr~="value"]   : 속성값이 공백으로 구분된 단어로 구성되어 있을때, 그 단어 중 하나가 "value"인 요소
[attr|="value"]   : 속성값이 정확히 "value"이거나 "value"로 시작하면서 "-"(U+002D) 문자가 곧바로 뒤에 붙는 요소
[attr^="value"]   : 접두사로 "value"가 값에 포함되어 있는 요소
[attr$="value"]   : 접미사로 "value"가 값에 포함되어 있는 요소
[attr*="value"]   : 속성값에 "value"라는 문자열이 포함되어 있는 요소
{% endhighlight %}

<br>

### 4. [가상 클래스(Pseudo Class)](https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-classes)
주로 `상태(Status)` 와 관련된 됨

#### 4.1 링크 선택자
아래 순서대로 정의하는 것이 좋다

{% highlight lua %}
:link    
:visited 
:hover   
:active 
:focus
{% endhighlight %}

<br>

#### 4.2 구조적 가상 클래스 선택자
위치를 기준으로 삼는다.

| 정의 | 설명 |
|---|---|
| E:root                 | 문서의 최상위 요소(html)를 선택 |
| E:nth-child(n)         | 위에서부터 n번째 요소가 E 이면 선택 |
| E:nth-last-child(n)    | 끝에서부터 n번째 요소가 E 이면 선택 |
| E:nth-of-type(n)       | E 요소 중, 위에서부터 n번째 요소가 E 이면 선택 |
| E:nth-last-of-type(n)  | E 요소 중, 끝에서부터 n번째 요소가 E 이면 선택 |
| E:first-child          | 첫번째 요소가 E 이면 선택 |
| E:last-child           | 마지막 요소가 E 이면 선택 |
| E:first-of-type        | E 요소 중, 첫번째 E 를 선택 |
| E:last-of-type         | E 요소 중, 마지막 E 를 선택 |
| E:only-child           | E 요소가 하나뿐인 자식 요소이면 선택 |
| E:only-of-type         | 여러 자식 요소 중, E 요소가 하나뿐인 자식 요소이면 선택 |
| E:empty                | 텍스트 및 공백을 포함한 자식 요소가 없는 E 요를 선택 |
  
<br>

#### 4.3 그 외의 선택자

언어 선택자

{% highlight lua %}
:lang(ko) 
{% endhighlight %}

부정 선택자

{% highlight lua %}
:not
{% endhighlight %}

목적 선택자

{% highlight lua %}
:target
{% endhighlight %}

UI요소 상태 선택자

{% highlight lua %}
:enabled
:disabled
:checked
{% endhighlight %}

<br>

### 5. [가상 요소(Pseudo Element)](https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-elements)

문서의 `특정 부분`을 스타일  
CSS2 에서는 가상 클래스와 가상 요소 앞에 `:` 썼으나, CSS3 부터는 가상 요소 앞에는 `::` 붙임

{% highlight lua %}
::before          {}
::after           {}
::first-line      {}
::first-letter    {}
::selection       {}
::backdrop        {}
::placeholder     {}
::marker          {}
::spelling-error  {}
::grammar-error   {}
{% endhighlight %}

<br>

### 6. 복합 선택자

#### 6.1 하위 선택자

{% highlight lua %}
a b   : a요소의 자손 요소 중 모든 b
a > b : a요소의 자식 요소 중 모든 b
{% endhighlight %}

#### 6.2 인접 형제 선택자

{% highlight lua %}
a + b : a요소 다음에 오는 형제 요소 중 바로 인접한 하나의 b
a ~ b : a요소 다음에 오는 형제 요소 중 모든 b
{% endhighlight %}
 
<br>

참고사이트)

- [MDN 선택자](https://developer.mozilla.org/ko/docs/Web/CSS/%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0/%EC%84%A4%EB%A0%89%ED%84%B0)
- [CSS: 선택자(Selector) 이해](http://www.nextree.co.kr/p8468/)