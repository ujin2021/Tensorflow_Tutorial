# tensorflow-Tutorial
opentutorial course  <br>

:white_check_mark: 오리엔테이션 <br>
:white_check_mark: 목표와 전략 <br>
:white_check_mark: 지도학습의 빅픽쳐 <br>
:white_check_mark: 실습환경 - Google Colaboratory <br>
:white_check_mark: 표를 다루는 도구 '판다스' <br>
:white_check_mark: 첫번째 딥러닝 - 레모네이드 판매 예측 <br>
:white_check_mark: 두번째 딥러닝 - 보스턴 집값 예측 <br>
:white_check_mark: 학습의 실제 <br>
:white_check_mark: 세번째 딥러닝 - 아이리스 품종 분류 <br>
:black_square_button: 신경망의 완성 : 히든레이터 <br>
:black_square_button: 부록1 : 데이터를 위한 팁 <br>
:black_square_button: 부록2 : 모델의 위한 팁 <br>
:black_square_button: 수업을 마치며 <br>

---

* 지도학습 - 회귀, 분류
> 회귀 : 순자로 된 결과 예측
> 분류 : 카테고리(범주) 예측

* algorithm : Decision Tree, Random Forest, KNN, SVM, Neural Network (여기서 Neural Network 사용)
> Neural Network : 사람의 뇌를 본 딴 알고리즘(= 딥러닝 = 인공신경망)
* Library : tensorflow, Pytorch, Caffe, teano (여기서 tensorflow 사용)

<br>

### :closed_book: 지도학습(Supervised Learning)
1. 과거의 data 준비
> ex) 레모네이드 판매
> ``` 온도(원인, 독립변수) <-> 판매량(결과, 종속변수) ```
2. model 구조 만들기
> input, output 의 갯수에 따라 정해진다
> 현재는 input 1개(온도), output 1개(판매량)
3. 데이터로 모델을 학습(FIT)한다
> 온도 x 2 = 판매량 이라는 것을 도출한다
4. model 이용하기
> 15도일때 판매량은? -> 30개

<br>

### :closed_book: Colaboratory 사용하기
google 에서 제공
Jupyter notebook과 비슷하다.

#### colaboratory 파일 만들기
1. google drive - 새로만들기 - 더보기 - 연결할 앱 더보기 - 'colaboratory' 검색 - 설치 <br>
2. 새로만들기 - 더보기 - 'colaboratory' 선택 

실행 : shift(or ctrl) + Enter

<br>

### :closed_book: Pandas
표를 다루는 라이브러리

<br>

### :closed_book: Lemonade 판매량 예측하기
1. 독립변수와 종속변수를 나누기 <br>
> 독립변수 : 온도, 종속변수 : 판매량 (독립변수에 의해 종속변수가 결정된다)

2. model 만들기
``` python
X = tf.keras.layers.Input(shape=[1]) # 독립변수 column의 갯수가 1
Y = tf.keras.layers.Dense(1)(X) # 종속변수 column의 갯수가 1
```
> shape[n] # n은 독립변수의 갯수, Dense(m) # m은 종속변수의 갯수 <br>

3. model 학습시키기
``` python
model.fit(idp, dp, epochs=10) # loss 값이 0에 가까워져야 함
# model.fit(idp, dp, epochs=10, verbose=0) verbose : 학습 시킬 때 화면에 출력하지 않도록
```
> verbose=0 옵션을 주면 학습시키는 과정이 출력되지 않는다
> 결과 출력에서 loss 값이 0에 가까워 져야 한다


### :closed_book: Boston 집값 예측하기
#### 📖퍼셉트론(perceptron)
1. 독립변수가 13개, 종속변수가 1개
<img src="https://user-images.githubusercontent.com/53362054/98071143-13c4c880-1ea6-11eb-82e1-f947f2682ae2.png" width=500 height=250>
2. 독립변수가 12개, 종속변수가 2개
<img src="https://user-images.githubusercontent.com/53362054/98071192-3d7def80-1ea6-11eb-94e1-a2c86df1303d.png" width=500 height=250>

> w : 가중치, 결과 y : bias

### :closed_book: DeepLearning Workbook
<a href="https://docs.google.com/spreadsheets/d/1hoXQEFUGL74Kg4tui7vXqF1zMujdFNAREl55cDNgCME/edit?usp=sharing"> workbook </a>

### :closed_book: Iris 품종분류하기
<img src="https://user-images.githubusercontent.com/53362054/98074468-d5330c00-1ead-11eb-819b-12fde2c762e4.png" width=500 height=250>

<br>

* 종속변수가 양적(판매량...) 데이터 -> 회귀(regression) 
* 종속변수가 범주형(합격/불합격...) 데이터 -> 분류(classification) => iris 품종 분류에 해당

#### 📖onehot-encoding
독립변수 4개(꽃잎길이, 꽃잎폭, 꽃받침길이, 꽃받침폭) / 종속변수 1개(품종) 
* 독립변수 수식으로 값이 숫자로 나타났었는데, iris 품종은 숫자값이 아니다
* 품종(범주)를 1과 0의 data로 만들어준다(onehot-encoding)
* code는 pd.get_dummies(iris)를 사용
* onehot-encoding에 의해 독립변수가 3가지가 됨(품종1, 품종2, 품종3)
<img src="https://user-images.githubusercontent.com/53362054/98074943-b84b0880-1eae-11eb-876d-ea1a5fdf0264.png" width=500 height=250>

#### 📖softmax
* 0% ~ 100% 사이의 확률값으로 분류를 표현하는 것(비율로 예측하기 위해 사용하는 도구)
> 비가 올 확률 30%, 합격할 확률 99%, ...
> sigmoid 도구도 있음

ex) 
|setosa | virginica | versicolor |결과|
|---|---|---|---|
|1|0|0|setosa일 확률이 100%|
|0.7|0.3|0|setosa일 확률 70%|
|0.2|0.3|0.5|versicolor일 확률 50%|

* softmax는 0~1 사이의 결과를 받을 수 있게 한다
> y = w1x1 + w2x2 + w3x3 + w4x4 + b -> 결과가 -∞ ~ ∞ <br>
> y = softmax(w1x1 + w2x2 + w3x3 + w4x4 + b ) -> 결과가 0 ~ 1
* softmax는 활성화(activation)함수이다
* loss로는 categorical_crossentropy를 사용한다(회귀에서는 mse)
* 평가지표로 정확도를 사용(metrics='accuracy') 1은 모두 맞춘것, 0은 모두 틀린것

