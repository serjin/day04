# Jin 포트폴리오

디자인 작업물을 소개하는 개인 포트폴리오 사이트.

## 핵심 기능

| 기능 | 설명 | 로그인 필요 |
| --- | --- | --- |
| 자기소개 | 이름, 소개 글, 연락처 등 | 아니오 |
| 작업물 목록 | 등록된 작업물을 카드 형태로 나열 | 아니오 |
| 작업물 상세 | 작업물 하나의 이미지·설명 등 자세한 내용 | 아니오 |
| 로그인 | 사이트 주인(Jin)만 로그인 | - |
| 작업물 등록/수정/삭제 | 작업물 관리 | 예 |

방문자는 보기만 하고, 등록·수정·삭제는 로그인한 사이트 주인만 할 수 있어야 한다.

## 기술 구성

- 빌드 도구 없이 순수 HTML / CSS / JavaScript 파일로 구성
- 데이터는 Supabase REST API(`https://xvybnyojhweiudjbktdq.supabase.co/rest/v1/`)를 `fetch`로 호출
- 브라우저에서 쓰는 공개용(publishable) 키만 코드에 넣는다. secret / service_role 키는 절대 넣지 않는다.
- 데이터 보호는 Supabase의 RLS 정책으로 한다 (조회는 모두 허용, 쓰기는 로그인한 사용자만).

## 현재 파일

- `index.html` — 홈
- `about.html` — 소개 페이지 (자기소개 기능의 기반)
- `preview.html` — Supabase `test_todos` 표를 불러와 목록으로 보여주는 연습 페이지. 작업물 목록을 만들 때 데이터 불러오기 방식의 참고용
- `style.css` — 모든 페이지가 함께 쓰는 공통 스타일

## 디자인 규칙

- 어두운 남색 테마. 색은 `style.css` 맨 위 `:root`의 변수(`--bg`, `--surface`, `--accent` 등)만 사용하고, 새 색이 필요하면 변수로 추가한다.
- 새 페이지는 `style.css`를 연결하고, 다른 페이지와 같은 상단 메뉴(`.site-header`)를 넣는다. 현재 페이지 메뉴에는 `class="active"`를 붙인다.
- 본문은 `<main>` 안에 두고, 카드는 `.card`, 버튼은 `.button` / `.button.secondary`를 쓴다.
- 화면에 보이는 글과 코드 주석은 한국어로 쓴다.

## 작업 규칙

- 커밋 메시지는 한국어로 쓴다.
- 작업 후 `main` 브랜치에 커밋하고 `origin`(https://github.com/serjin/day04)에 푸시한다.

## 폰트 규칙
- 폰트는 컬러를 green컬러로 설정한다.