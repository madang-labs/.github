# 마당

**마당**은 서로 다른 시스템이 독립적으로 자라고, 필요한 순간 자연스럽게 만나는 작업 공간입니다.

한국의 마당은 집과 집, 사람과 활동을 이어 주는 열린 공간입니다. 이 Organization도 같은 방식으로 UI, 서비스, 검증, 에이전트, 개인 지식 시스템을 한곳에 모으되, 각 시스템의 기술과 릴리스는 독립적으로 유지합니다.

## 구조

```text
마당 (madang)
├─ 다채 (dachae)         Frontend UI / Design System
├─ 가온 (gaon)           Backend / Service Platform
├─ 정결 (jeonggyeol)     Verification / Quality
├─ 슬기 (seulgi)         AI Agent Design
└─ 모은 (moeun)          Second Brain
```

## 시스템

### 다채 — UI와 디자인 시스템

다채는 색과 표현의 다양성을 뜻합니다. 디자인 토큰, 접근 가능한 컴포넌트, 화면 패턴, 카탈로그와 변경 검증을 제공해 일관된 인터페이스를 만듭니다.

### 가온 — 백엔드와 서비스 중심

가온은 중심을 뜻합니다. 서비스 경계, 데이터 흐름, 공통 계약, 실행 환경을 정리해 각 제품이 안정적으로 연결되도록 합니다.

### 정결 — 검증과 품질

정결은 기준에 맞고 흐트러짐이 없는 상태를 뜻합니다. 계약 검증, 테스트, 품질 게이트, 보안 및 릴리스 검토를 통해 변경의 신뢰도를 확인합니다.

### 슬기 — AI Agent 설계

슬기는 지혜와 판단력을 뜻합니다. 목표를 이해하고 계획하며, 도구를 안전하게 사용하고 결과를 검증하는 에이전트의 구조와 운영 방식을 다룹니다.

### 모은 — Second Brain

모은은 기록과 지식을 모아 두었다는 뜻입니다. 개인의 메모, 결정, 프로젝트 맥락, 자료를 연결하고 필요한 순간에 다시 찾을 수 있도록 합니다.

## 운영 원칙

- 각 시스템은 독립 Git 저장소, 독립 릴리스, 독립 CI를 가집니다.
- 시스템 간 결합은 Git submodule이 아니라 버전이 명시된 패키지와 공개 계약으로 관리합니다.
- 공통 원칙은 공유하되, 한 시스템의 기술 선택이 다른 시스템을 잠그지 않습니다.
- 모든 변경은 검증 가능한 근거와 되돌릴 수 있는 경로를 남깁니다.

## 시작하기

Organization의 레포를 모두 로컬에 내려받으려면 GitHub CLI를 사용합니다.

```bash
mkdir -p ~/github/madang
cd ~/github/madang

gh repo list madang --source --no-archived --limit 1000 \
  --json nameWithOwner --jq '.[].nameWithOwner' \
  | xargs -n 1 gh repo clone
```

`madang`은 실제 GitHub Organization 이름으로 바꿉니다.
