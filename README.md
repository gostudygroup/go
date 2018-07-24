> 스터디용으로 제작한 페이지입니다. 

# Go 

**Go** 언어는 2009년 구글이 공개한 프로그래밍 언어로 간결하게 생산성이 높은 프로그래밍을 만들 수 있다.

**스터디 일정** 

| 날짜            | 주제                                                           | 과제            | 팀장        | 장소       |
| :-------------: | ------------------------------------------------------------ | -------------- | :---------: | :-------: |
| 2018.07.20 | [0. Go 소개](#0_go) <br> [1. 기본문법: 세미콜론, 주석, 중괄호, 들여쓰기](#1_basic)      |  |  혜진     | 회의실3  |
| 2018.07.24 | [2. 변수: 종류, 선언, 숫자사용](#2_var)  <br> [3. 문자열 기초: 길이, 연산, 수정](#3_str)                  |  |  관훈  | 회의실2 |
| 2018.07.24 | [4. 조건문&반복문: if, for,switch](#4_forstat)  |  |승혁| 회의실2 |
| 2018.07.27 | 5. 배열&슬라이스:덧붙이기, 용량, 복사, 삽입,삭제  <br> 6. 맵: 맵사용, 집합, 한계  |  | 혜진 | 회의실3 |
| 2018.07.27 | 연습문제풀기: 디스커버리 Go언어(p108-110) + 추가예제     |                 |관훈 | 회의실3 |
| 2018.07.31 | 6.1. 함수 기초: 매개변수와 리턴값사용하기, 에러저장, 함수에 변수저장 등      |                 | 승혁 | 회의실2 |
| 2018.07.31 | 6.2. 함수 심화I: 값으로 취급되는 함수(함수리터럴, 고계함수, 클로저 등)        |                 | 혜진 | 회의실2 |
| 2018.08.07 | 6.3. 함수 심화II: 메서드(단순자료형, 문자열다중집항, 포인트리시버, 공개비공개)     |                 |관훈 | 회의실3 |
| 2018.08.07 | 7. 구조체: 사용법, 구조체-메소드 연결, 직렬화&역직렬화                      |                 | 승혁 | 회의실3 |
| 2018.08.10 | 8. 인터페이스: 정의, 커스텀프린터, 정렬과 힙, 빈인터베이스, 덕타입핑   |                 | 혜진 | 회의실3 |
| 2018.08.10 | 9. 동시성: 고루틴, 채널, 동시성 패턴 등   |                 |    관훈         | 회의실3 |
| 2018.08.14 | 미니프로젝트1: To do list 만들기                   |                 |  승혁           | 회의실3 |
| 2018.08.17 | 미니프로젝트2: 웹크롤러 작성하기                    |                 |  혜진           | 회의실3 |
| 2018.08.20 | 미니프로젝트3: 채팅서버 작성하기                    |                 |  관훈       | 회의실3 |
| 2018.08.24 | 10.1. Go로 구현하는 블록체인-하이퍼레저                           |  | 승혁  | 회의실3 |
| 2018.08.27 | 10.2. Go로 구현하는 블록체인-이더리움                    |                 | 혜진 | 회의실3 |
| 2018.08.31 | 미니프로젝트4: Go를 활용한 블록체인 프로젝트              |                 | 관훈 | 회의실3 |




스터디 커리큘럼 설계를 위해 [Discovery Go 언어](http://www.hanbit.co.kr/store/books/look.php?p_code=B5279497767)와 [가장 빨리 만나는 Go언어](http://pyrasis.com/go.html)를 참조하였습니다. 제가 분야 지식이 부족하여 일단 주요해보이는 것들을 넣었는데 스터디 리더가 공부를 하는 과정에서 빠진 내용 추가, 중요치 않은 내용은 삭제해도 좋습니다 :) 

## 스터디 방법

### Step 1) 매주 팀리더가 계획표에 해당하는 내용을 준비해온다. 

계획표를 만들 때, 활용했던 두 권의 책, 책의 설명이 부족하다면 추가적으로 넣는다. 

`Dos and Don'ts` <br>
✓ 흠.. 기본문법에 숫자형 내용이 들어가야겠는걸, 추가해서 준비해온다.      
✘ 문맥설명이 중요도에 대한 이해없이 책에 나온 코드만 똑같이 따라친다.

### Step 2) 스터디한 컨텐츠와 당시 나온 질문들을 잘 정리하여, 이 곳에 정리한다. 

## [1회차 스터디] Go 소개 & 기본문법
### 0. Go <a name = "0_go"></a> <br>
  - Go를 배워야하는 이유? [Fluidity & easy of construction](https://www.youtube.com/watch?v=FTl0tl9BGdc)
  - Go의 특징
    - 컴파일시 자료형이 결정되는 정적 타입
    - 별도의 가상머신이 필요없는 네이티브 바이너리
    - 때때로 인터프리터 언어가 준비 시간보다 빠른 컴파일어
    - 실행 파일 내에 존재하는 가비지 콜렉션(Garbage Collector)
    - CPU와 RAM에 부담이 훨씬 적은 고루틴(Goroutine)을 활용한 병행성(Concurrency) 확보 
    - 헤더파일을 없애고, 소스코드를 패키지화하여 변경된 부분만 컴파일
  
### 1. 기본문법: <a name = "1_basic"></a>
  - 세미콜론
  ``` go
  //마지막 구문의 세미콜론은 생략 
  fmt.Println("Hello, Go")
  ```

  - 주석
  ``` go
  //line comment
  
  /*
  block comment
  Java 주석과 동일하다
  */
  ```
  - 중괄호: 중괄호는 '절대 한 줄 띄지 말고' main과 if 뒤에 바로 붙쳐쓴다. Java처럼 한 줄을 띄면 에러가 난다. Go는 컴파일 중에 세미콜론(;)을 붙이기 때문!  
``` go
  //correct
  func main(){
  }
  
  //error
  func main()     //; 컴파일 중에 세미콜론이 자동으로 들어감
  {
  }
```
  - 들여쓰기: tab 사용, goplaygroud에서 사용할 때, 파이썬처럼 들여쓰기 규칙이 엄격하지 않은 것을 확인
  
 ### Q [1회차 스터디] 오늘 나온 질문 & 흥미로운 포인트
  - fmt 패키지는? 정형화(formatted)된 I/O 함수를 가지고 있는 패키지, 놀랍게도 펌트("fumpt")라 발음한다!
  - go파일이 실행될 때, main 함수에 정의되지 않은 함수가 있으면 아래쪽을 스캔해서 활용함(C에서는 불가능하다함). 이 점은 자바와 유사해보인다.  
  
  ``` go
package main

import "fmt"

func main() {
  a()
}

func a(){
 fmt.Println("abc")
}
```
  - 크로스 컴파일은 어떻게하는가? http://brownbears.tistory.com/68
  
  ## [2회차 스터디] 변수 & 문자열
### 2. 변수 <a name = "2_var"></a> 
  - 변수선언
  ``` go
  //선언하고 사용하지 않은 변수는 에러가 나옴! 
  이부분에 코드를 작성해주시면 됩니다! 
  
  ```

### 3. 문자열 <a name = "3_str"></a> 

 ## [3회차 스터디] 변수 & 문자열
### 4. 조건문 & 반복문 <a name = "4_forstat"></a> 
- 조건문
  ``` go
  //선언하고 사용하지 않은 변수는 에러가 나옴!  
  이부분에 코드를 작성해주시면 됩니다! 
  
  ```

