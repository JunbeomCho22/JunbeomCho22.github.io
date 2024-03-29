---
layout: single
title: "[Github Blog] 레이아웃 & 폰트 수정하기 - 6"
excerpt: "블로그의 전체적인 레이아웃 및 폰트를 수정합니다."
header:
    teaser: "/assets/teaser/2024-03-04-blog01.png"
date: 2024-03-04
last_modified_at: 2024-03-04
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
<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/687bac80-4a7a-46d0-984d-a3b3a993f212" alt="2024-03-04-blog01" style="height: 400px;">
</div>

<br>

<br>

# 시작하면서...

이전 단계에서 새로운 포스트를 포스팅하였습니다.
<br>
이때, 본문의 간격이 너무 좁다고 느껴졌고, 사이드바의 간격이 너무 넓다고 생각하였습니다.

간단한 코드수정으로 본문 및 사이드바의 레이아웃 크기를 조정해보도록 하겠습니다.

<br>

# 사이드바 레이아웃 수정

## 사이드바 너비(Width) - _variables.scss 수정

- 파일위치 : github.io 폴더 > _sass 폴더 > minimal-mistakes 폴더 > _variables.scss 파일

<script src="https://gist.github.com/JunbeomCho22/2063645d5d93d78b8fa8cf5817a200b6.js"></script>

_variables.scss 파일내 내가 필요로하는 코드를 찾기란 쉽지 않습니다.

**검색기능(Ctrl+F)**을 사용하여 $right-sidebar-width-narrow: 를 검색해봅시다.

![제목 없음](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/91328050-a2c2-4e0f-b175-bf6c77dab8b1)

해당 코드로 수정되는 범위는 위 이미지와 같습니다.
<br>
본문 영역 자체를 수정하는것이 아닌, 사이드바의 범위를 수정하여 본문영역의 크기를 늘리거나 줄이도록 합니다.

세가지 값을 임의로 수정해보신 뒤, 로컬서버[127.0.0.1:4000](http://127.0.0.1:4000)로 적용된 레이아웃을 확인해봅시다 !

## 본문 너비(max-width) - main.scss 수정

- 파일위치 : github.io 폴더 > assets 폴더 > css 폴더 > main.scss 파일

사이드바가 아닌 본문 자체의 너비를 수정할수도 있습니다.

<script src="https://gist.github.com/JunbeomCho22/f6af3e926580e34b08ed9d84522f0522.js"></script>

위 코드를 main.scss 의 하단부분에 추가해주시면 됩니다.
<br>
1600px값을 임의로 수정해보신 뒤, 로컬서버[127.0.0.1:4000](http://127.0.0.1:4000)로 적용된 레이아웃을 확인해봅시다 !

<br>

# 폰트 변경

우선 마음에 드는 폰트를 검색합니다. 저의 경우는 [Google Fonts](https://fonts.google.com/)를 사용하였습니다.
<br>
사용할 폰트를 정하셨다면, < > get embeded code를 눌러주세요.
<br>
이후, web -> @import를 클릭해주시면 코드가 @import코드로 바뀝니다.

![스크린샷 2024-03-04 오전 11 07 59](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/0dae7e96-8021-4a64-8895-a6e6be659629)

이제 코드의 @import 부분만 복사합니다.
<br>
예) @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&display=swap')

## main.scss 수정

- 파일위치 : github.io 폴더 > assets 폴더 > css 폴더 > main.scss 파일

<script src="https://gist.github.com/JunbeomCho22/9d0f8aa4d74e87984bd300b40de0c651.js"></script>

위 코드와 같이, 이전에 복사한 @import 코드를 추가하고 저장합니다.

<br>

## _variables.scss 수정

- 파일위치 : github.io 폴더 > _sass 폴더 > minimal-mistakes 폴더 > _variables.scss 파일

<script src="https://gist.github.com/JunbeomCho22/6fd463a9c5876b8c7c11b265300abd99.js"></script>

_variables.scss의 $sans-serif: 코드에 폰트명을 추가하면 적용됩니다.

<br>

# 블로그 폰트 크기 조절

## 폰트 크기 : _reset.scss 수정

- 파일위치 : github.io 폴더 > _sass 폴더 > minimal-mistakes 폴더 > _reset.scss 파일

<script src="https://gist.github.com/JunbeomCho22/01b4a05c9642d0f79227463fffa02818.js"></script>

출력되는 화면의 크기에 따라, 폰트 크기가 변경되는 구조입니다.

폰트의 크기를 임의로 변경해보고 로컬서버에서 확인하여, 원하는 크기로 설정해보도록 합시다 !

<br>

## 하이퍼링크 밑줄 제거 (선택사항) : _base.scss 수정

- 파일위치 : github.io 폴더 > _sass 폴더 > minimal-mistakes 폴더 > _base.scss 파일

새로운 포스팅을 생성하면, 제목이 하이퍼링크 처리됩니다.
<br>
저는 하이퍼링크 처리된 타이틀이 미관상 좋지않다고 판단하여 제거하려고 합니다.

<script src="https://gist.github.com/JunbeomCho22/b54d564116df58426c70835376d6ac6b.js"></script>

위 코드와 같이, text-decoration: none; 코드를 추가해주시면 하이퍼링크 처리되지 않습니다.
