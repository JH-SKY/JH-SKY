# JH-SKY

FastAPI 기반 백엔드와 LangGraph 기반 AI 에이전트를 직접 설계·구현하며 AI 서비스 개발 역량을 쌓고 있습니다.

기능을 빠르게 만드는 것보다 **문제를 정의하고, 구조를 설계하고, 실험 결과를 바탕으로 끝까지 개선하는 과정**을 중요하게 생각합니다.

채용 자동화, 정책 추천처럼 실제 사용자의 의사결정을 돕는 AI 서비스를 만들며 백엔드 설계, 데이터 구조화, LLM 워크플로우 개선 경험을 쌓고 있습니다.

---

## 핵심 역량

- **문제 정의와 구조화**
  - 사용자가 겪는 문제를 기능 단위로 나누고, 입력과 출력, 처리 흐름을 먼저 정리한 뒤 구현합니다.
  - 단순한 AI 응답 생성이 아니라, 어떤 기준으로 판단하고 개선할 수 있는지 함께 고민합니다.

- **FastAPI 기반 백엔드 개발**
  - API 명세를 기준으로 요청/응답 구조를 설계하고, 서비스 로직과 데이터 흐름을 분리합니다.
  - PostgreSQL, pgvector 등 관계형·벡터 데이터베이스를 활용해 서비스에 필요한 데이터를 구조화한 경험이 있습니다.

- **LangGraph 기반 AI 에이전트 워크플로우**
  - LangGraph StateGraph를 활용해 멀티 에이전트 기반 워크플로우를 설계하고 구현했습니다.
  - 평가 하네스, LangSmith trace, 실험 로그를 통해 AI 응답 품질을 정량 기준으로 개선한 경험이 있습니다.

- **실험, 개선, 문서화**
  - 결과를 감으로 판단하지 않고 평가 기준과 로그를 남기며 개선합니다.
  - WBS, API 명세서, 기술 문서, 실험 기록을 직접 작성하며 팀 기준을 맞춘 경험이 있습니다.

---

## 기술 스택

### Backend

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![pgvector](https://img.shields.io/badge/pgvector-4169E1?style=flat-square)

### AI Service

![OpenAI API](https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square)
![LangSmith](https://img.shields.io/badge/LangSmith-1C3C3C?style=flat-square)

### Collaboration & Documentation

![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)
![Notion](https://img.shields.io/badge/Notion-000000?style=flat-square&logo=notion&logoColor=white)

---

## 대표 프로젝트

### 프로젝트 1. [HR-Copilot](https://github.com/bamti95/hr-copilot)

LangGraph 기반 멀티 에이전트 면접 질문 자동 생성 시스템입니다.

- Repository: [bamti95/hr-copilot](https://github.com/bamti95/hr-copilot)
- Notion: [HR-COPILOT 프로젝트 문서](https://checker-gambler-0f8.notion.site/HR-COPILOT-7331480769ac83ef971881f22f063100?)
- Project Type: 팀 프로젝트

채용 담당자가 지원자 서류를 보고 매번 면접 질문을 직접 구성해야 하는 부담을 줄이기 위해, 지원자 문서를 분석해 직무 적합성과 리스크를 검증하는 질문을 자동 생성하는 시스템을 설계·구현했습니다.

#### 문제 정의

- 단순히 질문을 많이 생성하는 것보다, 지원자 서류 속 리스크(공백기·성과 과장·협업 이력 부족)를 실제 면접 질문으로 전환하는 것이 더 중요하다고 판단했습니다.
- AI가 생성한 질문의 품질을 개선하려면 명확한 평가 기준과 실험 기록이 필요했습니다.

#### 구조 설계와 구현

- **6노드 멀티 에이전트 파이프라인**: `prepare_context → verification_point_extractor → questioner → predictor → driller → reviewer` 순으로 역할을 분리했습니다.
- **verification_point_extractor**: 지원자 문서에서 반드시 확인해야 할 검증 포인트(공백기, 성과 기여도, 협업 리스크)를 사전 분류하는 노드를 추가했습니다. questioner 이전 단계에서 검증 방향을 먼저 구조화하는 것이 프롬프트 수정보다 효과적이었습니다.
- **Reviewer + review_router**: 루브릭 기반 채점(10항목, 100점 환산) 후 품질 미달 시 questioner로 재시도하는 루프를 설계했습니다.

#### 실험과 개선

- 자체 평가 루브릭(질문 품질 5항목 + 평가가이드 품질 5항목)을 기준으로 AI 개발/데이터 직무 후보자 10명, 50문항을 측정했습니다.
- 질문 품질 평균 점수를 **78.6점 → 91.8점 (+13.2점)** 으로 개선, 목표치 90점을 초과 달성했습니다.

#### 맡은 역할

- 팀 리더로 프로젝트 일정과 작업 범위를 WBS로 관리했습니다.
- LangGraph 에이전트 설계·구현, API 명세서, 실험 기록, 기술 문서를 담당했습니다.

#### 사용 기술

`FastAPI` `PostgreSQL` `OpenAI API` `LangGraph` `LangSmith`

---

### 프로젝트 2. [Biz-Up — 소상공인 정책자금 AI 플랫폼](https://github.com/JH-SKY/biz-fund-ai)

소상공인이 자신에게 맞는 정책자금을 빠르게 찾을 수 있도록, Hybrid RAG 파이프라인과 LangGraph 기반 AI 상담 에이전트를 직접 설계·구현한 개인 프로젝트입니다.

- Repository: [JH-SKY/biz-fund-ai](https://github.com/JH-SKY/biz-fund-ai)
- Notion: [Biz-Fund-AI 프로젝트 문서](https://phrygian-periodical-80a.notion.site/__Biz-Fund-AI__-8f2a1038d825836fbeb381945485ec15?)
- Project Type: 사이드 프로젝트

#### 문제 정의

- 정부지원사업 공고는 많지만, 지역·업종·조건이 제각각이라 사용자가 본인에게 맞는 정책을 직접 찾기 어렵습니다.
- 단순 키워드 검색만으로는 의미가 비슷한 표현이나 기관명 검색이 약하고, 벡터 검색만으로는 정확한 단어 매칭이 안 됩니다.
- AI 추천 결과가 품질을 유지하면서 운영 비용을 감당할 수 있는 구조가 필요했습니다.

#### 구조 설계와 구현

- **LangGraph 기반 AI 상담 에이전트 (비즈몽)**: 사용자 의도를 4개(greeting / general_qa / rag / stats)로 분류하는 Router 노드 + 전문 처리 노드로 구성된 StateGraph를 설계했습니다. Router는 GPT-4o-mini(JSON mode) → 키워드 매칭 2단계 폴백 구조로 안정성을 확보했습니다.
- **Hybrid RAG 파이프라인**: pgvector 벡터 검색(상위 20개)과 FTS 키워드 검색(상위 20개)을 Reciprocal Rank Fusion(k=60)으로 결합해 의미 검색과 정확 매칭을 동시에 처리합니다.
- **Contextual Embedding**: 정책명·주관기관·유형을 청크 앞에 주입해 임베딩 벡터를 생성하고, 사용자 노출용 텍스트와 분리 저장해 섹션명만 같은 청크끼리 혼동되는 문제를 해결했습니다.
- **PolicySyncAgent**: 비정형 공고 원문을 GPT-4o로 구조화하고, 파싱 실패 시 Self-Correction(최대 2회 재시도)으로 데이터 파이프라인을 안정화했습니다.

#### 실험과 개선

- **품질 평가 하네스**: 실제 서버를 띄우지 않고 `httpx.ASGITransport`로 앱을 직접 호출하는 12케이스 자동 평가 스크립트를 작성했습니다. 라우팅 정확도(route_ok) · 정책 포함 여부(policy_ok) · 키워드 구성(keyword_ok) 3축으로 판정, **12케이스 중 10개 통과(83.3%)** 를 확인했습니다.
- **비용 최적화**: 모든 노드에 gpt-4o를 쓰던 초기 설계에서 작업 복잡도를 분석해 모델을 재배정했습니다. Router·RAG 답변 → gpt-4o-mini, Greeting → 정적 문자열로 교체한 결과 채팅 비용 약 **15배 절감**. 최적화 후 평가 하네스를 재실행해 **83.3% 품질 유지를 확인**했습니다.

#### 사용 기술

`FastAPI` `PostgreSQL` `pgvector` `OpenAI API` `LangGraph` `text-embedding-3-small`

---

## 현재 학습과 관심사

- FastAPI 기반 서비스 구조 설계와 API 품질 개선
- LangGraph를 활용한 AI 에이전트 워크플로우 설계
- RAG 파이프라인 최적화 (Hybrid 검색, Contextual Embedding)
- 실험 기록, 회고, 기술 문서를 통한 포트폴리오 정리

---

## 연락처

- Email: whdgur2034@naver.com
- GitHub: [JH-SKY](https://github.com/JH-SKY)

---

## 개발자로서 중요하게 생각하는 것

프로젝트를 진행할 때 결과물만큼 과정도 중요하다고 생각합니다.

문제를 먼저 정의하고, 구조를 설계한 뒤, 구현 결과를 실험과 로그로 확인하며 개선하는 개발자가 되고 싶습니다. 그 과정을 문서로 남겨 다음 작업과 협업에 도움이 되도록 만드는 습관을 계속 키우고 있습니다.
