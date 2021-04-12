---
layout: post
title: 3.5장 이진 코드
subheading: Binary Code
author: JunHo
categories: 컴퓨터구조
banner: https://bit.ly/32PAjtM
tags: 컴퓨터구조 computer 디지털논리회로 구조론 컴퓨터 개발 코딩 디지털 컴포넌트 아날로그 이진코드
sitemap :
  changefreq : daily
  priority : 1.0




---







# 3.5 Binary Code

---

## Code

- 유한 개의 원소로 구성된 집합의 원소들에게 서로 구분할 수 있는 유일한 수를 부여한 숫자
- Binary Code : 10진수를 2진수의 조합으로 구별할 수 있도록 조합한 부호



### Code 종류

숫자 코드

- 10진수에 0과 1로 구성된 코드를 부여한 것
- 이진화 십진 코드(BCD, Binary Coded Decimal)

문자 코드

- 문자를 숫자로 표현한 것
- ASCII code, Unicode



## Gray Code

- 한 숫자에서 다음 숫자로 올라갈 때 한 비트만 변함
- 즉, 연속된 코드를 비교하면 1bit만 다름
- 제어 계통에 사용

- binary code -> gray code

- - 상위 첫 비트는 그대로
  - 나머지는 이웃하는 상위비트와 XOR 연산
  - ![K-044](https://user-images.githubusercontent.com/38898759/114407987-f11ca580-9be3-11eb-8653-6936bf6db3b9.jpg)

  gray code -> binary code

  - 상위 첫 비트는 그대로
  - 나머지는 0이면 상위 비트와 같게, 1이면 상위 비트의 보수

- ![K-045](https://user-images.githubusercontent.com/38898759/114407994-f24dd280-9be3-11eb-9b72-e12a39a9e279.jpg)





## 이진화 십진 코드

- 10진수 기호(0~9)를 2진수로 표현
- 모두 10개이므로 최소 4비트 필요(2^3<10<2^4)



## 가중치 코드

- 자리수에 가중치에 따라 값 설정
- - BCD code(8421 code)
  - 2421 code : 9의 보수로 연산



## 가중치가 없는 코드

- 자리수의 가중치와 무관하게 설정
- - Excess-3 code : BCD+3 : 9의 보수로 연산
  - Excess-3 gray code





# Alphanumeric Codes

---

## 문자 코드

- ASCII(American Standard Code for Information Interchange) code
- - 7bits로 문자 표현
  - 128 문자(대, 소영문자, 숫자, 특수 기호 등)
- EBCDIC(extended BCD interchange code)
- - IBM 장비의 영자숫자 코드





# 3.6 Error Detection Code

ERROR : 정보를 전송 시 정보가 변질되는 것



## Error Detection Code

- 에러가 있는지 체크하는 코드

- 패리티 검사(parity check)

- - 정보 외에 별도의 에러 검출용 비트(parity bit)를 포함하여 에러가 있는지 검사
  - even parity / odd parity

  순환 중복 검사(Cyclic redundancy checks : CRCs)



## Error Correction Code

- 에러를 검출하고 정정하는 코드
- Automatic repeat request(ARQ)
- Hamming Code
- Convolutional code



