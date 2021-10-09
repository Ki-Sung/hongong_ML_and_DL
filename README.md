# Hongong Machin Learning and Deep Learning chapter 6
## 6-1. 군집 알고리즘  
#### * 책 페이지: "혼자공부하는 머신러닝 + 딥러닝" P286 ~ P302
#### * 참고 코드: "6_1_Clustering_Algorithm.ipynb"
### 과정 
1. 타깃을 모르는 비지도 학습 
2. 과일 사진 데이터 준비하기
3. 픽셀값 분석하기 
4. 평균값과 가까운 사진 고르기
### 정리 및 결론
- 과정 정리 
  - 타깃값이 없을 때 데이터에 있는 패턴을 찾거나 데이터 구조를 파악하는 머신러닝 방식을 비지도 학습이라고 한다.
  - 타깃이 없기 때문에 알고리즘을 직접적으로 가르칠 수가 없다. 대신 알고리즘은 스스로 데이터가 어떻게 구성되어 있는지 분석한다.
  - 대표적인 비지도 학습 문제는 '군집'이다. 군집은 비슷한 샘플끼리 그룹으로 모으는 작업을 말한다. 이 절에서는 사진의 픽섹을 사용해 군집과 비슷한 작업을 수행해 보았다.
  - 하지만 샘플이 어떤 과일인지 미리 알고 있었기 때문에 사과 사진의 평균값을 알 수 있었다. 실제 비지도 학습에서는 타깃이 없는 사진을 사용해야 한다. (다음 절에서 이런 경우 어떻게 샘플 그룹의 평균값을 찾는지 알아본다.) 
