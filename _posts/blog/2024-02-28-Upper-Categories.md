---
layout: single
title: "[Github Blog] 상단 카테고리(Category) 수정 - 3"
excerpt: "상단 카테고리를 수정합니다."
header:
    teaser: "/assets/teaser/2024-02-28-blog01.png"
date: 2024-02-28
last_modified_at: 2024-02-28
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
<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/8e537a05-f9e4-41b9-9aea-9cb7bc4535e4" alt="2024-02-28-blog01" style="height: 400px;">
</div>

<br>

<br>

# 시작하면서..

이전 단계에서 기본적인 세팅은 모두 마쳤습니다.
<br>
블로그 우측 상단의 카테고리를 설정해야 합니다.
<br>
Url 연결 방식이기 때문에, 원하는 Url을 기입하여 블로그외 사이트로의 리다이렉트도 가능합니다.

<br>

# Navigation.yml

- 파일위치 : github.io 폴더 > _data 폴더 > navigation.yml 입니다.

<script src="https://gist.github.com/JunbeomCho22/801fee56ee53d190f2d676b7bdd749a6.js"></script>

**title: "값"**
<br>
title 값이 화면에 출력됩니다.

**url: 값**
<br>
url 값에 따라 특정 링크로 이동합니다.

**sublinks:**
<br>
부모인 메인 title에 부가적으로 생성되는 자식 카테고리입니다.

기본적으로 **_pages** 폴더 내에 .md 파일을 양식으로 사용합니다.

위의 코드에서, title: Introduce를 출력하고 url: /about/ about.md 파일을 양식으로 사용하는 페이지로 이동합니다.
<br>
즉, Introduce를 클릭하면, (username).github.io/about/으로 이동합니다.

<br>

# _pages > about.md 수정

- 파일위치 : github.io 폴더 > _pages 폴더 > about.md 입니다.

다른 파일은 아직 수정하지 않아도 괜찮습니다.
<br>
우선, about.md 를 수정하여 자기소개 페이지를 만들어봅시다 !

<script src="https://gist.github.com/JunbeomCho22/7326093c38a63af40bb24f7e2cbb815f.js"></script>

**permalink** : 고유 주소 입니다.
<br>
(해당 값 변경 시, navigation.yml 값도 변경되어야 합니다.)

**title** : 출력 표시되는 제목 입니다. (/about/ 페이지로 이동 후, 좌측 상단에 표시됩니다.)
<br>
자기소개 페이지에 어울리지 않는 것 같아서, 주석(#)처리 하였습니다.
<br>
필요에 의해 주석처리 해제하시고 사용하셔도 무방합니다.

**toc** : 간단하게, 목차와 같은 기능을 합니다.
<br>
(깔끔한 느끔이 들지 않아서, 사용하지 않았습니다.)
<br>
필요한 기능이라면, false -> true 로 변경하시어 사용해주세요.

 - toc : 목차 (클릭 시, 해당 주제로 이동.)
 - toc_sticky : 스크롤 시, 항상 우측에 toc폼 고정
 - toc_label : toc의 title을 설정합니다.

 포스팅 시, Markdown 문법의 헤더(Header)사용으로 자동으로 toc에 등록됩니다.

<br>

# 자기소개 페이지 작성

- 파일위치 : github.io 폴더 > _pages 폴더 > about.md 입니다.

toc_label 하단의 - - - 이후 **Markdown 문법** 또는 **html 문법**으로 글을 작성해주면 됩니다.
<br>
저의 경우 html 문법으로 자기소개 글을 작성해보았습니다.

<script src="https://gist.github.com/JunbeomCho22/d541e51daf53efd685f511326df82631.js"></script>

**align="center"** : 출력되는 요소를 중앙 정렬합니다.
<br>
- Markdown의 경우, 앞뒤로 <'center'><'/center'>를 붙여줍니다. ('제거)

**'h2' '/h2'** : 제목 요소입니다. h2와 /h2 사이에 작성한 제목이 출력됩니다. (h1~h6 크기 설정)
<br>
- Markdown의 경우, #~##### 이후 입력합니다.

### <center>(Example)</center>

<h2 align="center"> Hi there 👋<br/>I'm Junbeom Choi</h2>

<br>

**'p' '/p'** : 일반 텍스트 요소입니다. p와 /p 사이에 작성한 텍스트가 출력됩니다.
<br>
- Markdown의 경우, 별다른 코드없이 텍스트를 입력합니다.

### <center>(Example)</center>
<p align="center">무능한 개발자의 블로그입니다.</p>

<br>

**onclick="sendEmail()** : 해당 요소를 클릭 시, sendEmail() 함수를 실행합니다.

**function sendEmail()** : 지정한 이메일 클라이언트를 열도록 구성되어있습니다.

### <center>(Example)</center>
<h3 align="center" style="cursor: pointer;" onclick="sendEmail()">💌 >Ask me< </h3>

<br>

<script>
    function sendEmail() {
        window.location.href = "mailto:junbeom.cho22@gmail.com";
    }
</script>

<br>

# 상단 카테고리 완성

![image](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/a02fec5e-c831-48fa-b3da-fcd47a95f4b5)

완성된 화면의 예시 입니다. 우측 상단 표시한 부분이 수정되었습니다.
<br>
우선은 title 부분부터 내용까지 차근차근 수정해봅시다.
<br>
자세한 카테고리 생성 및 설정 방법은 다음 게시물에 기록하겠습니다.

*Introduce (또는 임의로 설정한 자기소개 페이지 이름)을 클릭하여, /about/으로 이동하는지 확인합니다.*

