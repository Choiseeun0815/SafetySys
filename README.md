# 블록도
![image](https://github.com/Choiseeun0815/Calendar/assets/103297048/400534e6-ed5a-48a0-9b37-df1a1b786cef)

해당 프로젝트는 Firebase의 실시간 DB를 활용하여 직원의 출-퇴근 시간 및 지정 복장 준수 여부에 대한 정보를 관리하는 시스템이다. (in Android Studio)

# 1. 어플의 메인 화면
![image](https://github.com/Choiseeun0815/Calendar/assets/103297048/c3ee765a-7976-4c6f-a7f7-74c75a11ebc6)

시작 화면에는 출근 및 퇴근 버튼이 배치 되어있다. 

누르는 버튼에 따라 블록도에 작성된 flow대로 기능이 실행된다. 

# 2. 얼굴 인식 
![image](https://github.com/Choiseeun0815/Calendar/assets/103297048/d59da685-b904-4786-8be4-ac823dd604d8)

출근하고자 하는 근로자가 누구인지 식별하기 위하여 얼굴 인식이 진행된다. 인식된 결과는 바운딩 박스의 좌측 상단에 표시.

대리 출근을 염두에 두어 휴대폰으로 촬영된 사진으로 인식을 시도할 경우 fake로 인식이 되도록 처리하였다. 

# 3. 인식된 근로자 정보 출력
![image](https://github.com/Choiseeun0815/Calendar/assets/103297048/dae2c6fd-26c8-4b74-ae6d-2aed5a6db042)

인식이 원활하게 수행되었다면 해당 근로자에 대한 정보를 화면에 보여준다. 

근로자의 이름과 직무는 실시간 DB에, 근로자에 대한 사진은 Firebase Storge에 저장되어있다. 

# 4. 복장에 대한 객체 인식
![image](https://github.com/Choiseeun0815/Calendar/assets/103297048/a513a21a-f1af-4f0e-b0c8-684284e2e5fe)

근로자의 직무에 따라 요구되는 규정 복장이 있다. 

이미지의 예시는 화학 약품 관리자로서, 필히 착용해야만 하는 복장으로는 보안경, 마스크, 연구 가운이 있다. 

규정 복장이 착용되지 않았을 경우 어미에 non_을 붙여 표시해주었다. 

예외 처리로서 일반 안경도 보안경이라 인식될 것을 우려하여 해당 부분 역시 non_goggle으로 인식될 수 있도록 하였다.

# 5. 금일의 스케줄
![image](https://github.com/Choiseeun0815/Calendar/assets/103297048/2ac2c082-d246-41f5-8cb0-85c251cd8b5c)

상기의 과정이 모두 정상적으로 수행되었다면, 해당 근로자의 DB에 저장되어있는 금일의 스케줄이 화면에 출력된다. 

Office Schedule은 회사의 공식 일정을, Personal Schedule은 근로자 개인의 일정에 대한 정보다. 

이는 작성자의 Calendar repo를 보면 일정에 대한 또 다른 시스템을 확인할 수 있다. 

# 6. 하루 총평
![image](https://github.com/Choiseeun0815/Calendar/assets/103297048/c0ba7912-ef5e-486d-90e5-7c3375b93dad)

퇴근 버튼을 눌렀을 때에도 출근 때와 마찬가지로 퇴근자가 누구인지 식별하기 위하여 얼굴 인식이 진행된다. 

정상적으로 완료가 된 후에는 해당 근로자의 하루에 대해 총평할 수 있는 정보를 출력해주는데,

이는 출-퇴근 시간 및 각 복장 규정에 대한 준수 여부와 지각 여부를 예로 들었다. 

# Database 구조
![image](https://github.com/Choiseeun0815/Calendar/assets/103297048/a531f358-1e20-4ac3-9514-92eaffbdaa42)

