## PyTorch Basic

**Tensor**

- 다차원 Arrays를 표현하는 PyTorch 클래스
- 사실상 numpy의 ndarray와 동일
  - TensorFlow의 Tensor와도 동일
- Tensor를 생성하는 함수도 거의 동일

```python
numpy - ndarray
import numpy as np
n_array = np.arange(10).reshape(2,5)
print(n_array)
print("ndim :", n_array.ndim, "shape :", n_array.shape)
```



```python
# pytorch - tensor
import torch
t_array = torch.FloatTensor(n_array)
print(t_array)
print("ndim :", t_array.ndim, "shape :", t_array.shape)
```

