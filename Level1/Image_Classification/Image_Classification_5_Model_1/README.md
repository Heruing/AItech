# 5. Model 1

**모델이 무엇이란?**

- 정보의 표현
  - object, person or **system**





**PyTorch**

- `torch.nn.Module`
- low-level, Pythonic, Flexibility
- 코드를 해석하는 과정이 어떻게 학습되는지 이해하는 과정



**nn.Module**

- PyTorch 모델의 모든 레이어는 `nn.Module` 클래스를 따름
- modules
  - `__init__`에서 정의한 또 다른 `nn.Module`



**Parameters**

- `.state_dict()`
  - parameter 호출
- `data`, `grad`, `requires_grad` 변수 등을 가짐
