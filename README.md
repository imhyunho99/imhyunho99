# 🚀 안녕하세요, 실용적인 가치와 견고한 시스템을 만드는 개발자 나현호입니다.

인공지능(AI) 모델 서빙 및 대규모 트래픽을 지탱하는 웹 백엔드 아키텍처 설계에 강점을 둔 **현업 백엔드 엔지니어**입니다.  
단순한 기능 구현을 넘어 비즈니스 흐름을 분석하고, 서비스 환경에 최적화된 인프라 및 CI/CD 파이프라인을 구축하여 지속 가능한 프로덕션을 지향합니다.

---

## 🛠️ Skills & Expertise

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

## 🚀 Production & Engineering Projects

### 🥂 [bar-menu](https://github.com/imhyunho99/bar-menu) — 스마트 QR 메뉴판 & 비대면 오더 솔루션 (운영 서비스)
> **테이블 QR 코드를 활용하여 앱 설치 없이 주문/결제 및 매장을 관리하는 스마트 솔루션**
- **실무 프로덕션 서비스**: 실제 이자카야 및 다이닝 펍 매장([Bidbar](https://naver.me/5ISHAhLZ))에서 100% 프로덕션 서비스로 실운영 중인 솔루션입니다.
- **핵심 아키텍처**: Next.js 16 + Django REST Framework 분리형 아키텍처. Vercel(Edge SSR)과 Oracle Cloud Infrastructure(OCI) 리버스 프록시 연동.
- **해결한 기술 과제**:
  - **단일 도메인 통합**: Nginx 리버스 프록시 우회 설정을 구축하여 Vercel Frontend와 uWSGI Backend API를 단일 도메인(`https://bar-menu.ddnsfree.com`)으로 무중단 통합함으로써 CORS 원천 해결 및 SEO 점수 99점 확보.
  - **Wi-Fi 권한 제어**: Vercel Edge Middleware의 IP 감지 기능과 매장 Wi-Fi 공유기 SSID 매칭 알고리즘을 설계하여 매장 와이파이 접속자만 주문할 수 있도록 완벽한 권한 통제 구현.
  - **결제 API 통합**: 페이히어(Payhere) POS API와 연동된 결제 시뮬레이터 및 실시간 실물 POS 주문 내역 동기화 파이프라인 개발.
  - **실시간 관제**: Django Admin 내부에 WebSocket 및 Polling 기반 실시간 주문 대시보드를 연동하고, Web Audio API chime 알림을 적용하여 매장 회전 속도 극대화.
- **기술 스택**: `Next.js 16 (TypeScript)`, `Django REST Framework`, `PostgreSQL`, `Nginx`, `uWSGI`, `Vercel`, `Oracle Cloud`

---

### 📦 [magic_container](https://github.com/imhyunho99/magic_container) — 로컬 AI 오케스트레이터
> **로컬 AI 모델 환경 자동 구성 및 데스크톱 배포용 크로스 플랫폼 컨테이너**
- **특징**: 복잡한 환경 설정 없이 로컬에서 다양한 AI 모델(LLM, CV, TTS 등)을 손쉽게 구동하고 UI를 서빙할 수 있도록 빌드 및 실행 프로세스를 자동화합니다.
- **기술 스택**: `Rust`, `Tauri`, `llama-cpp`

---

### 📈 [alpha](https://github.com/imhyunho99/alpha) — AI 기반 투자 어드바이저
> **앙상블 머신러닝 모델 기반 실시간 시계열 자산 가치 분석 및 투자 추천 시스템**
- **특징**: NASDAQ 지수 및 주요 암호화폐 시장의 100여 개 기술 지표를 고성능 시계열 데이터베이스에 추적/기록하고, 학습된 머신러닝 파이프라인을 연동해 의사결정을 보조하는 시각화 대시보드입니다.
- **기술 스택**: `Python/FastAPI`, `scikit-learn`, `XGBoost`, `LightGBM`, `PySide6 (Qt)`, `QuestDB`

---

### 🚗 [CarLogoDetection](https://github.com/imhyunho99/CarLogoDetection) — 실시간 차량 엠블럼 분류기
> **PyTorch Deep Learning 기반의 차량 로고 고속 검출 및 피드백 학습 파이프라인**
- **특징**: 도로 및 주차장 CCTV 스트림에서 차량 엠블럼 영역을 정확히 ROI로 추출하고, CNN 모델을 거쳐 브랜드를 분류 및 이상치를 감지하여 피드백 순환 학습을 수행하는 데모 시스템입니다.
- **기술 스택**: `Python`, `PyTorch`, `OpenCV`, `Nginx`

---

## 📬 Contact & Links

- **Email**: nahyunho1999@gmail.com
- **Blog**: [https://im-hyunho99.tistory.com/](https://im-hyunho99.tistory.com/) (대규모 트래픽 분산 처리, DB 쿼리 튜닝, 인프라 자동화 등에 특화된 기술 포스팅 운영 중)

---
<p align="center">
  💡 <b>"단순히 작동하는 코드를 넘어, 비즈니스의 가치를 가장 안정적이고 우아하게 담아내는 시스템을 만듭니다."</b>
</p>
