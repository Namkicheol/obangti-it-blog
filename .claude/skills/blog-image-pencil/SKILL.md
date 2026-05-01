---
name: blog-image-free
description: obangti 블로그 글 작성 시 무료 이미지(Pexels/Unsplash/Pixabay)를 검색·다운로드해 본문 이미지 3장을 준비하는 워크플로우. 블로그 글 작성 중 이미지가 필요할 때, "이미지 찾아", "이미지 추가", "무료 이미지" 등의 요청이 있을 때 반드시 이 스킬을 사용할 것. 이미지 검색 → 다운로드 → 파일명 변경 → HTML URL 업데이트까지 한 번에 처리.
---

# 블로그 이미지 준비 (무료 이미지 검색 + 다운로드)

블로그 글 1편당 이미지 **3장** — 상단/중간/하단 위치에 배치.

## 워크플로우

### 1단계 — 글 내용 파악 & 검색 키워드 선정

HTML 파일을 읽고 각 이미지 위치(상단/중간/하단)에 어울리는 **영어 검색 키워드** 3개를 정한다.

- 상단: 글 전체 주제를 대표하는 이미지
- 중간: 글의 핵심 개념·전환점과 연결되는 이미지
- 하단: 결론·시사점을 상징하는 이미지

### 2단계 — Pexels에서 이미지 검색

WebSearch로 Pexels 검색 결과 URL에서 직접 다운로드 가능한 이미지 URL을 찾는다.

검색 쿼리 예시:
```
site:pexels.com {keyword} free photo download
pexels.com photo {keyword}
```

또는 Unsplash / Pixabay에서 검색:
```
site:unsplash.com {keyword}
site:pixabay.com {keyword} free download
```

**목표**: 각 키워드당 직접 다운로드 가능한 이미지 URL 1개 확보.

### 3단계 — 이미지 다운로드

Bash의 `curl`로 이미지를 올바른 폴더에 저장한다.

```bash
curl -L "이미지URL" -o "/Users/namgicheol/Library/Mobile Documents/com~apple~CloudDocs/Developments/blog writings/images/YYYY-MM-DD-{글번호}/img1-{키워드}.png"

curl -L "이미지URL" -o "/Users/namgicheol/Library/Mobile Documents/com~apple~CloudDocs/Developments/blog writings/images/YYYY-MM-DD-{글번호}/img2-{키워드}.png"

curl -L "이미지URL" -o "/Users/namgicheol/Library/Mobile Documents/com~apple~CloudDocs/Developments/blog writings/images/YYYY-MM-DD-{글번호}/img3-{키워드}.png"
```

다운로드 후 `ls -lh` 로 파일 크기 확인 (1KB 미만이면 다운로드 실패).

### 4단계 — HTML 업데이트

HTML 파일의 이미지 `src`를 GitHub raw URL로 교체:

```
https://raw.githubusercontent.com/Namkicheol/obangti-it-blog/main/images/YYYY-MM-DD-{글번호}/{파일명}.png
```

`width="350"` 유지.

**교체 예시:**
```html
<!-- 변경 전 -->
<img src="[이미지자리]" alt="설명" width="350"/>

<!-- 변경 후 -->
<img src="https://raw.githubusercontent.com/Namkicheol/obangti-it-blog/main/images/2026-05-01-004/img1-terminal.png" alt="터미널 화면" width="350"/>
```

### 5단계 — 폴더 구조 확인 및 커밋

최종 폴더 구조:
```
images/YYYY-MM-DD-{글번호}/tistory_{글이름}.html
images/YYYY-MM-DD-{글번호}/img1-{키워드}.png
images/YYYY-MM-DD-{글번호}/img2-{키워드}.png
images/YYYY-MM-DD-{글번호}/img3-{키워드}.png
```

GitHub에 push해야 raw URL이 작동한다. 사용자에게 확인 후 커밋/push.

## 이미지 다운로드 실패 시 대처

1. **URL 재확인**: WebSearch로 같은 키워드 재검색, 다른 이미지 URL 시도
2. **사이트 변경**: Pexels → Unsplash → Pixabay 순서로 시도
3. **키워드 변경**: 더 단순하거나 다른 방향의 키워드 시도
4. **3회 실패 시**: 사용자에게 보고하고 수동 검색 요청

## 글 발행일 표시

HTML 상단(첫 번째 이미지 바로 위)에 날짜 확인:
```html
<p style="font-size:13px;color:#a0aec0;margin-bottom:4px;">YYYY년 M월 D일</p>
```

## 티스토리 태그

글 작성 시 HTML 상단 주석에 태그를 포함한다. 항상 이 형식을 유지:

```html
<!--
  카테고리: AI/최신뉴스
  제목(안): ...
  발행일: YYYY-MM-DD
  태그: 키워드1, 키워드2, 키워드3, ...
  소스: ...
-->
```

태그 작성 기준 (10개):
- 핵심 키워드: AI 모델명, 기업명 등 고유명사
- 검색 유입 키워드: 독자가 네이버/구글에서 검색할 법한 한국어
