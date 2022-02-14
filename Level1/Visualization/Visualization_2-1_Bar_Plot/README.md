## Bar Plot 사용하기

#### 1. 기본 Bar Plot

1. Bar plot이란?
   - 직사각형 막대를 사용하여 데이터 값을 표현한 차트/그래프
   - 범주에 따른 수치 값을 비교하기 적합한 방법
     - 개별 비교, 그룹 비교 모두 적합
   - 방향에 따른 분류(`.bar()`, `.barh()`)
     - 수직(vertical): x축에 범주, y축에 값을 표기(default)
     - 수평(horizontal): y축에 범주, x축에 값을 표기하는 범주가 많을 때 적합한 방법



#### 2. 다양한 Bar Plot

그룹이 5개 ~ 7개 이하일 때 효과적으로, 그룹이 많다면 적은 그룹은 ETC로 처리하는 것이 나음

1. Multiple Bar Plot

   - Bar Plot에서는 범주에 대한 각 값을 표현
     - 즉, 1개의 feature에 대해서만 표시
   - 여러 Group을 보여주기 위해서는 여러 방법 필요

   1. 플롯을 여러 개 그리는 방법
   2. 한 개의 플롯에 동시에 나타내는 방법
      1. 쌓아서 표현하기
      2. 겹쳐서 표현하기
      3. 이웃에 배치해서 표현하기

2. Stacked Bar Plot

   - 2개 이상의 그룹을 쌓아서 표현하는 Bar Plot
     - 각 bar에서 나타나는 그룹의 순서는 항상 유지
     - 맨 밑의 bar 분포 외에는 파악하기 어려움
     - annotation 등을 통해 명확하게 표시하는 것을 추천
   - Percentage Stacked Bar Chart
     - 전체에서 비율을 나타내는 차트

3. Overlapped Bar Plot

   - 3개 이상에서는 파악이 어려움
   - 비교가 쉬우며 투명도를 조정하여 겹치는 부분 파악(`alpha`)
   - Bar plot보다는 Area plot에서 더 효과적

4. Groupted Bar Plot

   - 그룹별 범주에 따른 bar를 이웃되게 배치하는 방법
   - Matplotlib으로는 비교적 구현이 까다로움
     - `set_xticks()`, `.set_xticklabels()`





#### 3. 정확한 Bar Plot

1. principle of Proportion Ink
   - 잉크양 보존 법칙: 실제 값과 그에 표현되는 그래픽으로 표현되는 잉크 양은 비례해야 함
   - 항상 x축의 시작은 0
     - 차이를 나타내고 싶다면 plot의 세로 비율을 늘릴 것
   - 다수의 시각화에서 적용되는 원칙
2. 데이터 정렬하기
   - 더 정확한 정보를 전달하기 위함
     - Pandas: `sort_values()`, `sort_index()`를 사용해 정렬
   - 데이터 종류에 따른 정렬
     - 시계열: 시간순
     - 수치형: 크기순
     - 순서형: 범주의 순서
     - 명목형: 범주의 값에 따라 정렬
   - 여러 기준으로 정렬하여 패턴 발견
   - 대시보드에서는 Interactive로 제공하는 것이 유용
3. 적절한 공간 활용
   - 여백과 공간 조정
   - X/Y axis Limit
     - `.set_xlim()`, `.set_ylim()`
   - Spines
     - `.spines[spine].set_visible()`
   - Gap
     - `width`
   - Margin
     - `margin`
4. 복잡함과 단순함
   - 필요없는 복잡함은 제거
     - 특히 데이터 분석에 있어서 무의미한 3D와 직사각형이 아닌 다른 형태의 bar는 지양
   - 목적과 독자에 따라 표시할 정보를 결정
5. 기타
   - 오차 막대를 추가하여 Uncertainty 정보를 추가
     - `errorbar`
   - 히스토그램
     - Bar 사이 Gap이 0
     - `.hist()`
     - 연속된 느낌을 줄 수 있음





**실습**

- head보다는 sample로 요소들을 보는 것을 추천

- `info()`를 통해 null 값이 있는지 Data type은 무엇인 지 확인하는 것이 좋음
- `matplotlib`는 비율을 맞춰주기 때문에, 비슷해보이는 그래프도 scale이 다를 수 있음
  - `sharey=True` 또는 `set_ylim()`을 통해 y축을 같게 하여 비교
- Stacked Bar Plot
  - `bar(bottom=group['group'])`옵션으로 밑을 지정한 group만큼 공간을 둠
- total 개수로 나누는 비율 그래프
- grouped bar plot
  - 하나는 1/2두께만큼 앞으로, 하나는 1/2큼 뒤로 밀려남
  - width와 여백 조절
  - label + legend로 색에 대한 설명
