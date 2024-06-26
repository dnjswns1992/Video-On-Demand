# # Video-On-Demand
Storage for video projects
### 프로젝트 제목 : Spring Boot 기반 동영상 스트리밍 플랫폼

## 프로젝트 설명

**목적 :** 넷플릭스, 라프텔, 무빙, 티빙 등 관리자가 동영상을 업로드하면 사용자가 그 동영상을 클릭해 동영상을 볼 수 있는 비디오 스트리밍 서비스입니다.

**기간:** 2024.05.20 ~ 

## 사용 기술

| **프론트엔드** | **백엔드** | **인증 및 권한 관리** | **실시간 통신** | **클라우드 인프라** | **데이터베이스** | **CI/CD** |
| --- | --- | --- | --- | --- | --- | --- |
| Vue.js, HTML5, CSS3, JavaScript | Spring Boot, Spring Security, Spring Data JPA | OAuth 2.0, JWT (JSON Web Token) | 웹소켓 (WebSocket) | AWS EC2, AWS S3 | MySQL | 예정 |

### 주요 기능

- **사용자 인증 및 권한 관리:**
    - OAuth 2.0을 사용한 소셜 로그인 (Google, Facebook 등)
    - FormLogin을 통한 사용자 인증
    - JWT를 사용한 인증 및 권한 관리
- **동영상 업로드 및 스트리밍:**
    - AWS S3를 이용한 동영상 파일 저장
    - 동영상 스트리밍 기능 구현
- **백엔드 개발:**
    - Spring Boot를 사용하여 RESTful API 개발
    - Spring Security와 JWT를 사용하여 보안 강화
    - 동영상 업로드 및 스트리밍을 위한 AWS S3 연동
- **웹소켓**
    - 백엔드와 웹소켓 통신을 이용해 업로드 진행 상황 확인
- **사용자 인터페이스:**
    - Vue.js를 사용한 직관적이고 반응형인 사용자 인터페이스 구현
    - 사용자 프로필 관리, 동영상 목록 보기, 좋아요(추가 예정) 및 댓글 기능

## 주요 화면

### 홈페이지 메인화면

### 사용자가 해당 포스터를 클릭 시

**이러한 에피소드 각 에피소드들이 나타나게 됨.**

---

**각 에피소드 클릭 시 해당 영상이 재생되며 영상 시청을 할 수 있습니다.**

## 회원가입 로그인 폼

**로그인 창으로 이동하면, OAuth2 로그인과 일반 로그인 등이 존재합니다.**

### 동영상 업로드

**동영상 올리기 버튼을 클릭 시, 메인 타이틀 등록(메인 화면에 보여 줄 이미지)과 각 에피소드를 등록할 수 있는 화면이 있습니다.**

**에피소드 등록 시, 현재 얼마나 영상이 업로드되었는지 표시해주는 웹소켓 기능을 통해 실시간으로 진행 상황을 확인할 수 있습니다.**

### 동영상 업로드 방식

1. **클라이언트가 백엔드로부터 서명된 URL을 받아옵니다.**
    - 클라이언트는 각 파트를 업로드하기 위해 백엔드에게 서명된 URL을 요청합니다.
    - 백엔드는 S3에 요청하여 각 파트에 대한 사전 서명된 URL을 생성하고 이를 클라이언트에게 반환합니다.

2. **클라이언트는 서명된 URL을 가지고 각 파트를 쪼개서 서명된 URL과 함께 S3에 보냅니다.**
    - 클라이언트는 받은 사전 URL을 사용하여 각 파트를 S3에 업로드합니다.
    - 각 파트를 업로드할 때, 사전 서명된 URL을 사용하여 S3에 직접 요청을 보냅니다.

3. **이 파트 작업이 S3에 다 올라가면 백엔드로 완료 요청을 보냅니다.**
    - 모든 파트가 성공적으로 업로드되면 클라이언트는 각 파트의 ETag과 파트 번호를 포함하여 백엔드에게 완료 요청을 보냅니다.

4. **백엔드는 완료 요청을 받아 S3에 완료되었다고 알립니다.**
    - 백엔드는 클라이언트로부터 받은 정보(각 파트의 ETag와 파트 번호)를 사용하여 S3 업로드 완료 요청을 보냅니다.

5. **S3는 백엔드에 완료 요청을 받아서 쪼개진 작업을 하나로 병합합니다.**
    - S3는 업로드 완료 요청을 받으면 업로드된 모든 파트를 병합하여 하나의 객체로 만듭니다.

### 커뮤니티 게시판

**사용자들이 게시판을 등록, 수정, 삭제할 수 있는 기능을 제공합니다.**

**기본적인 CRUD 기능을 사용했습니다.**


## 1. Repository Classification


|Repository|Description|URL|
|:---|:---|:---|
|Front end Server |It's a front-end server.|[link](https://github.com/dnjswns1992/Vod-Frond-end-Server)|
|back end Server |It's a back-end server.|[link](https://github.com/dnjswns1992/Vod-Back-End)|

## 2. Team

|Front-end |back-end|
|:---|:---|
|WooHeeSeop |WooHeeseop|

