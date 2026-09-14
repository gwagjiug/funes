# 데이터 대시보드 디자인

[English](README.md)

데이터 대시보드를 설계하고 검토하고 개선하기 위한 Agent Skill입니다. 사용자의 목적을 명확한 정보 위계, 근거 있는 차트 선택, 접근 가능한 시각 규칙, 증거 기반 리뷰 결과로 변환합니다.

## 사용 범위

- 데이터셋이나 API를 바탕으로 대시보드 설계
- 차트, 지표, 라벨, 축, 비교 방식 선택
- AI가 생성했거나 “바이브 코딩”으로 만든 대시보드 개선
- 정보 위계, 밀도, 테이블, 색상, 타이포그래피 검토
- 불확실성, 출처, 독립적 이해 가능성, 재현성 확인

## 동작 방식

세 가지 작업 모드를 지원합니다.

- **Create** — 대시보드 브리프, 사용자 여정, 차트 명세, 시각 시스템 결정, 명시적 가정을 작성합니다.
- **Review** — 확인된 문제를 `Blocker`, `Major`, `Minor`로 분류하고 각각 가장 작은 수정안을 제시합니다.
- **Refine** — 유효한 기존 구조는 유지하고 명확성이나 정확성에 필요한 최소 변경만 적용합니다.

다음 순서로 판단합니다.

```text
사용자 질문 → 지표 → 시각적 인코딩 → 대시보드 위계 → 표현 스타일
```

질문하기 전에 사용 가능한 데이터, 코드, UI, 디자인 시스템을 먼저 확인합니다. 결과를 실질적으로 바꾸거나 정확한 해석을 방해하는 미확정 사항만 사용자에게 묻습니다.

## 핵심 원칙

- 대시보드는 차트 모음이 아니라 답에 도달하는 경로입니다.
- 모든 차트와 KPI는 서로 구분되는 질문에 기여해야 합니다.
- 중요한 추정치를 툴팁, 약어, 보조 문구에 묻어두지 않습니다.
- 해석에 영향을 주는 라벨, 단위, 기간, 분모, 불확실성, 출처를 명확히 표시합니다.
- 색상만으로 상태나 범주를 구분하지 않습니다.
- 새로운 시각 언어보다 기존 제품의 디자인 토큰을 우선합니다.
- 장식용 3D는 사용하지 않으며, 이중 축에는 명시적인 근거가 필요합니다.
- 구현된 대시보드는 실제 렌더링 화면에서 검증합니다.

## 사용 예시

에이전트에게 자연스럽게 요청하면 됩니다.

```text
이 매출 데이터셋으로 대시보드를 설계해줘.
이 대시보드를 검토하고 가장 작은 수정부터 우선순위를 정해줘.
지역별 추세와 현재 값을 비교하려면 어떤 차트가 적절할까?
기존 디자인 시스템을 유지하면서 이 대시보드를 개선해줘.
```

“이 CSV로 보기 좋은 대시보드를 만들어줘”처럼 요청이 모호하면 곧바로 차트를 나열하지 않습니다. 먼저 대표 사용자, 핵심 질문, 기대 행동, 지표의 의미, 대상 화면을 확인합니다.

## 파일 구성

| 파일 | 역할 |
| --- | --- |
| [`SKILL.md`](SKILL.md) | 사용 조건, 작업 절차, 필수 규칙, 결과물 형식 |
| [`references/intake-and-workflow.md`](references/intake-and-workflow.md) | 프로젝트 조사, 결정 질문, 대시보드 브리프, 차트 명세 템플릿 |
| [`references/dashboard-rules.md`](references/dashboard-rules.md) | 사용자 여정, 위계, hero, KPI, 테이블, 색상, 타이포그래피, 간격, 반응형 규칙 |
| [`references/chart-decisions.md`](references/chart-decisions.md) | 질문별 차트 선택, 라벨, 축, 불확실성, 독립적 맥락, 재현성 |
| [`references/audit-checklist.md`](references/audit-checklist.md) | 심각도 기반 대시보드 리뷰와 구현 검증 |

## 참고 자료

이 스킬은 다음 글의 디자인 원칙을 종합해 구성했습니다.

- Adam Kucharski, [“Ten reasons your vibe-coded dashboard looks terrible”](https://kucharski.substack.com/p/ten-reasons-your-vibe-coded-dashboard)
- Saloni Dattani, [“Saloni's guide to data visualization”](https://www.scientificdiscovery.dev/p/salonis-guide-to-data-visualization)

두 원문이나 이미지를 복제하지 않습니다. 대시보드와 차트 수준의 가이드를 실제로 실행할 수 있는 디자인 워크플로로 변환했습니다.