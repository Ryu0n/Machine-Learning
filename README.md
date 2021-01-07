# Machine-Learning

## 2021-01-04
### 머신러닝이란?
한국말 그대로 해석하면 기계학습, 즉 기계에게 인간의 판단을 위임해주는 것이다.  

인간은 '수'라는 체계를 통해 세상을 표현했다. 이것은 '통계'이다. 그리고 통계를 바탕으로 컴퓨터에게 자잘한 계산을 맡기면서 인간은 본질적인 판단에 집중을 할 수 있게 되었다. 하지만 인간의 욕심은 끝이 없어 **판단** 마저도 기계에게 맡기려 한다. 이것이 '*머신러닝*'이다. 

습관을 머신러닝을 통해 고쳐보자. 나의 의지로는 습관이 쉽게 고쳐지지 않는다. 하지만 나의 의지로 환경을 고칠 수 있다. 그리고 그 환경은 지속적으로 나의 습관에 영향을 주므로 습관을 고칠 수 있다. 하지만 이런 환경을 구축하느 것은 누군가가 나를 지속적으로 지켜봐야 한다. 그것은 쉽지 않기 때문에 머신러닝으로 이러한 환경을 조성해보는 것은 어떨까?  

https://teachablemachine.withgoogle.com/train  
위 링크에서 머신러닝을 통해 **모델**을 학습시키고 테스트할 수 있다.

### 모델
인간은 경험을 통해 학습을 하고 그 후에는 가설을 세우고 검증하는.. 등 판단을 통하여 결과를 예측한다. 마찬가지로 기계에게 판단력을 부여하는 과정은 학습(Learning)을 시키고, 모델(Model)을 생성한 뒤, 좋은 예측(Prediction)을 하는 것이다. 예측을 잘해야 좋은 결정(Decision)도 할 수 있다.  

## 2021-01-05
### 머신러닝머신
https://ml-app.yah.ac  
위 사이트에서 우리가 학습한 모델을 통해 앱을 바로 만들어 볼 수 있는 사이트이다. 해당 사이트에 학습한 모델을 업로드하고 코드 블럭을 통해 우리가 원하는 로직을 구현할 수 있다.  

### 애플리케이션과 프로그램
애플리케이션과 프로그램은 둘다 같은 것을 가르킨다(소프트웨어라는 관점에서). 
애플리케이션은 **어떤 기능을 부품으로 응용**하여 만든 소프트웨어(완제품)이다. 예를 들자면, 우리는 teachable machine과 같은 부품(모듈)을 이용해서 머신러닝머신(애플리케이션)을 만들었다고 봐도 된다.  
프로그램은 시간의 순서에따라 작동하는 소프트웨어이다.  

### 모르면 마법, 알면 기술
우리가 어떤 마법⚛️을 부리고 싶은지 생각해보자. 우리가 IoT를 모르면 그것은 마치 마법이 되는것 처럼 말이다..  
#### IoT (Internet of Thing)
IoT는 사물인터넷을 의미한다. 쉽게 말해서 사물에 인터넷에 속한 것을 의미한다. 최근들어 작은 전등부터 (스마트홈) 크게는 자동차까지 애플리케이션을 통해 제어할 수 있다. 이것은 전부 사물에 컴퓨터가 들어가 있고, 인터넷으로 연결되어 있기 때문에 가능한 일들이다.  

우리가 레몬에이드를 판매한다고 쳐보자. 그때 우리는 레몬을 너무 적게사면 레몬에이드를 만들 수 없으니 손해다. 반대로 너무 많이 사면 버려야되는 경우가 생겨서 손해이다. 그래서 우리는 생각했다. 온도와 판매량 사이의 관계를.. 그러나.. 현실은 그렇게 단순하지 않다. 단순히 온도 뿐만 아니라 유행이라던가 경쟁자등 판매량을 결정하는 변수들은 다양하다. 머신러닝은 이러한 **변수들 사이의 관계의 공식**을 만들어준다.  

그리고 교양은 여기까지이다.  

## 2021-01-06
### 작업의 시작
현실은 아주 많은 데이터로 복잡하게 구성되어 있다. 그래서 복잡한 현실을 아주 단순한 데이터 단위로 변환하는 과정이 필요하다. 현실을 데이터화시킬 수 있다면 발견하기 어려운 것들을 단순한 데이터를 통해 통찰할 수 있게 된다. 이렇게 현실을 변화시키는 일을 '*데이터산업*'이다. 데이터 산업은 크게 두 가지로 나뉠 수 있다. 첫 번째는 '*데이터 과학*'과 두 번째는 '*데이터 공학*'으로 구분할 수  있다.  

- 데이터 과학은 데이터를 만들고 만들어진 데이터를 이용  
- 데이터 공학은 데이터를 다루는 도구를 만들고 관리  

### 표
인류가 데이터를 시각화 시키기 위한 도구로 대표적인 것을 뽑으라면 '*표*'와 '*좌표평면*'을 고르라고 할 수 있을 것 같다. 머신러닝 분야에서는 표 즉, **행렬**을 이해하는 것은 매우 중요한 일이다. 행은 한건의 데이터를 의미하고, 열(feature)은 데이터의 속성을 의미한다.  

### 독립변수와 종속변수
데이터를 표에 가두는 것에서 끝나는 것이 아니라 의미있는 데이터를 뽑아내는 것도 중요하다. 그래서 우리는 독립변수와 종속변수를 이해하는 것도 중요하다. 변수는 변할 수 있는 값 즉, 표(table)에서는 필드를 의미하게 된다.  
독립변수는 *원인*, 종속변수는 *결과*과 되는 필드를 의미한다. 이렇게 생각하면 쉽다.  

- 원인은 어떠한 것에도 의존받을 이유가 없다. 고로 독립변수라는 이름이 붙여진 것이고
- 결과는 원인에 의존하고 있다. 그래서 종속변수라는 이름이 붙여진 것이다.

독립변수와 종속변수는 '*인과관계*'에 놓여져 있다.  
우리는 이제 표를 마주하게 되면 서로 영향을 주는 필드를 발견해야 한다. 이 필드들의 관계를 '*상관관계*'에 놓여있다고 한다.  
(상관관계 사이에는 인과관계가 있을 수 도 있다. 고로, 모든 인과관계는 상관관계에 속해있지만, 모든 상관관계가 인과관계에 놓이는 것은 아니다.)

### 심리전
우리가 처음 스마트폰을 사면 이 많은 기능들은 언제 공부하지?라는 생각은 잘 안할 것이다. 우리가 주로 쓰는 기능들을 익숙하게 사용해보고, 잘 사용하지 않는 기능들은 이름정도만 알아두었다가 추후에 필요할 때 공부하고 사용한다. 머신러닝도 이 스마트폰처럼 바라보고 공부를 해보자. 그러면 절망에 빠질 일은 없을 것이다.  

## 2021-01-07
### 머신러닝의 분류
머신러닝은 단일기술이 아니다. 머신러닝에 있는 핫한 기술들을 정리해보자.  

- 지도학습 (Supervised Learning)  
지도학습은 기계에게 정답을 주고 학습을 시키는 것을 의미한다.  
eg) 분류(classification), 회귀(regression)  

- 비지도학습 (Unsupervised Learning)  
비지도학습은 기계에게 정답을 주지 않고 데이터만 준 상태로 관찰을 통해 통찰력을 늘리는 방식으로 학습시키는 것을 의미한다.  
eg) 군집화(clustering), 변환(transform), 연관(association)  

- 강화학습 (Reinfocement Learning)  
경험을 통해 어떤 것이 최적의 해인지를 찾아가는 방식으로 학습시키는 것을 의미한다. (더 좋은 보상을 받기 위해) 경우에 따라 다르지만 잘했을 경우 리워드가 주어지거나 못했을 경우 벌이 주어진다.  

### 지도학습 (Supervised Learning)
지도학습은 과거의 데이터로부터 학습한다. 레몬에이드 예제를 들어보자. 충분히 많은 과거의 데이터(온도에 따른 판매기록)과 그 안에 독립변수(원인)과 종속변수(결과)가 필요하다. 그리고 머신러닝을 통해 이들을 학습하여 새로운 모델(판단력)을 만들어낸다. (판매량 = 2 * 온도라는 하나의 방정식) 그리고 우리는 생성된 모델을 사용하면 된다. 좋은 모델을 만드려면 정확하고 많은 데이터가 필요하다.  

### 회귀 (Regression)
예측하고 싶은 **종속변수가 숫자일 때** 회귀를 사용한다. 독립변수(feature)가 여러 개가 될 수 있다. 이러한 경우에는 각 feature별로 영향을 끼치는 정도인 weight가 모델로써 계산된다. 
eg) Linear Regression, Ridge Regression, Lasso Regression ...

### 분류 (Classification)
결과가 숫자가 아닌 클래스이다. 결과값에 따라 성질이 비슷한 것끼리 그루핑하는 것이다. 
eg) Logistic Regression, k-NN, Naive Bayes, Support Vector, Decision Tree ...

### 군집화 (Clustering)
비슷한 것들은 찾아서 그루핑하는 것이다. 분류와 혼동될 수 있다. 하지만 명확히 해두자.  
군집화는 예를 들어 1000만개의 데이터와 100개의 클러스터가 필요하다고 가정하자. 데이터들의 유사성을 파악하여 (머신러닝을 통해 정답이 주어지지 않고 직접 파악하여) 군집을 만들어주는 것이 클러스터링이다. 반면 분류는 클래스별로 정답이 주어진 데이터들로 학습을 하는 점에서 클러스터링이랑 다르다.

### 연관규칙학습 (Association Rule Learning)
주로 추천되는 알고리즘에 사용된다. 서로 연관되는 것들을 찾아내는데에 용이하다. 예를 들면, (표를 사용하는 것이 용이하다.) 라면, 계란, 식빵, 우유, 햄 등... 여러가지 음식을 구매한 이력의 테이블이 있다고 가정하자. 라면을 샀을 경우 대부분의 사람들이 계란을 같이 산다면 라면과 계란 사이에는 연관관계가 존재하는 것이다. 그러나, 이러한 속성들이 많아질 경우, 사람이 직접 일일이 찾아내는 것은 불가능 하다. (데이터가 많아질 경우에도 마찬가지이다.) 이러한 상황에서 구원해주는 것이 연관규칙학습이다.  

## 2021-01-08  
### 강화학습 (Reinforcement Learning)
