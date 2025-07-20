# ✈️ MyLittleTrip - 여행일정 추천 시스템 (Backend)

> **여행 스타일에 맞춘 맞춤형 여행지 일정을 추천해주는 백엔드 시스템**

---

## 📌 프로젝트 개요

- 사용자의 리뷰, 좋아요, 지역 기반 행동 데이터를 활용해 여행 일정을 자동 생성
- 로그인/회원가입, 장소 등록, 댓글, 좋아요, 리뷰 작성 등 **여행 기반 커뮤니티 기능 포함**
- EC2 + Docker + Nginx 기반의 **클라우드 배포**
- [Notion 포트폴리오 보기](https://your.notion.link/) *(선택사항)*

---

## 🔧 기술 스택

| 구분 | 기술 |
|------|------|
| Language | Python 3.8 |
| Framework | Django REST Framework |
| DB | PostgreSQL |
| Infra | AWS EC2, Nginx, Docker |
| Auth | JWT 기반 인증/인가 |
| DevOps | GitHub Actions (CI/CD), docker-compose |

---

## 🧩 주요 기능

- 🔐 **JWT 로그인 및 회원 관리**
- 📍 **장소 등록 및 조회 API**
- 💬 **댓글 및 좋아요 기능**
- 🤖 **여행 일정 자동 생성 알고리즘**
- 📦 **도커 기반 서버 배포 및 nginx 연동**

---

## 🧠 핵심 구현 설명

> 📎 코드 전체는 비공개입니다. 요청 시 시연자료 또는 리뷰용 코드 일부를 제공할 수 있습니다.

### 🗺️ 추천 알고리즘 개요
- 사용자 히스토리 + 장소 유형별 선호도를 기반으로 일정 추천
- 하루 단위 클러스터링을 기반으로 거리 최소화 일정 생성

### 🔐 인증/인가
- JWT 토큰 발급 및 만료 처리
- 권한에 따라 리뷰/댓글 수정 권한 분기

### ☁️ 배포
- EC2 인스턴스에서 Nginx + Docker 기반 서버 실행
- `docker-compose.prod.yaml`로 운영환경 배포 자동화

---

## 📸 시연 이미지

| 메인 화면 | 일정 추천 결과 |
|-----------|----------------|
| ![main](./screenshots/main.png) | ![result](./screenshots/result.png) |

---

## 📊 성과 및 개선

- 1개월 MVP 개발 후 실제 여행자 대상 시연 진행
- 향후 **챗봇 연계 여행추천** 및 **OpenAI 기반 자동 코멘트** 기능 연동 예정

---

## 🙋‍♀️ 면접/검토용 안내

- 본 프로젝트는 포트폴리오용 비공개 프로젝트입니다.
- 코드 전체는 Github Private Repository 또는 PDF 문서로 제공 가능합니다.
- 요청 시 다음 내용도 공유 가능합니다:
  - DB ERD
  - REST API 명세서
  - 테스트 시나리오

👉 문의: [your.email@example.com](mailto:your.email@example.com)

---

## 📁 프로젝트 구조 (요약)

```bash
MyLittleTrip_backend/
│
├── comment/               # 댓글 관리 기능
├── like/                  # 좋아요 기능
├── place/                 # 장소 등록 및 조회
├── recommend/             # 일정 추천 로직
├── review/                # 장소 리뷰 작성 및 조회
├── trip/                  # 여행 일정 구성
├── user/                  # 로그인, 회원가입 등
├── nginx/                 # nginx config
├── docker-compose.prod.yaml
└── Dockerfile
