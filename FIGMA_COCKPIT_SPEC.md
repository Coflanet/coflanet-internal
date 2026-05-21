# Coflanet Cockpit · Figma 디자인 스펙

> 이 문서는 `coflanet-internal/index.html` 사이트와 동일한 레이아웃으로 Figma의 Cockpit 페이지(파일 `LcK8I83FPelBoPFxFOSAmm`)를 재구성하기 위한 명세입니다. Figma MCP 연결이 복구되면 그대로 적용할 수 있습니다.

## 파일 / 페이지

- **fileKey:** `LcK8I83FPelBoPFxFOSAmm`
- **Page:** `Cockpit` (기존 프레임 전체 삭제 후 재구성)
- **Top-level Frame:** `Cockpit / Dashboard 1440` — 1440 × 900 (Auto Layout: Horizontal)

## 디자인 토큰

| Token | Value |
| ----- | ----- |
| `color/bg` | `#0F0F11` |
| `color/bg-2` | `#16161A` |
| `color/bg-3` | `#1E1E24` |
| `color/sidebar` | `#1B1C1E` |
| `color/card` | `#1B1C1E` |
| `color/primary` | `#6541F2` |
| `color/primary-soft` | `#6541F215` |
| `color/text` | `#F4F4F6` |
| `color/text-2` | `#A8A8B4` |
| `color/text-3` | `#68687A` |
| `color/border-soft` | `#22222C` |
| `color/green` | `#34D399` |
| `color/yellow` | `#FBBF24` |
| `color/blue` | `#60A5FA` |
| `color/red` | `#F87171` |
| `radius/card` | 16 |
| `radius/btn` | 10 |
| `radius/avatar` | 100 |
| `font/family` | Pretendard |
| `shadow/card` | `0 4 24 rgba(0,0,0,0.25)` |

## 레이아웃

```
┌──────────────────────────────────────────────────────────────┐
│  Sidebar (240) │  Main (1200)                                │
│                │                                             │
│  Logo + Brand  │  Page Header                                │
│  Nav × 6       │  ─────────────                              │
│                │  4 stat cards (Design System/Widget/Token/  │
│                │  Vibe Coding) — grid 4 × 1                  │
│                │                                             │
│                │  2-col grid: 잔여작업 · 타임라인              │
│                │                                             │
│                │  Persona cards 5 (grid 2col)                │
│                │                                             │
│                │  Roadmap Phase 1/2/3 (좌측 컬러 액센트)       │
│                │                                             │
│                │  Cost compare (Vibe 0원 / Dev 700~1300만)   │
│                │                                             │
│  Footer        │                                             │
└──────────────────────────────────────────────────────────────┘
```

### Sidebar — 240 × 900

- 배경 `color/sidebar` (#1B1C1E), 우측 1px `color/border-soft`
- **Header** (padding 22 × 18)
  - Logo symbol 34 × 34 · `primary-soft` 배경 · 9 radius · 1px inset border `primary 20%`
  - Brand text: `Coflanet` (14 / 700) + `Cockpit` (10 / 600 · letter-spacing 8% · uppercase · color text-3)
- **Nav** (padding 14 × 10, gap 2)
  - Item: padding 10 × 12 · radius 10 · 13 / 500 · icon 17 + label
  - Hover: bg `bg-3`, text `text`
  - Active: bg `primary-dim` (#6541F233), text `primary-light` (#8B6FFF), 600
  - 항목 6: 현재 상황 / 퍼소나 / 퍼소나 의사결정 / 로드맵 / IA 정보구조 / 개발 비용 분석
- **Footer** (padding 16 × 18)
  - 6px green pulse dot + `Coflanet © 2025 · 택림` (11 / text-3)

### Main — 1200 × auto

- Padding 32 × 36
- Page title 24 / 800 · letter-spacing -2%
- Page description 13 / 400 · color text-2

#### 1. 상단 4 stat 카드 — grid 4 × 1, gap 14

각 카드: 240 × 152, radius 16, padding 22, bg `color/card`, 좌측 3px 컬러 액센트

| Card | Color | Value | Sub |
| ---- | ----- | ----- | --- |
| Design System | `primary` | 78% | 토큰 통일 · Variables 91,030 바인딩 완료 |
| Widget | `green` | 12개 | Figma → 앱 이관 완료 · Liquid Glass 적용 |
| Token | `blue` | 91K | Variables 바인딩 · Color/Spacing/Typo |
| Vibe Coding | `yellow` | 73% | 15개 기능 중 11개 자체 구현 가능 |

구조:
1. Icon 32 × 32 · radius 8 · 컬러 18% 배경
2. Stat name 12 / 600 · letter-spacing 4% · uppercase · text-3
3. Stat value 28 / 800 · -3%
4. Stat sub 12 / 400 · text-2
5. Progress bar 5px · bg-4 트랙 · 해당 컬러 fill

#### 2. 2-col grid — 잔여 작업 · 최근 완료 타임라인

`card` 컴포넌트 2개 (radius 16, padding 22)

- **잔여 작업** — 10개 체크리스트 (3 done, 7 pending)
  - 항목 padding 10 × 0, border-bottom 1px `border-soft`
  - check 18 × 18 · radius 6 · 1.5 border
  - done: bg `green`, ✓ #000, 본문 line-through + text-3
- **최근 완료 타임라인** — 8개 항목
  - 좌측 2px 그라데이션 라인 (primary → border 70%)
  - 각 항목 dot 10 × 10 · primary · 2.5px card bg ring
  - 날짜 11 / 600 + 본문 13 / 400 / text-2

#### 3. 퍼소나 카드 5종 — grid 2col, gap 14

각 카드: radius 16 · padding 22 · 상단 3px 컬러 그라데이션 액센트

| # | 이름 | 나이 · 역할 · 레벨 | Color | Avatar |
| - | --- | ----------------- | ----- | ------ |
| 1 | 이서현 | 41 · 사무직 · 홈카페 2년차 | `#6541F2` | `images/persona-1-seohyun.jpg` |
| 2 | 한은성 | 32 · 전업주부 · 8년차 중급자 | `#34D399` | `images/persona-2-eunsung.jpg` |
| 3 | 이민재 | 34 · 개발자 · 입문 | `#60A5FA` | `images/persona-3-minjae.jpg` |
| 4 | 박지원 | 28 · MZ 디자이너 · 입문~초급 (★신규) | `#FBBF24` | `images/persona-4-jiwon.jpg` |
| 5 | 최도현 | 36 · 1인 카페 바리스타 · 프로 (★신규) | `#F87171` | `images/persona-5-dohyun.jpg` |

카드 내부:
1. **Header** — 원형 아바타 60 × 60 (radius 100, 2px border) + 이름 16/700 + 서브 12/text-3
2. **장비/소비** 섹션 라벨 (11/700, 6% 자간, uppercase, text-3) + 본문 13/text-2
3. **페인포인트** — 동일 형식, • 불릿
4. **결제 의향** — 동일 형식

#### 4. 로드맵 — Phase 1 / 2 / 3 (좌측 컬러 액센트 바)

각 Phase 블록: padding 18, padding-left 22, radius 16, bg `bg-3`, 좌측 4px 컬러 액센트

| Phase | Period | Accent | 기능 수 |
| ----- | ------ | ------ | ------ |
| Phase 1 | 0~3개월 (MVP) | `#34D399` | 6 |
| Phase 2 | 3~9개월 | `#FBBF24` | 5 |
| Phase 3 | 9~18개월 | `#F87171` | 4 |

각 feature row: 13/500 이름 + 우측 badge 그룹 (`badge-vibe`/`badge-risk` + `badge-phase`(IA 경로) + `cf. 벤치마크` 11/text-3)

#### 5. 개발 비용 비교 — Vibe vs Dev (cost-compare)

2-col grid (768 이하 단열)

- **Vibe** 카드 — 22 padding · radius 16 · linear-gradient `green 12% → 3%` · 1px `green 20%` border
  - 제목 `바이브코딩` 14/700
  - 큰 숫자 `0원` 32/800 / green
  - 서브 `11개 기능 · 73% · 자체 구현 가능` 12/text-2
  - 5개 불릿 리스트
- **Dev** 카드 — 동일 패턴, red 톤, `700~1,300만원/월`, 4개 불릿
- 하단 `card` 컴포넌트에 cost-table 15행 (기능 / 구분 / 바이브코딩 / 월 비용 / 비고)

## Auto Layout 가이드

- 모든 카드/섹션: Vertical Auto Layout, gap 14, padding 22
- Grid는 Figma Auto Layout `Wrap`으로 표현 (gap 14, fill container)
- Sidebar nav: Vertical Auto Layout · padding 14 × 10 · gap 2
- Persona header / stat header: Horizontal Auto Layout

## Components (Figma)

| Component | Variants |
| --------- | -------- |
| `Nav/Item` | state = default · hover · active |
| `Card/Base` | — |
| `Card/Stat` | color = primary · green · blue · yellow |
| `Card/Persona` | persona = 1~5 |
| `Card/Phase` | phase = 1 · 2 · 3 |
| `Card/Cost` | side = vibe · dev |
| `Badge` | tone = vibe · risk · phase · new |
| `Avatar` | size = 60 · variant = image · initial |
| `Checkbox` | state = unchecked · done |
| `ProgressBar` | color = primary · green · blue · yellow |
| `TimelineDot` | — |

## 변경 이력 (vs. 기존 Cockpit 페이지)

1. 사이드바 너비 248 → **240**
2. 사이드바 배경 `bg-2` (#16161A) → `sidebar` (#1B1C1E) — card와 동일 톤으로 통일
3. 브랜드 라벨 `Coflanet · Internal` → `Coflanet · Cockpit`
4. 카드 radius 24 → **16**
5. 상단 stat 카드 3개(디자인 시스템 / 앱 개발 / 인프라) → **4개(Design System / Widget / Token / Vibe Coding)**
6. 각 stat 카드에 좌측 3px 컬러 액센트 + 32px 아이콘 추가
7. 로드맵 Phase 헤더 → **좌측 4px 컬러 액센트 바를 가진 Phase 블록**으로 변경
8. 개발 비용 페이지 상단을 텍스트 통계 → **Vibe vs Dev 2-col 비교 카드**로 시각화

---

> 참고: 사이트는 `coflanet-internal/index.html` 단일 파일. Figma도 이 스펙에 맞춰 컴포넌트화하면 코드 ↔ 디자인 1:1 미러링이 가능합니다.
