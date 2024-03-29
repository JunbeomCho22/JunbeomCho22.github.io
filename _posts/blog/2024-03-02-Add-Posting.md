---
layout: single
title: "[Github Blog] 포스팅 글 생성하기 - 5"
excerpt: "_posts 폴더를 생성하고, 새로운 포스팅을 생성합니다."
header:
    teaser: "/assets/teaser/2024-03-02-blog01.png"
date: 2024-03-02
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
<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/929571ea-0d81-4c37-a657-8ed1033d0ca5" alt="2024-03-02-blog01" style="height: 400px;">
</div>

<br>

<br>

# 시작하면서...

이전 단계들에서, 기초적인 설정들을 완료하였습니다.
<br>
이제 포스팅을 올리는 방법에 대해 알아보겠습니다.
<br>
카테고리.md 파일을 만들었던 방법과 비슷하기 때문에 어렵지않게 포스팅을 생성이 가능하다고 생각됩니다.

<br>

# _posts 폴더 생성

- 파일위치 : github.io 폴더 > _posts 폴더 (신규생성)

최상위 폴더 위치에 _posts 폴더를 생성합니다.

![스크린샷 2024-03-02 오후 1 45 19](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/b460a6fb-ec7b-494e-a61e-4599129ac423)

앞으로 생성되는 포스팅.md 파일은 _posts 폴더내에 생성합니다.
<br>
여기까지 준비하신다면, 포스팅을 생성할 모든 준비가 완료되었습니다.

<br>

# 포스팅 생성하기

## &nbsp; 양식 작성

- 파일위치 : github.io 폴더 > _posts 폴더 > (Date "yyyy-mm-dd)-name.md 파일 (신규생성)

<script src="https://gist.github.com/JunbeomCho22/8635431577c495dfa704ed6b2bb0ceb6.js"></script>

제가 현재 작성한 글의 양식을 예시로 살펴보겠습니다.
<br>
'- - -'로 구분되어 있는 부분을 수정하여 양식을 작성합니다.

- **파일이름** : yyyy-mm-dd-파일-이름.md 와 같이 작성합니다.

- title: 화면에 출력되는 포스트의 제목
- excerpt: 포스트 목록에서 출력되는 포스트의 상세설명
- header:
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
teaser: 포스트 목록에서 출력되는 포스트의 썸네일 이미지
- date: 포스트 작성일
- last_modified_at: 포스트의 마지막 수정일
- categories: 포스트의 카테고리
- tags: 포스트의 태그

<br>

### # TOC 생성 (추가사항)

toc는 Table of Contents의 약칭으로, 게시물 우측에 생성되는 목차입니다.
<br>
필수항목은 아닙니다.

양식 작성시 아래 항목들을 추가해주시면 적용됩니다.
<br>
지정방법으로는, Markdown의 헤더(Header)인 #을 사용해주시면 자동으로 기재됩니다.

**(별도의 목차 사용시, 적용되지 않습니다.)**

- toc : true # 클릭 시 해당 타이틀로 이동
- toc_sticky : true # 화면을 스크롤을 해도 항상 우측 상단에 고정됩니다.
- toc_label : "title_text" # toc의 제목입니다. 지정하지 않으면 기본값으로 표시됩니다.

<br>

## &nbsp; 내용 작성

- 파일위치 : github.io 폴더 > _posts 폴더 > 생성한포스트.md 파일

양식 작성도 끝마쳤다면 ' - - - ' 이후의 공간에 포스트 내용을 작성해 봅시다 !

![스크린샷 2024-03-02 오후 2 07 45](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/9993c78e-0304-406a-bef4-4cc6c8b62deb)

<br>

### 이미지 업로드

저의 경우엔, 생성한 github.io repo의 Issue에 이미지를 업로드 후, 코드를 생성하여 포스트에 사용하였습니다.
<br>
아래 순서에 맞게 이미지 파일을 업로드하고, 포스트에 이미지를 업로드 해봅시다 !

- (github ID).github.io 로 생성한 repo의 상단탭의 Issues를 클릭합니다. (Code / **<u>Issuses</u>** / Pull requests ...)

- **New Issue**를 클릭하여 새로운 Issues 생성 창으로 이동합니다.

- 이미지 파일을 **Write 블록**안으로 드래그 하면 자동으로 코드가 생성됩니다.

- 해당 코드를 복사하여 포스트에 붙여넣으면 이미지가 출력됩니다.

![스크린샷 2024-03-02 오후 2 35 13](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/12c0f185-ab4c-4e43-a1ff-e91fb226fc6b)

위의 이미지와 같이 코드가 표시되고 해당 코드를 포스트에 옮겨야 합니다.

<br>

### Markdown 문법

이전에도 설명드린대로, Github Blog는 Markdown 문법이 적용됩니다.
<br>
이중 적용되는 문법도 있는 반면, 적용되지 않는 문법들도 있습니다. 
<br>
그렇기에, 항상 배포전에 Localserve(127.0.0.1:4000)에서 구동 후 포스트의 내용을 확인하고 포스팅 해야합니다.

우선은, 포스트 작성시 [공식문서](https://mmistakes.github.io/minimal-mistakes/docs/utility-classes/#image-alignment) 및 서칭을 통해 제가 사용했던 문법들을 간략히 기재해 보겠습니다.

### Header

      # ~ ###### 로 제목 크기에 따라 h1 ~ h6을 나타낸다

<br>

### Text

**강조 텍스트**

      **강조된 텍스트입니다**

*기울여진 텍스트*

      *기울여진 텍스트*

<u>밑줄</u>

      <u>밑줄 있는 텍스트</u>

**줄바꿈**

      <br> : 텍스트 사이에 추가하여 줄바꿈 출력

**공백**

      &nbsp; : 텍스트 사이에 추가하여 공백 출력

<br>

### 링크

**링크만 있는 inline 링크** <http:127.0.01:4000>

      <http:127.0.01:4000>

**설명 있는 inline 링크** [로컬테스트](http:127.0.01:4000)

      [로컬테스트](http:127.0.01:4000)

<br>

### 문자 정렬

- **왼쪽 정렬 {: .text-left}** (Default)

      왼쪽 정렬
      {: .text-left}

- **중앙 정렬 {: .text-center}**

      중앙 정렬
      {: .text-center}

- **오른쪽 정렬 {: .text-right}**

      오른쪽 정렬
      {: .text-right}

<br>

### 이미지 정렬 

- **왼쪽 정렬 {: .align-left}** (Default)

      (이미지코드)
      {: .align-left}

- **중앙 정렬 {: .align-center}**   

      (이미지코드)
      {: .align-center}

- **오른쪽 정렬 {: .align-right}**

      (이미지코드)
      {: .align-right}

<br>

지금까지 제가 포스팅을 작성하면서 자주 사용했던 내용들을 기록하였습니다.
<br>
포스팅전 항상 로컬환경에서 테스트 후 이상이 없는것을 확인한 뒤 git push 해주세요 !