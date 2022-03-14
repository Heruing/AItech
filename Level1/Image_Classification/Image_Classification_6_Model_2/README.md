# 6. Model 2

Computer Vision의 발전

- ImageNet
  - CV의 역사적 분기점
  - 1400만 장의 이미지와 2만개의 카테고리를 가진 대용량 데이터 셋





**Pretrained Model**

매번 수 많은 이미지를 학습시키는 것은 비효율적

- `torchvision.models`
  - 기존에 학습된 모델 다운로드 가능
  - `pretrained=True`
    - pretrained weight 다운로드 가능



**Transfer Learning**

- CNN base Model
  - Input + CNN Backbone + Classifier → Output
    - `fc` == fully connected layer == classifier



**! 사용할 모델과 내 문제의 유사성을 고려**

- 학습 데이터가 충분한 경우
  - 유사도가 높을 경우
    - Backbone을 Freeze하고 Classifier만 Trainable한 상태에서 Train
  - 유사도가 낮을 경우
    - Backbone과 Classifier 모두 Trainable하게 학습
- 학습 데이터가 충분하지 않은 경우
  - 유사도가 높을 경우 사용
  - 상관 관계가 낮을 경우 사용 불가능
