# Fitmap
**FITMAP은 사용자의 운동 기록을 Heatmap으로 시각화해 보여주고, 균형있는 운동 부위 추천을 통해 사용자들이 건강한 운동 습관을 형성할 수 있도록 돕는 서비스입니다.** <br>
[FITMAP 소개 자료](SSAFY_서울7반_1조_FITMAP.pdf) 

<!-- ![fitmap_main](https://user-images.githubusercontent.com/83811753/175043224-25522a43-b5d2-4a99-a2ea-f5cdf6c8dae4.png)<br> -->
<!--FITMAP is a service that helps users to build their healthy exercise habits through visualizing their daily exercise records as a heatmap, and recommending daily workout parts.<br>-->

## 소개 및 시연 영상
### 시연 영상
[![시연영상](https://user-images.githubusercontent.com/83811753/176327316-910fcbcd-6ee4-4656-b35c-cc1f97896ff9.png)](https://youtu.be/VpVORzzLoD4 "FITMAP 시연 영상")

### 발표 영상 https://youtu.be/uRWiP32PyVA

<!-- [![발표영상](http://img.youtube.com/vi/uRWiP32PyVA/0.jpg)](https://youtu.be/uRWiP32PyVA "FITMAP 발표") -->

<br>

## 핵심 기능
1. Heatmap을 통한 운동 기록 시각화<br>
2. 알고리즘에 의한 운동 부위 추천<br>
3. 월별 운동 시간 기준 랭킹 제공<br>
4. 회원 별 개인 페이지 및 팔로우 기능<br>

## 실행 환경
- Window 11
- Java version  zulu 8.33.0.1
- spring-tool-suite version 3.9.14
- lombok
- Chrome

## 기술 스택
<p align="center">
<img src="https://img.shields.io/badge/java-007396?style=for-the-badge&logo=java&logoColor=white">
<img src="https://img.shields.io/badge/spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white">
<img src="https://img.shields.io/badge/springboot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white">
<img src="https://img.shields.io/badge/mysql-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
</p>
<p align = "center">
<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">
<img src="https://img.shields.io/badge/vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white">
<img src="https://img.shields.io/badge/html-E34F26?style=for-the-badge&logo=html5&logoColor=white">
<img src="https://img.shields.io/badge/css-1572B6?style=for-the-badge&logo=css3&logoColor=white">
<img src="https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=white">
</p>


## 구현 기능

### Backend

- DB 설계 및 mybatis 데이터 객체 연결 및 별 기본적인 CRUD 작성
- MVC 패턴으로 RESTful API 개발
- 회원가입 시 패스워드 암호화, 로그인 기능 예외 처리
- 사용자 별 운동 부위 추천, 동영상 추천
- 월별 운동 시간 기준 회원 랭킹 산정
- 팔로우한 친구의 최근 운동 기록 산정

### Frontend

- Vuex 기반 MVVM 패턴으로 작성
- 회원 별 개인 페이지 작성, 히트맵 표시
- 추천 운동 부위 별로 운동 영상 표시
- 랭킹, 친구 운동 근황 표시
- 회원 팔로우 언팔로우 기능
- 데일리 운동기록 CRUD
- Youtube API 이용 영상 검색 및 찜, 삭제 기능
- 영상 별 상세 페이지, 댓글 CRUD
