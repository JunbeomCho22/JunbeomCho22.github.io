---
layout: single
title: "[Github Blog] 방문 통계 (Google Analystics) - 8"
excerpt: "Google Analystics을 사용하여 방문 통계를 확인합니다."
header:
    teaser: "/assets/teaser/2024-03-06-blog01.png"
date: 2024-03-06
last_modified_at: 2024-03-06
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
<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/ea4637f6-a09a-4f60-9274-1b25e57e4b11" alt="2024-03-06-blog01" style="height: 400px;">
</div>

<br>

<br>

# 시작하면서...

기업, 개인매장 등 많은 분야에서 운영하는데에 있어 가장 큰 원동력은 **'얼마나 많은 사람들이 구매(방문)하는가?'** 라고 생각합니다.

블로그 운영도 같은 맥락에서, **'얼마나 많은 사람들이 내 블로그를 방문하고 있을까?'** 라는 생각이 자연스럽게 드실겁니다.

이를 분석하여 제공해주는 도구가 **'Google Analystics'** 입니다.

<br>

# Google Analystics 등록

## 시작

[Google Analystics](https://analytics.google.com)에 접속하시고, **<u>'측정시작'</u>** 버튼을 눌러주세요

![1](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/d7f8f5e5-2b96-4146-ad2c-1452fdba26ff)

<br>

## 계정 설정

계정 이름은 임의의 이름을 적어주시면 됩니다. 다음으로 이동합니다.

![2](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/a2363b36-dad3-475b-b221-6ad0706168fc)

<br>

## 속성 설정

속성 이름에는 나의 블로그 주소를 입력해주고, 시간대 및 통화를 나에게 맞게 설정하고 다음으로 이동합니다.

![3](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/3237eb36-d32f-47fa-88a5-96d2c5a46d2d)

여기까지 해주시면 Google Analystics 등록은 끝나고, 메인화면으로 이동합니다.

<br>

# Tracking ID 설정

1) Analystics의 좌측탭 하단의 **설정**을 클릭합니다.

<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/bb35e178-1034-472b-9777-8bc631c0126d" alt="4" style="margin-left: 100px; max-height:600px;">

<br>

2) **데이터 수집 및 수정 > 데이터 스트림**을 클릭합니다.

![5](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/34c35c50-16a3-400f-92dc-92fa8c049ad8)

<br>

3) **스트림 목록 > 자신의 Github Blog 주소 클릭 > 측정 ID**

측정 ID는 설정에 사용해야 합니다.

![6](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/3c4dad4f-304a-4196-a802-eef1dacb78ad)

<br>

# _config.yml 수정

- 파일위치 : github.io 폴더 > _config.yml 파일

<script src="https://gist.github.com/JunbeomCho22/30b6b970b0b35222d23ce42f15854b27.js"></script>

**tracking_id** 항목을 **자신의 측정 ID**로 수정합니다.

<br>

# 완성

![7](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/aa3f3ff5-9d04-42a8-aaef-33516f52df64)

모든 설정을 완료하고 배포까지 마친 뒤,
<br>
다시 Google Analystics에 접속해보면 방문자 수가 카운팅됩니다.