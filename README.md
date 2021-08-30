# hongong_ML_and_DL
#### 폴더 소개 및 순서
- [chapter 1 - 나의 첫 머신러닝](https://github.com/Ki-Sung/hongong_ML_and_DL/tree/chap1)
  1) 머신러닝과 딥러닝의 역사와 개념
  2) 첫 번째 머신러닝 **KNeighborsClassifier(k-최근접 이웃 알고리즘)** 소개와 예제

## Chapter 1 Folder
### Market & Machine Learning
- 도미와 빙어의 데이터셋으로 첫 번째 머신러닝 기법인 K-최근접 이웃 알고리즘을 이해하고 사용해보기
#### * 책 페이지: "혼자공부하는 머신러닝 + 딥러닝" P44 ~ P64
### 과정 
- 생선 도미, 빙어 데이터셋 선언 
- 산점도 그래프 구현
- 데이터셋을 합치고(fish_data) 2차원 리스트로 선언, 정답 데이터(fish_target) 만들기 
- sklearn에 있는 **KNeighborsClassifier** 선언
- **fit()** 매서드로 trainig 후 **score()** 매서드로 모델 평가하기 
- **predict()** 매서드를 이용하여 다른 생선 데이터가 도미인지 빙어인지 예측
### 정리 및 결론
- 도미와 빙어 분류 문제해결 과정과 결론
  - 도미와 빙어를 구분하기 위해 첫 번째 머신러닝 프로그램을 만듬
  - 먼저 도미 35마리와 빙어 14마리의 길이와 무게를 측정해서 파이썬 리스트로 만듬
  - 그 다음 도미와 빙어 데이터를 합쳐 리스트의 리스트로 데이터를 준비
  - 사용할 알고리즘은 K-최근접 이웃(KNeighborsClassifier) 알고리즘
  - K-최근접 이웃(KNeighborsClassifier) 알고리즘은 주변의 5개의 데이터를 보고 다수결의 원칙에 따라 데이터를 예측함.
- 결과
  - K-최근접 이웃(KNeighborsClassifier) 알고리즘의 매개변수 기본값 5(n_neighbors=5)를 설정하고 모델을 사용한 결과 도미와 빙어 데이터를 모두 완벽하게 맞혔음 (정확도: 1.0(100%)
