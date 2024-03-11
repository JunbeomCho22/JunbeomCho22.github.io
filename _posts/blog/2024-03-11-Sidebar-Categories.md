---
layout: single
title: "[Github Blog] 사이드바 카테고리 - 10"
excerpt: "좌측 프로필 하단에 사이드바 카테고리를 생성합니다."
header:
    teaser: "/assets/teaser/2024-03-11-blog01.png"
date: 2024-03-11
last_modified_at: 2024-03-11
categories: [blog]
tags: [Blog]
toc: true
toc_sticky: true
toc_label: "목차"
---

<style>
    .gist {
        margin: 0 auto;
        width: 90%; /* 또는 원하는 너비 */
        max-height: 500px; /* 최대 높이 설정 */
        overflow: auto; /* 스크롤이 필요할 경우 스크롤 표시 */
        margin-top: 10px;
        margin-bottom: 24px;
    }
</style>

<div style="text-align: center;">
<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/e4d0016a-76f3-489d-92ac-6c0d1820bc90" alt="2024-03-11-blog01" style="height: 400px;">
</div>

<br>

<br>

# 시작하면서...

추가적으로, 좌측 프로필 하단에 카테고리를 생성하고, 게시글의 갯수를 표시하도록 하겠습니다.

이전에 포스팅한 [카테고리 생성](https://junbeomcho22.github.io/blog/Categories/)과 연결되는 내용입니다.

<br>

# navigation.yml 수정

- 파일위치 : github.io 폴더 > _data > **navigation.yml**

<script src="https://gist.github.com/JunbeomCho22/0b870e5b77c46847a9921bb9ee4c56bf.js"></script>

기존에 카테고리 생성 시 수정했던 navigation.yml 내용을 그대로 사용합니다.

<br>

# nav_list_main 생성

- 파일위치 : github.io 폴더 > _includes > **nav_list_main 파일 (신규생성)**

<script src="https://gist.github.com/JunbeomCho22/6f1800ae0893403188d074dfed4bdeb2.js"></script>

위의 코드를 그대로 복사하여 **nav_list_main**을 생성합니다. (해당파일은 확장자가 없습니다.)

<br>

## #(추가사항) 토글식 카테고리 생성

- 파일위치 : github.io 폴더 > _includes > **nav_list_main 파일**

선택사항 입니다.
<br>
카테고리가 늘어날 경우, 사이드바가 지저분해질 수 있기때문에, 대분류 카테고리를 토글식으로 변경하려고 합니다.

<script src="https://gist.github.com/JunbeomCho22/b57d28cd1c833289db1a3a0afba2df79.js"></script>

기존 코드와의 변경 사항입니다.

**id="blogSubMenu"** 요소를 **style="display: none;"** 처리하여, 기본적으로 표시되지 않게 설정하였습니다.

**function toggle(id)** 함수를 추가하였습니다.

대분류 Blog를 클릭 시, **onclick="toggle('blogSubMenu')"**가 동작하여
<br>
toggle함수가 작동하여 toggle함수가 작동합니다.
<br>
toggle함수가 작동하면 id="blogSubMenu" 요소의 display: none; 코드가 display: block; 으로 변경되어 화면에 출력됩니다.

<script src="https://gist.github.com/JunbeomCho22/044164680236b909229f1f3e74de5941.js"></script>

위 코드를 참고하여, 새로운 토글 카테고리를 생성해봅시다 !
<br>
한글로 적혀진 부분을 자신이 설정한 값에 맞게 수정하여 사용해야 합니다.

<br>

# sidebar.html

- 파일위치 : github.io 폴더 > _includes > **sidebar.html**

<script src="https://gist.github.com/JunbeomCho22/a7d5ff06c342baf14c4cf34a0f287751.js"></script>

기존의 sidebar.html 에서 include nav_list_main의 사용을 지정하는 코드가 추가되었습니다.
<br>
위 코드를 참고하여, 기존 코드를 덮어씌우거나 여러분의 코드에 코드를 추가하여 수정하시면 됩니다.

<br>

# sidebar_main: true 추가

## 파일위치 : github.io 폴더 > _config.yml 파일

<script src="https://gist.github.com/JunbeomCho22/706cfeb1838b68f120cf21dd025d729c.js"></script>

**defaults:** 하단에 **sidebar_main: true**를 추가하여, sidebar_main 사용을 선언합니다.

<br>

## 파일위치 : github.io 폴더 > _pages > about.md 파일 / categories > 각각 카테고리.md 파일

**about.md 파일 및 각각의 카테고리.md** 파일에 **sidebar_main: true**를 추가합니다.

    title: "카테고리: Blog"
    layout: archive
    permalink: /blog/
    author_profile: true
    sidebar_main: true

<br>

## 파일위치 : github.io 폴더 > index.html 파일

**index.html** 파일에 **sidebar_main: true**를 추가합니다.

    layout: home
    author_profile: true
    sidebar_main: ture

<br>

# 완성

![제목 없음](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/d63121d8-00e1-4dae-b7f7-23535d103584)

**최소한 1개이상의 카테고리에 대한 포스트가 존재해야 사이드바에 카테고리가 출력됩니다.**

로컬환경에서 사이드바 카테고리를 클릭 시, 정상적으로 페이지가 이동하는지 테스트를 거친 뒤 배포합니다.





