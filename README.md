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
## 3-2. 선형 회귀
- K-최근접 이웃 회귀와 선형 회귀 알고리즘의 차이를 이해하고 사이킷런을 사용해 여러 가지 선형 회귀 모델을 만들어 보기
#### * 책 페이지: "혼자공부하는 머신러닝 + 딥러닝" P130 ~ P149
#### * 참고 코드: "3-2_LinearRegression.ipynb"
### 과정 
- K-최근접 이웃의 한계
- 선형 회귀 개념
- 다항 회귀 개념
### 정리 및 결론 
- 과정 정리 
  - K-최근접 이웃 회귀를 사용해서 농어의 무게를 예측했을 때 발생하는 큰 문제는 훈련 세트 범위 밖의 샘플을 예측할 수 없다는 점이다. (아무리 멀리 떨어져 있더라도 가장 가까운 샘플 타깃을 평균하여 예측함)
  - 이 문제를 해결하기 위해 사용하는 모델이 바로 선형 회귀이다. 선형 회귀는 훈련 세트에 잘 맞는 직선의 방정식을 찾는 것이다. (사이킷런의 LinearRegresison 클래스를 사용)
  - 가장 잘 맞는 직선의 방정식을 찾는다는 것은 최적의 기울기와 절편을 구한다는 의미이다. 이 값들은 선형 회귀 모델의 coef, intercept 속성에 저장되어 있다.
  - 단순 선형 회귀로 예측한 결과, K-근접 이웃 회귀와 다르게 훈련 세트를 벗어난 범위의 데이터도 잘 예측했다. 하지만 모델이 단순하여 농어의 무게가 음수일 수도 있다라는 문제가 발생하였다. 이 문제를 해결하기 위해 다항 회귀를 사용하였다.
  - 간단히 농어의 길이를 제곱하여 훈련 세트에 추가한 다음, 선형 회귀 모델을 다시 훈련 시킴, 이 모델은 2차 방정식의 그래프 형태를 학습하였고, 훈련 세트가 분포된 형태를 잘 표현하였다.
- 결론
  - 첫 번째 단순 선형 회귀 모델을 훈련한 뒤 R2 스코어로 모델을 평가 한 결과, 훈련 세트: 0.94, 테스트 세트: 0.82로 나왔으며 훈련 세트의 점수가 높아 과대 적합 처럼 보였지만 과소적합이라고 판단 되었다.
  - 두 번째 2차 방정식을 이용한 다항 회귀 모델로 다시 훈련한 뒤 R2 스코어로 모델을 평가 한 결과, 훈련 세트: 0.9706, 테스트 세트: 0.9776으로 두 데이터가 비슷한 결과가 나왔지만 테스트 세트의 점수가 높아 여전히 과소 적합 문제가 발생한 것으로 판단 되었다. 
## 3-3. 특성 공학과 규제 
- 여러 특성을 사용한 다중 회귀에 대해 배우고 사이킷런의 여러 도구를 사용해 본다.
- 복잡한 모델의 과대적합을 막기 위한 릿지와 라쏘 회귀를 배운다.
#### * 책 페이지: "혼자공부하는 머신러닝 + 딥러닝" P150 ~ P173
#### * 참고 코드: "3-3_Feature_Engineering_and_Regularization.ipynb"
### 과정
- 다중 회귀 개념
- 판다스 데이터 프레임으로 데이터 준비 
- 사이킷런 변환기 사용
- 다중회귀 모델 훈련하기 
- 규제 사용 
- 릿지 회귀 
- 리쏘 회귀
### 정리 및 결론 
- 과정 정리 
  - 이번 문제해결 과정은 모델의 과대적합을 제어하는 것이었다.
  - 선형 회귀 알고리즘을 사용해 농어의 무게를 예측하는 모델을 훈련시켰지만 훈련 세트에 과소적합되는 문제가 발생하였다. 이를 위해 농어의 길이 뿐 아니라 높이와 두께도 사용하여 다중 회귀 모델을 훈련 시킴.
  - 또한 다항 특성을 많이 추가하여 훈련 세트에서 거의 완벽에 가까운 점수를 얻는 모델을 훈련했다.
  - 특성을 많이 추가하면 선형 회쉬는 매우 강력한 성능을 낸다. 하지만 특성이 너무 많으면 선형 회귀 모델을 제약하기 위한 도구가 필요하다.
  - 이를 위해 릿지 회귀와 라쏘 회귀 모델을 각각 훈련하고 평가를 해보았다.
  - 또 릿지와 라쏘 모델의 규제 양을 조절하기 위해 최적의 alpha 값을 찾는 방법을 배웠다. 
- 결론
  -  다중 회귀를 알고리즘을 사용하기 위해 PloynomialFeatures 클래스를 사용하여 훈련, 평가를 한 결과 훈련 세트 점수 0.99로 좋은 점수가 나왔지만 테스트 세트 점수가 -144로 형편없는 점수가 나왔다.
  - 특성이 많이 추가되어 과대 적합이 난 것으로 판단하여 규제하기 위해 릿지와 라쏘 모델을 사용하기로 한다.
  - 릿지 모델로 최적을 alpha값을 찾은 결과 -1, 즉 0.1이 나왔고, 해당 alpha 값을 지정하여 훈련, 평가를 한 결과 훈련 세트 0.99, 테스트 세트 0.98로 점수가 비슷하게 모두 높고, 과대적합과 과소적합 사이에 균형을 맞추고 있다.
  - 라쏘 모델도 똑같이 최적의 alpha 값을 찾은 결과 1, 즉 10이 나왔고, 해당 alpha 값을 지정하여 훈련, 평가를 한 결과 훈련 세트 0.98, 테스트 세트 0.98로 점수가 비슷하여, 훈련이 모두 잘되는 결과를 도출하였다.
  - 라쏘 모델의 경우 계수의 값을 아예 0으로 만들 수 있어, 계수가 coef_속성에 저장된 0의 수를 모두 나타낸 결과 55개의 특성 모델 중 라쏘 모델이 사용한 특성은 15개 밖에 되지 않았다. 이런 특징 때문에 라쏘 모델은 유용한 특성을 골라내는 용도로 사용할 수 있다는 결과가 도출 되었다.
