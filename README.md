# Kaggle_Competition
 I joined Kaggle competition and studied the data analysis methods. I write the code for the implementation.

## 1. Kaggle_Titanic (2020.05.23)  
- Data (csv files)   [Click](https://github.com/youngbinwoo/Kaggle_Competition/tree/master/Kaggle_Titanic/Data)  
 : Train  
 : Test  
 : gender_submission

- Method   [Code](https://github.com/youngbinwoo/Kaggle_Competition/tree/master/Kaggle_Titanic/Code)    
 : Exploratory Data Analysis   
 : K-Nearest Neighbor 

- Result (csv files)    [Click](https://github.com/youngbinwoo/Kaggle_Competition/tree/master/Kaggle_Titanic/Result) 

## 2. Kaggle_Boston: 1970년대 BOSTON 어느 집을 사는 것이 현명할까? (2020.07.14)     
### 1) 시대적 상황 
- 보스턴은 경제에 중요한 관광 산업 도시이다.   
- 1970년이 되어서 보스턴 지역은 경기 침체와 구조 변화를 겪었다.  
- 하버드 대학 등 유명 대학이 있고, 최초의 공립 학교가 설립되는 등 교육 도시이다.   
- 보스턴 지역은 미국에서 가장 높은 생계비를 요구하는 도시이며 고급 주택이 많은 지역이다.   
- 1970년대 미국은 집 값이 폭등했다.   
- 보스턴 시의 가장 심각한 문제는 도심의 교통체증이였다. 

### 2) 분석하고자 하는 방향
EDA를 통해 각 변수에 대한 인사이트를 얻은 후, 각 모델링으로 높은 중요도를 가지는 변수를 택한다. 이를 통해1970년대 보스턴에서 집을 구매할 때, 가장 중요하게 고려해야하는 요소와 가장 좋은 집을 택한다.   

### 3) 변수에 대한 가정   
- 범죄율: 범죄율이 낮을수록 집 값이 높아질까?  
- 주거지 비율: 주거지 비율이 높을수록 집 값이 높을까?  
- 비소매업 비율: 비소매업 비율이 낮을수록 집 값이 높을까?  
- 조망권: 조망권이 집 값이 높을까?  
- 산화질소: 산화질소 농도는 집 값과 관련이 없을 것 같은데 진짜일까?   
산화질소 농도를 매번 체크하고 민감하게 반응하는 사람은 흔하지 않기 때문에 관련이 없을 것이라는 추측을 한다.     
- 주거당 평균 객실 수 : 주거당 평균 객실 수가 많을수록 집 값이 높을까?  
- 노후 건물 비율: 노후건물 비율이 낮을수록 집 값이 높을 것이라 예상된다.  
- 중심지 접근거리: 중심지 접근거리가 가까울수록 집 값이 높을까? 회사가 집에서 가까운 것이 최고이기때문에 높을 것이라 예상한다.   
- 고속도록 접근 편이성 지수: 고속도로 접근 편이성 지수가 낮을수록 집 값이 낮을까? 고속도록 접근 편이성이 높으면 매연 등 좋지 않은 공기와 소음이 발생하기 때문에 집 값이 낮을것이라고 예상된다.   
- 재산세율: 재산세율이 높을수록 집 값이 높을까? 집 값이 비싸야 세금이 높아지기 때문이다.  
- 학생당 교수비율: 학생당 교수 비율은 영향이 없을 것 같다.   
- 흑인 인구 비율: 흑인 인구 비율이 낮을수록 집 값이 높을까? 흑인이 많은 곳은 할렘가 같은 곳이 연상되기때문에 낮을 것 같다.  
- 저소득층 비율: 저소득증 비율이 낮을수록 집 값이 높을까?  
  
  
### 4) Getting Started 
#### 4-1) Data (csv files)    [Click](https://github.com/youngbinwoo/Kaggle_Competition/tree/master/Kaggle_Boston/Data)   
  : BOSTON_HOUSING

#### 4-2) Exploratory Data Analysis(EDA)   [Code](https://github.com/youngbinwoo/Kaggle_Competition/tree/master/Kaggle_Boston/EDA)  
- 평균 검정과 Box plot을 통해 범죄율이 낮은 지역의 주택 가격 평균이 높다는 것을 알 수 있다.    
- 주거지 비율이 높은 지역일수록 주택 가격이 높은 것을 알 수 있다.    
- 비소매율이 낮은 지역이 주택 가격이 높다는 것을 예상할 수 있다.   
- 조망권과 비조망권의 차이가 유의미한다고 나왔지만 데이터셋 자체의 비조망권의 개수는 471개로 무수히 많고, 조망권의 개수는 35개 적다. 불균형한 데이터셋이라고 판단하여 결과는 믿을 수 없다는 결론을 냈다.    
- 산화질소 농도가 낮을수록 집값이 높다는 것을 알 수 있다.  
- 주거당 평균 객실 수가 많을수록  집 값이 높다는 것을 알 수 있다.  
- 노후 건물 비율이 낮을수록 집단의 주택가격 평균이 높다.  
- 중심지 거리가 멀수록 주택가격 평균이 높다.  
- 고속도로 접근성이 낮을수록 주택가격 평균이 높다.  
- 재산세율이 높을수록 주택 가격 평균이 낮다. 결과가 유의미한다고 나왔지만, 데이터셋에 600 이상은 약 150개로 적고 미만은 350개로 많다. 불균형한 데이터셋이라고 판단하기 위해서는 더 확연한 차이가 나야한다. 
- 학생당 교수 비율이 작을수록 집 값이 높다는 것을 예상할 수 있다. 상식적으로는 학생당 교수 비율이 높아야 좋은 학군이고, 집값이 높을 것이라 예측되는데 다시 생각해보니 좋은 학교일수록 학생수가 무수히 많다. 그러므로 학생당 교수 비율이 적을수록 집 값이 높다는 인사이트를 얻었다.    
- 흑인이 많은 집단의 집 값이 더 비싸다는 편견을 깨는 인사이트를 얻었다.   
- 저소득층 비율이 낮을수록 집 값이 더 비싸다는 인사이트를 얻었다.  

#### 4-3) Modeling Method    [Code](https://github.com/youngbinwoo/Kaggle_Competition/tree/master/Kaggle_Boston/Modeling)    
 : Multiple Linear Regression
- p 값이 0.05이상인 INDUS, AGE을 제거했으나 더빈왓슨이 1.011이기 때문에 잔차들은 양의  상관관계가 있다고 할 수 있다.  
- 상관분석에서 값이 낮게 나온 변수인 "ZN"(0.36),"DIS"(0.25),"CRIM"(-0.388),"NOX"(-0.427),"INDUS"(-0.484)를 제거하고 다시 생각해본다.  
- "ZN"(0.36),"DIS"(0.25),"CRIM"(-0.388),"NOX"(-0.427),"INDUS"(-0.484)를 제거하여도 수정된R-squaired 값은 늘어나지 않고, 줄어든다.  
- 가장 R-squaired가 가장 크도록 하는 변수는 CRIM, ZN, NOX, RM, DIS, RAD, TAX, PTRATIO, B, LSTAT이다.  
- 하지만, Durbin-Watson 값이 1.011이기 때문에 잔차가 독립적이지 않고, Prob(JB) 0.05 보다 작으므로 잔차의 정규성이 성립하지 않는다.  
- 변수를 줄이거나 제거하거나 scaling을 해도 잔차의 독립성, 정규성, 등분산성이 성립하지 않는다.    
- 변수 설명력 순서 : NOX > RM > DIS > PTRATIO > LSTAT > RAD       

 : Decision Tree    
 - max_depth=6, min_samples_leaf=1, min_samples_split=14일 때, 정확도 83.2%     
 - 변수의 중요도 순서 : LSTAT -> RM -> DIS   
 
 : Random Forest   
 - min_samples_leaf=1,max_depth=10, min_samples_split=4일 때, 정확도 89.8%      
 - 변수의 중요도 순서 : LSTAT -> RM -> DIS     
 
 : GrandientBoosting     
 - min_samples_leaf=2,max_depth=6, learning_rate=0.1일 때, 정확도 90%  
 - 변수의 중요도 순서 : LSTAT -> RM -> DIS   
  
#### 4-4) Model evaluation    [Code](https://github.com/youngbinwoo/Kaggle_Competition/tree/master/Kaggle_Boston/Model%20evaluation)
: 오차가 가장 작은 순서 (그레디언트부스팅 -> 랜덤 포레스트 -> 의사결정나무 -> 회귀분석)

#### 4-5) Reprot (pdf files)  [Click](https://github.com/youngbinwoo/Kaggle_Competition/blob/master/Kaggle_Boston/Boston%20Report.pdf)   

