# Theory

## 1. Battery State of Health (SOH)

- SOH(State of Health)는 배터리의 건강 상태를 나타내는 지표이다.
- 일반적으로 초기 용량 대비 현재 용량의 비율로 정의된다.

SOH = (현재 Capacity / 초기 Capacity) × 100

- 배터리 열화가 진행될수록 SOH는 감소한다.

---

## 2. Battery Aging Mechanism

배터리는 충·방전이 반복될수록 열화가 진행된다.

주요 특징:
- 내부 저항 증가
- Capacity 감소
- 전하 전달 저항 증가

이러한 변화는 배터리 성능 저하로 이어진다.

---

## 3. Equivalent Circuit Model (ECM)

배터리는 전기적으로 RC 회로로 모델링할 수 있다.

구성 요소:
- R: 내부 저항 (Internal Resistance)
- C: 전하 저장 능력 (Capacity 관련 요소)

이 모델은 배터리의 동적 특성을 설명하는 데 사용된다.

---

## 4. Time Constant (τ)

RC 회로에서 시상수(Time Constant)는 다음과 같이 정의된다.

τ = R × C

- 시상수는 전압이 변화하는 속도를 결정한다.
- 배터리에서도 충·방전 시 전압 응답 특성과 관련된다.

배터리 열화 시:
- R 증가
- C 감소
→ τ 변화 발생

---

## 5. Impedance and Internal Resistance

배터리의 임피던스는 내부 상태를 나타내는 중요한 지표이다.

주요 성분:
- Re: 전해질 저항
- Rct: 전하 전달 저항

특징:
- 열화가 진행될수록 증가
- SOH와 높은 상관관계 존재


## 6. Automotive Battery Tester Principle

현재 공업사에서 사용되는 배터리 테스트기는 AC Conductance 방식을 사용한다.

### 측정 방식
- 약 90Hz의 미세한 교류 전류 인가
- 전압 강하 측정 후 내부저항 계산

### 계산 방식
- Internal Resistance 측정
- Lookup Table 기반으로 CCA 추정
- SOH = (Measured CCA / Rated CCA) × 100

### 한계
- 출력(시동 성능) 중심 평가
- 실제 저장 용량(Capacity) 반영 부족
- 중간 열화 상태 정밀 추적 어려움

---

## . Connection to This Study

본 연구에서는 EIS와 같은 정밀 장비 없이,  
공업사에서 측정 가능한 데이터만을 사용한다.

사용 데이터:
- Internal Resistance → R 역할
- CCA → Capacity와 관련된 변수
- Voltage, Temperature → 보조 변수

이를 통해 RC 등가회로 특성을 간접적으로 반영하고,  
배터리 SOH를 예측하고자 한다.
