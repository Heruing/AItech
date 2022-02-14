## Polar Coordinate

#### 1. Polar Plot

1. Polar Plot
   - 극 좌표계를 사용
   - 회전, 주기성을 표현하기 적함
   - `projection = plar`를 추가하여 사용
2. Data Converting
   - 직교 좌표계 X, Y에서 변환 가능
     - X = Rcosθ
     - Y = Rsinθ

#### 2. Radar Plot

1. Radar Plot
   - 별 모양으로 생겨 Star Plot으로도 불림
   - 중심점을 기준으로 N개의 변수 값을 표현
   - 데이터의 Quality를 표현하기 좋음
     - 포켓몬 status
2. Radar Plot 주의점
   - 각 feature는 독립적이며 척도가 같아야 함
   - feature 순서에 따라 면적이 달라지므로 크게 중요하지 않음
   - feature가 많아질수록 가독성이 많이 떨어짐

**실습**

- 기본적으로 360˚ 원형
  - 반지름 `r`값을 max로 가지며 시작점을 바꿔도 도넛형이 아님
  - `set_rlabel_position`: 반지름 label이 적히는 위치 각도 조정
  - 부채꼴로 그리기
    - `set_thetamin()`, `set_thetamax()`
    - 표시할 각도 지정
  - Ploar Plot에서는 Bar Chart도 중심점에서 바깥쪽으로 넓어지는 형태이므로 면적 비교가 어려움
  - 
