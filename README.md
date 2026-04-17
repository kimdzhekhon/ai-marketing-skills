<div align="center">

<img src="https://raw.githubusercontent.com/kimdzhekhon/ai-marketing-skills/main/assets/icon.png" width="100" alt="AI Marketing Skills Logo" onerror="this.style.display='none'"/>

# ai-marketing-skills

Claude Code 기반 마케팅 & 세일즈 자동화 스킬 모음 — 10개 카테고리, 즉시 실행 가능한 워크플로우

![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Claude Code](https://img.shields.io/badge/Claude_Code-Anthropic-D97757?style=for-the-badge)

![Python](https://img.shields.io/badge/Python-3-3776AB?style=flat-square&logo=python)
![Bash](https://img.shields.io/badge/Shell-Bash-4EAA25?style=flat-square&logo=gnu-bash)
![REST API](https://img.shields.io/badge/REST-API-FF6C37?style=flat-square)
![Webhook](https://img.shields.io/badge/Webhook-지원-blueviolet?style=flat-square)

[시작하기](#설치-및-실행) · [사용법](#데이터-흐름--사용법) · [기여하기](https://github.com/kimdzhekhon/ai-marketing-skills/issues)

</div>

---

## 목차

1. [소개](#소개)
2. [주요 기능](#주요-기능)
3. [기술 스택](#기술-스택)
4. [아키텍처](#아키텍처)
5. [데이터 흐름 / 사용법](#데이터-흐름--사용법)
6. [설치 및 실행](#설치-및-실행)
7. [Roadmap](#roadmap)
8. [라이선스](#라이선스)

---

## 소개

ai-marketing-skills는 Claude Code(Anthropic)와 통합되어 동작하는 오픈소스 마케팅 & 세일즈 자동화 스킬 모음입니다. 성장 실험 자동화부터 콘텐츠 생성, 아웃바운드 이메일, SEO 최적화, 재무 분석까지 10개 카테고리 워크플로우를 `/skill` 명령어 하나로 즉시 실행할 수 있습니다. ericosiu/ai-marketing-skills를 포크하여 한국 시장에 맞게 확장하고 있습니다.

> **"마케터의 반복 업무를 Claude Code 스킬로 자동화 — 아이디어 입력에서 실행 결과까지 한 번에."**

<div align="right"><a href="#목차">↑ 맨 위로</a></div>

---

## 주요 기능

| 기능 | 설명 |
|------|------|
| Growth Engine | 성장 실험 자동화, 페이싱 알림, 주간 스코어카드 생성 |
| Sales Pipeline | 방문자→파이프라인 전환, 딜 복구, 리드 자동 생성 |
| Content Ops | 90점 이상 콘텐츠 자동 생성, 품질 게이트 검사 |
| Outbound Engine | ICP 정의 → 이메일 작성까지 완전 자동화 |
| SEO Ops | 경쟁사 미흡 키워드 발굴, GSC 최적화 제안 |
| Finance Ops | AI CFO 보고서, 비용 시나리오 모델링 |
| Revenue Intelligence | 콘텐츠 ROI 분석, 영업 통화 → 전략 도출 |
| Conversion Ops | 랜딩 페이지 CRO 감사, 설문 → 리드 마그넷 변환 |
| Podcast Ops | 에피소드 1개 → 20개 이상 콘텐츠 파편화 |
| Sales Playbook | 가치 기반 가격 책정, 통화 분석 자동화 |

<div align="right"><a href="#목차">↑ 맨 위로</a></div>

---

## 기술 스택

| 레이어 | 기술 | 역할 |
|--------|------|------|
| AI 엔진 | Claude Code (Anthropic) | 스킬 실행 및 자연어 처리 |
| 스크립트 | Python 3 | 데이터 처리 및 API 연동 로직 |
| 자동화 | Bash | 파이프라인 흐름 제어 |
| 연동 | REST API | 외부 서비스 데이터 수집 및 전송 |
| 이벤트 | Webhook | 실시간 트리거 및 알림 |
| 환경 설정 | .env | API 키 및 설정값 관리 |

<div align="right"><a href="#목차">↑ 맨 위로</a></div>

---

## 아키텍처

```
ai-marketing-skills/
├── growth-engine/            # 성장 실험 자동화 스킬
│   ├── experiment_automation.py
│   ├── pacing_alerts.py
│   └── weekly_scorecard.py
├── sales-pipeline/           # 세일즈 파이프라인 스킬
├── content-ops/              # 콘텐츠 운영 스킬
├── outbound-engine/          # 아웃바운드 자동화 스킬
├── seo-ops/                  # SEO 최적화 스킬
├── finance-ops/              # 재무 분석 스킬
├── revenue-intelligence/     # 매출 인텔리전스 스킬
├── conversion-ops/           # 전환 최적화 스킬
├── podcast-ops/              # 팟캐스트 콘텐츠 스킬
├── sales-playbook/           # 세일즈 플레이북 스킬
├── .env.example              # 환경 변수 템플릿
└── README.md
```

**핵심 패턴**
- 각 카테고리는 독립된 디렉토리로 분리되어 필요한 스킬만 선택적으로 사용 가능
- Claude Code `/skill` 명령어로 스킬을 직접 호출하거나 Python/Bash 스크립트로 실행
- `.env` 파일로 API 키와 설정값을 중앙 관리

<div align="right"><a href="#목차">↑ 맨 위로</a></div>

---

## 데이터 흐름 / 사용법

```
스킬 호출 (/skill <name> 또는 python script.py)
     ↓
.env에서 API 키 로드 → 외부 서비스 데이터 수집 (REST API / Webhook)
     ↓
Claude Code AI 처리 → 결과물 생성 (리포트 / 이메일 / 콘텐츠)
     ↓
출력 또는 외부 서비스로 전송
```

**Claude Code에서 스킬 실행**
```bash
/skill <skill-name>
```

**스크립트 직접 실행**
```bash
git clone https://github.com/kimdzhekhon/ai-marketing-skills.git
cd ai-marketing-skills/<category>
pip install -r requirements.txt
cp .env.example .env
# .env 파일에 API 키 입력 후 실행
python <script-name>.py
```

<div align="right"><a href="#목차">↑ 맨 위로</a></div>

---

## 설치 및 실행

**요구 사항**
- Python 3
- Claude Code (Anthropic) 설치
- 각 스킬별 외부 서비스 API 키 (해당 시)

```bash
# 저장소 클론
git clone https://github.com/kimdzhekhon/ai-marketing-skills.git
cd ai-marketing-skills

# 원하는 카테고리로 이동
cd <category>

# 의존성 설치
pip install -r requirements.txt

# 환경 변수 설정
cp .env.example .env
# .env 파일을 편집하여 API 키 입력
```

Claude Code를 사용하는 경우 별도 설치 없이 `/skill <skill-name>` 명령어로 바로 실행할 수 있습니다.

<div align="right"><a href="#목차">↑ 맨 위로</a></div>

---

## Roadmap

- [x] 10개 카테고리 스킬 구현
- [x] Claude Code 통합 (/skill 명령어)
- [x] Python / Bash 자동화 스크립트
- [ ] 한국어 마케팅 특화 스킬 추가
- [ ] 자동화 파이프라인 고도화
- [ ] 실행 결과 대시보드

<div align="right"><a href="#목차">↑ 맨 위로</a></div>

---

## 라이선스

MIT License — Copyright © 2024-2026 kimdzhekhon

이 프로젝트는 [ericosiu/ai-marketing-skills](https://github.com/ericosiu/ai-marketing-skills)를 포크한 오픈소스 프로젝트입니다. MIT 라이선스 하에 자유롭게 사용, 복사, 수정, 배포할 수 있습니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참고하십시오.

<div align="right"><a href="#목차">↑ 맨 위로</a></div>
