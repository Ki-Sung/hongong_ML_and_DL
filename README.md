# Hongong Machin Learning and Deep Learning chapter 5
## 5-1. 결정 트리 
#### * 책 페이지: "혼자공부하는 머신러닝 + 딥러닝" P220 ~ P241
#### * 참고 코드: "5-1_decision_tree.ipynb"
### 과정 
- 로지스틱 회귀로 와인 분류하기
  - 설명하기 쉬운 모델과 어려운 모델 
- 결정트리 
  - 불순도
  - 가지치기 
### 정리 및 결론
- 과정 정리 
  - 가을 신상품으로 준비한 캔 와인은 실수로 와인의 종류(레드 와인 / 화이트 와인)가 캔에 인쇄되지 않았다.
  - 알코올 도수, 당도, pH 데이터를 기준으로 화이트 와인을 골라내는 이진 분류 로지스틱 회귀 모델을 훈련 했지만, 다른 사람이 보고서를 이해할 수 없었다.
  - 그래서 결정 트리를 사용해 레드 와인과 화이트 와인을 분류하는 문제를 풀었다.
  - 특성을 더 추가하지 않고도 결정 트리의 성능이 로지스틱 회귀 모델보다 더 좋음을 알 수 있었다. 게다가 결정 트리는 깊이가 너무 깊지 않다면 비교적 설명하기 쉬웠다.
  - 그리고 결정 트리가 어떻게 데이터를 분할하는지 이해하기 위해 불순도 개념과 정보 이득에 대해 알아보았다.
- 결과
  - 머신러닝 모델을 종종 블랙박스와 같다고도 말한다. 실제로 모델의 계수나 절편이 왜 그렇게 학습되었는지 설명하기가 어렵다.
  - 하지만 결정 트리는 비교적 비전문가에게도 설명하기 쉬운 모델을 만들어 낸다.
  - 결정 트리는 여기서 끝이 아니다. 결정 트리는 많은 앙상블 학습 알고리즘의 기반이 된다. (앙상블 학습은 신경망과 함께 가장 높은 성능을 내기 때문에 인기가 높은 알고리즘이다.)  
## 5-2. 교차 검증과 그리드 서치
#### * 책 페이지: "혼자공부하는 머신러닝 + 딥러닝" P242 ~ P262
#### * 참고 코드: "5-2_Cross_Validation_and_Grid_search.ipynb"
### 과정 
- 검증 세트 
- 교차 검증 
  - 분할기를 사용한 교차 검증
- 하이퍼파라미터 튜닝
  - 그리드 서치 
  - 랜덤 서치 
### 정리 및 결론
- 과정 정리 
  - 레드 와인과 화이트 와인을 선별하는 작업의 성능을 끌어올리기 위해 결정 트리의 다양한 하이퍼파라미터를 시도해 봐야 한다. 이런 과정에서 테스트 세트를 사용하면 결국 테스트 세트에 맞춰 모델을 훈련하는 효과를 만들어 낸다.
  - 테스트 세트는 최종 모델을 선택할 때까지 사용하지 않아야 한다. 테스트 세트를 사용하지 않고 모델을 평가하려면 또 다른 세트가 필요하다. 이를 검증 세트라고 부른다.
  - 검증 세트는 훈련 세트 중 일부를 다시 덜어 내어 만든다.
  - 검증 세트가 크지 않다면 어떻게 데이터를 나누었는지에 따라 검증 점수가 들쭉날쭉할 것이다. 훈련한 모델의 선응을 안정적으로 평가하기 위해 검증 세트를 한 번 나누어 모델을 평가하는 것에 그치지 않고, 여러 번 반복할 수 있는데, 이를 교차 검증이라고 한다.
  - 보통 훈련 세트를 5등분 혹은 10등분 한다. 나누어진 한 덩어리를 폴드라고 부르며 한 폴드씩 돌아가면서 검증 세트의 역할을 한다. 따라서 전체적으로 5개 혹은 10개의 모델을 만든다.
  - 교차 검증을 사용한 다양한 하이퍼파라미터를 탐색한다. 머신러닝 라이브러리에서는 클래스와 메서드의 매개변수를 바꾸어 모델을 훈련하고 평가해 보는 작업이다.
  - 이런 과정은 때론 지루하고 반복적이다. 테스트하고 싶은 매개변수 리스트를 만들어 이 과정을 자동화하는 그리드 서치를 사용하면 편리하다.
  - 매개변수 값이 수치형이고 특히 연속적인 실수값이라면 싸이파이의 확률 분포 객체를 전달하여 특성 범위 내에서 지정된 횟수만큼 매개변수 후보 값을 샘플링하여 교차 검증을 시도할 수 있다.
  - 이는 한정된 자원을 최대한 활용하여 효율적으로 하이퍼파라미터 공간을 탐샐할 수 있는 아주 좋은 도구이다.
## 5-3. 트리의 앙상블
#### * 책 페이지: "혼자공부하는 머신러닝 + 딥러닝" P263 ~ P283
#### * 참고 코드: "5-3_Tree_Ensemble.ipynb"
### 과정 
- 정형 데이터와 비졍형 데이터
- 랜덤 포레스트 
- 엑스트라 트리
- 그레이디언트 부스팅
- 히스토그램 기반 그레이디언트 부스팅
### 정리 및 결론
- 과정 정리 
  - 이번 절은 앙상블 학습을 배웠다. 결정 트리 기반의 앙상블 학습은 강력하고 뛰어난 성능을 제공하기 때문에 인기가 아주 높다. 사이킷런에서 제공하는 앙상블 학습 알고리즘 중 랜덤 포레스트, 엑스트라 트리, 그레이디언트 부스팅, 히스토그램 기반 그레이디언트 부스팅을 다루었다.
  - 랜덤 포레스트는 가장 대표적인 앙상블 학습 알고리즘이다. 성능이 좋고 안정적이기 때문에 첫 번째로 시도해 볼 수 있는 앙상블 학습 중 하나이다. 랜덤 포레스트는 결정 트리를 훈련하기 위해 부트스트랩 샘플을 만들고 전체 특성 중 일부를 랜덤하게 선택하여 결정 트리를 만든다.
  - 엑스트라 트리는 랜덤 포레스트와 매우 비슷하지만 부트스트랩 샘플을 사용하지 않고 노드를 분할할 때 최선이 아니라 랜덤하게 분할한다. 이런 특징 때문에 랜덤 포레스트보다 훈련 속도가 빠르지만 보통 더 많은 트리가 필요하다.
  - 그레이디언트 부스팅은 깊이가 얕은 트리를 연속적으로 추가하여 손실 함수를 최소화하는 앙상블 방법이다. 성능이 뛰어나지만 병렬로 훈련할 수 없기 때문에 랜덤 포레스트나 엑스트라 트리보다 훈련 속도가 느리다. 그레이디언트 부스팅에서 학습률 매개변수를 조정하여 모델의 복잡도를 제어할 수 있다. 학습률 매개변수가 크면 복잡하고 훈련 세트에 과대적합된 모델을 얻을 수 있다.
  - 가장 뛰어난 앙상블 학습으로 평가받는 히스토그램 기반 그레이디언트 부스팅 알고리즘은 훈련 데이터를 256개의 구간으로 변환하여 사용하기 때문에 노드 분할 속도가 매우 빠르다. 히스토그램 기반 그레이디언트 부스팅 라이브러리인 XGBoost, LightGBM을 사용할 수 있다.
  - 5절에서는 앙상블 학습과 그리드 서치, 핸덤 서치를 사용한 하이퍼파라미터 튜닝을 사용하면 최고 수준의 성능을 내는 머신러닝 모델을 얻을 수 있음을 배웠다.
  - 여기까지 입력과 타깃이 준비된 문제를 풀어보았다. 이런 머신러닝 분야를 지도 학습(supervised learning)이라고 부른다. 
