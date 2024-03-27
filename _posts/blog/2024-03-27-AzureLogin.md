---
layout: single
title: "[Azure보안] 로그인 보안 (조건부 액세스)"
excerpt: "EntraID의 로그인 보안 작업"
header:
    teaser: "/assets/teaser/2024-03-27-azure01.png"
date: 2024-03-27
last_modified_at: 2024-03-27
categories: [azure]
tags: [Azure]
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
<img src="https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/66720200-eff9-40e8-86f5-2384f99898ec" alt="2024-03-27-azure01" style="height: 400px;">
</div>

<br>

<br>

# 시작하면서...

Azure 및 Office365는 따로 해외 IP차단과 같은 설정이 존재하지 않습니다.

따라서, Azure의 보안설정을 기본값으로 사용하여 2차인증을 사용하지 않는다면, 외부의 무차별대입(BruteForce)공격에 취약할 수 밖에 없습니다.
<br>
Azure 및 Office365 환경을 구성한 뒤, 반드시 필요한 작업입니다.

아래 이미지는 실제로 구성중인 환경에서 무차별대입 공격이 들어온 상황입니다.

![1](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/05a521f5-b07c-4494-ac34-6b1caef387d0)

<br>

# Azure 보안값 기본설정

[Microsoft Entra ID의 보안 기본값](https://learn.microsoft.com/ko-kr/entra/fundamentals/security-defaults?WT.mc_id=Portal-Microsoft_AAD_IAM)

위 기술문서를 기반으로 작성하겠습니다.

 - Microsoft Entra 관리 센터(구 Azure AD) 포털에 접속합니다.

    https://entra.microsoft.com/ 

 - "개요" > "속성" > "보안 기본값 관리"를 클릭합니다.

    ![3](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/24bf55a2-60e3-4634-8063-293f4682d508)

     <br>

 - 보안 기본값 사용 옵션을 "사용(권장)" 또는 "비활성화(권장하지 않음)"으로 설정합니다.

    ![4](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/02536259-aca9-4f9a-8e9c-377a366e5fbd)

     <br>

    "사용(권장)" - 계정에 대한 기본 보안을 유지하고, 관리자 권한이 있는 계정의 MFA 설정을 원할 경우
    "비활성화(권장하지 않음)" - 계정에 대한 기본 보안 정책 불필요하고, 기본으로 설정된 MFA가 불편한 경우

 - "저장"을 클릭합니다.

<br>

# Azure 보안값 기본설정의 문제점

 - MFA 사용이 강제됨
 - SMB, SMTP 등 공유연결이 제한될 가능성 높음

제가 겪은 큰 문제점은 위 두가지 입니다.

우선, MFA 사용이 강제됨으로, 사용자의 기기에 2단계 인증툴을 설치해야 합니다.
<br>
고령의 사용자들인 점, 인증방식의 이해도가 부족한 상황에서 환경을 구축해야 했습니다.

또한, SMB 방식으로 공유프린터에서 스캔을 이용하고, SMTP 방식으로 exchange서버를 통해 outlook으로 문서를 전송하는 상황에서,
<br>
보안값 기본설정 후, 해당 기능들이 작동하지 않는 문제가 발생하였습니다.

<br>

# 조건부 액세스 설정

위와 같은 문제점들이 발생하여, 외부IP로 들어오는 무차별대입공격 및 사용자들의 환경까지 고려해야하는 상황입니다.

MS지원부서에 서비스티켓을 발행하여 위와같은 상황을 설명하여, 문제점을 해결한 방안을 문의한 결과 **"조건부 액세스"** 설정의 검토를 요청하였습니다.

[조건부 액세스란?](https://learn.microsoft.com/ko-kr/entra/identity/conditional-access/overview)

 - Azure Portal의 Entra ID로 접속합니다.

 - **(관리) > (보안) > (조건부 액세스) > (새 정책 만들기)** 순으로 이동합니다.

 ![제목 없음 (1)](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/eaf1d92a-c8e9-43ff-9a91-5650a5b96380)

  <br>

 - (사용자) 탭에서, 모든 사용자를 대상으로 할지, 특정 사용자를 대상으로 할지 선택합니다. (포함 및 제외)

![스크린샷 2024-03-27 13 14 56](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/58755142-577c-45b2-8a4a-72720659b523)

 <br>

 - (대상 리소스) 탭에서, 조건부 액세스를 적용시킬 앱을 설정합니다. 클라우드 앱을 선택하면, Office365 앱 및 자체 배포앱들에 대해 조건부 액세스를 적용시킵니다.

![스크린샷 2024-03-27 13 14 56](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/58755142-577c-45b2-8a4a-72720659b523)

 <br>

 - (조건) 탭에서, 임의의 IP주소 위치를 허용하기 위해서, **(위치) > (제외) > (선택한 위치)** 를 설정합니다.
 
 이때, 명명된 위치를 설정하지 않았다면, 선택한 위치가 표시되지 않습니다. [명명된 위치 설명](#명명된-위치-설정)

![스크린샷 2024-03-27 13 32 43](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/23abaec8-cf50-4bd1-be63-43f0f82141c7)

 <br>

 - (허용) 탭에서, (액세스 허용), (인증 강도 필요) > (암호+Mobile인증) 을 선택합니다.

![스크린샷 2024-03-27 13 37 33](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/d8c18e7a-e602-4207-a500-8e9362b878b2)

 <br>

 - 마지막으로 가장 하단의 (정책 사용)을 **설정**으로 변경해준 뒤, 저장을 눌러 정책을 저장하고 활성화합니다.

![스크린샷 2024-03-27 13 39 39](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/45dc1bff-a87b-472d-9c95-0539a648f284)

 <br>

## 명명된 위치 설정

 (조건부 액세스) > (명명된 위치) > (IP 범위 위치) 순으로 클릭하여 새로운 명명된 위치를 생성합니다.

 ![스크린샷 2024-03-27 13 23 21](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/987e017b-c10a-4f22-937b-a3e5d97e0204)

 <br>

 - **신뢰할 수 있는 위치로 표시 (체크)**
 - IP주소 (192.168.0.- 와 같은 주소가 아닌, **공인IP 주소**를 입력해야 합니다.)

 <br>

# 결과

위 방법대로 설정하셨다면, 조건부 액세스의 설정이 완료되었습니다.

허용한 IP외의 환경에서 로그인 시, 아래와 같이 인증을 요구하는 창이 나온다면 조건부 액세스 정책이 정상적으로 작동합니다.

![스크린샷 2024-03-27 13 42 30](https://github.com/JunbeomCho22/JunbeomCho22.github.io/assets/156159216/62cc6d31-9c60-4bb9-baa3-3a9fae77ce29)

**조건부액세스 정책은 변경 및 활성화 후 최소 10분 ~ 30분정도 기다려주셔야 적용됩니다.**

