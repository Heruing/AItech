## Image Classification 1

#### 1. Course Overview

1. Why is visual perception important?
   - AI
     - 사고하고 인과관계를 분석하는 것과 함께 **시각**, 음성 등을 이해하는 것을 포함
   - AI의 Reference는 "인간"
     - 지각능력의 획득이 매우 중요
   - 지각 능력
     - 입력과 출력
     - 상호작용
     - multi-modal association
   - 시각 정보가 가장 큰 영향을 끼침
2. What is computer vision?
   - `Visual World` - `Sensing device` - `Interpreting device` - `Interpretation`
   - CV는 사람의 시각 인지에 대한 이해와 이를 적용하는 것 까지 포함
   - 인간에게서 보이는 불완전한 인지에 대한 이해도 중요
   - 고전 Machine Learning에서 Feature extraction과 Classification을 직접 하던 것이
     Deep Learning으로 넘어오며 자동화 됨
3. What you will learn in this course
   - 간단한 기술부터 trend에 맞는 방향의 기술
   - Multi-modal learning



#### 2.  Image classification

1. What is classification?
   - Classifier
     - mapping
2. An ideal approach for image recognition
   - 모든 대상이 정보에 들어있을 때
     - k-NN(k Nearest Neighbors)
     - query정보가 들어왔을 때 주변 정보를 불러와 유사도가 높은 label로 반환
     - 데이터가 많아질수록 필요한 시간과 메모리 등 시스템 복잡도가 커짐
     - 모든 데이터를 가지고 있는 것도 어려움
     - 영상 간의 유사도에 대한 정의가 필요
     - 현실적으로 사용되는 neural network들은 데이터를 추출해 적용시키는 것
3. Convolutional Neural Networks (CNN)
   - Single Layer, Fully Connected Layer
     - 데이터 변형에 취약하고 출력 변환이 어려움
   - Locally Connected Neural Networks
   - Local feature learning
   - parameter sharing
   - 다양한 CV task에서 backbone network로 사용



#### 3. CNN architectures for image classification 1

1. History
2. AlexNet
   - 기존 2개만 사용되던 Conv layer가 5개로 증가
   - 개발 당시에는 GPU 메모리가 충분하지 않아 2개의 GPU를 사용하였음
   - `MaxPool`에서 `Linear`(tensor → vector)
     - `flatten`
     - Average Pooling: `AvgPool`
     - 두 방법은 Dimension 차이
   - LRN(Local Response Normalization)은 부분적으로 명암을 조절함
     - 요즘은 Batch normalization으로 대치됨
   - 큰 filter size도 요즘은 쓰이지 않음
     - 당시에는 11x11 filter를 사용
   - Receptive field
     - activation에서 한 element가 출력됐을 때 의존성 있는 입력 pixel의 영역
     - dependency가 있는 영역
     - input layer 수준까지 내려감
     - pooling layer size, kernel size
3. VGGNet 
   - 깊은 구조
     - 16, 19 layer
     - 3x3, 2x2 pooling
   - 높은 성능을 가지고 있으면서 일반화가 잘 됨
   - 기본적으로 AlexNet 구조를 유지함
     - 224 x 224 image input
     - 평균 RGB값을 추출함
   - 작은 kernel size
     - 깊이가 깊어지면 큰 receptive field사이즈를 얻을 수 있음
     - parameter 수가 줄어듦
   - 3 fully-connected layers
