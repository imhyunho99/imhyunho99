# 나현호 · Hyunho Na

**조용히 틀리고 있는 것을 찾아냅니다.** 크래시로 드러나지 않고 그냥 틀린 답을 내놓는 종류의 결함 - 프로덕션에서 그걸 찾아 고치고, AI와 일할 때도 같은 걸 하려고 도구를 직접 만듭니다.

**I find the things that are quietly wrong** - the failures that don't crash, they just return the wrong answer. I hunt them in production, and I build my own tooling to do the same when working with coding agents.

---

## 두 가지를 합니다 · Two things

**1. 증상이 아니라 원인을 지웁니다 · Remove the cause, not the symptom**

커머스 AI 챗봇 SaaS에서 백엔드·프론트 양쪽 프로덕션을 맡고 있습니다. 6개월간 550건을 머지했고 그중 **91건이 배포 승격 PR**, 남의 PR을 **67건** 리뷰했습니다.

- 파일 처리 전 경로의 **O(N²) 쓰기 증폭** 제거 - 한 문서가 2.2GB에서 31MB로. 파일 크기 제한으로 증상을 가리는 대신, 쓰기량이 페이지 수에 비례하는지 검사하는 테스트를 남겨 같은 결함이 다시 들어오면 배포 전에 걸리게 했습니다
- 전체 컬렉션 스캔 제거로 프로덕션 먹통 근본수정, 재발방지 가드 동봉
- 조용히 버려지던 채널 전송 실패를 표면화 - 실패가 성공으로 보이던 경로들
- 검색 리랭커를 바로 켜지 않고 **shadow 모드로 먼저 관측**하도록 설계하고 그 판단을 ADR로 남김
- 음성 응답 경로 지연시간 실측 개선: 첫 토큰까지 11~14초 → **1.7초**

Backend and frontend production for a commerce AI chatbot SaaS. 550 merged PRs in six months, 91 of them production releases, 67 reviews on other people's PRs.

**2. 필요한 장치를 직접 만듭니다 · Build the instrument I need**

AI가 내놓은 결과를 검증할 방법이 없으면 만듭니다. 신기한 걸 만들되 아는 개념 위에 올립니다.

- **[runahead](https://github.com/imhyunho99/runahead)** - CPU의 runahead execution을 개발 워크플로우로 이식. 투기적으로 미리 실행하고, 안 고르면 버리고, 토큰 장부로 "어떤 예측이 비용만큼 값을 하는가"에 답합니다. 500세션 시뮬레이션에서 miss 12% → 0% 수렴. `pip install runahead`
- **[end-test](https://github.com/imhyunho99/end-test)** - 끝난 세션을 문제로 되돌려 "돌아가는데 왜인지 모르는" 구간을 찾는 Claude Code / Codex 스킬. 공개 레포에 사적 식별자가 섞이지 않는지까지 계약 테스트로 막습니다
- **xreview** - 3패스 교차 코드리뷰 하네스. 시드해둔 과거 버그 3/3을 검출했습니다 (사내)

---

## Tech

**Languages** Python · TypeScript · Java · Rust · Kotlin · SQL
**Backend** FastAPI · Django / DRF · Spring Boot · Next.js
**AI** LangGraph · LangChain · MCP · RAG · Pinecone · PyTorch
**Data** PostgreSQL · MongoDB · MySQL / MariaDB · Redis · QuestDB
**Infra** GCP · AWS · Oracle Cloud · Docker · Nginx · GitHub Actions · Vercel

---

## Projects

### [runahead](https://github.com/imhyunho99/runahead)

코딩 에이전트를 위한 투기적 병렬 실행 도구. 에이전트가 다음 작업을 묻고 멈추는 대신, 답을 미리 추측해 격리된 worktree에서 실행하고 돌아왔을 때 결과 큐에서 고르게 합니다. bypass 모드가 선택을 없애는 것과 달리, 선택을 유예합니다.

Speculative parallel execution for coding agents. Instead of stopping to ask what's next, it guesses, runs each guess in an isolated worktree, and hands you a queue to pick from - your choice is deferred, not removed.

Python · git worktree

### [end-test](https://github.com/imhyunho99/end-test)

끝난 코딩 세션을 다시 문제로 되돌려주는 Claude Code / Codex 스킬. 에이전틱 코딩은 코드가 돌아가는 것과 내가 그것을 이해하는 것을 분리하는데, 그 간격을 측정합니다. 채점을 ○/✗ 이분법이 아니라 △(결론은 맞지만 이유가 빔)를 포함한 3단계로 두는 것이 핵심입니다 - 돌아는 가는데 왜인지 모르는 상태가 이분법에서는 ○으로 흡수되기 때문입니다.

A Claude Code / Codex skill that turns the session you just finished back into questions. Agentic coding separates the code working from you understanding it; this measures that gap. Grading is three-level rather than binary, because "it runs and I don't know why" gets absorbed into a pass otherwise.

Python · Claude Code / Codex plugin · 계약 테스트

### [bar-menu](https://github.com/imhyunho99/bar-menu)

앱 설치 없이 테이블 QR로 주문·결제·매장 관리를 처리하는 스마트 메뉴판. 실제 이자카야/다이닝 펍([Bidbar](https://naver.me/5ISHAhLZ))에서 프로덕션으로 운영 중입니다. Nginx 리버스 프록시로 Vercel 프론트와 백엔드를 단일 도메인에 통합했고, 매장 Wi-Fi 접속자만 주문하도록 IP·SSID 기반 권한 제어를 넣었습니다.

An install-free QR ordering, payment, and store-management service, running in production at a real dining pub. Frontend and backend are unified under one domain via an Nginx reverse proxy, with Wi-Fi-scoped ordering enforced by IP/SSID checks.

Next.js 16 · Django REST Framework · PostgreSQL · Nginx · Vercel · Oracle Cloud

### [ONZ](https://github.com/imhyunho99/Cocktail_backend)

취향 태그로 칵테일을 추천·큐레이션하는 모바일 앱. React Native 앱과 Spring Boot 백엔드로 구성되며, 팀([MobileOnz](https://github.com/MobileOnz)) 사이드 프로젝트로 실제 서비스 중입니다. 저는 백엔드 설계와 운영을 담당합니다. 소셜 로그인(Naver·Kakao·Google·Apple)을 전략 패턴으로 통합했고, 태그·도수·맛·시즌 필터 검색과 QR 방문 인증을 구현했습니다.

A cocktail-curation mobile app driven by taste tags. A React Native client with a Spring Boot backend, shipped as a live team side project. I own the backend architecture and operations, including a strategy-pattern social login and tag/ABV/taste/season filtered search.

Spring Boot 3 · Java 17 · MariaDB · QueryDSL · AWS S3 / app: React Native · Firebase

### [magic_container](https://github.com/imhyunho99/magic_container)

로컬 LLM(Qwen·Gemma 등)을 원클릭으로 설치·실행하고 채팅 UI를 서빙하는 크로스플랫폼 데스크톱 앱. 하드웨어를 감지해 모델을 내려받고, 로컬 추론 서버를 띄워 SSE로 응답을 스트리밍합니다.

A cross-platform desktop app that installs and runs local LLMs in one click. It detects your hardware, downloads a suitable model, launches a local inference server, and streams responses over SSE.

Rust · Tauri 2 · React 19 · SSE

### [alpha](https://github.com/imhyunho99/alpha)

NASDAQ와 암호화폐의 100여 개 기술 지표를 시계열 DB에 기록하고, 앙상블 머신러닝 파이프라인으로 의사결정을 보조하는 시각화 대시보드입니다.

Tracks 100+ technical indicators for NASDAQ and crypto into a time-series database, and assists decisions with an ensemble ML pipeline in a desktop dashboard.

Python · FastAPI · scikit-learn · XGBoost · LightGBM · PySide6 · QuestDB

### [CarLogoDetection](https://github.com/imhyunho99/CarLogoDetection)

업로드된 이미지에서 차량 로고 영역을 추출하고 CNN으로 브랜드를 분류하는 딥러닝 웹 서비스입니다.

A deep-learning web service that extracts car-logo regions from images and classifies the brand with a CNN.

Python · PyTorch · OpenCV · Django REST Framework · React · Oracle Cloud

---

## Contact

- Email: nahyunho1999@gmail.com
- Blog: [im-hyunho99.tistory.com](https://im-hyunho99.tistory.com/) - 대규모 트래픽 분산 처리, DB 쿼리 튜닝, 인프라 자동화
