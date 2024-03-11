---
layout: single
title: "[Github Blog] 검색 노출 (Google Search Console) - 9"
excerpt: "Google Search Console을 사용하여 블로그 검색 노출을 활성화합니다."
header:
    teaser: "/assets/teaser/2024-03-07-blog01.png"
date: 2024-03-07
last_modified_at: 2024-03-07
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
<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/033222ee-5309-42e9-8858-c65a7c2629f9" alt="2024-03-07-blog01" style="height: 400px;">
</div>

<br>

<br>

# 시작하면서...

이전 포스트에서 **'Google Analystics'**를 사용하여, 방문자 통계를 확인했다면.

이번 포스트에서는 **'Google Search Console'**을 사용하여 사용자들이 구글 검색 시
<br>
내 블로그가 검색창에 나타나도록 설정해보겠습니다.

<br>

# Google search Console

**Google Search Console**은 Google 검색 시, 나의 블로그가 나타날 수 있도록 등록하는 서비스입니다.

## 시작하기

우선은 [Google Saerch Console](https://search.google.com/search-console/about)로 이동합니다.

**'시작하기'** 버튼을 눌러 다음으로 이동합니다.

<br>

## URL 접두어

<img width="700" alt="1" src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/60f51b33-29a1-4103-9f84-62fe27a21e39">

도메인 옵션은 github.io가 아닌 개인의 도메인으로 블로그 개설 시, 사용하는 옵션입니다.

저는 github에서 제공하는 url을 사용하기 때문에, 우측의 **'URL 접두어'**를 사용하겠습니다.

여러분의 **https://'Github ID'.github.io** 주소를 입력한 뒤 **'계속'** 버튼을 눌러 다음으로 이동합니다.

<br>

## 소유권 확인

<img width="500" alt="2" src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/7a1cbaf9-093d-48f6-919f-a8c116b4b7ce">

Google계정과 블로그 주소의 사용자가 같은지 소유권 확인이 필요합니다.

여러가지 옵션이 있지만, 저는 **HTML 파일** 방법을 사용하겠습니다.

google로시작하는 .html 파일을 다운로드 받습니다.

<br>

## google ~ .html

다운로드 받은 html 파일은 **github.io 폴더(Root)**내에 위치해주면 됩니다.

파일을 옮겨준 뒤, 로컬에서 **127.0.0.1:4000/google(파일명).html** 로 접속 테스트를 해주세요.

<img width="395" alt="스크린샷 2024-03-07 13 59 56" src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/fdd7b80f-3154-4e49-9a9c-fef974d91dfc">

위 이미지와 같이 출력되었다면 정상적으로 준비를 마치셨습니다.

Google Search Console로 돌아가서, **'확인'** 버튼을 클릭하여 소유권 확인을 완료하세요.

<br>

## sitemap.xml

sitemap.xml을 이용해 Google 크롤러가 주기적으로 나의 블로그 url을 체크할 수 있도록 설정해야 합니다.

<script src="https://gist.github.com/JunbeomCho22/95e070d556507729729a3516bb1187f2.js"></script>

위의 코드를 복사하여 google ~.html 과 같은 경로인 **github.io 폴더(Root)**내에 **sitemap.xml**을 만들고 붙여넣기 합니다.

<img width="981" alt="스크린샷 2024-03-07 14 07 01" src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/524a7e9c-6e43-4a28-b57c-ef5b59d1ff44">

완료되었다면, 로컬 127.0.0.1:4000/sitemap.xml로 이동하여 위 이미지와 같은 형식으로 결과가 출력되는지 확인합니다.

<br>

## robot.txt

<script src="https://gist.github.com/JunbeomCho22/c88aa767298ff4b6a3c87139d089ba2e.js"></script>

위의 코드와 같이 **github.io 폴더(Root)**내에 robot.txt를 생성합니다.

robot.txt와 관련하여 아래의 게시물에 자세히 설명되어 있습니다.

[robots.txt란?](https://www.cloudflare.com/ko-kr/learning/bots/what-is-robots-txt/)

<br>

## sitemap.xml 등록

<img width="1026" alt="스크린샷 2024-03-07 14 16 50" src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/4aa15a51-4823-44de-ab5a-e4217087226c">

Google Search Console 좌측 탭의 **'색인생성'** > **'sitemaps'** 으로 이동합니다.

새 사이트맵 추가의 **'사이트맵 URL 입력'** 란에 sitemap.xml을 입력한 뒤, **'제출'**버튼을 클릭합니다.

처음 등록할 때는 위의 이미지와 같이 성공이 출력되지 않습니다.
<br>
알수없음, 실패 등등 다양한 내용이 출력됩니다.
<br>
과정중에 문제가 있거나, 코드가 잘못된 것이 아니니 차분히 기다리시면 됩니다.

<br>

# 등록 결과

<img width="861" alt="스크린샷 2024-03-07 14 22 14" src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/a33f2a2d-7014-4eac-99aa-b8493fc137cf">

등록이 완료되면 구글 검색창에 노출이 시작됩니다.
<br>
아직 블로그 포스트는 색인이 되지 않았는지, 사이트 메인만 노출이 되고있습니다.

저의 경우는 2~3일 정도 기다린 뒤, 검색창에 노출이 시작되었습니다.
