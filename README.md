<!-- Made By     : 2_tuna_97 -->

# iOS앱 KimeME
<br>

<p align="center">
    <img width="400px" src="https://user-images.githubusercontent.com/50114556/121816502-016e0100-ccb7-11eb-96a9-7f9b0b4b6cd3.png">
</p>
<br>
<!-- KimpMe 앱 사진 -->
<p align="center">
    <img width="900px" src="https://user-images.githubusercontent.com/50114556/122393980-6de74980-cfb0-11eb-8838-8f09b2269645.png">
</p>
<br>

## 개발 목표

* 2021년 2월부터 내 주변의 많은 사람들이 코인판에 발을 들이게 되었다.
<br> 당시만 해도 극적인 수익률에 광기에 취해있었지만, 김프란 존재를 모르고 시작한 분들이 생각 보다 많았다.
<br> 그렇게 광기에 베일이 감춰진 김프에 의해 지금 많은 사람들이 큰 손해를 보기 시작하면서, 김프를 빠르고 쉽게 확인할 수 있는 방법을 고민하다가 위와 같은 앱을 제작하게 되었다.
* 제작에 늦은 이유는 바쁜 인턴 생활과 기말고사 시즌으로 인한 지연..
* 처음으로 제작한 iOS앱에 의의를 둠
<br>

### 김프란?
> 2017년 한국 뿐만 아니라 전세계에 암호화폐붐이 일면서 유행한 신조어이다. <br> 구글 트렌드 통계에 따르면 2016년 이전에는 거의 쓰이지 않았으며, 다른 의미의 '한국 프리미엄'만이 쓰였다. 2017년 5월 땡글이라는 암호화폐 전문 커뮤니티에서 한 사용자가 시세 정보를 알려주는 크롬 확장프로그램을 개발하면서 처음 김치 프리미엄이라는 단어를 사용하여 정착되기 시작했다. <br> 이후 '코인원 채팅방' 및 디시인사이드 비트코인 갤러리에서 '김프'라고 줄여 부른 단어가 크게 유행하면서, 다른 투자자들 사이로 퍼져나갔다. [김치프리미엄 나무위키](https://namu.wiki/w/%EA%B9%80%EC%B9%98%20%ED%94%84%EB%A6%AC%EB%AF%B8%EC%97%84)
<br>

## KimpME 기능 소개
> 사용자가 가장 쉽고 빠르게 김프를 확인할 수 있도록 제작 (못만들어서 기능 추가 안한것이 아님)

1. 실시간 김치 프리미엄 확인 기능 <br>
[바이낸스](https://binance.com/ko)시세와 [업비트](https://upbit.com)의 실시간 시세를 받아와 차액을 계산하여 각 코인당 김치 프리미엄 가격을 표기

2. 다양한 정렬 조건으로 원하는 순으로 정렬 <br>
현재가 최고, 최저액순, 김프 최고, 최저순, 전일대비 최고, 최저순, 거래량 최고, 최저순으로 다양한 정렬을 지원함 (구현하는데 많이 힘들었음, 버튼이 꼬이게 되는것이 문제)

3. 검색하여 해당 코인 시세 및 김프 확인 <br>
상단에 SearchBar를 두어서 원하는 코인의 김프 및 현재가를 볼 수 있도록 제작 <br>
현재 한글명, 영어 티커를 지원하며, 추후 한글 초성 검색까지 지원되도록 업데이트 할 예정 <br>
<br>

## 개발 상황

 - Kakao AdFit 적용 완료 (2021.06.23)
    > 서버 유지비가 필요합니다...🥲
 - 네트워크 상태 확인 적용 중 (2021.06.24)
<br>

## 사용 기술
 - Jetson NX가 현재 바이낸스 시세와 업비트 시세를 가지고와 DB에 실시간으로 저장 (Python)
    > DB에는 영문 티커, 한글 티커, 티커 이미지 경로, 업비트 가격, 바이낸스 가격, 김프 퍼센트, 김프 가격, 전일대비 퍼센트, 전일대비가, 업비트 거래량, 바이낸스 거래량으로 저장 (바이낸스 거래량은 현재 미지원)

 - 실시간 DB정보를 Firebase Realtime Database에 계속 Update (Python, 주기 0.1초)
 - Snapkit으로 UI구축 (Swift)
 - Kingfisher을 통한 티커 이미지 캐시화 (Swift)
 - Firebase Realtime Database에서 계속 KimpMe로 실시간 정보 갱신
<br>

## 추후 목표
 * 앱을 좀 더 다듬어서 앱스토어에 퍼블리싱 하는것이 목표! <br>
 현재 아쉬운 디자인과 색상 배치는 다크모드시에 눈이 아픈 경향이 있음. (iOS15에서 systemMint지원은 아쉽다)
 * 데이터 경량화를 통해 Firebase요금을 덜 내는 방식 구현 <br>
 데이터가 작은데도 불구하고, DB 다운로드 횟수가 많아 금액이 부담.
 * 더 많은 회사 지원 <br>
 김프 비교대상으로는 후오비 코리아 지원 및 국내 거래소 추가 (빗썸, 코인원)
<br>

## 참고 문서
* [업비트 소켓통신](https://docs.upbit.com/docs/upbit-quotation-websocket)
* [바이낸스 소켓통신](https://github.com/binance/binance-spot-api-docs)
* [MariaDB](https://mariadb.org)
* [Firebase](https://firebase.google.com/?hl=ko)
* [Kingfisher](https://github.com/onevcat/Kingfisher)
* [snapkit](https://github.com/SnapKit/SnapKit)
<br>

## 코인 투자에 참고해야하는 사이트
* [바이낸스](https://binance.com/ko)
* [업비트](https://upbit.com)
<br>

## Developer
<table>
    <tr>
        <td align="center" width="135px">
            <a href="https://github.com/97tuna"><img height="100px" width="100px" src="https://avatars3.githubusercontent.com/u/50114556?s=400&v=4"></img></a><br />
            <sub> <b> 97tuna </b> </sub>
        </td>
    </tr>
</table>

<!-- 2020.12.27(SUN) [MOD] update README.md -->
