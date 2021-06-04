---
layout: post
title: 6장 기본 컴퓨터 프로그래밍
subheading: Programming the Basic Computer
author: JunHo
categories: 컴퓨터구조
banner: https://bit.ly/32PAjtM
tags: 기본 컴퓨터 프로그래밍 컴퓨터구조
sitemap :
  changefreq : daily
  priority : 1.0

---



## 6. Programming the Basic Computer

---

### 6.1 개요

- 컴퓨터 시스템 = 하드웨어+소프트웨어
- 하드웨어 = 물리적인 부품,  관련된 장비
- 소프트웨어 = 컴퓨터를 위해 작성된 프로그램
- 컴퓨터 구조에 관련된 사람들은 두 지점이 서로 영향을 미치기 때문에 하드웨어와 소프트웨어 모두에 대한 지식을 가지고 있어야 한다.



- 프로그램
- - 물리적인 컴퓨터에 의존한다.
  - 물리적엔 컴퓨터위에서 독립적인다.
  - - 컴파일러 : 컴퓨터에 의존



![K-124](https://user-images.githubusercontent.com/38898759/120757049-04485380-c54b-11eb-9aa4-af502a34c015.png)



### 6.2 기계어

- 프로그램 : 컴퓨터가 필수 데이터 처리 작업을 수행하도록 지시하는 지침 또는 명령어 목록
- 프로그래밍 언어의 다양한 타입
- - 프로그래밍 언어의 계층
  - - 기계어
    - - 이진 코드
      - 8진수, 16진수 코드
    - 어셈블리어 (Assembler)
    - - 심볼릭 코드
    - 고수준 언어 (Compiler)



- 프로그래밍 언어 비교

- - ![K-125](https://user-images.githubusercontent.com/38898759/120757412-7c167e00-c54b-11eb-8621-90304c876a39.png)
  - ![K-126](https://user-images.githubusercontent.com/38898759/120757468-8d5f8a80-c54b-11eb-9870-2b6d2c33af0e.png)

  - - ![K-127](https://user-images.githubusercontent.com/38898759/120757542-a36d4b00-c54b-11eb-9baa-75cde70b7fa2.png)

  





### 6.3 어셈블리 언어

- 기본 컴퓨터 어셈블리언어의 문법

- - 각 행은 필드라고 불리는 세 컬럼들로 나열된다.

  - 라벨 필드

  - - 3개 이상의 문자로 구성된 심볼릭 주소가 비거나 구체화 될지도 모른다.  
    - 콤마에 의해 제거된다.

  - 명령어 필드

  - - 기계 또는 의사 명령어로 구체화된다.

    - 다음 중 하나를 지정할 수 있다.

    - - 메모리 참조 명령어 (MRI : Memory reference instruction)

      - - MRI는 두개 또는 세개의 스페이스에 의해 분리된 심볼로 구성된다.
        - ADD OPR (직접 주소 MRI)
        - ADD PTR I (간접 주소 MRI)

- - - 레지스터 참조 또는 입력-출력 명령어
    - - Non-MRI는 주소 부분을 가지지 않는다.
    - 오퍼랜드가 있거나 없는 의사 명령어
    - - 명령어 필드에 사용되는 심볼릭 주소는  레이블로 정의 되어야 한다. 
  - Comment field
  - - 비거나 comment를 포함해야 할지도 모른다.



- 의사 명령어
- - 정의
  - ![K-128](https://user-images.githubusercontent.com/38898759/120759150-abc68580-c54d-11eb-862e-7340910aacd9.png)
- - 예제
  - ![K-129](https://user-images.githubusercontent.com/38898759/120759216-c39e0980-c54d-11eb-8be9-3cfea35b86a8.png)

- - - 주소 100번에서 프로그램이 시작된다.
    - AC에 SUB위치에 있는 값을 로드한다. (-23)
    - AC를 보수한다. (23)
    - AC를 증가시킨다. (-23)
    - MIN에 있는 값을 AC에 더한다. (106)
    - DIF에 AC의 값을 저장한다. (DIF = 106)
    - 프로그램을 종료한다.

​        ![K-130](https://user-images.githubusercontent.com/38898759/120760114-b59cb880-c54e-11eb-8760-a13ada02933f.png)



### 6.4 어셈블러

#### Assembler : First PASS

- Assembler

- - Source Program = 심볼릭 어셈블리어 프로그램
- - Object Program = 이진 기계어 프로그램



- Two pass assembler
- - 1st pass : 모든 사용자 정의 주소 기호를 이진 등가값(주소)과 상호 연관시키는 주소 구분 테이블을 생성한다.
  - 2nd pass : 이진 변환

![K-131](https://user-images.githubusercontent.com/38898759/120760526-2c39b600-c54f-11eb-8d45-e6c952b9faf9.png)



- Second Pass

- - 어셈블리 언어로 작성되어 있는 것들이 기계어로 번역된다. 이러한 번역과정에서 테이블 룩업 프로시저라는 단계를 거치게 된다. 

  - - 이러한 기계 명령어로 번역하기 위해 여러개의 테이블이 있고 그 테이블에서 내가 찾고자 하는 명령어가 있으면 그 어셈블리어를 그대로 테이블 오른쪽에 특정한 값으로 번역해준다.
    - 슈도 명령어 테이블
    - MRI 테이블
    - Non-MRI 테이블
    - 주소 심볼 테이블
    - ![K-132](https://user-images.githubusercontent.com/38898759/120761847-969f2600-c550-11eb-8744-227504f68e2d.png)

    



### 6.5 프로그램 루프

- 루프 : 여러 번 실행되는 일련의 명령으로, 각 명령마다 데이터 집합이 다르다.
- 100개의 숫자를 추가하는 포트란 프로그램
- - ![K-133](C:\Users\carto\Desktop\칼무리\K-133.png)

- 100개의 숫자를 추가하는 어셈블리 언어 프로그램

- - ![K-134](https://user-images.githubusercontent.com/38898759/120762155-f1388200-c550-11eb-8d7b-45ed0afb3644.png)

  - - ADS에 있는 오퍼랜드 주소를 로드한다. (AC = HEX 150)

    - PTR에 저장한다. (PTR = HEX 150)

    - NBR에 있는 값을 로드한다. (AC = -100)

    - CTR에 저장한다. (CTR = -100)

    - AC를 클리어한다. (AC = 0)

    - AC에 오퍼랜드를 추가한다. (AC = 75(10))

    - PTR를 1 증가시킨다. (HEX 151)

    - CTR를 1 증가시킨다. (CTR = -99)

    - LOP로 분기한다. (CTR이 0이 되면 반복문을 빠져나간다.)

    - AC에 있는 값을 sum에 저장한다.

      프로그램 종료



### 6.6 산술 및 논리 연산의 프로그래밍

- 산술과 논리 연산의 수행

- - 소프트웨어 수행

  - - 기계 명령어 집합을 사용한 프로그램의 연산 수행
    - 보통 연산은 명령어 집합에 포함되지 않는다.

  - 하드웨어 수행

  - - 하나의 기계 명령어의 컴퓨터 연산 수행

    

- 소프트웨어 수행 : 곱셈
- - 간단하게, 부호가 없는 숫자
  - 8비트 숫자 -> 16비트 product
  - ![K-135](https://user-images.githubusercontent.com/38898759/120765290-05ca4980-c554-11eb-998c-292ebb4146d8.png)



- 어셈블리 언어 프로그램 : 곱셈
- - ![K-136](https://user-images.githubusercontent.com/38898759/120765376-1d093700-c554-11eb-9ba5-f57a257a5439.png)
  - - E를 클리어한다. E=0
    - Y를 AC로 로드한다. AC = 000B (16)
    - 오른쪽으로 쉬프트 한다. E=1, AC =0005(16)
    - Y에 쉬프트된 값을 저장한다. Y=0005(16)
    - 0인지 확인한다. 0이 아니면 넘어간다.
    - ONE 으로 분기한다.
    - AC = 000F
    - P에 있는 값을 AC에 더한다.
    - AC 값을 P에 저장한다. P=000F
    - E를 클리어한다. E=0
    - X에 있는 값을 AC에 로드한다. AC=000F
    - 왼쪽으로 쉬프트한다. AC = 001E
    - X에 AC에 있는 값을 저장한다. X=001E
    - CTR에 해당하는 값이 0이면 다음으로 넘어간다. 
    - CTR = -7



- 소프트웨어 수행 : Double precision addition

- - 16비트 숫자 -> 32비트 product

  - ex) A X B -> C

  - - 하나의 배정밀도 숫자가 두개의 연속적인 메모리 영역에 저장되는 형태로 위치해 있다.
    - ![K-137](https://user-images.githubusercontent.com/38898759/120801791-974db180-c57c-11eb-88a5-74de68b9d1f6.png)

    ![K-139](https://user-images.githubusercontent.com/38898759/120802357-51451d80-c57d-11eb-9a46-fe64ba9da300.png)



- 어셈블리언어 프로그램 : 논리 연산
- - 기본 컴퓨터 명령어 : AND, CMA, CLA
  - OR 연산 프로그램 (드모르간 이론 사용)
  - ![K-140](C:\Users\carto\Desktop\칼무리\K-140.png)
  - - A 위치에 있는 오퍼랜드를 로드한다.
    - AC에 있는 값을 1의 보수한다.
    - TMP에 저장한다.
    - B에 있는 연산자를 AC에 로드한다
    - TMP와 AND 연산을 수행한다.
    - AC에 있는 값을 보수한다. (총 2의 보수)



- 어셈블리언어 프로그램 : 쉬프트 연산

- - 기본 컴퓨터는 순환 쉬프트를 가지고 있다.

  - - ![K-141](https://user-images.githubusercontent.com/38898759/120804024-22c84200-c57f-11eb-8a36-4a723e4a5287.png)
    - ![K-143](https://user-images.githubusercontent.com/38898759/120804339-7cc90780-c57f-11eb-8984-b6c77f164a55.png)

    ![K-144](https://user-images.githubusercontent.com/38898759/120822481-6a57c980-c591-11eb-980a-ffef7e9981ee.png)

    



### 6.7 서브루틴

- 프로그램에서 여러 번 사용할 수 있는 일반적이 명령어의 집합

- 서브루틴 링크 : 서브루틴으로 분기하여 메인 프로그램으로 복귀하는 절차

- ![K-145](https://user-images.githubusercontent.com/38898759/120823991-f28a9e80-c592-11eb-83a4-e664b24ee502.png)

- - X에 있는 값을 AC로 로드한다. AC = HEX 1234
  - SH4로 분기한다. HEX 102로 반환주소 저장.

  - 왼쪽으로 4번 순환시프트 한다. AC = 2340(16)
  - MSK와 AC에 저장된 값을 AND 연산을 수행한다. AC = 2340(16)
  - SH4로 분기한다. 102로 분기하게 된다.
  - Y 값을 로드한다. AC = 4321(16)
  - SH4로 분기한다. 
  - 4번 왼쪽으로 쉬프트 한다. AC = 3210(16)
  - MSK와 and 연산을 수행한다. AC = 3210(16)
  - 105로 분기한다.
  - AC에 저장된 값을 Y 위치에 저장한다. Y=3210(16)



- 서브루틴 파라미터와 데이터 링키지
- - 메인 프로그램과 서브루틴 사이의 파라미터와 데이터 연계
  - - 레지스터
    - 메모리 위치
  - 예제 : 메모리 위치를 통한 링크
  - - 논리 OR 연산을 수행하는 서브루틴
    - 두개의 파라미터가 필요
    - ![K-146](https://user-images.githubusercontent.com/38898759/120825652-90cb3400-c594-11eb-9cd9-d5777f8513a7.png)
    - X의 값을 AC로 로드한다. AC = 7B95(16)
    - OR로 분기하되, 복귀 주소를 저장한다.
    - AC의 값을 1의 보수를 취한다. AC = AC' = 846C
    - TMP에 AC의 값을 저장한다. TMP = 846C
    - OR에 있는 값을 AC에 로드한다. AC = 3AF6(16)
    - 보수연산을 한다. AC = C509(16)
    - AC와 TMP와 and연산을 수행한다. C509 AND 846C = 8408(16) = AC
    - 보수 한다. AC = 7BF7(16)
    - OR에 저장된 값이 0 이아니면 하나 증가시킨다. OR = 203 
    - OR가 저장하고 있는 주소값으로 분기한다.
    - AC 값을 Y에 저장시킨다. Y = 7BF7(16)
    - 프로그램 종료



- 데이터 블록 이동 예제
- ![K-147](https://user-images.githubusercontent.com/38898759/120827313-48147a80-c596-11eb-8fa4-4389ee68171a.png)





### 6.8 입출력 프로그래밍

#### 입/출력 프로그램

- ![K-148](https://user-images.githubusercontent.com/38898759/120827804-c83ae000-c596-11eb-8b6a-4220dea768e7.png)

- SKI = skip on input flag - input flag가 있으면 다음 명령어를 스킵한다.
- INP : AC에 입력받은 문자를 저장하라
- OUT : AC에 있는 것을 출력하라.
- CHR에 AC의 값을 저장하라.





- ![K-149](https://user-images.githubusercontent.com/38898759/120827834-d38e0b80-c596-11eb-854f-302573b0a8c9.png)
- CHR에 있는 값을 AC에 로드한다.
- output flag가 있으면 다음 명령어를 스킵한다.
- OUT : AC에 있는 값을 출력한다.



- 문자 조작
- - 서브루틴으로 2자를 입력하고 한 단어로 묶는다.
  - ![K-150](https://user-images.githubusercontent.com/38898759/120828430-7a72a780-c597-11eb-97de-7b70898a5c84.png)
  - input flag가 있으면 다음 명령을 스킵한다.
  - 문자를 입력 받는다.
  - 출력한다.
  - 왼쪽으로 4번 쉬프트한다.
  - 왼쪽으로 4번 쉬프트한다.
  - input flag가 있으면 다음 명령을 스킵한다.
  - 문자를 입력받는다.
  - 출력한다.
  - IN2의 간접주소로 분기한다.





- 타이핑된 문자들이 저장될때 연속적인 메모리에 저장된다. 연속되는 메모리 영역을 버퍼라고 부른다.
- ![K-151](https://user-images.githubusercontent.com/38898759/120829356-46e44d00-c598-11eb-8df0-0f62809aa943.png)
- ADS에 있는 값을 AC로 로드한다. AC = 500(16)
- PTR에 AC 값을 저장한다. PTR = 500(16)
- IN2로 분기한다. 문자 2개를 저장한다.
- PTR에 저장하고 있는 값의 주소에 AC의 값을 저장한다. 500번지에 저장하게 된다.
- PTR의 값을 증가시킨다.
- LOP로 돌아간다.



- 문자 조작 : Table lookup (두개의 단어를 비교한다)
- - 두번째 패스에서 두 개의 패스 어셈블러가 테이블 조회를 수행한다.
  - 테이블을 검색하여 표에 지정된 기호가 포함되어 있는지 확인한다.





인터럽트 서비스 루틴의 작업
\1. CPU 상태 저장
\- 프로세서 레지스터 및 플래그의 내용
\2. 인터럽트의 원인 파악
\- 설정된 플래그 확인
\3. 플래그가 설정된 장치 서비스(입력/출력 서브루틴)
\4. 프로세서 레지스터 및 플래그의 내용 복원
\5. 인터럽트 기능을 켭니다.
\6. 실행 중인 프로그램으로 돌아가기
\- 중단된 프로그램의 PC 로드



![K-152](https://user-images.githubusercontent.com/38898759/120832697-e7883c00-c59b-11eb-939a-6f867105109d.png)