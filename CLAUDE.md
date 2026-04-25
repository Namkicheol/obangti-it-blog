# CLAUDE.md — obangti IT/AI 블로그 프로젝트 지침

> Claude Code에서 이 프로젝트를 열면 자동으로 이 지침을 읽습니다.
> 사용자: 남기철 (코딩 초보, Canva Pro)

---

## 🎯 블로그 핵심 미션

**"Claude 공식 발표는 영어고, 스레드는 너무 혼잡해 — 그걸 이해 쉽게, 친근하게 전달한다"**

- **역할**: 흩어진 영어 원문과 혼잡한 스레드를 한국어 독자가 바로 이해할 수 있도록 정리·번역·해석
- **톤**: 전문 용어를 쓰되 쉽게 풀어서. 딱딱하지 않게, 친근하게

---

## 📰 글감 발굴 워크플로우 (매 글 작성 전 필수)

### 1단계 — 스레드 인기글 먼저 읽기 (최우선)
- `https://www.threads.com/@choi.openai` 최신 글 훑기
- 좋아요/댓글/리포스트 많은 글이 주제 후보
- 스레드는 "사람들이 지금 뭘 궁금해하는지"를 보여주는 온도계

### 2단계 — 최우선 소재 체크
1. **Claude 공식 발표** (red.anthropic.com, anthropic.com/news)
2. **Claude 관련 X(구 트위터) 인기 포스트**
3. 위 두 곳에서 소재가 없을 때만 → TechCrunch, VentureBeat, The Verge 등 테크 미디어

### 3단계 — 중복 체크
- `blog writings/` 폴더의 기존 HTML 파일 확인
- 이미 쓴 주제는 건너뜀

### 4단계 — 소재 확정 후 원문 읽기
- 공식 발표 원문 WebFetch로 직접 읽기
- 스레드 원문 WebFetch로 읽고 핵심 수치·인용 확인

---

## 👤 사용자 기본 정보

- 블로그 화자: **"현직쌤"**
- 코딩 수준: **왕초보** → 용어 설명 필수, 복잡한 작업은 완성 파일 제공
- 관심사: AI, 바이브코딩, 업무자동화

---

## 📡 채널

| 채널 | 주소 | 목표 |
|---|---|---|
| 티스토리 AI/최신뉴스 탭 | obangti.tistory.com | 구글 애드센스, 검색 유입 |
| 네이버 블로그 | 별도 운영 | 네이버 상위노출 → 티스토리 트래픽 연결 |

---

## ✍️ AI/최신뉴스 탭 글쓰기 스타일

- **형식**: HTML (인라인 스타일)
- **길이**: 10,000~12,000자
- **톤**: 어그로 제목 + 진지 본문. 번역투 금지, 사람이 쓴 자연스러운 한국어
- **구성**:
  1. 도입부 3줄 — 강한 훅 (손해회피/충격수치 심리 자극)
  2. 충격 수치 박스
  3. 짧은 문단 + 센 한 줄 교차로 리듬감
  4. ⚠️경고 박스, 💡현직쌤 팁 등 시각 요소
  5. 정리 표
- **섹션 수**: 소제목 5개 내외 (너무 잘게 쪼개면 산만해짐)
- **팩트체크**: 정보성 글은 `web_search`로 확인 필수

### 네이버 버전
- 스마트에디터 특성: **iframe ❌, 마크다운 ❌, 색깔 ❌, SVG ❌**
- 구성: 텍스트 + `[이미지자리]` + `[링크버튼자리]`
- 최소 1,500자, 이미지 최소 3장, 친근체 (`~이에요`, `~거든요`)

---

## 🎨 HTML 색깔 시스템

| 용도 | 색상 코드 |
|---|---|
| 핵심 개념·정의 | `#3182ce` (파랑) |
| 주의·경고·충격 | `#c53030` (빨강) |
| 현직쌤 팁 | `#dd6b20` (주황) |
| 장점·긍정 | `#319795` (청록) |
| 인물명·브랜드 | `#805ad5` (보라) |

**사용량**: 10,000~12,000자 기준 10~15개 span  
**금기**: 한 문단 4색 이상 ❌, 전체 문장 색 감싸기 ❌, 헤더에 색 ❌

---

## 🖼 이미지 — Pencil MCP 사용 (기본)

- **본문 이미지는 3장** — 상단/중간/하단. 나머지는 SVG로 대체
- **Pencil MCP로 3장 AI 생성** (사용자 지시: 2026-04-25)
  1. Pencil.app이 실행 중인지 확인 (안 되어 있으면 `open /Applications/Pencil.app` 알려주기)
  2. `get_editor_state` → `find_empty_space_on_canvas`
  3. 프레임 생성 후 `G(frameId, "ai", "프롬프트")` 로 이미지 생성
  4. `get_screenshot` 으로 결과 확인
  5. `export_nodes` → `images/YYYY-MM-DD-{글번호}/` 폴더로 내보내기
- **이미지 width: 350px** (HTML `width="350"`)
- 폴더 구조: **HTML 파일 + 이미지를 같은 폴더에** (사용자 지시: 2026-04-25)
  - `images/YYYY-MM-DD-{글번호}/tistory_글이름.html`
  - `images/YYYY-MM-DD-{글번호}/img1-설명.png`
  - 예: `images/2026-04-25-002/tistory_mythos_2026.html`
- GitHub raw URL로 HTML에 삽입: `https://raw.githubusercontent.com/Namkicheol/obangti-it-blog/main/images/YYYY-MM-DD-{글번호}/{파일명}.png`
- **글 상단에 발행일 표시** — `<p style="font-size:13px;color:#a0aec0;">YYYY년 M월 D일</p>`

---

## 🖼 SVG 도해

위계·흐름·비교 구조가 있으면 제안 없이 바로 제작.

```html
<p align="center">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 700 280" width="700" style="max-width:100%;height:auto;">
  <rect x="0" y="0" width="700" height="280" fill="#fafafa" stroke="#e2e8f0"/>
  <text x="350" y="28" text-anchor="middle" font-size="15" font-weight="bold" fill="#2d3748">제목</text>
</svg>
</p>
```

---

## 💻 코딩 작업 규칙

1. **용어 설명 필수** — 괄호 안에 쉬운 설명
2. **이유 설명** 필수
3. **복잡한 작업은 완성 파일로 제공**
4. **단계별로 나눠서** 설명

---

---

## 📰 발행된 글 목록

| 파일명 | 주제 | 발행일 |
|---|---|---|
| tistory_claude_controversy_2026.html | Claude Code 성능 저하 논란 + Anthropic 사과 | 2026-04-25 |
| tistory_colleague_skill_2026.html | Claude Code colleague 스킬 소개 | 2026-04-25 |
| images/2026-04-25-002/tistory_mythos_2026.html | Claude Mythos 공개금지 AI + 해킹 유출 사건 | 2026-04-25 |

*마지막 업데이트: 2026-04-25*
