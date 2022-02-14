# 모델 불러오기

- **model.save()**
  - 학습의 결과를 저장하는 함수
  - 모델 형태(architecture)와 Parameter를 저장
  - 모델 학습 중간과정의 저장을 통해 최선의 결과 모델을 선택
  - 만들어진 모델 공유를 통해 재연성 향상



- **checkpoints**
  - 학습의 중간 결과를 저장하여 최선의 결과를 선택
  - earlystopping 기법 사용시 이전 학습의 결과물 저장
  - loss와 metric값을 지속적으로 확인 저장
    - 일반적으로 epoch, loss, metric을 함께 저장하여 확인
  - colab에서 지속적인 학습을 위해 필요



- **Transfer learning**
  - 다른 데이터셋으로 만든 모델을 현재 데이터에 적용
    - 대용량 데이터셋으로 만들어진 모델의 성능이 높음
    - DL에서 현재 일반적인 학습기법
  - backbone architecture가 잘 학습된 모델에서 일부분만 변경하여 학습 수행



- **Freezing**
  - pretrained model을 활용시 모델의 일부분을 frozen  시킴
    - 특정 위치까지만 Back-propagation만 일어나게 하는 등의 작업
