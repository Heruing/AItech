# PyTorch Troubleshooting

- **OOM**
  - Out Of Memory
  - Error backtracking이 작성한 코드가 아닌 곳을 가리킴
    - 발생 원인과 위치를 파악하기 어려움
    - 메모리의 이전 상황의 파악이 어려움

  - Batch Size를 줄이고 GPU clean 후 가동해보기






- **GPUtil**사용하기

  ```python
  #pip install GPUtil
  
  import GPUtil
  GPUtil.showUtilization()
  ```

  - GPU의 상태를 보여주는 모듈
  - Colab은 환경에서 GPU 상태를 보여주기 편함
  - iter마다 메모리가 늘어나는지 확인



- `torch.cuda.empty_cache()` 써보기
  - 사용되지 않은 GPU상 cache를 정리
  - 가용 메모리 확보
  - `del`과 구분 필요하며`reset` 대신 쓰기 좋음
    - `del`을 사용해도 garbage collector가 가동을 해야 메모리 확보 가능
    - `torch.cuda.empty_cache()`를 통해 수행
  - loop 시작 전에 사용하는 것을 권장



- training loop에 tensor로 축적되는 변수 확인
  - tensor로 처리도니 변수는 GPU상 메모리 사용
  - 해당 변수가 loop 내부 연산에 있을 때 GPU에 computational graph를 생성하여 메모리 잠식 발생
  - 1-d tensor 또는 한 번만 사용하는 tensor의 경우 python 기본 객체로 변환하여 처리
    - `.item` 또는 `float()`을 활용하여 python 기본 객체로 변환 등



- ` del` 사용하기
  - python의 메모리 배치 특성상 loop이 끝나도 메모리 차지
  - 필요 없어진 변수는 적절히 삭제



- 가능한 batch 사이즈 실험
  - batch size 1로 실험



- `torch.no_grad()`
  - Inference 시점에서는 torch.no_grad() 구문을 사용



- 기본적으로 주의할 것
  - Colab에서 너무 큰 사이즈의 데이터 실행하지 말 것
    - linear, CNN, LSTM 등
  - CNN의 대부분의 에러는 크기가 맞지 않아 발생
    - torchsummary 등 사이즈 조절
  - tensor의 float precision을 16bit로 줄이기
