## AutoGrad & Optimizer

**torch.nn.Module**

- 딥러닝을 구성하는 Layer의 base class
  - Layer: Block이라고 할 수 있는 기본 구조 단위
    - encoder, decoder, nomalization
- Input, Output, Forward, Backward 정의
  - Input, Output은 optional하지만 일반적으로 모두 정의
  - Backward: weights → parameter
- 학습의 대상이 되는 parameter(tensor)정의

**nn.Parameter**

- Tensor 객체의 상속객체
- nn.Module 내에 attribute가 될 때는 required_grad = True로 지정되어 학습대상이 되는 Tensor
- 직접 지정할 일은 적음
  - 대부분의 layer에는 weights값들이 지정되어 있음



**Backward**

- Layer에 있는 Parameter들의 미분을 수행
- Forward의 결과값과(model의 output=예측치) 실제 값 간의 차이(loss)에 대해 미분을 수행
  - 해당 값으로  Parameter업데이트



**Backward from the scratch ** 

- 실제 backward는 Module 단계에서 직접 지정가능
- Module에서 backward와 optimizer오버라이딩
- 사용자가 직접 미분 수식을 써야하는 부담이 있으며 쓸 일이 없으나, 순서에 대한 이해는 필요



