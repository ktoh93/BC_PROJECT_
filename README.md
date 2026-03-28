
<img width="186" height="91" alt="스크린샷 2025-12-19 143006" src="https://github.com/user-attachments/assets/643a1033-66a7-48c6-b3de-8234cb36d45a" />

# BC Project

생활체육 시설 정보를 조회하고, 예약을 진행하고, 함께 운동할 인원을 모집할 수 있는 Django 기반 웹 플랫폼입니다.  
일반 사용자 기능과 관리자 기능을 분리해 운영할 수 있도록 구성되어 있으며, 관리자 화면에서는 통계 기반 AI 분석 기능도 제공합니다.

## 프로젝트 소개

이 프로젝트는 공공 체육시설 데이터를 바탕으로 사용자가 원하는 시설을 탐색하고, 예약 가능 여부를 확인하고, 운동 메이트를 모집할 수 있도록 만든 서비스입니다.

주요 목표는 다음과 같습니다.

- 체육시설 정보 탐색과 예약 흐름 단순화
- 모집 게시글을 통한 사용자 간 커뮤니티 형성
- 관리자 중심의 운영, 배너 관리, 회원/예약/게시글 관리 지원
- 예약 및 이용 데이터 기반 AI 통계 분석 제공

## 주요 기능

### 사용자 기능

- 시설 목록 및 상세 조회
- 예약 가능 시설 확인 및 시간대별 예약
- 모집 게시글 작성, 조회, 참여
- 공지사항 / 이벤트 / FAQ / 일반 게시판 이용
- 회원가입, 로그인, 마이페이지, 내 예약/내 글/내 모집 관리

### 관리자 기능

- 관리자 로그인 및 대시보드
- 회원 관리
- 시설 관리
- 게시글 및 배너 관리
- 예약 현황 및 모집 현황 관리
- 시설 점검/안전 관련 통계 확인

### AI 분석 기능

- 예약/회원/시설/안전 통계 집계
- OpenAI API 기반 관리자용 인사이트 생성
- 대시보드 분석, 이상 징후 탐지, 채팅형 질의응답 지원

## 기술 스택

- Backend: Django 5
- Database: MySQL
- Data Processing: pandas, django-pandas
- API / External: OpenAI API, requests, XML 데이터 처리
- Frontend: Django Templates, JavaScript, CSS

## 프로젝트 구조

```text
BC_Project/
├─ BC/
│  ├─ BC_Contest/        # Django settings, urls, wsgi/asgi
│  ├─ common/            # 메인, 로그인/회원가입, 공통 레이아웃
│  ├─ facility/          # 시설 조회 및 데이터 관리
│  ├─ reservation/       # 예약 및 시간대 관리
│  ├─ recruitment/       # 모집 게시글, 참여, 평점
│  ├─ board/             # 공지/이벤트/FAQ/게시판
│  ├─ member/            # 회원, 마이페이지
│  ├─ manager/           # 관리자 화면 및 운영 기능
│  ├─ ai_analytics/      # 관리자용 AI 분석 기능
│  ├─ manage.py
│  └─ requirements.txt
└─ ERD/
   └─ BC_erd.erd
```

## ERD

<img width="3240" height="3240" alt="BC_erd" src="https://github.com/user-attachments/assets/a56bcb01-7e2c-44d3-a3ef-9569767382ab" />

## 발표영상 / 자료
- 프로젝트 발표 영상 : [발표 영상 링크](https://www.youtube.com/watch?v=LaZt3GMA-yY&feature=youtu.be)
- 프로젝트 발표 화면 영상 : [발표 화면 영상 링크](https://www.youtube.com/watch?v=XAM7G9b4QOg&feature=youtu.be)
- 발표 자료(PPT) : [PDF 링크](https://github.com/user-attachments/files/26318886/_.PPT.pptx)


## 설치 및 실행

### 1. 저장소 클론

```bash
git clone <repository-url>
cd BC_Project
```

### 2. 가상환경 생성 및 활성화

```bash
python -m venv venv
venv\Scripts\activate
```

### 3. 패키지 설치

```bash
cd BC
pip install -r requirements.txt
```

### 4. `.env` 파일 설정

`BC/.env` 파일을 생성하고 아래 값을 설정합니다.

```env
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=127.0.0.1
DB_PORT=3306
OPENAI_API_KEY=your_openai_api_key
```

### 5. 마이그레이션

```bash
python manage.py migrate
```

### 6. 서버 실행

```bash
python manage.py runserver
```

브라우저에서 `http://127.0.0.1:8000/` 으로 접속할 수 있습니다.

## 주요 앱 설명

- `common`: 메인 페이지, 인증 관련 화면, 공통 레이아웃
- `facility`: 공공 체육시설 데이터 저장, 목록/상세 조회
- `reservation`: 예약, 시간대(TimeSlot), 결제/취소 상태 관리
- `recruitment`: 운동 메이트 모집, 참여 상태, 평점
- `board`: 공지사항, 이벤트, FAQ, 게시글
- `member`: 회원 정보, 마이페이지, 내 활동 조회
- `manager`: 운영자 대시보드, 회원/시설/예약/배너 관리
- `ai_analytics`: 통계 수집 및 OpenAI 기반 관리자 분석

## 데이터 및 운영 관련 참고

- 공공 체육시설 데이터와 내부 운영 데이터를 함께 사용합니다.
- 시설 관련 관리 명령어가 포함되어 있어 데이터 갱신 작업을 지원합니다.
- ERD 파일은 `ERD/BC_erd.erd`에 포함되어 있습니다.

## 환경 변수 및 주의사항

- 현재 설정 파일은 MySQL 연결을 기준으로 구성되어 있습니다.
- OpenAI 기반 기능을 사용하려면 `OPENAI_API_KEY`가 필요합니다.
- 개발 설정에서는 `DEBUG = True`, `ALLOWED_HOSTS = ['*']`로 되어 있으므로 배포 전 별도 설정 분리가 필요합니다.



- 서비스 소개 이미지 또는 메인 화면 캡처
- 팀원 소개 및 담당 역할
- 개발 기간
- 와이어프레임 / ERD / API 명세 링크
- 배포 주소 및 데모 계정

