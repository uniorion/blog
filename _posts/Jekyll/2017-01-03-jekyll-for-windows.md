---
layout: post
comments: true
categories: Jekyll
title: Windows에 Jekyll 설치하기
---

### 1. 필요한 요소
* Ruby - Jekyll은 루비 기반
* Jekyll
* Python - syntax highlignting 을 사용하기 위한 Pygments 가 파이썬 기반
* rouge - code blocks 사용을 위해

<br>

### 2. 루비(Ruby) 설치하기

#### 2.1 설치파일 다운받기
> http://rubyinstaller.org/downloads/

#### 2.2 아래 옵션을 선택하면 어느 경로에서든지 루비를 실행할 수 있다
![ruby-install-step]({{ site.baseurl}}/static/img/content/ruby-install-step.PNG)

설치된 루비 버전확인
{% highlight lua %}
ruby -v
{% endhighlight %}

#### 2.3 Development Kit 설치
같은 사이트에서 dev kit을 다운받아 압축해제, 초기화 및 루비와 binding 해준다
{% highlight lua %}
cd C:\RubyDevKit

ruby dk.rb init

ruby dk.rb install
{% endhighlight %}

<br>

### 3. 지킬(Jekyll) 설치하기
루비의 gem 패키지 인스톨러를 사용하여 지킬 설치
{% highlight lua %}
gem install jekyll
{% endhighlight %}

code blocks 사용을 위해 rouge를 설치
{% highlight lua %}
gem install rouge
{% endhighlight %}

<br>

### 4. 파이썬(Python) 설치하기

#### 4.1 설치파일 다운받기
> https://www.python.org/downloads/

#### 4.2 환경변수 설정
아래 경로를 Path 에 추가
> C:\Program Files\Python36  
> C:\Program Files\Python36\Scripts

<br>

### 5. Pygments 설치
syntax highlighting 을 사용하기 위해서 Pygments를 설치 (관리자권한)
{% highlight lua %}
pip install Pygments
{% endhighlight %}
윈도우 계정이 한글일 경우 오류가 발생할 수 있음

<br>

### 6. 지킬(Jekyll) 실행하기

#### 6.1 wdm 설치
{% highlight lua %}
gem install wdm
{% endhighlight %}

#### 6.2 작업 폴더에서 지킬 실행
{% highlight lua %}
jekyll serve
{% endhighlight %}

#### 6.3 127.0.0.1:4000 에 접속 확인
![jekyll-serve-run](../assets/jekyll-serve-run.PNG)

<br>

### 7. 지킬(Jekyll) 사이트 생성하기
{% highlight lua %}
jekyll new ./blog
{% endhighlight %}


<br>

참고사이트) 
- [Jekyllrb-ko](http://jekyllrb-ko.github.io/)
- [WhaTap Tech Blog - Jekyll 윈도우에 설치해서 사용하기](http://tech.whatap.io/2015/09/11/install-jekyll-on-windows/)