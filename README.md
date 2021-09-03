# Hongong Machin Learning and Deep Learning chapter 3
## 3-1. K-최근접 이웃 회귀
- 지도 학습의 한 종류인 회귀 문제를 이해하고, K-최근접 이웃 알고리즘을 사용해 농어의 무게를 예측하는 회귀 문제 풀어보기
#### * 책 페이지: "혼자공부하는 머신러닝 + 딥러닝" P114 ~ P129
#### * 참고 코드: "3-1_KNeighborsRegressor.ipynb"
### 과정 
-  K-최근접 이웃 회귀 - K-최근접 이웃 분류와 K-최근접 이웃 회귀의 차이
- 결정계수 (R2 score)
- 과대적합 VS 과소적합 비교 
- 과대적합, 과소적합 해결 방법 및 결론 도출
### 정리 및 결론
- 과정 정리 
  - K-최근접 이웃 회귀 모델은 분류와 동일하게 가장 먼저 가까운 K개의 이웃을 찾지만 차이점은 회귀 모델은 샘플의 타깃값을 평균하여 이 샘플의 예측값으로 사용한다는 점이다.
  - 사이킷런은 회귀 모델의 점수로 R2(결정계수)스코어를 반환한다. 이 값은 1에 가까울수록 좋다.
  - 정량적인 편가를 하고 싶다면 사이킷런에서 쟁공하는 MSE(mean_absolute_error, 평균제곱오차)를 사용한다.
  - 모델을 훈련하고 나서 훈련 세트와 테스트 세트에 대한 평가 점수를 구할수 있다. 훈련 세트의 점수와 테스트 세트의 점수 차이가 크면 좋지 않다. 일반적으로 훈련 세트의 점수가 테스트 세트의 점수보다 조금 더 높다.
  - 만약 테스트 세트의 점수가 너무 낮다면 모델이 훈련 세트에 과도하게 맞춰진 것이다. 이를 과대적합 이라고 한다. 반대로 테스트 세트 점수가 너무 높거나 두 점수가 모두 낮으면 이를 과소적합 이라고 한다.
  - 과대적합일 경우 모델을 덜 복잡하게 만들어야 한다. -> K-최근접 이웃일 경우 K값을 늘린다.
  - 과소적합일 경우 모델을 복잡하게 만들어야 한다. -> K-최근접 이웃일 경우 K값을 줄인다.
- 결론
  - 예제 모델을 훈련해보니 테스트 세트 점수가 높고 훈련 세트 점수가 낮은 과소적합 문제가 발생하였다.
  - 모델을 복잡하게 만들기 위해 K값을 3으로 줄여 모델을 다시 훈련 시켰다.
  - 결과 훈련 세트의 R2 스코어가 0.96 -> 0.98로 높아졌고, 테스트 세트 R2 스코어가 0.99 -> 0.97로 낮아져, 과소적합 문제를 해결 하였다.
  - 또한 두 점수차이가 크지 않으므로 이 모델이 또한 과대적합 되지 않은 것으로 보여, 추후 추가될 논어 데이터에도 일반화를 잘할 것이라는 결론이 도출 되었다.
