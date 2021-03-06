# 2021-01-10
## 오리엔테이션
우리는 텐서플로우 프레임워크를 사용하여 지도학습(분류, 회귀)을 하려고 한다. 지도학습의 알고리즘으로 대표적으로 꼽으라면 Decision Tree, Random Forest, SVM, KNN, Neural Network가 있다. 이중 우리가 사용할 알고리즘은 Neural Network이다. NN은 인공신경망을 의마하며, 인간의 신경을 모방한 형태이다. (딥러닝으로 알려짐) 딥러닝의 원리를 모르더라도 이를 사용하게 할 수 있는 프레임워크들이 있다. 예를들면, Tensorflow, PyTorch, Caffe2, Theano

## Keras
https://ko.wikipedia.org/wiki/케라스  
Keras에 관해 간략히 설명하자면, 순수 Tensorflow를 가지고 신경망을 구현하려면 디테일한 부분이 필요하다. 이를 간단히 할 수 있는 API가 Keras이다.  Tensorflow 이외에도 다른 프레임워크에서도 Keras 라이브러리를 지원한다.

# 2021-01-11
## 지도학습의 빅픽쳐
우리는 도구(라이브러리)에 구애받지 않기 위해 지도학습의 큰 플로우를 살펴볼것이다. 지도학습의 과정은 크게 4가지로 이루어진다.  
1. 과거의 데이터를 준비한다.  
2. 모델의 구조를 만든다.(독립변수와 종속변수의 개수에 따라 모델의 구조가 바뀐다.)  
3. 데이터로 모델을 학습(FIT)한다. (독립변수의 영향력을 구한다. - 가중치)  
4. 완성된 모델을 이용한다.  

## Google Collaboratory
jupyter notebook의 웹 버전이라고 생각하면 된다. 구글 드라이브에서 새로만들기 - 연결할 앱을 통해 설치할 수 있고, https://colab.research.google.com/  링크에서 연동이 가능하다.  
새 노트를 만들고 나면 셀 단위로 코드를 실행할 수 있다. 물론, 쉘을 추가할 수 도 있다.  

### 단축키 
- ctrl + enter : 해당 쉘만 실행
- shift + enter : 해당 쉘을 실행한 후 현재 쉘이 다음 쉘로 이동한다.  

## Pandas
지도학습을 위해서 우리는 독립변수와 종속변수를 구분하는 작업부터 해야한다. 그리고 데이터를 테이블 형식으로 관리하기 때문에 우리는 pandas모듈의 DataFrame이라는 자료구조를 사용할 것이다.  

## 2021-01-12
### Pandas 실습
이번 시간에 다룰 내용은 크게 6가지이다.  
1. csv 파일 읽어오기 : pd.read_csv(path)  
2. 모양 확인하기 : df.shape  
3. 컬럼 선택하기 : df[['col1', 'col2', 'col3']]  
4. 컬럼 이름 출력하기 : df.columns  
5. 맨 위의 5개 데이터 출력하기 : df.head()
6. 맨 아래의 5개 데이터 출력하기 : df.tail()  

### 레모네이드 판매 예측
이번 시간에는 앞에서 다뤘던 지도학습의 빅픽쳐 내용을 사용하여 신경망의 가장 작은 단위인 뉴런을 코드로 구현해본다.  

```
# 독립변수가 하나이므로 shape에 [1]
X = tf.keras.layers.Input(shape=[1])

# 종속변수가 하나이므로 Dense의 인자에 1
Y = tf.keras.layers.Dense(1)(X)
```  

```
# epochs는 전체데이터를 몇번 학습시킬 것인지를 의미한다. (한번에 학습되기는 어렵기 때문)
model.fit(x=lemonade_independent_variable, y=lemonade_dependent_variable, epochs=1000)
```  

## 2021-01-13
### 손실의 의미
하나의 epoch을 거칠때마다 loss값이 떨어지는 것을 확인할 수 있다. 이는 학습이 얼마나 잘되었는지를 비교하는 지표이다.  
우리는 학습된 모델에 데이터(독립변수)를 넣어서 예측치를 얻는다. 그리고 실제정답(종속변수)과 예측치를 비교한다.  
loss = (실제정답 - 예측치)^2 의 평균으로 정의된다.  
분산 = (평균 - 데이터)^2의 평균. 즉, loss는 실제정답에 대한 분산을 의미한다. 고로, loss가 낮을수록 학습이 잘된 모델이라고 할 수 있다.  

## 2021-01-15
### 보스턴 집값 예측
레몬에이드에서 만든 모델은 y = 2x라는 독립변수가 하나밖에 없는 아주 간단한 모델이었다. 하지만 머신러닝은 이보다 더 복잡한 모델을 만들 수 있다. 이번에 보스턴 집값 예측은 독립변수가 무려 13개나 있다. 아마 y = ax1 + bx2 + cx3 + ... + mx13 + bias(절편) a부터 m은 각 독립변수가 끼치는 영향의 정도(가중치)를 의미한다. 보스턴 집값 예측의 종속변수는 medv(median value - 중위수(중앙값))이다.  

잠시 통계적인 이야기를 하겠다. 보통은 평균이 특정 집단의 값을 대표하기 좋다. 하지만 그렇지 않은 경우도 있다. 예를 들면 직장인 평균 연봉을 따졌을 때, 상위 집단의 직장인들이 연봉이 극도로 높을 때 평균을 적용하면 나머지 집단은 괴리를 느낄 것이다. 그렇기에 중위수가 평균값에 비해 상대적으로 대표하기 좋은 수다.  

### 수식과 퍼셉트론
퍼셉트론은 인공신경망의 종류 중 한 종류로, 단층 퍼셉트론 같은 경우에는 1과 0밖에 output이 존재하지 않은 선형 분류기이다. (퍼셉트론의 함수를 그렸을 때 그 선을 기준으로 위에 있거나 아래에 있는 경우로 분류한다.)  
그러나, 다층 퍼셉트론을 활용하면 XOR연산도 가능해진다.  

<img width="494" alt="스크린샷 2021-01-15 오후 12 31 27" src="https://user-images.githubusercontent.com/32003817/104677916-a8149c80-572d-11eb-9a9f-a301b7ea27f2.png">  

위 그림은 보스턴 집값 예측 모델을 도식화한 것이다. 마치 신경세포(뉴런)과 닮지 않았는가? 우리는 이것을 뉴런이 아닌 퍼셉트론이라고 부른다. 그리고 각 독립변수별로 끼치는 영향은 가중치(Weight), 편향은은 절편(bias)라고 한다.  

<img width="494" alt="스크린샷 2021-01-15 오후 12 41 39" src="https://user-images.githubusercontent.com/32003817/104678559-0beb9500-572f-11eb-87eb-28e589ab1b31.png">  

그렇다면 종속변수가 2개인 경우는 어떨까? 위 그림에서 보면 독립변수가 12개 종속변수가 2개인 상황이다. 종속변수가 2개이므로 모델(방정식) 또한 2개가 나올 것이고, 퍼셉트론이 병렬적으로 연결되어 있다고 생각할 수 있다.  

## 2021-01-16
### 학습의 실제  
W에 dt(step size)만큼 더하고 Loss값의 변화를 관찰하자. Loss가 늘어난 경우 W에 dt값을 빼는 방향으로 결정해야하고 줄어든 경우에는 dt값을 더하는 방향으로 유지하면 된다. dLoss/dt는 Loss의 방향을 의미한다.
mse = mean sqaure error, (예측 - 실제값)^2 의 평균  

## 2021-01-19
### 아이리스 품종 분류
이전까지는 독립변수를 통해 추측한 종속변수는 수치 데이터이므로 regression를 사용했다. 하지만 아이리스 품종 분류의 종속변수는 품종을 구분하는 클래스이므로 classification을 해야한다. 즉, Softmax Regression을 통해 나온 k차원의 벡터를 One-Hot Encoding을 통해 각 클래스를 1과 0으로 표현한다.  

e.g) 4개의 독립변수와 3개의 클래스가 존재하고, 배치사이즈가 1일때..  
이 경우 입력이 4차원의 벡터일 것이다.(독립변수의 갯수만큼) 그러나 아웃풋은 3차원의 벡터(이를테면 [0.01 0.05, 0.04])형식일텐데 어떻게 하지요? 각 독립변수에 가중치곱을 하면 된다.  

<img width="310" alt="image" src="https://user-images.githubusercontent.com/32003817/104968998-bd8a0f00-5a2a-11eb-8dbc-31aa30ee487a.png">  

참고 : Regression의 Loss function은 MSE, Classification의 Loss function은 Cross Entropy  

