# 6. Computer Vision Applications

- **Semantic Segmentation**
  - 이미지의 모든 속성에 대해 분리하여 구분하는 기법
  - 자율주행에 많은 활용
- Fully Convolutional Network
  - flat, dense → convolution
  - input image에 상관없이 수행 가능
    - shared parameter
  - output dimension이 줄어드는 한계가 있음
- Deconvolution (conv transpose)
  - convolution 역연산
  - 실제로 복원할 수는는 없음 

**Detection**

- R-CNN
  - input image 선택
  - 2000 region extract
  - AlexNet
  - Classify
  - 이미지 처리 속도가 매우 느림
- SPPNet
  - CNN을 한 번만 돌리도록
  - 결국 bounding box를 분리하는 과정이 오래 걸림
- Fast R-CNN
  - 미리 bounding box를 선정
  - CNN
  - 각 region에 대해 ROI pooling
  - class와 bounding box regressor
- Faster R-CNN
  - image에서 bounding box를 뽑아내는 방법도 Network로 학습
    - Region Proposal Network
    - image에서 특정 영역에 물체의 유무에 대한 판단 능력 학습
  - Fully Conv
- YOLO
  - image를 SxS grid로 나누고 B개의 bounding box
  - box마다 C개의 classes
