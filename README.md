# 다 맡케팅

소상공인을 위한 AI 마케팅 자동화 플랫폼

KT AIVLE School 7기 빅프로젝트 **대상(1위)** · 2025.07.07 ~ 2025.09.02 · 7인 팀 (AI/백엔드 5, AI/프론트 2)

## 저장소 구성

이 저장소는 프로젝트 소개용입니다. 코드는 아래 세 저장소에 있으며, 각각 팀 원본 저장소를 브랜치와 커밋 기록까지 그대로 포크한 것입니다.

| 폴더 | 내용 | 포크 | 원본 |
|---|---|---|---|
| `backend_ai/` | FastAPI + LangChain/LangGraph AI 서버 | [damatketing-backend_ai](https://github.com/choiminji-020102/damatketing-backend_ai) | [KT-AIVLE-04/backend_ai](https://github.com/KT-AIVLE-04/backend_ai) |
| `backend/` | Spring Boot 기반 MSA | [damatketing-backend](https://github.com/choiminji-020102/damatketing-backend) | [KT-AIVLE-04/backend](https://github.com/KT-AIVLE-04/backend) |
| `frontend/` | React 웹 클라이언트 | [damatketing-frontend](https://github.com/choiminji-020102/damatketing-frontend) | [KT-AIVLE-04/frontend](https://github.com/KT-AIVLE-04/frontend) |

## 프로젝트 소개

- 숏폼 광고 영상 자동 생성
- SNS 게시글 · 해시태그 자동 작성과 YouTube · Instagram · Facebook 게시
- 댓글 감성 분석 기반 성과 리포트

## 담당 — SNS 게시글 관리 기능의 AI · 프론트

SNS 게시글 관리 기능에서 AI 서버의 게시글 생성 에이전트와 프론트 화면을 맡았습니다.

**AI**
- LangGraph StateGraph로 콘텐츠 분석 → 트렌드 분석 → 게시글 생성 → 해시태그 생성 4개 노드로 책임 분리
- 노드별 모델과 temperature 차등 (콘텐츠 분석 gpt-4o-mini 0.3, 트렌드 분석 gpt-4o 0.7, 게시글 생성 gpt-4o-mini 0.5, 해시태그 생성 gpt-4o-mini 0.7)
- 해시태그만 다시 만드는 API (트렌드 분석과 해시태그 생성 노드만 실행)
- 플랫폼별 해시태그 개수 규칙 (Instagram 7~11, Facebook 2~3, YouTube 3~5)

**프론트**
- SNS 계정 연동 페이지 (OAuth 팝업)
- 콘텐츠 선택 → AI 작성 → 게시 옵션 → 플랫폼별 미리보기 4단계를 한 화면으로 통합
- 게시물 관리 페이지 (플랫폼 필터, 조회수 · 좋아요 · 댓글, 수정 · 삭제)

## 기술 스택 (프로젝트 전체)

AI: Python, FastAPI, LangChain, LangGraph, OpenAI API
Backend: Java, Spring Boot, Spring Cloud Gateway, Kafka, Redis
Frontend: React, Redux
Infra: AWS (S3, CloudFront, EC2), Docker
