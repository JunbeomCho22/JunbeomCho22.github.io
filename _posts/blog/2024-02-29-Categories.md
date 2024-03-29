---
layout: single
title: "[Github Blog] 카테고리(Category) 생성 - 4"
excerpt: "카테고리를 생성합니다."
header:
    teaser: "/assets/teaser/2024-02-29-blog01.png"
date: 2024-02-29
last_modified_at: 2024-02-29
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
<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/feda458f-eb63-46f6-afa6-5e7968d0547b" alt="2024-02-29-blog01" style="height: 400px;">
</div>

<br>

<br>

# 시작하면서..

이전 단계에서 상단 카테고리 및 간단한 자기소개 페이지(about.md)를 작업해보았습니다.
<br>
이번 시간에는 나에게 맞는 카테고리를 설정하고, md파일을 생성하는 방법에 대해 알아보겠습니다.

<br>

# 카테고리 파일(.md) 생성

- 파일위치 : github.io 폴더 > _pages 폴더 > categories 폴더 (신규생성) > (카테고리명.md)

저는 카테고리 예시로 **Blog.md** 파일을 생성하겠습니다.

<script src="https://gist.github.com/JunbeomCho22/227b2cac18b0f614ab9bdd279df5add0.js"></script>

위 코드를 참고하시어, 여러분들이 원하는 이름의 카테고리를 생성해봅시다 !

<br>

# #새로운 카테고리 생성 시

- 파일위치 : github.io 폴더 > _data > navigation.yml

항상 새로운 카테고리를 생성 시, 카테고리의 permalink를 navigation.yml에도 동일하게 적용시켜주셔야 합니다.

<script src="https://gist.github.com/JunbeomCho22/9b0491666bc016f3bdda26679bc0fc81.js"></script>

위 코드를 참고하여 ,카테고리.md 파일을 생성하고 navigation.yml의 title 및 permalink를 추가하여 카테고리를 제작해봅시다 !

<br>

![image](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/7e48f067-4f94-4d5a-a595-85e2bbd4650a)

완성된 출력 화면입니다.

<br>

# #sub 카테고리 생성 시

## Masthead.html 수정

- 파일위치 : github.io 폴더 > _includes > masthead.html

<script src="https://gist.github.com/JunbeomCho22/b07553a7d7a8703815d85e157bf71b3e.js"></script>

ul class="visible-links" 하단의 코드에 Dropdown 관련 코드를 추가하였습니다.

## _navigation.scss 수정

- 파일위치 : github.io 폴더 > _sass > minimal-mistakes > _navigation.scss

<script src="https://gist.github.com/JunbeomCho22/8b39716ee322bd676c4a20518a9ae70d.js"></script>

**Ctrl + F > .greedy-nav 검색 (171째 행)**

기존의 **.greedy-nav** 를 위 코드로 대체합니다.

## Navigation.yml 수정

- 파일위치 : github.io 폴더 > _data > navigation.yml

<script src="https://gist.github.com/JunbeomCho22/f421b73422f6315b3f198d19f4f30a10.js"></script>

sublinks를 사용하기 위해선, 부모 카테고리의 url을 제거하거나, 주석(#)처리 해야합니다.

<br>

## **부모 카테고리 (main:)**

**'Introduce'**의 url을 주석 처리하였습니다.

<br>

## **자식 카테고리(sublinks:)**

**'About Me'**
<br>
기존 'Introduce'에 사용하던 about.md 의 permalink를 url로 사용하였습니다.
<br>
자식 카테고리인 'About Me'를 클릭하면 about.md 페이지로 이동합니다.

**'Career"**

<script src="https://gist.github.com/JunbeomCho22/205fb92ef19f283138879b29a419a85c.js"></script>

_pages > categories 폴더내에 'Career.md'파일을 생성해야 합니다.
<br>
위 코드를 참고하여 md파일을 작성한 뒤 navigation.yml의 url을 동일하게 설정해주세요.

<br>

# 완성

 - **Introduce > About Me** 를 클릭하게되면 **/about/** 으로 이동하게 됩니다.

![image](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/8c37a5cf-634e-422c-b859-2e778a5db001)

<br>

 - **Introduce > Career**를 클릭하게되면 **/career/** 으로 이동하게 됩니다.

![image](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/59a1f17d-4ad1-411d-be85-44c4a3ad5cd8)