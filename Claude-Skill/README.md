---
name: zapier-automation
description: >
  Zapier 개인 업무 자동화 스킬. Google 앱(Gmail, Sheets, Drive, Calendar), 협업 툴(Slack, Notion, Trello),
  AI 툴(ChatGPT, Claude)을 연동한 Zap 자동화 워크플로우를 설계하고 단계별 가이드 문서를 생성한다.
  사용자가 "~를 자동화하고 싶어", "Zapier로 ~연결해줘", "Zap 만들어줘", "자동으로 ~되게 해줘"와 같은
  요청을 하거나, 반복 업무·알림·데이터 동기화·AI 연동에 대해 언급할 때 반드시 이 스킬을 사용한다.
  기초 수준 사용자도 이해할 수 있도록 쉬운 언어로 설명하되, Multi-step, Filter, Formatter 등
  중급 기능으로 성장할 수 있는 로드맵도 함께 제공한다.
---
# Zapier 개인 업무 자동화 스킬
## 이 스킬의 목적

기초 Zapier 사용자가 Google 앱 · 협업 툴 · AI 툴을 연동해 개인 업무를 자동화할 수 있도록

**Zap 설계 + 단계별 가이드 문서**를 생성한다.

---

## Step 1. 업무 분석 (요청 파악)

사용자의 요청에서 아래 3가지를 먼저 파악한다.

| 항목 | 질문 |
|------|------|
| **무엇을 자동화?** | 반복되는 작업이 무엇인가? |
| **언제 시작?** | 어떤 사건(이메일 수신, 폼 제출 등)이 발생할 때인가? |
| **결과는?** | 어디에 무엇을 저장/전송/생성하고 싶은가? |

파악이 안 된 항목이 있으면 한 번에 하나씩 질문한다.

---

## Step 2. Zap 설계 구조 출력

파악한 내용을 아래 구조로 정리해 보여준다.

```
🔵 Trigger (시작 조건)
   └── 앱: [앱 이름]
   └── 이벤트: [이벤트명]  예) New Email, New Row, Form Submission

🟢 Action(s) (실행할 작업)
   └── Action 1 — 앱: [앱 이름] / 이벤트: [이벤트명]
   └── Action 2 — (필요 시 추가)

🔧 중간 처리 (필요 시)
   └── Filter: [조건]  예) 제목에 "긴급" 포함된 경우만
   └── Formatter: [변환]  예) 날짜 형식 변환, 텍스트 분리
```

---

## Step 3. 단계별 설정 가이드 문서 생성

아래 순서대로 단계별 가이드를 작성한다.

### 📋 가이드 문서 형식

```
## [과목명] 자동화 가이드

### 개요
- 목적: ~
- 예상 소요 시간: ~분
- 필요한 앱 계정: ~

---

### 1단계. Zapier 접속 및 새 Zap 만들기
- zapier.com 접속 → [+ Create] 클릭
- ⚠️ 주의: 무료 플랜은 Zap 5개, 월 100회 실행 제한

### 2단계. Trigger 설정
- 앱 검색창에 [앱 이름] 입력 후 선택
- Event: [이벤트명] 선택
- 계정 연결: [Connect] 클릭 → 로그인 허용
- 테스트 데이터 불러오기: [Test trigger] 클릭
- ✅ 확인: 샘플 데이터가 보이면 성공

### 3단계. Action 설정
- 앱 검색창에 [앱 이름] 입력 후 선택
- Event: [이벤트명] 선택
- 필드 매핑:
  - [필드1]: Trigger에서 가져온 [데이터] 선택
  - [필드2]: 직접 입력 또는 Trigger 데이터 조합
- ✅ 확인: [Test action] 으로 실제 실행 테스트

### 4단계. 활성화
- [Publish] 클릭 → Zap 이름 저장
- ⚠️ 주의: 테스트 후 실제 데이터가 생성될 수 있으니 확인 필요

---

### 자주 발생하는 오류와 해결법
[상황에 맞는 오류 목록 — references/troubleshooting.md 참고]
```

---

## Step 4. 앱 조합별 추천 Zap 패턴

자세한 패턴은 `references/zap-patterns.md` 를 읽어 활용한다.

**빠른 참고 — 카테고리별 대표 패턴:**

| 카테고리 | 패턴 예시 |
|----------|-----------|
| Google 계열 | Gmail 수신 → Sheets 자동 기록 |
| 협업 툴 | Google Form 제출 → Slack 알림 |
| AI 연동 | Gmail 수신 → ChatGPT 요약 → Notion 저장 |
| 캘린더 동기화 | Google Calendar 새 일정 → Notion DB 추가 |

---

## Step 5. 기초 → 중급 성장 로드맵

가이드 마지막에 항상 아래 로드맵을 추가한다.

```
📈 다음 단계로 성장하기

현재 수준: 2-step 단순 Zap ✅

▶ 중급 1단계: Filter 추가
  → 특정 조건일 때만 Action 실행
  → 예) 이메일 제목에 "긴급" 포함된 경우만 Slack 알림

▶ 중급 2단계: Formatter 활용
  → 날짜 형식 변환, 텍스트 분리/결합
  → 예) "홍길동 010-1234-5678" → 이름/전화번호 분리

▶ 중급 3단계: Multi-step Zap
  → 하나의 Trigger로 여러 Action 연달아 실행
  → 예) 폼 제출 → Sheets 기록 + Slack 알림 + Gmail 자동 회신
```

---

## 참고 파일

- `references/zap-patterns.md` — 앱 조합별 상세 Zap 패턴 30가지
- `references/troubleshooting.md` — 자주 발생하는 오류 및 해결법
