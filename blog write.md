# 임용고시 (영어학·영교론) 블로그 글쓰기 규칙

> 이 파일은 `linguistics` / `englisheducation` 레포의 블로그 글 작성 공통 가이드.
> 각 레포 CLAUDE.md의 "블로그 글 작성" 섹션에서 이 파일을 참조한다.

---

## 📁 파일 관리

| 항목 | 규칙 |
|------|------|
| 형식 | `.md` (마크다운 + 인라인 HTML 스타일) |
| 저장 위치 | 각 레포의 `blog/` 폴더 |
| 파일명 (개념편) | `Ch0N-챕터명.md` (예: `Ch01-Stress.md`) |
| 파일명 (OX편) | `Ch0N-챕터명-OX.md` (예: `Ch01-Stress-OX.md`) |
| 썸네일 | `blog/thumbnails/` 폴더 |

---

## 📐 개념 정리 글 구조 (메인편)

```
[상단] iframe — 자신의 GitHub Pages 개념정리 페이지
[본문] 4섹션 보강
[하단] OX·응용 링크 버튼 + 태그
```

### 상단 iframe (필수)

자신의 GitHub Pages 개념정리 페이지를 문서 맨 위에 iframe으로 삽입한다.

```html
<iframe src="https://namkicheol.github.io/{레포명}/{챕터}_study.html"
  width="100%" height="1000" style="border:1px solid #e2e8f0;border-radius:8px;">
</iframe>
```

- **phonetics-phonology**: `namkicheol.github.io/phonetics-phonology/{챕터}_study.html`
- **englisheducation**: `namkicheol.github.io/englisheducation/{챕터}_study.html`
- ❌ 외부(타인) 사이트 iframe 금지

### 본문 — 4섹션

| 섹션 | 내용 | 필수 여부 |
|------|------|-----------|
| ① 개념 정의 | 영어 원문 한 문단 + 한글 설명 한 문단 교차 | **필수** |
| ② 기출 맥락 | 연도·출제 형태 (refs 검증 후에만 표기) | 최소 2개 중 택 |
| ③ 키텀 비교 | 혼동하기 쉬운 개념 대조 | 최소 2개 중 택 |
| ④ 수험 팁 | 현직쌤 팁, 답안 작성 포인트 | 합격자 노트에 팁 있으면 무조건 포함 |

### 하단

```markdown
<p align="center">
<a href="https://obangti.tistory.com/<post-id>" target="_blank"
  style="display:inline-block;padding:14px 28px;background:#3182ce;color:#fff;
  text-decoration:none;border-radius:8px;font-weight:bold;font-size:15px;">
  📝 [챕터명] OX 풀러 가기 →
</a>
</p>

---

*태그: 키워드1, 키워드2, ...*
```

---

## 📝 OX·응용 글 구조 (별도 발행)

```
① 짧은 도입 (1-2줄)
② 본문 = N문항 × 자세한 해설 (90%)
③ 개념정리 글로 돌아가기 링크 버튼
```

**문항당 해설 구성**:
- 문항 텍스트
- 정답 (✅ 맞음 / ❌ 틀림)
- 영어 원문 인용 1-2문장
- 한글 풀이
- ⚠️ 함정·주의 (해당 시)
- 기출 연도 <span style="color:#c53030;">빨간색</span> (refs 검증 후에만)
- 5색 하이라이트

분량: 5,000~10,000자 (문항당 250-500자)

---

## 🎨 5색 하이라이트 시스템

| 용도 | 색상 | 코드 |
|------|------|------|
| 이론명·rule·기술 용어 | 파랑 | `<span style="color:#3182ce;">**...**</span>` |
| 학자명 | 보라 | `<span style="color:#805ad5;">**...**</span>` |
| 함정·주의·오개념 | 빨강 | `<span style="color:#c53030;">**...**</span>` |
| 정답·올바른 분석 | 청록 | `<span style="color:#319795;">**...**</span>` |
| 현직쌤 팁 | 주황 | `<span style="color:#dd6b20;">**현직쌤 팁**</span>` |

**기출 연도** → `<span style="color:#c53030;">**20XX 기출**</span>` (refs 검증 후에만)

---

## 🖼 썸네일 이미지

임용 블로그는 **썸네일만** 생성 (본문 이미지 없음). 저장: `blog/thumbnails/`

| 순위 | 방법 | 비고 |
|------|------|------|
| 1순위 | **Canva** (권장) | 사용자가 직접 제작 후 저장 |
| 2순위 | HuggingFace Flux | `~/scripts/gen_thumb.py --style [레포명]` |
| 3순위 | Pollinations.ai | HF 실패 시 fallback |

**공통 규칙**: Canva 텍스트는 **English only** (한국어 텍스트 금지)

| 레포 | Canva 스타일 |
|------|-------------|
| linguistics | dark + yellow accent / IPA · articulation elements |
| englisheducation | dark green + lime accent / classroom elements |

---

## ✍️ 공통 작성 원칙

- **한글 설명 내 학술 키워드는 영어 원어** — `Input Hypothesis`를 "입력 가설"로 번역 X
- **출처 인용 표기 불필요** — `— PLLT 6th, Ch.10` 같은 표기 X
- **기출 연도·출제 정보는 refs 검증 후에만** — 추정 금지
- **SVG 사용 금지** (블로그 한정)
- **본문에 출처 인용 표기 불필요**
