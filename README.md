# 안녕하세요, 실용적인 가치와 견고한 시스템을 만드는 개발자 나현호입니다.

인공지능(AI) 모델 서빙 및 대규모 트래픽을 지탱하는 웹 백엔드 아키텍처 설계에 강점을 둔 **현업 백엔드 엔지니어**입니다.  
단순한 기능 구현을 넘어 비즈니스 흐름을 분석하고, 서비스 환경에 최적화된 인프라 및 CI/CD 파이프라인을 구축하여 지속 가능한 프로덕션을 지향합니다.

---

## Skills & Expertise

### Languages & Frameworks
<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Django-092E20?style=flat-square&logo=django&logoColor=white" alt="Django">
  <img src="https://img.shields.io/badge/DRF-A30000?style=flat-square&logo=django&logoColor=white" alt="Django REST Framework">
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI">
  <img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" alt="Rust">
  <img src="https://img.shields.io/badge/Next.js%2016-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js">
</p>

### Databases & Cache
<p>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="MySQL">
  <img src="https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white" alt="MariaDB">
  <img src="https://img.shields.io/badge/QuestDB-F25B2A?style=flat-square&logo=questdb&logoColor=white" alt="QuestDB">
</p>

### AI / Machine Learning
<p>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" alt="PyTorch">
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white" alt="TensorFlow">
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white" alt="OpenCV">
  <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=chainlink&logoColor=white" alt="LangChain">
</p>

### DevOps & Cloud
<p>
  <img src="https://img.shields.io/badge/Oracle%20Cloud-F01F0A?style=flat-square&logo=oracle&logoColor=white" alt="OCI">
  <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white" alt="AWS">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker">
  <img src="https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white" alt="Nginx">
  <img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions">
  <img src="https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white" alt="Vercel">
</p>

---

## Featured Production & Engineering Projects

### [bar-menu] QR 주문 & 스마트 메뉴판 (운영 서비스)
> **테이블 QR 코드를 활용한 무앱(Appless) 주문 결제 및 관리 서비스**
- **소개**: 비대면 스마트 오더 솔루션으로, 실제 프랜차이즈 매장([Bidbar](https://naver.me/5ISHAhLZ))에서 프로덕션 운영 중인 서비스입니다.
- **핵심 아키텍처**: Next.js 16 + Django REST Framework의 완전 결합 분리 구조. OCI + Vercel 분산 서버 환경 구성.
- **주요 해결 과제**:
  - Nginx 리버스 프록시를 통해 Vercel(Edge SSR)과 uWSGI(Django API)를 하나의 단일 도메인(`bar-menu.ddnsfree.com`)으로 결합하여 CORS 문제를 원천 해결하고 SEO 및 유저 편의성을 극대화.
  - Payhere POS API 연동 및 결제 시뮬레이터 통합 개발.
  - 매장 WiFi 환경 검증 시스템 구축 (Vercel Edge의 IP 파싱 및 SSID QR 매칭을 통한 주문 권한 제어).
  - 실시간 주문 관제 대시보드 (WebSocket / Polling 및 Web Audio API를 사용한 주문 접수 알림음 발생).
- **기술 스택**: `Next.js 16 (TypeScript)`, `Django REST Framework`, `PostgreSQL`, `Nginx`, `uWSGI`, `Vercel`, `Oracle Cloud`
- **Repo**: [bar-menu](https://github.com/imhyunho99/bar-menu)

---

### [magic_container] 로컬 AI 오케스트레이터
> **로컬 AI 모델 환경 자동 구성 및 데스크톱 배포 솔루션**
- **소개**: 한 번의 빌드로 사용자 기기 내 로컬 런타임 환경에서 다양한 AI 모델(LLM, CV, TTS 등) 구동용 UI 및 환경설정을 자동화해주는 크로스 플랫폼 컨테이너입니다.
- **기술 스택**: `Rust`, `Tauri`, `llama-cpp`
- **Repo**: [magic_container](https://github.com/imhyunho99/magic_container)

---

### [Alpha] AI 기반 투자 어드바이저
> **앙상블 머신러닝 모델 활용 자산 가치 분석 및 투자 추천 시스템**
- **소개**: NASDAQ 100 지수 및 Top 100 암호화폐의 실시간 기술 지표를 추적 및 시계열 분석하여 투자 의사결정을 보조하는 시각화 도구입니다.
- **기술 스택**: `Python/FastAPI`, `scikit-learn`, `XGBoost`, `LightGBM`, `PySide6 (Qt)`, `QuestDB`
- **Repo**: [alpha](https://github.com/imhyunho99/alpha)

---

### [CarLogoDetection] 실시간 차량 엠블럼 분류기
> **PyTorch 딥러닝과 OpenCV 기반 차량 로고 인식 및 강화학습 파이프라인**
- **소개**: 차량 엠블럼 이미지를 CNN 모델로 분석하여 제조사를 고속 분류하고, 미분류 이미지 발생 시 자동 피드백 학습 순환을 처리하는 인공지능 프로토타입입니다.
- **기술 스택**: `Python`, `PyTorch`, `OpenCV`, `Nginx`
- **Repo**: [CarLogoDetection](https://github.com/imhyunho99/CarLogoDetection)

---

## Contact & Channels

- **Email**: nahyunho1999@gmail.com
- **Tistory Blog**: [https://im-hyunho99.tistory.com/](https://im-hyunho99.tistory.com/) (주로 대규모 트래픽 분산 처리, DB 쿼리 최적화, 인프라 자동화 관련 포스팅 업로드 중)

---
<p align="center">
  💡 <b>"단순히 돌아가는 코드를 넘어, 비즈니스 흐름을 가장 우아하게 담아내는 설계를 지향합니다."</b>
</p>
