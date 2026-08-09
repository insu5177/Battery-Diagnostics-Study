## 7. Proposed Approach

### 7.1 Limitations of Conventional Battery Testing

현재 자동차 배터리 테스트기는 내부저항 기반의 AC Conductance 방식을 사용하여  
CCA를 추정하고, 이를 통해 SOH를 계산한다.

SOH는 일반적으로 다음과 같이 단순 비율로 계산된다.

SOH = (Measured CCA / Rated CCA) × 100

이 방식은 빠르고 실용적이지만, 다음과 같은 한계를 가진다.

- 배터리의 출력 특성(시동 성능) 중심 평가
- 실제 저장 용량(Capacity) 반영 부족
- 중간 열화 상태에 대한 정밀한 추적 어려움

---

### 7.2 Proposed Strategy

본 연구에서는 기존 방식의 한계를 보완하기 위해  
배터리의 물리적 특성을 반영한 Feature 기반 접근을 제안한다.

핵심 아이디어는 다음과 같다.

1. 내부저항을 통해 저항 성분(R) 추정
2. CCA를 통해 용량 특성(C)에 대한 간접 정보 확보
3. 두 요소를 결합하여 시상수 기반 Feature 구성

---

### 7.3 Time Constant-Based Feature

이론적으로 RC 회로의 시상수는 다음과 같이 정의된다.


::contentReference[oaicite:0]{index=0}


(※ 실제 시상수 식은 τ = R × C 이지만, 공업사 데이터에서는 C를 직접 측정할 수 없음)

따라서 본 연구에서는 실제 시상수를 직접 계산하는 대신,  
다음과 같은 근사 Feature를 정의한다.

τ_proxy = Internal Resistance × CCA

여기서 τ_proxy는 물리적으로 정확한 시상수가 아닌,  
배터리의 저항 및 출력 특성을 동시에 반영하는 경험적 Feature이다.

---

### 7.4 CCA-like Feature in NASA Dataset

NASA 데이터에는 실제 CCA 값이 존재하지 않는다.  
따라서 공업사 데이터와의 구조적 대응을 위해  
CCA와 유사한 특성을 갖는 CCA_like 변수를 정의한다.

CCA는 내부저항과 반비례하며, 용량 및 전압 상태에 영향을 받는다.

이에 따라 다음과 같은 형태의 CCA_like를 고려한다.

CCA_like ∝ Capacity / Resistance

중요한 점은 CCA_like가 실제 CCA를 정확히 재현하는 것이 아니라,  
SOH와의 관계를 학습하기 위한 Feature로 사용된다는 것이다.

---

### 7.5 Modeling Strategy

본 연구는 다음과 같은 단계로 진행된다.

1. NASA 데이터에서 τ_real 후보 Feature 생성
   - Rct
   - Rct × Capacity
   - Rct / Re

2. τ 기반 Feature와 SOH 간 관계 학습

3. 공업사 데이터에서 τ_proxy 생성
   - τ_proxy = Internal Resistance × CCA

4. NASA에서 학습된 관계를 공업사 데이터에 적용하여  
   SOH 및 잔존 수명 예측 수행

※ 공업사 데이터는 모델 학습에 사용하지 않고,  
   최종 검증(Validation) 용도로만 사용한다.

---

### 7.6 Expected Contribution

본 연구는 다음과 같은 기여를 목표로 한다.

- 기존 CCA 기반 단순 진단 방식의 한계 보완
- RC 등가회로 기반 물리적 해석 도입
- 제한된 공업사 데이터만으로도 SOH 예측 가능성 제시
- 실제 정비 환경에서 활용 가능한 진단 방법 제안