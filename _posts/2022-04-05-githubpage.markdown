---
layout: post
title:  "github page 활용"
date:   2022-04-05 21:03:39 +0530
categories: githubpage
---

# github page란
Github Pages는 정적인 페이지를 호스팅 해주는 서비스입니다.  
많은 호스팅 서비스 중에 Github Pages를 선택한 이유는 다음과 같습니다.  
호스팅하는 소스코드를 공개할 경우 무료입니다.  
깃허브 리포지토리의 소스코드를 직접 호스팅해줍니다.  
무료인것도 좋지만, 깃허브 리포지토리를 직접 호스팅해주는 것은 굉장한 강점입니다.  
버전 관리 시스템인 Git을 통해 안정적으로 코드를 관리할 수 있습니다.  


# jekyll 소개
jekyll이란?  

텍스트 파일로 정적 웹페이지를 만들 수 있는 서비스임  
ruby 기반에서 실행됨  
github pages에서 무료로 호스팅 할 수 있음  
보통 markdown으로 작성된 텍스트 파일을 배포함  
https://cmjeon.github.io/env/config/jekyll/  


장점 : 간단하게 정적 페이지 호스팅  
깃헙을 이용한 안정적인 형상관리  
단점 : 사진같은거 올리기 번거로움  
마크다운 언어에 익숙해야함.


# wsl에서 jekyll

windows에선 jekyll 환경설정이 번거로움  
공식사이트에서도 wsl을 이용하여 설치하는 방법을 소개하고 있음(그러나, 공식사이트 가이드대로 하면 안됨..)  
https://jekyllrb-ko.github.io/  


그냥 wsl에 루비깔고나서, jekyll 설정하는것으로 진행하니 성공.  

https://velog.io/@hyungwook/WSL-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C-RUBY-%EC%84%A4%EC%B9%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95  

```
$ cat /etc/issue
Ubuntu 18.04.6 LTS \n \l
```

```
$gem install jekyll bundler
```
```
$jekyll -v
jekyll 4.2.2
```

# jekyll theme 고르기

Jekyll Themes 제공 사이트
대부분의 오픈소스 개발자들이 그러하듯 지킬 역시 많은 양의 테마를 오픈 소스로 제공하고 있다. 아래 사이트에 접속하시면 무료로 제공되는 테마를 원없이 구경하고 선택하실 수 있다. 오히려 많아서 선택하기 어려울 지경이다.
http://jekyllthemes.org/  
https://jekyllthemes.io/free  
http://themes.jekyllrc.org/  
https://github.com/topics/jekyll-theme  

제가 고른 테마는
https://github.com/samarsault/plainwhite-jekyll  


# 테마적용하기

```
$git clone [테마 깃주소]
$.git 폴더 지우고
$복사
```

```
$bundle install
$bundle exec jekyll serve
...
Server address: http://127.0.0.1:4000
```

# 트러블 슈팅

```
$ bundle exec jekyll serve
...
.rbenv/versions/3.1.1/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve/servlet.rb:3:in `require': cannot load such file -- webrick (LoadError)
```

이럴땐

```
bundle add webrick
```

ruby 3.0.0부터 webrick이 기본으로 포함된 gem에서 빠졌기 때문입니다.  

https://junho85.pe.kr/1850
