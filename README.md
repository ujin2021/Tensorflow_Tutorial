# tensorflow-Tutorial
opentutorial course  <br>

:white_check_mark: 오리엔테이션 <br>
:white_check_mark: 목표와 전략 <br>
:white_check_mark: 지도학습의 빅픽쳐 <br>
:white_check_mark: 실습환경 - Google Colaboratory <br>
:white_check_mark: 표를 다루는 도구 '판다스' <br>
:white_check_mark: 첫번째 딥러닝 - 레모네이드 판매 예측 <br>
:black_square_button: 두번째 딥러닝 - 보스턴 집값 예측 <br>
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
