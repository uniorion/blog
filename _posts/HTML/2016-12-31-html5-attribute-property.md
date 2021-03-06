---
layout: post
comments: true
categories: HTML
title: HTML5 주요 요소와 속성
---

### [article](https://developer.mozilla.org/ko/docs/Web/HTML/Element/article)
* 문서, 페이지, 애플리케이션 사이트 안에 독립적으로 구분되거나 신디케이션과 같은 재사용이 가능한 영역
* 포럼의 글, 매거진/신문의 기사, 블로그 글 혹은 기타 콘텐츠의 독립적인 항목.
* `<article>` 요소가 중첩될 경우 안쪽의 요소는 밖의 `<article>` 내용과 관련이 있는 내용이라는 것을 의미
* 각 article 은 구별되어야 하며, 일반적으로 헤딩요소를 자식으로 가진다

허용된 부모 요소  
> 플로우 콘텐츠를 허용하는 모든 요소  
> `<article>` 요소는 `<address>`의 자식이 될수 없다

<br>

### [aside](https://developer.mozilla.org/ko/docs/Web/HTML/Element/aside)
* 문서의 주 내용과 관련성이 희박한 콘텐츠를 분리한 영역
* 사이드바, 관련사이트, 광고, nav 요소의 그룹 등

<br>

### [header](https://developer.mozilla.org/ko/docs/Web/HTML/Element/header)
* 소개나 네비게이션 그룹, 목차나 검색창, 로고 등
* 보통 헤딩요소를 포함하지만 반드시 포함할 필요는 없다
* 섹션으로 간주되지 않는다. `<header>`를 써도 문서 구조상 새로운 섹션이 생기지 않는다

허용된 부모 요소
> 플로우 콘텐츠를 허용하는 모든 요소  
> `<article>` 요소는  `<address>`, `footer>`, 다른 `<header>` 의 자식이 될수 없다

<br>

### [figure](https://developer.mozilla.org/ko/docs/Web/HTML/Element/figure)
* 메인 플로우와 연관이 있지만 플로우에서 독립적으로 위치할 수 있다
* 본문에서 참조하는 이미지, 도표, 코드나 스키마가 해당되며, 메인 플로우에 영향이 없는 다른 페이지나
부록으로 옮기는 것도 가능하다
* `<figcaption>` 을 내부에 추가하여 캡션을 연결할 수 있다. (첫번째 또는 마지막 자식으로서)
{% highlight lua %}
<figure>
  <img src="https://developer.cdn.mozilla.net/media/img/mdn-logo-sm.png" alt="An awesome picture">	
  <figcaption>Fig1. MDN 로고</figcaption>
</figure>
{% endhighlight %}

<br>

### [footer](https://developer.mozilla.org/ko/docs/Web/HTML/Element/footer)
* 가장 가까운 선행하는 섹션의 푸터를 의미. 저자나 저작권 등을 포함할 수 있다
* 저자나 편집자의 연락처는 보통 footer 요소 안의 address 요소로 표현이 된다
* 섹션으로 간주되지 않는다. `<header>`를 써도 문서 구조상 새로운 섹션이 생기지 않는다

<br>

### [nav](https://developer.mozilla.org/ko/docs/Web/HTML/Element/nav)
* 페이지의 부분이나 다른 페이지로의 탐색 링크가 있는 영역
* 모든 링크가 `<nav>` 안에 있을 필요 없으며, 주요 탐색 링크를 위해 사용
* 전형적으로 `<footer>` 요소는 `<nav>`에  필요없는 링크 리스트를 가진다
* 문서는 여러개의 `<nav>` 영역을 가질 수 있다. 하나는 사이트 탐색에, 다른 하나는 내부 페이지 탐색 등을 위해 사용

허용된 부모 요소
> 플로우 콘텐츠를 허용하는 모든 요소  

<br>

### [section](https://developer.mozilla.org/ko/docs/Web/HTML/Element/section)
* 문서의 일반적인 구획. 즉, (전형적으로 제목을 가진) 콘텐츠의 주제 그룹
* 책의 1장, 2장이나 탭형식으로 되어 있는 콘텐츠의 각 탭
* 각 section 은 구별되어야 하며, 일반적으로 헤딩요소를 자식으로 가진다

허용된 부모 요소
> 플로우 콘텐츠를 허용하는 모든 요소  
> `<section>` 요소는 `<address>`의 자식이 될수 없다



<br>

참고사이트)  

- [[MDN] HTML 요소 레퍼런스](https://developer.mozilla.org/ko/docs/Web/HTML/Element)
- [HTML5 markup - 신현석](https://hyeonseok.com/docs/html/html5-markup.php)