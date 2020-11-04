# tensorflow-Tutorial
opentutorial course  <br>

:white_check_mark: 오리엔테이션 <br>
:white_check_mark: 목표와 전략 <br>
:white_check_mark: 지도학습의 빅픽쳐 <br>
:white_check_mark: 실습환경 - Google Colaboratory <br>
:white_check_mark: 표를 다루는 도구 '판다스' <br>
:white_check_mark: 첫번째 딥러닝 - 레모네이드 판매 예측 <br>
:white_check_mark: 두번째 딥러닝 - 보스턴 집값 예측 <br>
:black_square_button: 학습의 실제 <br>
:black_square_button: 세번째 딥러닝 - 아이리스 품종 분류 <br>
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

### :closed_book: Lemonade
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


### :closed_book: Boston
#### 퍼셉트론(perceptron)
1. 독립변수가 13개, 종속변수가 1개
<img src="https://user-images.githubusercontent.com/53362054/98071143-13c4c880-1ea6-11eb-82e1-f947f2682ae2.png" width=500 height=250>
2. 독립변수가 12개, 종속변수가 2개
<img src="https://user-images.githubusercontent.com/53362054/98071192-3d7def80-1ea6-11eb-94e1-a2c86df1303d.png" width=500 height=250>

> w : 가중치, 결과 y : bias
