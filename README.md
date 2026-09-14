# Hi there, I'm Sehoon Kim (김세훈) 👋

**측정한 근거로 판단하고, 원리부터 검증하는 AI Engineer**

공간 컴퓨팅(Spatial Computing)과 인공지능 기술을 융합하여 에이전트·RAG 시스템, 멀티모달 XR 라이프로깅, 의료 AI를 연구·개발합니다. 추상적인 가정을 실측으로 검증하고, 성공뿐 아니라 실패와 기각한 결론까지 문서로 남기는 것을 원칙으로 합니다.

---

## 🎯 What I value

- **가정을 실측하는** — 유행하는 기술도 내 데이터로 재보고 도입 여부를 결정합니다. (골든셋 25문항 직접 라벨링해 recall@k 실측, 토크나이저 통제 비교 실험으로 "ppl은 토크나이저 다르면 비교 불가" 확인)
- **기록으로 남기는** — 성공뿐 아니라 실패와 기각한 결론까지 문서로 남깁니다. (검색 전략 7종·임베딩 3종 비교 후 "바꾸지 않는다"를 결론으로 문서화)
- **안전하게 설계하는** — 되돌릴 수 없는 행동은 LLM에게 도구로 주지 않습니다. (승인 게이트 분리, 도구 화이트리스트 + 재귀 한도로 에이전트 루프에 가드레일)

---

## 🛠 Tech Stacks

### 🤖 AI & Agents
<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"/>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=PyTorch&logoColor=white"/>
  <img src="https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=HuggingFace&logoColor=black"/>
  <img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=LangChain&logoColor=white"/>
  <img src="https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=Ollama&logoColor=white"/>
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=OpenCV&logoColor=white"/>
</p>

### 🌐 Spatial Computing & Frontend
<p>
  <img src="https://img.shields.io/badge/WebXR-FF4A5A?style=flat-square&logo=WebXR&logoColor=white"/>
  <img src="https://img.shields.io/badge/Three.js-000000?style=flat-square&logo=Three.js&logoColor=white"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=JavaScript&logoColor=black"/>
</p>

### ⚙️ Backend & DevOps
<p>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=FastAPI&logoColor=white"/>
  <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=Node.js&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=SpringBoot&logoColor=white"/>
  <img src="https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=MariaDB&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=Docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/AWS_EC2-232F3E?style=flat-square&logo=AmazonAWS&logoColor=white"/>
</p>

---

## 🚀 Key Projects

### 🖥️ screenlog — 화면 기록 기반 개인용 RAG 서비스
**MAIN PROJECT · 기획·설계·구현·평가·배포 100% 단독 수행 (2026.06 – 2026.08)**
* **개요**: 화면 기록을 로컬에서 임베딩까지 처리하고, 서버로는 벡터·리덕션 텍스트만 전송하는 개인용 RAG 에이전트. LangGraph 커스텀 ReAct 에이전트가 도구 화이트리스트 6개로 검색·정리·비교·집계 질의에 답합니다.
* **주요 기술**: LangGraph, FastAPI, SSE Streaming, Docker → GHCR → EC2, Ollama, LoRA
* **핵심 성과**:
  * 검색 recall@8 **0.99** (골든셋 25문항 직접 구축·라벨링, 검색 전략 7종·임베딩 3종 비교 실험)
  * 첫 응답 **5.3초 → 1.4초** (−74%, SSE 스트리밍 + 비동기 전환 + `as_completed` 조기 반환)
  * 색인 대상 글자 수 **−79%** (프레임 단위 → 그룹화·중복 제거·경계 분할 기반 이벤트 단위 재설계)
  * 되돌릴 수 없는 행동을 LLM이 직접 수행한 사례 **0건** (슬랙 전송은 사용자 승인 후에만 호출되는 별도 엔드포인트로 분리)

### 🔤 바닥부터 만든 한국어 LLM (Korean Chatbot)
**SUB PROJECT · PyTorch로, 원리부터 — HuggingFace 없이 토크나이저·모델 직접 구현 (기여도 100%)**
* **개요**: 순수 Python BPE 토크나이저와 Decoder-only Transformer를 처음부터 구현하고, 사전학습 → 파인튜닝 → FastAPI 서빙까지 end-to-end 파이프라인을 직접 구축했습니다.
* **주요 기술**: PyTorch, 자체 구현 BPE / HF ByteLevel BPE, FastAPI
* **핵심 성과**:
  * 약 **52M** 파라미터 Decoder-only Transformer 직접 구현 (d_model 512 / 12층 / 8헤드)
  * 사전학습 15 epoch, validation perplexity **134 → 40** 개선
  * 토크나이저 학습 시간 **5시간 → 수 분** 단축 (증분 pair 카운트, 역인덱스, 인코딩 캐싱)
  * 토크나이저 v1↔v2 통제 비교 실험으로 "ppl은 토크나이저가 다르면 비교 불가"함을 실측 확인

### 🥽 LifeGo — Egocentric XR Lifelogging
**KIST 연구 인턴 · CDE 2025 학회 논문 제1저자 (2025.03 – 2025.08, 3인 공저)**
* **개요**: 안경형 AR 글래스의 1인칭 멀티모달 데이터(공간·음성·환경음·이미지)를 VLM으로 실시간 의미 압축하는 디지털 트윈 라이프로깅 시스템. 브라우저·AR·VR 세 모드로 구현.
* **주요 기술**: SLAM3R, SpatialLM, Whisper, YAMNet, Qwen2.5-VL-7B, WebXR
* **핵심 성과**: 저장 압축률 **102,678:1** (27GB → 506KB), 일상 환경 상황인지 정확도 **89%**, 핵심 서사 mIoU **93%**, 산업 SOP 핵심 절차 검색 정확도 **90%**

### 💆 FaceDx — 안면마비 자동진단·재활 플랫폼
**KIST · 건국대병원 협력 · 모델개발·데이터파이프라인 100% (2025.03 – 진행중)**
* **개요**: MediaPipe 478 landmark 기반 근육별 자동 Grade 산출 → 원격재활 → 자가재활로 이어지는 3단계 로드맵의 안면마비 진단 플랫폼. 한국연구재단 신진연구 국책과제 선정(3년, 2.7억 원) 및 언론 보도.
* **주요 기술**: MediaPipe, Optuna, Soft Voting
* **핵심 성과**: 표정 진단 정확도 **47% → 82.67%** 개선, House-Brackmann 그룹별 검증 정확도 **80~96%**

### 🏆 ILLO — 외국인 근로자 다국어 권리구제 AI 에이전트
**카카오테크 부트캠프 AI 해커톤 · 본선 우수상 (2위 / 23팀)**
* **개요**: 근로계약서 위험을 이해하지 못하는 외국인 근로자가 진정서 작성·제출까지 이어갈 수 있도록 돕는 에이전트. React·Spring Boot·FastAPI 3계층으로 배포.
* **주요 기술**: DeepSeek, Upstage 임베딩, Chroma, LangGraph, Naver Clova OCR
* **기여도**: OCR 100% · 법령 RAG 100% · AI 에이전트 30%

---

## 📐 Core Competencies

* **측정으로 설계한다** — 골든셋 3회 구축(screenlog 25문항 · LLM 12문항 rubric · LifeGo GT 50개 질의). 실측 없이 도입한 기술은 없습니다.
* **실패를 자산으로 남긴다** — 검색 전략 7종 중 6종을 기각·문서화, 프롬프트 분할 3회 시행착오, AI/ML 실패 양상을 웹·클라우드와 대비한 6가지로 정리했습니다.
* **안전 경계를 설계한다** — 되돌릴 수 없는 행동은 승인 게이트 뒤로, 도구 화이트리스트와 재귀 한도로 에이전트 루프에 가드레일을 둡니다.

---

## 📊 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=kkkk2058&show_icons=true&theme=radical&include_all_commits=true" alt="Sehoon's GitHub Stats" />
</p>
<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=kkkk2058&layout=compact&theme=radical" alt="Top Langs" />
</p>

---

## ✉️ Contact & More

* **GitHub**: [github.com/kkkk2058](https://github.com/kkkk2058)
* **Email**: sehoon.dev.kim@gmail.com
* **Hobbies**: 🏸 Badminton | 🏀 Basketball | 🎮 League of Legends (Big Fan of T1!)

"The best way to predict the future is to invent it."
