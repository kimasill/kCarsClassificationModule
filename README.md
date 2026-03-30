# kCarsClassificationModule (YOLOv5)

<p align="center">
  <a href="https://github.com/kimasill/kCarsClassificationModule"><img alt="GitHub Repo" src="https://img.shields.io/badge/GitHub-kCarsClassificationModule-181717?style=for-the-badge&logo=github&logoColor=white" /></a>
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" />
  <img alt="YOLOv5" src="https://img.shields.io/badge/YOLOv5-Model-2EA44F?style=for-the-badge" />
</p>

> YOLOv5 기반 국산 차량 분류 프로젝트입니다.  
> 데이터 수집(크롤링)→라벨링→학습→평가까지의 전체 파이프라인을 구성하고, 데이터 구성에 따른 정확도 변화와 모델 선택 과정을 정리했습니다.

## Links

- **Portfolio (PDF/웹)**: `https://kimasill.github.io/`
- **Repo**: `https://github.com/kimasill/kCarsClassificationModule`

---

## kCarClassificationModule

> YOLOv5 🚀 is a family of compound-scaled object detection models trained on the COCO dataset, and includes simple functionality for Test Time Augmentation (TTA), model ensembling, hyperparameter evolution, and export to ONNX, CoreML and TFLite.

> -- YoloV5 official documents <br>
> &nbsp;&nbsp;&nbsp; [Pytorch_YoloV5](https://pytorch.org/hub/ultralytics_yolov5/)
<br/> 

## Overview
차종인식 분류기는 방범, 교통 분석, 자율 주행 등 다양한 분야에 활용될 수 있다.
이를 위해서 AI-HUB 에서 제공하는 KCars 데이터셋을 사용하고, 이미지 데이터 학습에
적합한 물체인식 네트워크 중 R-CNN(Region Convolution Neural Network) 방식의
훈련을 통한 국산 차량 분류기를 생성했다. 
<br/><br/>
부족한 데이터셋을 보완하기 위해 표준라이브러리 selenium을 사용하여 크롤링 한 이미지 데이터셋을 구성하여 사용하였다.
적합한 네트워크를 찾기 위해 물체인식 네트워크를 연구하였고, 이 중 빠른 처리속도 및
높은 정확도를 나타내는 YOLO 모델을 선정하였다. 최근의 YOLO 모델은 여러 버전이
있는데, 가장 적합한 버전을 찾기 위해 버전 별로 성능 테스트를 하였고, 이를 통해
학습하는 전체 과정을 살펴보고, 다양한 형식으로 구성한 이미지 데이터에 따른 정확도를
평가함으로써 최적의 학습 모델을 제시한다.
<br/><br/>
모델을 학습시키기 위해 Imglabel 프로그램을 사용하여 네트워크에 맞는 라벨링 방식인
YOLO 방식의 BBox 라벨링을 하였다. 여러 데이터셋 버전과, 모델에 따라 다른 정확도와
성능을 평가하고, 국산 차량 인식 분류기를 위한 적합한 학습데이터를 제공하고, 효율적인
학습 방안을 제시한다.
<br/><br/>
파일에는 이미 학습된 모델, 코드가 포함 되어있습니다.

## Documentation 
국산차량 분류기에 대한 문서(논문)은[여기](https://drive.google.com/file/d/1yvAup_TsUFzezoIm_G3MFoH2Chk5qVIA/view?usp=sharing) 에서 확인 가능합니다.

## Dataset
사용된 데이터셋의 일부를 공개합니다[Dataset](https://github.com/kimasill/kCarsDataSetLabel).   
데이터셋은 AI-HUB KCar 데이터셋 일부 + 웹 크롤링 이미지 세트를 라벨링 하여 사용했습니다.


