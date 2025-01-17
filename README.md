<img src="https://capsule-render.vercel.app/api?type=waving&color=BDBDC8&height=150&section=header" />

# 2023년도 졸업논문


## 📁 졸업작품 소개
** 수면 무호흡증 진단 및 방지 졸업작품 **은  합성곱신경망과 모델 경량화 기술을 통한 임베디드 AI를 통해 구현했습니다


##  개발 배경
2022년 기준 국민건강보험공단의 자료를 보면 수면장애로 진료받은 인원이 5년 새 ** 25**만명이 증가했다 (30%)
수면장애는 능률 저하 , 안전 사고등 여러 가지 개인적, 사회적 문제를 초래한다
삶의 질을 저하시키는 수면장애를 진단하고, 방지하고자 개발을 하기로 결정했다

## 개발 목표 및 내용

1. **카메라, 마이크, 딥러닝(CNN)을 이용하여 사람의 수면자세 및 상태를 진단**

2. **서보 모터를 이용해 자세를 교정**

3. **진동 모터 , 스피커를 이용해 기상**

##  기대효과 및 시장성
수면은 건강과 밀접한 관계가 있으므로 수면의 질을 높임으로써 건강에 좋은 영향을 미친다
수면의 질을 높임으로써 건강뿐 아니라 , 집중력과 주의력, 기억력이 향상되어 일상생활의 만족도가 높아진다
딥러닝을 활용하여 수면 장애를 진단 / 방지하고 , 수면의 질을 향상하고자 하였다

## 📖자료
- 졸업작품 발표자료
- Read me 파일
- 졸업작품 논문자료

## 🔗팀 구성
| 팀원  | 박준영 |
| 팀원  | 문동주 |
| 팀원  | 유인호 |

## 💡요약

<details open>
<summary>AI 기반의 수면장애 진단 및 방지 기술</summary>
  
- 최근 비약적인 반도체의 발달로 인해 저전력 MPU에서도 AI 추론이 가능해졌다
- 임베디드시스템은 소형 및 경량화에 따른 휴대성, 경제성, 신뢰성이 높은 장점이 있다
  <br>
- AI와 임베디드시스템의 장점을 합친 On-device 형태의 임베디드 AI로 수면의 질을 향상하는 기술 및 제품을 개발한다면, 규모가 커지고 있는 슬립테크 시장에서 높은 상품성과 경쟁력을 
갖출 수 있을 것으로 기대된다
-건강, 생명, 삶의 질에 밀접한 연관이 있는 수면장애를 개선함으로써 개인뿐만 아니라 사회적으로도 많은 이로움이 있을 것으로 예상된다

**<주요 특징>**<br>

- 이미지데이터와 음성데이터로 수면 자세와 수면장애를 추론하는 높은 성능의 모델을 학습하는 것이다
- 모델 경량화 기술을 이용해서 계산 복잡도와 지연시간을 줄이고, 저전력 MPU에서 실시간 추론이 가능하게 한다
- MCU가 모델의 예측값을 이용하여 스피커, 서보모터, 진동모터를 제어하는 회로를 설계한다

**<키워드>**<br>
- 단시간 푸리에 변환, 딥러닝, 합성곱신경망, 전이학습, 미세조정, VGG16, 모델 경량화, On-device AI


<br>


  **<데이터 수집>**<br>

- 수면 자세 데이터는 보건의료 데이터로 분류되어 있어 데이터를 외부에서 수집 및 활용하는 데 어려움이 있어, 직접 데이터를 생성하였다
-데이터 편향 문제를 방지하고자, 카메라의 각도, 피사체까지의 거리, 성별, 조명 세기, 침구 주변 환경 등을 다양하게 고려해서 데이터를 생성하였다

**<데이터 분포>**<br>

- ‘수면 자세가 정자세인 경우’
- ‘왼쪽으로 치우쳐진 경우’
- ‘오른쪽으로 치우쳐진 경우’
- ‘사람이 침대에 없는 상황’


**<vgg16 모델 전이학습>**<br>
<img width="341" alt="vgg16" src="https://github.com/user-attachments/assets/ed50ac7d-7c50-48f1-a51b-38efdda991e6">

**<최종 모델의 하이퍼파라미터와 과대적합을 방지하는 학습 구조>**<br>
<img width="483" alt="최종 모델 학습 구조" src="https://github.com/user-attachments/assets/8cde06aa-f8a3-46d3-8dab-0b8a990a87c7">

**<최종 모델의 일반화 성능 및 모델 저장>**<br>
<img width="332" alt="최종 모델 저장" src="https://github.com/user-attachments/assets/2645c05d-66a5-49e7-a7c7-4e07704b65e4">


  **<음성데이터 데이터분포>**<br>
-‘수면 상태 정상’
-‘약한 코골이’
-‘심한 코골이 또는 수면 무호흡 증상’


**<음성 최종 모델의 일반화 성능 및 모델 저장>**<br>
<img width="402" alt="음성 모델 저장" src="https://github.com/user-attachments/assets/09cbc994-0a0f-4c8e-899d-85366c1f4abd">


## 📒수면장애 진단 및 방지 시스템 설계

### Environment
학습한 모델을 경량화해서 라즈베리파이에 저장하고, 라즈베리파이와 연결된 카메라와 마이크 모듈을 이용해서 이미지데이터와 음성데이터를 실시간으로 추출해서 라즈베리파이의 MPU로 데이터 전처리를 하고, 모델의 입력데이터로 사용해서 수면장애를 추론한다

### Development
사용자의 베개에서 동작할 수 있도록 전원 공급 장치, HC-06 블루투스 모듈, 아두이노, 진동모터, 서보모터를 이용해서 
회로를 구성했다

-블루투스 모듈은 무선통신 방식으로 라즈베리파이가 송신한 신호를 받아서 시리얼 통신 방식으로 아두이노에 전달한다

### 📈결과 및 분석
-수면 자세와 수면 상태를 추론하는 모델 각각의 일반화 성능은 Test Data Set을 이용한 정확도 지표를 이용하면 94%, 96%로 높은 성능을 보였다
-모델의 예측값과 반복 횟수 조합에 대응되는 동작을 제어기와 제어대상이 안정적으로 수행하는 것을 확인하였다
-사용자 기기 내에서 AI 모델 개선이 어렵다는 단점이 
있었다

### 📚 참고 문헌 
[1] 국민건강보험 Magazine, 2020.08, https://www.nhis.or.kr/magazin/160/html/sub1.html,  
(accessed, 11.10.23).
 [2] Chattu et al.(2018), “The Global Problem of Insufficient Sleep and Its Serious Public 
Health Implications”, Healthcare.
 [3] 국민건강보험 Magazine, 2018.09, https://www.nhis.or.kr/magazin/137/html/c01.html, 
(accessed, 11.10.23).
 [4] Hafner et al.(2017),“Why Sleep Matters—The Economic Costs of Insufficient Sleep”, 
Rand Health Quarterly.
 [5] 남미래, “"밤마다 뒤척뒤척, '꿀잠' 잘 수만 있다면"…판 커지는 '슬립테크'”, 머니투데이, 
2023.02.14, https://news.mt.co.kr/mtview.php?no=2023021114194749942, (accessed, 11.10.23).
 [6] 아주대학교산학협력단. 수면의 질 결정 장치 및 방법. 특허 출원번호 10-2010-0107335, 
출원일자 2010년10월29일, 등록일자 2012년12월28일.

