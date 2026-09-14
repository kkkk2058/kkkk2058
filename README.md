<h1 align="center">Hi, I'm Sehoon Kim 👋</h1>
<p align="center"><b>측정한 근거로 판단하고, 원리부터 검증하는 AI Engineer</b></p>
<p align="center">에이전트·RAG 시스템, 멀티모달 XR 라이프로깅, 의료 AI를 연구·개발합니다.</p>

<p align="center">
  <a href="https://github.com/kkkk2058"><img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=GitHub&logoColor=white"/></a>
  <a href="mailto:sehoon.dev.kim@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=Gmail&logoColor=white"/></a>
</p>

<br>

## 🛠 Tech Stack

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"/>
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=PyTorch&logoColor=white"/>
  <img src="https://img.shields.io/badge/Hugging_Face-FFD21E?style=flat-square&logo=HuggingFace&logoColor=black"/>
  <img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=LangChain&logoColor=white"/>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=FastAPI&logoColor=white"/>
  <img src="https://img.shields.io/badge/WebXR-FF4A5A?style=flat-square&logo=WebXR&logoColor=white"/>
  <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=React&logoColor=black"/>
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=TypeScript&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=Docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/AWS_EC2-232F3E?style=flat-square&logo=AmazonAWS&logoColor=white"/>
</p>

## 🚀 Projects

| | Project | Tech | Result |
|---|---|---|---|
| 🖥️ | **screenlog** — 화면 기록 기반 개인용 RAG 에이전트 (기획~배포 단독 수행) | LangGraph · FastAPI · SSE · Docker | recall@8 `0.99` · 응답속도 `-74%` |
| 🔤 | **Korean LLM from Scratch** — HuggingFace 없이 BPE 토크나이저 + Transformer 직접 구현 | PyTorch | 52M params · val ppl `134→40` |
| 🥽 | **LifeGo** — 1인칭 XR 라이프로깅 (KIST 연구 · CDE 2025 포스터 제1저자) | WebXR · VLM · SLAM3R | 압축률 `102,678:1` · 정확도 `89%` |
| 💆 | **FaceDx** — 안면마비 자동진단·재활 플랫폼 (KIST · 건국대병원 협력) | MediaPipe · Optuna | 진단 정확도 `47%→82.67%` |
| 🏆 | **ILLO** — 외국인 근로자 권리구제 AI 에이전트 (카카오테크 해커톤 2위/23팀) | LangGraph · Chroma · OCR | 본선 우수상 |

<details>
<summary><b>프로젝트 상세 보기</b></summary>
<br>

**🖥️ screenlog** — 화면 기록을 로컬에서 임베딩까지 처리하고 서버로는 벡터만 전송하는 개인용 RAG 에이전트. LangGraph 커스텀 ReAct 에이전트가 도구 화이트리스트 6개로 검색·정리·비교·집계 질의에 답합니다. 골든셋 25문항을 직접 라벨링해 검색 전략 7종·임베딩 3종을 비교했고, SSE 스트리밍 + 비동기 전환으로 첫 응답을 5.3초 → 1.4초로 줄였습니다. 되돌릴 수 없는 행동(슬랙 전송)은 별도 승인 엔드포인트로 분리해 LLM이 직접 수행한 사례가 0건입니다.

**🔤 Korean LLM from Scratch** — 순수 Python BPE 토크나이저와 52M 파라미터 Decoder-only Transformer를 처음부터 구현하고, 사전학습 → 파인튜닝 → FastAPI 서빙까지 end-to-end 파이프라인을 직접 구축했습니다. 토크나이저 v1↔v2 통제 비교 실험으로 "ppl은 토크나이저가 다르면 비교 불가"함을 실측 확인했습니다.

**🥽 LifeGo** — 안경형 AR 글래스의 1인칭 멀티모달 데이터(공간·음성·환경음·이미지)를 VLM으로 실시간 의미 압축하는 디지털 트윈 라이프로깅 시스템. 브라우저·AR·VR 세 모드로 구현했고, 저장 압축률 102,678:1(27GB → 506KB), 핵심 서사 mIoU 93%를 달성했습니다. KIST 연구 인턴 중 CDE 2025 학회에 제1저자로 논문을 게재했습니다.

**💆 FaceDx** — MediaPipe 478 landmark 기반 근육별 자동 Grade 산출 → 원격재활 → 자가재활로 이어지는 3단계 로드맵의 안면마비 진단 플랫폼. 표정 진단 정확도를 47%에서 82.67%로 개선했고, 한국연구재단 신진연구 국책과제(3년, 2.7억 원)에 선정되어 언론 보도되었습니다.

**🏆 ILLO** — 근로계약서 위험을 이해하지 못하는 외국인 근로자가 진정서 작성·제출까지 이어갈 수 있도록 돕는 에이전트. React·Spring Boot·FastAPI 3계층으로 배포했으며 OCR·법령 RAG 파이프라인을 담당했습니다 (카카오테크 부트캠프 AI 해커톤 본선 우수상, 2위/23팀).

</details>

## 📐 How I Work

- **가정을 실측하는** — 유행하는 기술도 내 데이터로 재보고 도입 여부를 결정합니다.
- **기록으로 남기는** — 성공뿐 아니라 실패와 기각한 결론까지 문서로 남깁니다.
- **안전하게 설계하는** — 되돌릴 수 없는 행동은 LLM에게 도구로 주지 않습니다.

<br>

<p align="center"><i>"The best way to predict the future is to invent it."</i></p>
