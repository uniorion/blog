
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
![ruby-install-step](../assets/ruby-install-step.PNG)

설치된 루비 버전확인
```sh
ruby -v
```

#### 2.3 Development Kit 설치
같은 사이트에서 dev kit을 다운받아 압축해제, 초기화 및 루비와 binding 해준다
```sh
cd C:\RubyDevKit

ruby dk.rb init

ruby dk.rb install
```

<br>

### 3. 지킬(Jekyll) 설치하기
루비의 gem 패키지 인스톨러를 사용하여 지킬 설치
```sh
gem install jekyll
```

code blocks 사용을 위해 rouge를 설치
```sh
gem install rouge
```

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
```sh
pip install Pygments
```
윈도우 계정이 한글일 경우 오류가 발생할 수 있음

<br>

### 6. 지킬(Jekyll) 실행하기

#### 6.1 wdm 설치
```sh
gem install wdm
```

#### 6.2 작업 폴더에서 지킬 실행
```sh
jekyll serve
```

#### 6.3 127.0.0.1:4000 에 접속 확인
![jekyll-serve-run](../assets/jekyll-serve-run.PNG)

<br>

### 7. 지킬(Jekyll) 사이트 생성하기
```sh
jekyll new ./blog
```


<br>

참고사이트) 
- [Jekyllrb-ko](http://jekyllrb-ko.github.io/)
- [WhaTap Tech Blog - Jekyll 윈도우에 설치해서 사용하기](http://tech.whatap.io/2015/09/11/install-jekyll-on-windows/)