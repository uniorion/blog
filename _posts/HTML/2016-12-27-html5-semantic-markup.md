---
layout: post
comments: true
categories: HTML
title: HTML5와 시맨틱 마크업
---

#### * 표현에 기준을 둔 요소들로 CSS로 대체 가능하며 더이상 사용하지 않는다.

> `<acronym>, <applet>, <basefont>, <big>, <center>, <dir>, <font>,`  
> `<frame>, <frameset>, <isindex>, <noframes>, <s>, <strike>, <tt>, <u>`

### 1. HTML5 문서의 기본 구조

#### 1.1 사이트의 대표 언어를 설정
* 리더기는 텍스트를 해당 언어로 읽으므로 접근성 향상에 중요하다.
* __다중 언어로 된 문서__ 의 경우, html 의 lang 값은 주언어로 값을 주고, 다른 언어는 각 요소에 "lang" 속성 값을 부여한다.
{% highlight lua %}
<html lang="ko-KR">
<p lang="en">This is paragraph</p>
{% endhighlight %}

#### 1.2 요소의 텍스트 방향성을 명시
{% highlight lua %}
<html dir="ltr | rtl | auto">
{% endhighlight %}

#### 1.3 문자셋(character set)의 선언
{% highlight lua %}
<!-- HTML5 이전 -->
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<!-- HTML5 -->
<meta charset="utf-8">
{% endhighlight %}

<br>

### 2. HTML5의 콘텐츠 모델

#### 2.1 [HTML5에 추가된 요소](http://tcpschool.com/html/html5_intro_addition)
{% highlight lua %}
- 의미(semantic) 요소 : <header>, <nav>, <main>, <section>, <aside>, <article>, <footer>, <figure>
- 멀티미디어 요소 : <video>, <audio>, <embed>, <source>, <track>
- 그래픽 요소 : <canvas>, <svg>
{% endhighlight %}

#### 2.2 [콘텐츠 모델](https://developer.mozilla.org/ja/docs/Web/HTML/Content_categories#sectioning_content)
: HTML5의 요소들은 특성에 따라 아래와 같이 분류된다. 한 요소는 여러 분류에 속할 수 있고, 어느 곳에도 속하지 않을 수도 있다.  
![HTML5 Contents Model]({{ site.baseurl }}/static/img/content/HTML5_Content_categories.png)

##### 1) Metadata Contents (메타데이터 콘텐츠)
콘텐츠의 모양, 동작을 설정하거나 다른 문서에 대한 링크 설정 및 기타 통신 이외의 정보를 전한다.
> `<base>, <command>, <link>, <meta>, <noscript>, <script>, <style>, <title>`

<br>

##### 2) Flow Contents (플로우 콘텐츠)
: 대부분의 body 요소안의 요소들이 포함된다. 하위에 텍스트나 임베디드 콘텐츠를 포함.
> `<a>: <abbr>, <address>, <article>, <aside>, <audio>, <b>, <bdo>, <blockquote>, <br>, <button>, <canvas>, <cite>, <code>, <command>, <datalist>, <del>, <details>, <dfn>, <div>, <dl>, <em>, <embed>, <fieldset>, <figure>, <footer>, <form>, <h1>, <h2>, <h3>, <h4>, <h5>, <h6>, <header>, <hgroup>, <hr>, <i>, <iframe>, <img>, <input>, <ins>, <kbd>, <keygen>, , <label>, <map>, <mark>, <math>, <menu>, <meter>, <nav>, <noscript>, <object>, <ol>, <output>, <p>, <pre>, <progress>, <q>, <ruby>, <samp>, <script>, <section>, <select>, <small>, <span>, <strong>, <sub>, <sup>, <svg>, <table>, <textarea>, <time>, <ul>, <var>, <video>, <wbr>및 텍스트.`

<br>

##### 3) Sectioning Contents (섹셔닝 콘텐츠)
: 헤딩과 푸터의 범위를 결정하는 요소. 모든 섹셔닝 콘텐츠는 헤딩과 아웃라인을 가지고 있다.
> `<article>, <aside>, <nav>, <section>`

<br>

##### 4) Heading Contents (헤딩 콘텐츠)
: 섹션의 헤더를 의미한다.
> `<h1>, <h2>, <h3>, <h4>, <h5>, <h6>, <hgroup>`

<br>

##### 5) Phrasing Contents (프레이징 콘텐츠)
: 문서의 텍스트를 의미. 프레이징 콘텐츠는 하위에 텍스트나 임베디드 콘텐츠를 포함한다.
> `<abbr>, <audio>, <b>, <bdo>, <br>, <button>, <canvas>, <cite>, <code>, <command>, <datalist>, <dfn>, <em>, <embed>, <i>, <iframe>, <img>, <input>, <kbd>, <keygen>, <label>, <mark>, <math>, <meter>, <noscript>, <object>, <output>, <progress>, <q>, <ruby>, <samp>, <script>, <select>, <small>, <span>, <strong>, <sub>, <sup>, <svg>, <textarea>, <time>, <var>, <video>, <wbr>, (공백 만은 아닌)일반 텍스트`

<br>

##### 6) Embedded Contents (임베디드 콘텐츠)
: 이미지, 비디오, 플래시 등 외부 콘텐츠를 문서내에 표현한다.
> `<audio>: <canvas>, <embed>, <iframe>, <img>, <math>, <object>, <svg>, <video>`

<br>

##### 7) Interactive Contents (인터액티브 콘텐츠)
: 사용자와 상호작용하는 요소들이다.
> `<a>, <button>, <details>, <embed>, <iframe>, <keygen>, <label>, <select>, <textarea>`

<br>

##### 8) Transparent Contents (트랜스패런트 콘텐츠)
: 부모 요소의 콘텐츠에 따라 포함하는 콘텐츠의 분류가 바뀌는 요소를 말한다.

<br>

### 3. HTML5 의 아웃라인 알고리즘

#### 3.1 HTML5에서의 섹션 정의
 * HTML5에서 섹션은 서로 중첩될 수 있으며, body 안의 모든 요소는 적어도 하나의 섹션 안에 포함된다.
 * 모든 섹션은 명시적 또는 암묵적으로 자동으로 구분되어진다.

> 명시적으로 섹션을 정의하는 요소  
> ` <body>,  <section>,  <article>,  <aside>, <footer>,  <header>, <nav>`

<br>

#### 3.2 HTML5에서 제목 지정하는 법
{% highlight lua %}
<section>
  <h1>둥근귀코끼리</h1>    
  <p>이번 섹션에선, 잘 알려지지 않은 둥근귀코끼리에 관해 알아보겠습니다.</p>
  <section>
    <h2>서식지</h2>
    <p>둥근귀코끼리는 나무에 살지는 않고 나무들 사이에 그 서식지를 이루고 있습니다.</p>
  </section>
</section>
<section>
  <h3>몽골 게르빌루스쥐</h3>
  <p>이번 섹션에선, 잘 알려진 몽골 게르빌루스쥐에 관해 알아보겠습니다.</p>
</section>
{% endhighlight %}
heading 요소간의 상대적 등급은 오직 같은 섹션 안에서만 중요하다. 따라서 위의 코드는 아래와 같은 아웃라인을 구성한다.
{% highlight lua %}
1. 둥근귀코끼리
   1.1 서식지
2. 몽골 게르빌루스쥐
{% endhighlight %}

<br>

#### 3.3 은연중 자동으로 정의되는 섹션
* 헤딩요소가 명시적 섹션의 첫번째 제목으로 사용되지 않았다면, 자동으로 또 다른 섹션을 생성, 분류된다.
* 암묵적으로 생성된 아웃라인은 헤딩요소의 상대적 등급에 따라, 상위/동급/하위 섹션으로 자리 잡는다.

##### 1) 하위 섹션으로 생성
{% highlight lua %}
<section>
  <h1>둥근귀코끼리</h1>  
  <p>이번 섹션에선, 잘 알려지지 않은 둥근귀코끼리에 관해 알아보겠습니다.</p>
  <h3>서식지</h3>
  <p>둥근귀코끼리는 나무에 살지는 않고 나무들 사이에 그 서식지를 이루고 있습니다.</p>
</section>
{% endhighlight %}
{% highlight lua %}
1. 둥근귀코끼리
   1.1 서식지 (h3 요소에 의해 은연중 자동으로 정의됨)
{% endhighlight %}

<br>

##### 2) 동급 섹션으로 생성
{% highlight lua %}
<section>
  <h1>둥근귀코끼리</h1>  
  <p>이번 섹션에선, 잘 알려지지 않은 둥근귀코끼리에 관해 알아보겠습니다.</p>
  <h1>몽골 게르빌루스쥐</h1>
  <p>몽골 게르빌루스쥐는 귀엽고 작은 포유 동물입니다.</p>
</section>
{% endhighlight %}
{% highlight lua %}
1. 둥근귀코끼리
2. 몽골 게르빌루스쥐 (h1 요소에 의해 자동으로 정의됨과 동시에 이전 섹션과 구분되어 짐)
{% endhighlight %}

<br>

##### 3) 상위 섹션으로 생성
{% highlight lua %}
<body>
  <h1>포유 동물</h1>
  <h2>고래</h2>
  <p>이번 섹션에선, 유영하는 고래에 관해 알아보겠습니다.</p>
  <section>
    <h3>둥근귀코끼리</h3>  
    <p>이번 섹션에선, 잘 알려지지 않은 둥근귀코끼리에 관해 알아보겠습니다.</p>
    <h3>몽골 게르빌루스쥐</h3>
      <p>몽골 게르빌루스쥐의 무리는 몽골을 훨씬 벗어나는 구역까지 퍼져있습니다.</p>
    <h2>파충류</h2>
      <p>파충류는 냉혈 동물입니다.</p>
  </section>
</body>
{% endhighlight %} 
{% highlight lua %}
1. 포유 동물
   1.1 고래 (h2 요소에 의해 자동으로 정의됨)
   1.2 둥근귀코끼리 (섹션 요소에 의해 명시적으로 정의됨)
   1.3 몽골 게르빌루스쥐 (h3 요소에 의해 자동으로 정의됨과 동시에 이전 섹션과 구분되어 짐)
2. 파충류 (h2 요소에 의해 자동으로 정의됨과 동시에 이전 섹션과 구분되어 짐)
{% endhighlight %}

<br>

#### 3.4 섹셔닝 루트
: 섹셔닝 루트는 자기만의 아웃라인을 가질 수 있지만, 그 안의 섹션이나 헤딩요소가 상위의 아웃라인에는 어떠한 영향도 끼치지 않는
요소를 가르킨다.

> `<body>, <blockquote>, <detail>, <fieldset>, <figure>, <td>`

{% highlight lua %}
<section>
  <h1>숲 코끼리</h1> 
  <section>
    <h2>소개</h2>
    <p>이번 섹션에선, 잘 알려지지 않은 둥근귀코끼리에 관해 알아보겠습니다.</p>
  </section>
  <section>
    <h2>서식지</h2>
    <p>과학자들은 "<cite>보르네오 섬의 둥근귀코끼리</cite>"라는 책에서 다음과 같이...</p>
    <blockquote>
       <h1>보르네오 섬</h1>
       <p>보르네오 섬에 서식하는 둥근귀코끼리...</p>
    </blockquote>
  </section>
</section>
{% endhighlight %}

blockquote 가 포함하고 있는 내부 내용의 아웃라인이 외부의 것과 완전히 차단, 전체 아웃라인에는 포함되지 않는다.

{% highlight lua %}
1. 숲 코끼리
   1.1 소개
   1.2 서식지
{% endhighlight %}



<br>

참고사이트)  

- [[MDN] HTML5 문서의 섹션과 아웃라인](https://developer.mozilla.org/ko/docs/Web/HTML/HTML5_%EB%AC%B8%EC%84%9C%EC%9D%98_%EC%84%B9%EC%85%98%EA%B3%BC_%EC%9C%A4%EA%B3%BD)
- [[2014널리세미나] 시맨틱한 HTML5 마크업 구조 설계, 어떻게 할까?](http://www.slideshare.net/NULINTS/2014-html5)
- [HTML5 markup - 신현석](https://hyeonseok.com/docs/html/html5-markup.php)