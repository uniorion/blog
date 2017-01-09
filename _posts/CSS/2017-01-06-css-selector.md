---
layout: post
comments: true
categories: CSS
title: CSS의 선택자, 가상클래스, 가상요소
---

#### 가상 클래스와 가상 요소 (Pseudo Class VS Pseudo Element)
CSS2 에서는 가상 클래스나 가상 요소 모두 앞에 : 썼으나, CSS3 부터는 가상 요소 앞에는 ::  

가상 클래스 : `상태(Status)` 와 관련된 것
```css
:link     {}
:visited  {}
:hover    {}
:focus    {}
:active   {}
:lang(en) {}
```

가상 요소 : 가상으로 `요소` 를 추가

{% highlight lua %}
::before       {}
::after        {}
::first-line   {}
::first-letter {}
::selection    {}
{% endhighlight %}

  - a>b : a요소의 자식 요소 중 모든 b
  - a+b : a요소 다음에 오는 형제 요소 중 바로 인접한 하나의 b
  - a~b : a요소 다음에 오는 형제 요소 중 모든 b
 
```css
클래스명1.클래스명2     //멀티클래스 선택자: 한 요소에 '클래스명1'과 '클래스명2' 모두 부여된 요소를 선택
클래스명1 .클래스명2    //자손선택자     : '클래스명1' 요소의 _자손_ 중 모든 '클래스명2' 요소를 선택
클래스명1 > 클래스명2   //자식선택자     : '클래스명1' 요소의 _자식_ 중 모든 '클래스명2' 요소를 선택
클래스명1 ~ 클래스명2   //형제선택자     : '클래스명1' 요소의 형제요소 중 모든 '클래스명2' 요소를 선택
클래스명1 + 클래스명2   //인접형제선택자  : '클래스명1' 요소와 바로 인접한 형제요소 '클래스명2'를 선택 

[속성]                : 해당 속성을 가진 모든 요소.
[속성="값"]            : 해당 속성 값을 가진 모든 요소.
[href^="http://"]   : href 값이 http:// 로 시작하는 모든 a요소
[href$=".psd"]      : href 값이 .psd로 끝나는 모든 요소
[title*="css"]      : title 값에 css 문자가 포함되는 모든 요소
[data-app|="fds"]   : 하이픈으로 구분된 항목 중 'fds'과 일치하는 값을 가진 요소
[data-app~="fds"]   : 공백으로 구분된 항목 중 'fds'과 일치하는 값을 가진 요소
```

<br>

참고사이트)

- [MDN 선택자](https://developer.mozilla.org/ko/docs/Web/CSS/%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0/%EC%84%A4%EB%A0%89%ED%84%B0)