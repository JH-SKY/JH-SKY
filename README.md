# JH-SKY

AI 서비스 개발자를 준비하고 있는 도봉캠퍼스 교육생입니다.

FastAPI 기반 백엔드 API와 LangGraph 기반 AI 에이전트 개발을 중심으로 학습하고 있으며, 기능을 빠르게 만드는 것보다 **문제를 정의하고, 구조를 설계하고, 실험 결과를 바탕으로 끝까지 개선하는 과정**을 중요하게 생각합니다.

현재는 채용 자동화, 정책 추천처럼 실제 사용자의 의사결정을 돕는 AI 서비스를 만들며 백엔드 설계, 데이터 구조화, LLM 워크플로우 개선 경험을 쌓고 있습니다.

---

## 핵심 역량

- **문제 정의와 구조화**
  - 사용자가 겪는 문제를 기능 단위로 나누고, 입력과 출력, 처리 흐름을 먼저 정리한 뒤 구현합니다.
  - 단순한 AI 응답 생성이 아니라, 어떤 기준으로 판단하고 개선할 수 있는지 함께 고민합니다.

- **FastAPI 기반 백엔드 개발**
  - API 명세를 기준으로 요청/응답 구조를 설계하고, 서비스 로직과 데이터 흐름을 분리하려고 노력합니다.
  - PostgreSQL 등 관계형 데이터베이스를 활용해 서비스에 필요한 데이터를 구조화한 경험이 있습니다.

- **LangGraph 기반 AI 에이전트 워크플로우**
  - LangGraph를 사용해 멀티 에이전트 기반 질문 생성 흐름을 설계하고 구현했습니다.
  - LangSmith trace와 실험 로그를 확인하며 AI 응답 품질을 개선한 경험이 있습니다.

- **실험, 개선, 문서화**
  - 결과를 감으로 판단하지 않고 평가 기준과 로그를 남기며 개선합니다.
  - 팀 프로젝트에서 WBS, API 명세서, 회의록, 기술 문서, 실험 기록을 관리했습니다.

---

## 기술 스택

### Backend

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

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

AI 기반 채용 자동화 에이전트 프로젝트입니다.

- Repository: [bamti95/hr-copilot](https://github.com/bamti95/hr-copilot)
- Project Type: 팀 프로젝트

채용 과정에서 필요한 면접 질문을 더 일관되고 평가 가능한 방식으로 생성하기 위해, LangGraph 기반 멀티 에이전트 질문 생성 워크플로우를 설계하고 구현했습니다.

#### 문제 정의

- 채용 담당자가 지원자 정보와 직무 요구사항을 바탕으로 매번 면접 질문을 직접 구성해야 하는 부담이 있었습니다.
- 단순히 질문을 많이 생성하는 것보다, 직무 적합성과 평가 가능성이 있는 질문을 만드는 것이 더 중요하다고 판단했습니다.
- AI가 생성한 질문의 품질을 개선하려면 명확한 평가 기준과 실험 기록이 필요했습니다.

#### 구조 설계와 구현

- LangGraph를 활용해 질문 생성 과정을 여러 단계의 워크플로우로 나누었습니다.
- FastAPI 기반 백엔드에서 AI 질문 생성 요청을 처리하고, PostgreSQL을 사용해 서비스 데이터를 관리하는 구조를 경험했습니다.
- OpenAI API를 활용해 질문을 생성하고, LangSmith trace를 통해 각 단계의 입력과 출력을 확인했습니다.

#### 실험과 개선

- 자체 평가 루브릭을 기준으로 질문 품질을 측정했습니다.
- LangSmith trace와 실험 로그를 보며 프롬프트와 워크플로우를 반복 개선했습니다.
- 질문 품질 평균 점수를 **78.6점에서 91.8점**으로 개선했습니다.

#### 맡은 역할

- 팀 리더로 프로젝트 일정과 작업 범위를 WBS로 관리했습니다.
- API 명세서, 회의록, 기술 문서, 실험 기록을 정리하며 팀원이 같은 기준으로 작업할 수 있도록 문서화했습니다.
- 구현 결과뿐 아니라 어떤 이유로 구조를 바꾸고 개선했는지 기록하려고 노력했습니다.

#### 사용 기술

`FastAPI` `PostgreSQL` `OpenAI API` `LangGraph` `LangSmith`

---

### 프로젝트 2. [정책매칭 AI 서비스](https://github.com/JH-SKY/biz-fund-ai)

사용자의 조건에 맞는 정책자금과 정부지원사업 정보를 탐색하고 추천하는 AI 기반 정책 매칭 서비스입니다.

- Repository: [JH-SKY/biz-fund-ai](https://github.com/JH-SKY/biz-fund-ai)
- Project Type: 사이드 프로젝트

정책 정보를 단순히 검색해서 보여주는 것이 아니라, 사용자의 상황과 정책 조건을 비교해 적합도를 판단하는 구조를 고민했습니다.

#### 문제 정의

- 정부지원사업과 정책 정보는 많지만, 사용자가 본인에게 맞는 정책을 직접 찾기는 어렵습니다.
- 정책마다 대상, 조건, 지역, 기간, 지원 내용이 달라 단순 키워드 검색만으로는 충분하지 않다고 보았습니다.
- AI가 추천을 하더라도 왜 해당 정책이 적합한지 근거를 함께 제공해야 신뢰할 수 있다고 판단했습니다.

#### 구조 설계와 구현

- FastAPI 기반으로 정책 탐색과 추천을 위한 백엔드 API를 설계하고 구현했습니다.
- 정책 데이터를 조건별로 비교할 수 있도록 구조화하는 방향을 고민했습니다.
- 사용자 입력 조건과 정책 조건을 매칭하기 위한 필터링 기준과 추천 로직을 설계했습니다.

#### 개선 방향

- AI 응답의 정확도와 신뢰도를 높이기 위해 추천 결과에 정책 근거를 함께 제공하는 방향으로 개선했습니다.
- 취업 준비 과정에서 배운 AI 서비스 개발 역량을 개인 프로젝트로 확장해 적용했습니다.

#### 사용 기술

`FastAPI` `Python` `AI Service Backend`

---

## 현재 학습과 관심사

- FastAPI 기반 서비스 구조 설계와 API 품질 개선
- LangGraph를 활용한 AI 에이전트 워크플로우 설계
- LangSmith trace 기반 LLM 응답 품질 개선
- RAG, 정책 추천, 채용 자동화처럼 실제 의사결정을 돕는 AI 서비스
- 실험 기록, 회고, 기술 문서를 통한 포트폴리오 정리

---

## 연락처

- Email: whdgur2034@naver.com
- GitHub: [JH-SKY](https://github.com/JH-SKY)

---

## 개발자로서 중요하게 생각하는 것

아직 신입 개발자이지만, 프로젝트를 진행할 때 결과물만큼 과정도 중요하다고 생각합니다.

문제를 먼저 정의하고, 구조를 설계한 뒤, 구현 결과를 실험과 로그로 확인하며 개선하는 개발자가 되고 싶습니다. 또한 그 과정을 문서로 남겨 다음 작업과 협업에 도움이 되도록 만드는 습관을 계속 키우고 있습니다.
