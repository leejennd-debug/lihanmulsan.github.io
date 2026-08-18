# rihan 웹사이트 에셋 패키지 (v2 — 자간/점 수정 반영)

클라이언트 컨펌 받은 원본 로고에 자간 조정 + i 점 추가를 반영한 최신 버전입니다.

## 폴더 구성

- `logo/` — 워드마크 SVG(벡터, 투명 배경) + PNG, 다크 배지
  - `rihan-logo-ink.svg/png` — 밝은 배경용 (잉크 컬러)
  - `rihan-logo-cream.svg/png` — 어두운 배경용 (크림 컬러)
  - `rihan-badge-dark.svg/png` — 배경까지 포함된 자체완결형 다크 배지 (아무 곳에나 바로 붙여넣기용)
- `favicon/` — 파비콘 전 사이즈 + 매니페스트 아이콘
  - `favicon.svg` — 원본 벡터 (정사각형, 잉크 배경 + 크림 'r')
  - `favicon.ico` — 16/32/48/64px 번들
  - `favicon-16.png`, `favicon-32.png`, `favicon-48.png`
  - `apple-touch-icon.png` (180×180)
  - `icon-192.png`, `icon-512.png` — PWA/매니페스트용
- `social/` — `og-image.png` (1200×630, 카카오톡·페이스북·트위터 공유 미리보기용)
- `css/colors.css` — 브랜드 컬러 CSS 변수
- `site.webmanifest` — PWA 매니페스트

## HTML에 적용하는 법

`<head>` 안에 아래를 붙여넣으세요:

```html
<link rel="icon" href="/favicon/favicon.ico" sizes="any">
<link rel="icon" type="image/svg+xml" href="/favicon/favicon.svg">
<link rel="apple-touch-icon" href="/favicon/apple-touch-icon.png">
<link rel="manifest" href="/site.webmanifest">
<meta name="theme-color" content="#1E4FA0">

<!-- 소셜 공유 미리보기 -->
<meta property="og:title" content="rihan">
<meta property="og:description" content="시멘트 도매부터 물류까지">
<meta property="og:image" content="/social/og-image.png">
<meta property="og:type" content="website">
<meta name="twitter:card" content="summary_large_image">
```

CSS에서는 `css/colors.css`를 import한 뒤 변수로 색을 씁니다:

```css
@import url('/css/colors.css');

.button-primary {
  background: var(--rihan-blue);
  color: var(--rihan-cream);
}
```

## 이번 버전에서 바뀐 점

- r-i-h 사이 자간을 넓혀 더 여유 있게 (i 오른쪽은 비대칭으로 조금 더)
- h-a-n 사이 자간도 함께 넓힘
- i에 작은 점 추가 (본문 잉크/크림 컬러, 브랜드 포인트 블루 아님)
- 마지막 마침표(포인트 블루)는 살짝 축소
- r·h의 높이, 곡률 등 나머지 구조는 클라이언트 컨펌 받은 원본과 동일

## 로고 사용 규칙 (요약)

- 밝은 배경(흰색/크림)에는 `rihan-logo-ink`, 어두운 배경에는 `rihan-logo-cream`을 사용하세요.
- 로고 주변에는 로고 높이의 최소 1배 이상 여백을 두세요.
- 로고를 늘리거나, 기울이거나, 그림자·외곽선을 추가하지 마세요.
- 마침표(.)의 블루는 로고 전체에서 유일한 포인트 컬러입니다 — 페이지 안에서도 CTA 버튼/링크 등 핵심 지점에만 아껴서 쓰세요.
