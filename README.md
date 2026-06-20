# AI 강연 준비 — Okta Professional Network Night (Brisbane)

브리즈번 Okta 한인 모임 **Professional Network Night**에서 발표하는 15분 라이트토크 준비 자료입니다.

- **주제:** AI 시대에 직장인이 추구해야 할 방향
- **핵심 메시지:** AI가 일자리를 빼앗는 게 아니라, AI를 잘 쓰는 사람이 빼앗는다 — 주니어가 아니라 AI를 지휘하는 리더가 되어라
- **청중:** 호주 거주 한인 대학생·청년·사회초년생
- **형식:** 한국어 강연(기술 용어만 영어), PPT 기반(실제로는 HTML 슬라이드)
- **슬라이드 보기:** https://sdhwa92.github.io/okta-2026-ai-presentation/#1

## 폴더 구조

```
.
├── index.html              # 배포용 슬라이드 (talk/ 안의 최신 버전을 그대로 복사한 사본)
├── fonts/                   # index.html이 쓰는 웹폰트 (Pretendard)
├── research/                 # 리서치 자료 (시장 데이터, 사례, 출처)
├── talk/
│   ├── 01_content_strategy.md   # 컨텐츠 전략 (메시지 구조, 톤)
│   ├── 02_script_draft.md       # 강연 대본 (최신, 버전 히스토리는 파일 상단 참고)
│   ├── 03_slide_design.md       # 슬라이드 기획 문서
│   ├── 04_출처_및_근거.md         # 발표 중 인용하는 통계/주장의 출처
│   ├── 05_delivery_coaching.md  # 발표 전달력 코칭 노트
│   ├── AI 강연 슬라이드 v2.html   # 실제 작업 중인 슬라이드 (편집은 항상 이 파일에서)
│   ├── deck-stage.js             # 슬라이드 내비게이션/썸네일 레일 커스텀 엘리먼트
│   └── fonts/                    # talk/ 슬라이드용 웹폰트
└── references/                # 디자인 참고 이미지 (스크린샷 등) — git에는 커밋 안 함
```

## 슬라이드 작업 방법

1. **편집은 `talk/AI 강연 슬라이드 v2.html`에서만 한다.** 같은 HTML 파일 안에 `<style>`과 슬라이드별 `<section>`이 모두 들어있는 단일 파일 구조다.
2. 슬라이드 `<section>`은 `id="sN"`과 `class="sN"`을 **둘 다** 가져야 한다 — 썸네일 레일이 Shadow DOM으로 노드를 복제할 때 `id`를 제거하기 때문에, CSS가 레일에도 똑같이 적용되려면 class가 필요하다.
3. 변경 후에는 헤드리스 Chrome으로 스크린샷을 찍어 눈으로 확인한다:
   ```bash
   cd talk
   "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
     --headless --disable-gpu \
     --screenshot=/tmp/slide_N.png \
     --window-size=1920,1080 --virtual-time-budget=4000 \
     "file://$(pwd)/AI 강연 슬라이드 v2.html#N"
   ```
4. `talk/` 작업이 끝나면 **`index.html`에 그대로 복사**해서 배포용 사본을 최신 상태로 맞춘다 (`index.html`과 `talk/AI 강연 슬라이드 v2.html`은 내용이 동일해야 한다). `deck-stage.js`도 같은 폴더에 있어야 하므로 `talk/deck-stage.js`를 루트의 `deck-stage.js`로 함께 복사한다 — 빠지면 `<deck-stage>` 커스텀 엘리먼트가 정의되지 않아 슬라이드가 전혀 동작하지 않는다.

## 현재 상태

- 대본 v6.3 (최종 다듬기 단계), 슬라이드 18장 (S1~S13, AI-Native SDLC 5가지 변화 디테일 슬라이드 S7a~d, S8 포함) 완료.
- `talk/AI 강연 슬라이드.html`과 `.bak*` 파일들은 이전 버전(v1) 작업 히스토리이며 더 이상 사용하지 않는다.

## 발표자

Daehwa Seo — Atlassian Software Engineer
