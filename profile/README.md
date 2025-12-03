# kt-techup-shopping
KT Cloud TECH-UP Backend 1st Cohort Team 5’s e-commerce backend project. Implements RESTful APIs for shopping with Spring Boot.

# 🛒 KT Cloud TECH-UP 백엔드 1기 5조 - 쇼핑 프로젝트

## 📘 프로젝트 소개
KT Cloud TECH-UP 백엔드 1기 **5조**의 전자상거래 백엔드 프로젝트입니다.  
Spring Boot 기반으로 **전자상거래(쇼핑)** 의 기능을 제공하는 RESTful API를 설계하고 구현합니다.  
확장성과 유지보수성을 고려한 백엔드 아키텍처를 구축하여, 실제 배포 가능한 형태로 완성하는 것을 목표로 합니다.

### 🪜 하위 목표
- **프로젝트 : 전자상거래 백엔드**
    - 상품 등록 및 조회 API
    - 장바구니 및 주문 처리 API
    - 결제 연동 및 보안 관리
    - 리뷰 및 평점 시스템 구현
    - 관리자용 상품 관리 기능
    - 재고 관리 시스템

---

## 👥 팀원 소개
| 이름 | 역할 | GitHub |
|------|------|--------|
| **강슬기** | 팀장 / 백엔드 개발 | [SeulGi0117](https://github.com/SeulGi0117) |
| **이신영** | 백엔드 개발 | [youngyii](https://github.com/youngyii/kt-techup-shopping) |
| **김예은** | 백엔드 개발 | [YeKim1](https://github.com/YeKim1/kt-techup-shopping) |
| **양승희** | 백엔드 개발 | [seungh22](https://github.com/seungh22/kt_cloud_study.git) |

---
## 자기소개
**[강슬기]**
>안녕하세요, KT Cloud TECH-UP 백엔드 1기에서 학습 중인 강슬기입니다.
현재 5조 전자상거래 백엔드 프로젝트의 팀 리더로, 팀원들과 함께 Spring Boot 기반의 전자상거래 시스템을 설계·개발할 예정입니다.
백엔드 아키텍처와 클라우드 네이티브 개발에 집중하고 있으며, 특히 AI 모델 서빙과 시스템 아키텍처 설계에 관심을 가지고 있습니다.

**[김예은]**
> 안녕하세요. 앞으로 팀 프로젝트 서로 도와가며 즐겁게 완수했으면 좋겠습니다. 잘부탁드려요!

**[이신영]**
>안녕하세요!  
TECH UP에서 백엔드 개발을 공부 중인 이신영입니다.  
이번 프로젝트가 기대되네요. 최선을 다하겠습니다!

**[양승희]**
>안녕하세요! 양승희입니다!!! 반갑습니다

---

## 🎯 프로젝트 목표
- Spring Boot와 JPA를 활용한 **전자상거래 서비스용 RESTful API 구현**
- **회원 관리, 상품 등록, 주문, 결제, 채팅, 블로그 기능** 제공
- **클라우드 환경(KT Cloud, AWS 등)** 기반의 배포 환경 구축
- 팀 단위로 **효율적인 협업 및 브랜치 전략(Git Flow)** 적용

---

## ⚙️ 기술 스택
### Backend
- **언어**: Java 21
- **프레임워크**: Spring Boot 3.5.7
- **ORM**: Spring Data JPA, QueryDSL
- **보안**: Spring Security, JWT
- **데이터베이스**: MySQL (RDB)
- **캐싱**: Redis, Redisson (분산 락)
- **빌드 도구**: Gradle

### Infrastructure
- **문서화**: Swagger (OpenAPI 3.0)
- **모니터링**: Slack API
- **형상 관리**: Git, GitHub

### 디자인 패턴 및 아키텍처
- Layered Architecture (Controller - Service - Repository)
- AOP (Aspect-Oriented Programming)
- 이벤트 기반 아키텍처 (Spring Events)
- DTO 패턴
- Repository 패턴

---
## 🏗 시스템 아키텍처
```
┌─────────────────┐
│   API Gateway   │
│   (Future)      │
└────────┬────────┘
         │
┌────────▼────────────────────────────────────────┐
│           Spring Boot Application               │
│  ┌──────────────────────────────────────────┐   │
│  │         Controller Layer                 │   │
│  │  (REST API Endpoints)                    │   │
│  └──────────────┬───────────────────────────┘   │
│                 │                               │
│  ┌──────────────▼───────────────────────────┐   │
│  │         Service Layer                    │   │
│  │  (Business Logic)                        │   │
│  └──────────────┬───────────────────────────┘   │
│                 │                               │
│  ┌──────────────▼───────────────────────────┐   │
│  │         Repository Layer                 │   │
│  │  (Data Access)                           │   │ 
│  └──────────────┬───────────────────────────┘   │ 
└─────────────────┼───────────────────────────────┘
                  │
     ┌────────────┼────────────┐
     │            │            │
┌────▼────┐  ┌───▼────┐  ┌───▼────┐
│  MySQL  │  │ Redis  │  │ Slack  │
│   DB    │  │ Cache  │  │  API   │
└─────────┘  └────────┘  └────────┘
```
---
## 🌿 브랜치 전략

- **기본 브랜치**
  - **main**: 항상 배포 가능한 상태를 유지하는 브랜치

- **Jira 기반 기능 브랜치 (Jira Branch)**
  - **네이밍 규칙**: `/KAN-이슈번호`
  - 예시: `KAN-12`, `KAN-21`
  - Jira 이슈와 1:1 매핑을 권장

- **버그/핫픽스 브랜치 (Hotfix Branch)**
  - **네이밍 규칙**: `hotfix/짧은-설명`
  - 예시: `hotfix/login-error`

- **브랜치 운영 규칙**
  - `main` 에 직접 커밋 **금지**, 반드시 PR 통해 머지
  - 브랜치 생성 시 항상 최신 `main`기준으로 분기
  - 작업 완료 후 **PR + 코드리뷰 + 승인** 절차를 거친 후 머지

---

## 📝 커밋 메세지 규칙 (Commit Message Convention)


### ✅ 7가지 기본 규칙

1. **타입(type)은 소문자로 작성**
2. 제목과 본문은 **빈 줄(엔터 1줄)** 로 구분
3. 제목은 **50자 이내 한글로 작성**
4. 제목 끝에는 **마침표 금지**
5. 제목은 **명령문 형태**, **과거형 금지**
6. 본문 각 행은 **72자 이내**로 작성
7. **무엇과 왜**를 설명 (어떻게는 PR에 기술)

### 🔤 타입 분류

| 타입 | 설명 |
|------|------|
| feat | 새로운 기능 추가 |
| fix | 버그 수정 |
| build | 빌드 관련 변경 (모듈 설치/삭제 등) |
| chore | 자잘한 변경 (코드 영향 없음) |
| ci | CI/CD 관련 설정 변경 |
| docs | 문서 수정 |
| style | 포맷팅, 세미콜론 등 비기능적 수정 |
| refactor | 코드 리팩터링 |
| test | 테스트 코드 추가/수정 |
| perf | 성능 개선 |

### 🧱 구조

- **Header (필수)**  
  - `type(scope): subject`
- **Body (선택)**  
  - 변경 이유, 상세 내용
- **Footer (선택)**  
  - 이슈 번호, 연관 작업 등

- **스코프(scope) 예시**
  - `auth`, `order`, `product`, `user`, `build`, `deps` 등 (선택)
- **Footer 예시**
  - `fixes: #42`, `resolves: #1137` 등

```bash
git commit -m "feat(order): 주문 생성 API 구현

- 주문 요청 DTO 생성
- 주문 생성 시 재고 차감 로직 추가

fixes: #42"
```

---

## 🔄 PR 작성 규칙 (Pull Request Rules)

### 💬 PR 생성 규칙

- **대상 브랜치**
  - 기능 브랜치: `KAN-XX` → `main`
- **리뷰**
  - 최소 **1인 이상 리뷰 승인 필수**
  - 본인 PR은 **셀프 머지 금지** (브랜치 보호 규칙으로 막혀 있음)

### 🧩 PR 제목 포맷

- 형식: **`[type](scope): subject`**
- 예시: `feat(product): 상품 등록 API 구현`

### 📄 PR 본문 템플릿

```markdown
[type](scope): subject

### 🔧 구현 내용
- 무엇을 어떻게 왜 개발했는지
- 주요 변경 사항 요약

### 📌 관련 Jira Issue
- KAN-XX

### 🧪 테스트 방법
- [엔드포인트] /api/v1/...
- [파라미터] 예: ...
- [체크 포인트] 응답 코드/바디, DB 변경사항 등

### ❗ 기타 참고 사항
- 추가로 리뷰가 필요한 부분
- 브레이킹 체인지 여부 등
```

팀 합의에 따라 PR 템플릿은 GitHub 리포지토리 `.github/pull_request_template.md`로도 관리할 수 있습니다.

## 📐 코딩 컨벤션

본 프로젝트는 **Naver 코딩 컨벤션(Naver Hackday Java Convention)**을 따릅니다.

### Checkstyle 설정

프로젝트에는 코드 품질 관리를 위한 Checkstyle이 적용되어 있습니다:

- **컨벤션**: Naver Coding Convention
- **설정 파일**: `naver-checkstyle-suppressions.xml`
- **적용 범위**: Java 소스 코드 전체

---

## 🙏 감사의 말

kt cloud TECH-UP 프로그램과 강사님들께 감사드립니다.
---

