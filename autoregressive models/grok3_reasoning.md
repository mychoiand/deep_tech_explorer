![image](https://github.com/user-attachments/assets/0ddd5a41-1979-409b-9ae6-6ecc6caa0f48)
![image](https://github.com/user-attachments/assets/d2396c62-6c4d-4d7f-852e-d72f2b08e314)
![image](https://github.com/user-attachments/assets/bc34e269-e5bc-4876-96ee-11a90221189d)
![image](https://github.com/user-attachments/assets/f5fa948a-0220-4824-a82e-632799ec62ae)
![image](https://github.com/user-attachments/assets/c039e340-7586-4fdd-b60c-a47fbca2fcf4)

아래는 자동회귀 모델(Autoregressive Model, AR 모델)에 대한 설명입니다. 기본 개념부터 심화 내용까지 체계적으로 다루었습니다.
자동회귀 모델이란?
**자동회귀 모델(Autoregressive Model, AR 모델)**은 시계열 데이터를 분석하고 예측하는 데 사용되는 통계적 모델입니다. 이 모델의 핵심 아이디어는 현재의 데이터 포인트가 과거의 데이터 포인트들에 의존한다는 것입니다. 즉, 과거의 값을 이용해 현재 값을 예측하는 방식입니다.
1. 기본 개념
AR 모델은 다음과 같은 수식으로 표현됩니다:
X_t = c + \sum_{i=1}^{p} \phi_i X_{t-i} + \epsilon_t
수식의 구성 요소
X_t
: 시점 ( t )에서의 관측값
( c ): 상수항
\phi_i
: 모델의 파라미터 (과거 값의 가중치)
( p ): 모델의 차수(order), 몇 개의 과거 값을 사용할지 결정
\epsilon_t
: 시점 ( t )에서의 백색 잡음(white noise), 예측 오차를 나타냄
이 수식은 현재 값 
X_t
가 과거 ( p )개의 값에 대한 가중합과 오차항으로 구성된다는 것을 보여줍니다.
예시
AR(1) 모델: 직전 하나의 값만 사용  
X_t = c + \phi_1 X_{t-1} + \epsilon_t
AR(2) 모델: 직전 두 개의 값 사용  
X_t = c + \phi_1 X_{t-1} + \phi_2 X_{t-2} + \epsilon_t
2. 차수(order) 선택
모델의 차수 ( p )는 얼마나 많은 과거 데이터를 사용할지를 결정합니다. 적절한 ( p )를 선택하는 것은 매우 중요합니다:
너무 작을 경우: 데이터의 패턴을 충분히 포착하지 못함
너무 클 경우: 과적합(overfitting)이 발생할 수 있음
차수 선택 도구
ACF (Autocorrelation Function): 시계열의 자기상관을 보여줌
PACF (Partial Autocorrelation Function): 특정 시차에서의 직접적인 상관관계를 보여줌. AR 모델의 차수는 PACF가 끊기는 지점으로 결정할 수 있음
3. 파라미터 추정
AR 모델의 파라미터 
\phi_i
는 다음 방법으로 추정됩니다:
최소제곱법 (Least Squares Method): 잔차의 제곱합을 최소화
최대우도추정 (Maximum Likelihood Estimation, MLE): 데이터의 likelihood를 최대화
추정된 파라미터를 이용해 미래 값을 예측할 수 있습니다.
4. AR 모델의 특성
정상성 (Stationarity)
AR 모델은 시계열 데이터가 정상성을 가져야 합니다. 정상성이란 시계열의 통계적 특성(평균, 분산 등)이 시간에 따라 변하지 않는 것을 의미합니다. 비정상적인 데이터는 차분(differencing) 등의 방법을 통해 정상성을 확보한 후 모델을 적용할 수 있습니다.
선형성
AR 모델은 선형 모델이므로 데이터가 선형적인 관계를 가질 때 효과적입니다. 비선형 패턴에는 ARCH나 GARCH 모델과 같은 대안이 더 적합할 수 있습니다.
파라미터의 의미
AR(1) 모델을 예로 들면:
|\phi_1| < 1
: 시계열은 안정적이며 충격(shock)이 시간이 지남에 따라 사라짐
|\phi_1| > 1
: 시계열은 불안정하며 충격이 증폭됨
\phi_1 = 1
: 단위근(unit root) 문제로 비정상성을 나타냄
5. 확장 모델
AR 모델은 다음과 같이 확장될 수 있습니다:
VAR (Vector Autoregressive) 모델: 다변량 시계열에서 여러 변수 간 상호 의존성을 모델링
ARMA (Autoregressive Moving Average) 모델: AR과 MA(Moving Average) 모델을 결합
ARIMA (Autoregressive Integrated Moving Average) 모델: 비정상 시계열을 위해 차분을 추가한 모델
6. 안정성 조건
AR 모델이 안정적이기 위해서는 모델의 특성 방정식의 근이 단위원(unit circle) 내부에 있어야 합니다:
AR(1): 
|\phi_1| < 1
AR(2): 더 복잡한 조건을 만족해야 함 (파라미터 제약 필요)
안정성이 보장되지 않으면 시계열이 폭발적으로 증가하거나 감소할 수 있습니다.
7. 예측
AR 모델을 사용하면 과거 데이터를 바탕으로 미래 값을 예측할 수 있습니다:
점예측 (Point Forecast): 특정 시점의 예상값
구간예측 (Interval Forecast): 예측의 불확실성을 포함한 범위
8. 한계와 주의사항
선형성: 비선형 패턴에는 적합하지 않음
차수 선택: 잘못된 차수는 부정확한 예측을 초래
정상성: 데이터가 정상성을 갖지 않으면 모델의 유효성이 떨어지며, 필요시 차분 등의 처리가 요구됨
결론
자동회귀 모델(AR 모델)은 시계열 분석의 기초가 되는 중요한 모델로, 과거 데이터를 활용해 현재와 미래를 예측하는 데 유용합니다. 정상성과 선형성을 가정하며, 적절한 차수 선택과 파라미터 추정이 성공적인 적용의 핵심입니다. 또한, VAR, ARMA, ARIMA와 같은 확장 모델로 발전시켜 더 복잡한 시계열 문제를 해결할 수 있습니다.
