---
layout: single
title: "[Github Blog] 나만의 블로그 만들기 - 1"
excerpt: "나만의 Github Blog 시작하기"
header:
    teaser: "/assets/teaser/2024-02-26-blog01.png"
date: 2024-02-26
last_modified_at: 2024-02-26
categories: [blog]
tags: [Blog]
toc: true
toc_sticky: true
toc_label: "목차"
---

<div style="text-align: center;">
<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/60fdb127-9861-4aa3-8f78-09a9081351b2" alt="2024-02-26-blog01" style="height: 400px;">
</div>

<br>

<br>

# 시작하면서...
기존의 vultr를 통해, wordpress 를 구축하여 블로그를 제작하였습니다.
<br>
가장 큰 문제로는 달마다 고정적으로 비용이 발생하는 문제였습니다.
<br>
비용, 커스터마이징, 편의성 등을 고려하였을때, Github Pages 를 사용하는 것이 좋다는 판단에 구축을 시작하였습니다.

많이 부족하지만, 제가 Github Pages를 구축하였던 방법을 소개해 드리려고 합니다.

<br>

# Github Pages란 ?
Github Pages(Github.io)는 본인 계정의 저장소를 바탕으로 정적 호스팅을 제공해주는 서비스 입니다.
<br>
따로 웹 서버를 구축하거나 호스팅 서비스를 이용하지 않고, 간단하게 웹페이지를 만들어 제공할 수 있습니다.

기존의 유명 플랫폼으로 운영하면 편리하지만, 커스터마이징이 불가능하다는 단점이 있습니다.
<br>
하지만, Github Pages를 통하여 블로그를 구축할 경우, 내가 원하는 UI로 커스터마이징이 가능한 장점이 있습니다.

<br>

# Github Repo 만들기

github 내에서 repository 를 생성합니다.
<br>
본인의 github ID를 repository 이름으로 사용해야 합니다 !

**(Example)**
<br>
저의 github ID 는 junbeomcho22 입니다.
<br>
따라서 repository 이름을, 'junbeomcho22.github.io' 로 생성하였습니다.

여러분은 **'(본인의 Github ID).github.io'** 로 생성하시면 됩니다.

<br>

# 기초 세팅

## Ruby 설치

- **Ruby를 설치하는 이유 ?**

  Local(127.0.0.1:4000)환경에서 변경된 사항들이 잘 적용되었는지 검토 후 push 하기 위함입니다. 

- **Ruby 설치**

    ![2](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/590c0f31-254b-4921-9837-665fab53833d)

    [Ruby 공식 홈페이지](https://rubyinstaller.org/downloads/)

    With DEVKIT 항목에 **(x86)**으로 설치 진행해주세요. **(x64 로 설치하시면 안됩니다.)**

## Jekyll 설치

    gem install jekyll

해당 명령어를 '명령 프롬포트(CMD)' 창에서 입력해줍니다. **(관리자권한 실행 필수!)**


Ruby 설치 및 Jekyll 설치가 완료되었다면, '명령 프롬포트(CMD)' 창에서 각각

    ruby -v  
    jekyll -v

명령어를 실행하여, 정상적으로 설치되어 버전이 출력되는지 확인합니다.

<br>

# minimal-mistake 테마 설치

- [Quick Start 가이드](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)
- [minimal-mistake Git 링크](https://github.com/mmistakes/minimal-mistakes)

Git 링크 접속 후,
<br>
우측 상단의 Code(녹색) 클릭 후 주소 복사

    https://github.com/mmistakes/minimal-mistakes.git

VSCode 환경에서, '폴더열기' -> 터미널 (Ctrl + j) -> git clone [git 주소] 명령어 실행

생성 된 'minimal-mistake' 폴더 내
<br>
**docs > _pages** 폴더를 최상단 폴더로 빼줍니다. (페이지 및 카테고리 작성)

- _data
- _includes
- _layouts
- **_pages**  # 위의 폴더와 같은 경로로 추출

**_pages > about.md** 파일을 열어 수정합니다.

    ---
    permalink: /about/
    title: "About"
    excerpt: "Minimal Mistakes is a flexible two-column Jekyll theme."
    layouts_gallery:
      - url: /assets/images/mm-layout-splash.png
        image_path: /assets/images/mm-layout-splash.png
        alt: "splash layout example"
      - url: /assets/images/mm-layout-single-meta.png
        image_path: /assets/images/mm-layout-single-meta.png
        alt: "single layout with comments and related posts"
      - url: /assets/images/mm-layout-archive.png
        image_path: /assets/images/mm-layout-archive.png
        alt: "archive layout example"
    last_modified_at:
    toc: true
    ---
    (아래 코드 삭제)

 **---** 아래의 코드 내용은 삭제하시고, **last_modified_at:** 부분의 "2022-05-27T11:59:26-04:00" 라인을 삭제합니다. *(미삭제시 추후 로컬환경 진입 시 오류가 발생)*

여기까지 잘 따라오셨다면 기초 설치가 완료되었습니다.
<br>
생성된 디렉토리가 아래와 같이 되어야 합니다.

![3](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/29d66ae7-2585-4ea8-ba4d-7d8b34207589)

<br>

# 로컬 서버 실행

이대로 github으로 push하여 출력되는 결과를 확인해도 괜찮지만,
<br>
즉각적인 수정이되지 않기 때문에 로컬로 출력되는 결과를 확인하는 것을 추천드립니다.
<br>
생성한 minimal-mistake 폴더에서 '명령 프롬포트(CMD)' 를 실행하셔도 되고,
<br>
'명령 프롬포트(CMD)' 를 실행하시고, minimal-mistake 폴더를경로를 지정하시면 됩니다.

    gem install bundler

    bundle exec jekyll serve

이 두 명령어를 실행하시어, .jekyll-cache 폴더와 Gemfile.lock 파일이 생성되어야 로컬 서버에 연결할 수 있습니다.

    Server address: http://127.0.0.1:4000
    Server running... press ctrl-c to stop.

해당 명령어가 보이신다면 정상적으로 연결되었습니다.
<br>
[http://127.0.0.1:4000](http://127.0.0.1:4000) 으로 바로 확인해봅니다.

![4](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/2e98cf21-af69-4f5f-a9a7-b80dbda981f4)

모든 변경사항은 실시간으로 적용됩니다.
<br>
위와 같이 출력창이 생성된다면 성공입니다.

<br>

# **# Could not find compatible versions 오류 발생시**

    저의 경우, 해당 오류가 발생하였습니다.

        Could not find compatible versions

        Because every version of minimal-mistakes-jekyll depends on jekyll-include-cache ~> 0.1
          and jekyll-include-cache ~> 0.1 could not be found in locally installed gems,
          minimal-mistakes-jekyll cannot be used.
        So, because Gemfile depends on minimal-mistakes-jekyll >= 0,
          version solving has failed.

    '명령 프롬포트(CMD)' 에서 아래 명령어 실행하여 해결되었습니다.        

        gem install jekyll-include-cache -v '0.1'

<br>

# Git 업로드

이제 모든 사항이 완료되었다면, 본인의 Git으로 업로드 하여 사이트를 구성해보도록 합니다.
<br>
**'(본인의 Github ID).github.io'** 으로 생성한 Repository 의 주소를 복사한 뒤
<br>
VSCode 환경에서, '폴더열기' -> 터미널(Ctrl + j)

    git add .
    git commit -m '커밋명'
    git remote add origin (Repository 주소)
    git push origin main

위 순서대로 터미널 창에 입력해주시면 배포가 완료되며,

**(본인의 Github ID).github.io** 로 이동하시면 블로그가 정상적으로 생성됨을 확인할 수 있습니다.