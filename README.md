# kCarsClassificationModule — 국산 차량 연식·차종 인식 (YOLOv5)

<p align="center">
  <a href="https://github.com/kimasill/kCarsClassificationModule"><img alt="GitHub Repo" src="https://img.shields.io/badge/GitHub-kCarsClassificationModule-181717?style=for-the-badge&logo=github&logoColor=white" /></a>
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" />
  <img alt="YOLOv5" src="https://img.shields.io/badge/YOLOv5-Object%20Detection-2EA44F?style=for-the-badge" />
</p>

<p align="center">
  <img src="https://kimasill.github.io/images/Classification/classification_title.png" alt="훈련 배치 시각화" width="720" />
</p>

> **YOLOv5** 기반으로 국산 차량 **74종**(연식·모델)을 구분하는 객체 인식·분류 파이프라인을 담은 레포지토리입니다. 데이터 수집·전처리·학습·평가 과정과 인사이트는 [프로젝트 페이지](https://kimasill.github.io/projects/car-classification.html)에서 서술하고, 본 README는 **레포 목적·핵심 수치·문서·데이터 링크** 위주로 정리합니다.

---

## 한눈에 보기

| 항목 | 내용 |
| --- | --- |
| 기간 | 2021.12 |
| 역할 | 1인 — 데이터 수집·전처리·모델 설계·학습·평가 |
| 프레임워크 | PyTorch · YOLOv5 (s → x) |
| 도구 | Python · Selenium · AutoCrawler · LabelImg · TensorBoard |

---

## 목표 (요약)

- 국산 차량 연식·모델 단위 **데이터셋 구축**
- 객체 인식 기반 **차량 분류 모델** 설계·학습
- 크롤링·**증강 전략**으로 도메인 다양성 확대
- 데이터셋·모델 조합 **실험으로 최적안 탐색**

---

## 핵심 수치 (요약)

| 항목 | 내용 |
| --- | --- |
| 클래스 | 국산 차량 **74종** (연식·모델) |
| 데이터 규모 (확장 후) | AI-HUB 약 14,000장 + 웹 크롤링 약 21,000장 → **합계 약 35,000장** |
| 정확도 변화 (실험 요약) | 초기 **약 60.91%** → 데이터·증강 개선 후 **약 93.88%** (상세는 논문·웹) |

---

## 문서·데이터 링크

| 구분 | URL |
| --- | --- |
| 논문 (PDF) | [Google Drive](https://drive.google.com/file/d/1yvAup_TsUFzezoIm_G3MFoH2Chk5qVIA/view?usp=sharing) |
| 라벨·데이터셋 일부 | [kCarsDataSetLabel](https://github.com/kimasill/kCarsDataSetLabel) |
| AI-HUB K-Cars (참고) | [데이터셋 페이지](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&dataSetSn=554&topMenu=100) |
| 포트폴리오 (과정·인사이트) | [car-classification.html](https://kimasill.github.io/projects/car-classification.html) |

---

## 레포지토리 구성 (역할)

- 학습 스크립트·설정, 실험 로그 재현에 필요한 코드
- 사전 학습 가중치·결과물이 포함된 경우 상위 폴더 README 또는 릴리스 안내 참고

> 세부 실험 과정(데이터 편향, 증강 선택, 유사 연식 혼동 사례 등)은 웹 페이지와 논문에 두고, 여기서는 **무엇을 목표로 어떤 스택으로 재현 가능한지**만 빠르게 파악할 수 있게 했습니다.

---

## 스크린샷 (요약)

<p align="center">
  <img src="https://kimasill.github.io/images/Classification/carImg.png" alt="말리부 2015 vs 2018" width="480" />
</p>

<p align="center">
  <img src="https://kimasill.github.io/images/Classification/Train2/car_yolov5s_results_502/val_batch0_pred.jpg" alt="검증 예측" width="320" />
  <img src="https://kimasill.github.io/images/Classification/Train2/car_yolov5s_results_502/confusion_matrix.png" alt="Confusion Matrix" width="320" />
</p>

<p align="center">
  <img src="https://kimasill.github.io/images/Classification/%EB%AA%A8%EB%8D%B8%EC%A7%80%ED%91%9C.png" alt="모델 지표" width="560" />
</p>

---

## Getting Started

1. Python·PyTorch·YOLOv5 학습 환경을 준비합니다.
2. `requirements` 또는 레포 내 의존성 안내가 있으면 설치합니다.
3. [kCarsDataSetLabel](https://github.com/kimasill/kCarsDataSetLabel) 등과 경로를 맞춘 뒤 학습 스크립트를 실행합니다.

> 공개 데이터 라이선스·크롤링 이미지 사용 범위는 각 출처 정책을 따릅니다.

---

## 참고 (YOLOv5)

> YOLOv5는 COCO 등으로 학습된 객체 검출 모델 계열로, TTA·앙상블·하이퍼파라미터 탐색·ONNX 등 내보내기 기능을 제공합니다. — [PyTorch Hub · YOLOv5](https://pytorch.org/hub/ultralytics_yolov5/)
