---
layout: post
comments: true
categories: CSS
title: Background 의 기본
---

### 1. 속기형
순서

> selector { background: (color) (url) (repeat) (attachment) (position) }

기본값

> selector { #000 none repeat left top scroll border-box padding-box }

<br>

### 2.background-image

*  첫 번째로 지정한 배경이 가장 앞에 보이고 나중에 지정한 배경이 뒤에 보인다
*  `borders` 속성은 이미지 위에 그려지며 `background-color` 속성은 이미지 아래에 그려진다
* 불투명한 이미지를 배경으로 지정하더라도 color를 지정하는 것이 좋다. (이미지 로딩 실패)

<br>

### 3.background-position

* 다음의 키워드 `top, left, right, center, bottom` 과 상대 값 또는 절대 값의 오프셋을 지정할 수 있다
* 위치를 요소 상자 외부에도 설정할 수 있다

<br>

### 4.background-size
* `width height`
* `size` 속성을 속기형에 정의하려면 `position` 값 뒤에 `/(슬래쉬)` 로 구분하여 정의한다
* cover, contain, px, %, em, rem
    - cover 이미지 크기 비율을 그대로 유지한 상태에서 이미지가 들어 있는 영역의 가로 또는 세로에 이미지를 맞춘다.(가로와 세로 중 큰 값에 맞춘다)
    - contain 이미지 크기 비율을 그대로 유지한 상태에서 원하는 영역에 전체 이미지가 들어가도록 가장 작은 크기로 이미지 스케일을 조정한다.(가로와 세로 중 큰 값에 맞춘다)

<br>

### 5.background-repeat
* repeat - 영역 전체를 덮기위해 필요한 만큼 반복. 마지막 부분이 영역에 맞지 않으면 잘림
* space - flexbox 의 `space-between` 과 유사함
* round - 이미지가 추가 될 공간이 있을때까지 배치된 배경이미지들은 빈 공간없이 늘어남

<br>

### 6.background-origin

* 백그라운드 `이미지`가 적용될 박스 범위
* padding-box(기본), border-box, content-box

![background-origin test]({{ site.baseurl }}/static/img/content/background-origin.png)


<br>

### 7.background-clip

* 백그라운드 `배경색`이 적용될 박스 범위를 지정
* border-box(기본), padding-box, content-box

![background-clip test]({{ site.baseurl }}/static/img/content/background-clip.png)

<br>

### 8.background-attachment

* scroll - 해당 영역의 이미지 고정(예제의 DIV에 적용한 경우 스크롤해도 배경고정)
* fixed - 전체 영역에서 이미지 고정(화면을 스크롤해도 배경 고정)
* local - 이미지 고정없이 같이 스크롤

<br>

### 9.background-color

<br>

### 10. Tips

* 속성 값을 설정할 때 공백을 포함한다면 반드시 ""로 감싸야 한다.

* 콘텐츠이미지 vs 배경이미지

    - 의미가 있고 변경이 자주되는 이미지는 컨텐츠 이미지로 사용
    - UI요소 같이 추가 변경이 많이 없는 이미지들은 배경이미지로 스프라이트 처리해서 사용하는것이 좋다.

* 스프라이트 이미지를 사용하는 이유

> 이미지파일이 하나씩 늘어날수록 서버로의 요청횟수와 파일용량이 증가하게 되어    
> 렌더링 성능저하로 이어지기 때문에 하나의 이미지 파일로 묶어 성능저하를 최소한으로 하기 위해.

* 배경이미지를 고정하는 방법 중 `position:fixed` 보다 `attachment:fixed` 를 사용하는것이 성능 부담이 덜하다.

<br>

참고사이트)
- [[MDN] background](https://developer.mozilla.org/ko/docs/Web/CSS/background)
- [CSS 공작소 background-repeat](http://superkts.com/css/background-repeat)