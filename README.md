> 스터디용으로 제작한 페이지입니다. 

# Go 

**Go** 언어는 2009년 구글이 공개한 프로그래밍 언어로 간결하게 생산성이 높은 프로그래밍을 만들 수 있다.

**스터디 일정** 

| 날짜            | 주제                                                           | 과제            | 팀장        | 장소       |
| :-------------: | ------------------------------------------------------------ | -------------- | :---------: | :-------: |
| 2018.07.20 | [0. Go 소개](#0_go) <br> [1. 기본문법: 세미콜론, 주석, 중괄호, 들여쓰기](#1_basic)      |  |  혜진     | 회의실3  |
| 2018.07.24 | [2. 변수: 종류, 선언, 숫자사용](#2_var)  <br> [3. 문자열 기초: 길이, 연산, 수정](#3_str)                  |  |  관훈  | 회의실2 |
| 2018.07.24 | [4. 조건문&반복문: if, for,switch](#4_forstat)  |  |승혁| 회의실2 |
| 2018.07.27 | [5. 배열&슬라이스:배열슬라이스차이,복사,삽입,삭제](#5_slice)  <br> [6. 맵](#6_map)|  | 혜진 | 회의실3 |
| 2018.07.27 | 연습문제풀기: 디스커버리 Go언어(p108-110) + 추가예제     |                 |관훈 | 회의실3 |
| 2018.07.31 | [7.1. 함수 기초: 매개변수와 리턴값사용하기, 에러저장, 함수에 변수저장 등](#71_func)      |                 | 승혁 | 회의실2 |
| 2018.07.31 | [7.2. 함수 심화I: 값으로 취급되는 함수(클로저)](#72_func)     |                 | 혜진 | 회의실2 |
| 2018.08.07 | [7.3. 함수 심화II: 메서드(단순자료형, 문자열다중집항, 포인트리시버, 공개비공개)](#73_func)     |                 |관훈 | 회의실3 |
| 2018.08.07 | [8. 구조체: 사용법, 구조체-메소드 연결, 직렬화&역직렬화](#8_struct)               |                 | 승혁 | 회의실3 |
| 2018.08.10 | [9. 인터페이스: 정의, 커스텀프린터, 정렬과 힙, 빈인터베이스, 덕타입핑](#9_interface)   |                 | 혜진 | 회의실3 |
| 2018.08.10 | 10. 동시성: 고루틴, 채널, 동시성 패턴 등   |                 |    관훈         | 회의실3 |
| 2018.08.14 | 미니프로젝트1: To do list 만들기                   |                 |  승혁           | 회의실3 |
| 2018.08.17 | 미니프로젝트2: 웹크롤러 작성하기                    |                 |  혜진           | 회의실3 |
| 2018.08.20 | 미니프로젝트3: 채팅서버 작성하기                    |                 |  관훈       | 회의실3 |
| 2018.08.24 | 11.1. Go로 구현하는 블록체인-하이퍼레저                           |  | 승혁  | 회의실3 |
| 2018.08.27 | 11.2. Go로 구현하는 블록체인-이더리움                    |                 | 혜진 | 회의실3 |
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

 ## [4회차 스터디] 변수 & 문자열
### 5. 배열&슬라이스 <a name = "5_slice"></a> 
- 배열과 슬라이스의 차이점
  -1. C/C++와 Java의 배열과 다르게 Go의 배열은 values이다. 그래서 길이가 딱 정해져있고 Array를 복사하면, 원본과는 분리된 독립적인 파일이 생긴다(레퍼런스 타입 아님). 
  - 위의 이유로 함수로 사이즈가 큰 배열을 넘기면, 해당 함수는 배열의 포인터나 레퍼런스가 아닌 "복사본"을 가진다. 메모리 사용이 커질 수 있다.
  - 이 문제를 해결하기 위해 슬라이스를 사용한다, 실제로 스터디 교재에서도 슬라이스를 더 많이 쓰게 될 거라는 언급이 있다. 
  
	| 배열(Array)    | 슬라이스(Slice)  |
	| ------------- |---------------| 
	| 레퍼런스타입 X   | 레퍼런스타입 O  | 
	| 배열의 길이는 고정 | 훨씬 유연한 구조<br>(append함수로 resize 가능) | 
	| 해당 없음 | make함수로 메모리 초기화 | 
	

``` go
func main() {
	//배열 vs 슬라이스
	//배열명 := [길이]타입{구성요소}; var 배열명 [길이]자료형
	fruitArray := [3]string{"apple","banana","orange"}
	var fruitArrayCopy [3]string

	//복사
	fruitArrayCopy = fruitArray
	//복사한 녀석만 apple을 오렌지로!
	fruitArrayCopy[0] = "kiwi"

	fmt.Printf("fruitArray:%v\n", fruitArray)
	fmt.Printf("fruitArrayCopy:%v\n\n",fruitArrayCopy)

	//슬라이스
	//변수 := []자료형{구성요소,구성요소}; var 	변수명 자료명 []자료형
	fruitSlice := []string{"apple","banana","orange"}
	var fruitSliceCopy []string

	fruitSlice = append(fruitSlice,"plum")

	fruitSliceCopy = fruitSlice
	fruitSliceCopy[0] = "kiwi"

	fmt.Printf("fruitSlice:%v\n", fruitSlice)
	fmt.Printf("fruitSliceCopy:%v\n\n",fruitSliceCopy)
}

//결과값은?
fruitArray:[apple banana orange]
fruitArrayCopy:[kiwi banana orange]

fruitSlice:[kiwi banana orange plum]
fruitSliceCopy:[kiwi banana orange plum]

```

- 슬라이스에는.. 고생 좀 해보라는 것인지 따로 삽입 혹은 삭제가 빌트인 함수가 없다(•́ ̯•̀)
 - 삽입: 확 와닿지는 않지만 i번째 값이 두 번 복사가 되게 배열을 만들고, i번째에 원하는 값을 넣는 구조이다.
 
 ``` go
func main() {
	numSlice := []int{2,3,4,5}
	numSlice = append(numSlice, 0) //공간확보
	i := 0 //i번째에 넣는다 // 저장위치
	copy(numSlice[i+1:], numSlice[i:])
	fmt.Println(numSlice) // [2 2 3 4 5] copy 시행 이후numSlice[0]에 해당하는 2가 2번 생긴것을 확인할 수 있다.
	numSlice[i] = 1 //[1 2 3 4 5] numSlice[0] = 1 에 넣음
	fmt.Println(numSlice)
}
```


### 6. 맵 <a name = "6_map"></a> 
- 맵
  ``` go
	//변수명 := map[string]string{""}
	chatlog := map[string]string{"name":"승혁", "message":"안녕하세요"}
	var chatlogCopy = make(map[string]string)
	chatlogCopy = chatlog

	chatlogCopy["name"] = "관훈"
	fmt.Println(chatlog["name"])  //결과값: 관훈
	fmt.Println(chatlogCopy["name"]) //결과값: 관훈
	
	//chatlog["phoneType"] = "iPhone8" 
	//fmt.Println(chatlog) //map[message:안녕하세요 phoneType:iPhone8 name:관훈]

	//맵 key, value 삭제하기
	delete(chatlog, "phoneType")
	fmt.Println(chatlog) //map[name:관훈 message:안녕하세요]

	//맵 순회하기
	for key, value := range chatlog{
		fmt.Println(key,value) //message 안녕하세요 name 관훈
	}
	
  ```
 ### Q [4회차 스터디] 오늘 나온 질문 & 흥미로운 포인트
  - array와 slice를 가르는 요건이 make()인지? slice는 언제 make()를 해야하는지? 왜 하는지? 
  - 해당 변수의 메모리 초기화를 하는 역할로 파악된다. make()는 slices, maps, channels 에만 사용됨 ("three types represent, under the covers, references to data structures that must be initialized before use")
  - 왜 슬라이스에 용량 이상의 값을 넣어도 되는가? 슬라이스의 요소가 늘어나면 Go 런타임은 정해진 알고리즘에 의해 슬라이스의 용량을 늘리기 때문
  - 레퍼런스타입과 아닌 것들
  	*엄밀하게 map은 레퍼런스타입이 아니고 포인터라는 글이다. 사실, 아직 개념들이 정확히 안서서 흠.. 여기서 레퍼런스 타입은 copy의 구성데이터를 바꿨을 때, 원본의 데이터도 같이 바뀌는 경우를 의미한다(https://dave.cheney.net/2017/04/30/if-a-map-isnt-a-reference-variable-what-is-it)
	*계속해서 새로운 자료형이 나오면 추가할 것이다. 
	
	|   비레퍼런스타입    | 레퍼런스타입  |
	| ------------- |---------------| 
	| string, number, array| slice, map | 


 ### 7.1. 함수 <a name = "71_func"></a> 

 
 ### 7.2. 함수심화: 함수리터럴, 클로저, <a name = "72_func"></a> 
  - 클로저란? 내부함수에서 외부함수의 속성을 사용하는 것이다. 자바스크립트에서 고급 개념이며, Go에서도 다뤄진다. 
  - 예제로 우선 자바스크립트에서 내부함수가 외부함수인 title의 변수 정보를 활용하여 'coding everybody'를 출력해보자
   ``` javascript 
   //javascript 
   function outter(){
    var title = 'coding everybody';
    function inner(){
    	//함수내부에 title이 없으니, 외부에 있는 var title = ~ 를 활용하는 것을 클로저라고함 
        console.log(title);
    }
    inner(); 
}
outter();
   
   ```
   
   ``` go
   //golang 
   func main(){
	var title = "coding everybody"
	inner := func(){
	fmt.Println(title)
}
inner()
}
 ```

  - 클로저를 왜 사용하는지? 특징이나 [장점이 뭔지?](https://www.calhoun.io/5-useful-ways-to-use-closures-in-go/)
    - (1) 클로저를 활용하면, 특정 함수를 몇 번 사용했는지 알 수 있다는 장점이 자주 언급되었는데, 아래의 예제처럼 외부함수에 변수 i를 정의하고, 내부함수에서 i++를 넣어주면 된다. 클로저의 내부 함수로 익명함수(aka 함수리터럴)가 잘 쓰인다, 생각해보면 어차피 외부함수에서만 사용되는 것이기 때문에, <strong>굳이 이름을 가질 필요가 없지 않았나라는 생각이 든다.</strong> 
    
  ``` javascript 
   //javascript 
   function outter(){
    var title = 'coding everybody';
    i = 0
    //리턴된 함수의 생은 마감했다..
    return function(){
        i++
        console.log(title,i);
      }
    }
    //return 하면서 외부함수가 이미 죽었지만, 외부함수로 인해 파생된 내부함수에서 이미 사라진 외부함수에 접근하고 있고, 그 접근이 이뤄진다0.0
    inner = outter();
    inner(); //결과값: coding everybody 1
    inner(); //결과값: coding everybody 2
    inner(); //결과값: coding everybody 3
  
  ```
  ``` go 
  //golang 
  func main(){
	closure := outter()
	fmt.Println(closure()) //결과값: coding everybody 1
	fmt.Println(closure()) //결과값: coding everybody 2
	fmt.Println(closure()) //결과값: coding everybody 3
  }

  func outter() func() (string,int){
	 var title= "coding everybody"
	 i := 0
	 return func() (string, int) {
		i++
		return title, i
	}
   }
  
 ```
   - 클로저를 왜 사용하는지? Private Variables 
     - (2) Private Variables: 우선 아래와 같은 녀석도 클로저함수라고한다. 왜냐? <u>title은 외부에서 주어지는 매개변수이고, 이 title이 내부함수/메소드인 get_title, set_title에서 활용되는 글로벌 변수와 같은 역할을 한다</u>. 많은 사람들이 프로그램 개발에 참여하게 되고, 변수에 접근해서 마음껏 바꾼다면 프로그램이 맛이 갈 확률이 높아진다한다. 이를 방지하기 위해, 클로저 함수가 쓰인다. title에 접근하려면 반드시 get_title, set_title 메소드를 사용해야한다. 생활코딩을 보며 납득이 간다 간다..(*•̀ᴗ•́*)و해서 Go로 비슷하게 코드를 짰는데..  
 ```javascript 
 //javascript 
 //private variables?
//title에 접근하려면 get_title, set_title라는 메소드를 통해서만 접근가능
//다른 사람이 title이라는 변수를 어떤식으로 외부에서 사용해도, 해당 맥락에 영향을 주지 않는다.
function factory_movie(title){
    return {
        get_title : function(){
            return title;
        },
        set_title : function(_title){
            title = _title
        }
    }
}

title = '으헤헤헤헤헤' // 넌 아무런 영향도 줄 수 없지.ㅅ.

ghost = factory_movie("Ghost in the shell")
matrix = factory_movie("Matrix")

console.log(ghost.get_title())  //Ghost in the shell
console.log(matrix.get_title()) //Matrix

ghost.set_title('공각기동대')

console.log(ghost.get_title())  //공각기동대
console.log(matrix.get_title()) //Matrix

 ```
  - <strong>오류 일색이다</strong>. 여러가지 생각점이 일단 1) return으로 함수를 두개를 받는게 저런 형태로 받으면 되는지, 2) javascript처럼 함수 ghost의 변수로 넣고 활용할 때, ghost.get_title()로 쓸 수 있는지도 확실치 않구.. 좀 더 공부하면서 공부해봐야겠다(*문제를 해결해주는 사람에게 커피쿠폰을 주겠다).  

 ```go
 //go
package main
package main

import "fmt"

func main(){
	ghost := factory_movie("Ghost in the shell")
	fmt.Println(ghost.get_title())
	ghost.set_title("공각기동대")
	fmt.Print(ghost.get_title())

}

func factory_movie(title string){
	return{
		get_title := func(){return title};
		set_title := func(_title string){title = _title}
		}
	}
```

- 클로저를 왜 사용하는지? 자주하는 실수를 피할 수 있다! (결국 내부함수가 외부함수의 변수들에 접근할 수 있는 클로저의 속성을 활용!) 
     - (3) 예컨데 피보나치 수열(0 1 1 2 3 5 8 11 ...)을 코딩하려고 한다. 
 ```go
 //go
 func makeFibGen int {
 	f1 := 0
	f2 := 1
	f2, f1 = (f1+f2), f2
	return f1
 }
 
 func main(){
 	gen := makeFibGen()
 	for i:=0;i<10;i++{
	fmt.Println(gen())
	} 
 }
 
 ```
 
  - 위와 같이 코딩하면, 계속 1만 10번 나온다. f1 = f2 부분만 작용하고, 이후에 f1은 리턴되었고, return 밖의 업데이트된 f1도 f2도 참고할 수 없다. 이 때, 클로저함수를 사용하면 깔끔하게 문제가 해결 가능하다! <u>왜냐? 클로저 함수는 return한 이후에도 f1,f2 값을 활용할 수 있다.</u> 
  
 ```go
 //go
 func makeFibGen int {
 	f1 := 0
	f2 := 1
	return func() int {
	f2, f1 = (f1+f2), f2
	return f1
	}
 }
 
 func main(){
 	gen := makeFibGen()
 	for i:=0;i<10;i++{
	fmt.Println(gen())
	} 
 }
 
 ```  
  - 자바스크립트도 클로저를 활용하여, 피보나치 수열을 만들 수 있다. 클로저 파트에 대한 대부분의 예제와 설명을 [생활코딩 Javascript 클로저](https://opentutorials.org/course/743/6544)참고하여 재구성해보았다. 늘 감사한 생활코딩이다!  

```javascript
//javascript
function makeFibGen(){
    f1 = 0
    f2 = 1
    return function inner(){
        [f2, f1] = [f1 + f2, f2]
        return f1
    }
}

let result = makeFibGen()

for (let i=0;i<10;i++){
    console.log(result())
} 
```
 ### Q [5회차 스터디] 오늘 나온 질문 & 흥미로운 포인트
 -Go에서는 메소드와 함수를 구분한다. 객체지향형언어(Object-Oriented Programming)에서 class 내부에 정의된 함수를 메소드라 불렀다. 하지만, 엄밀하게 말하면 OOP가 아닌 Go에서 메소드란 리시버(receiver)를 가지고 있는 함수를 의미한다. receiver의 종류는 값을 가리키는 value receiver, 값이 저장된 주소를 알려주는 pointer receiver가 있다. Receiver points의 실제 값을 변경하고 싶을 때, point receiver를 사용하며, [A Tour of Go에 의하면 프로그래밍을 할 때, receiver 자체를 변경해야하는 경우가 많기 때문에 point receivers가 더 빈번하게 사용된다고 한다](https://tour.golang.org/methods/4). [다만, 기본적인 자료타입, 슬라이스, 작은 구조체의 경우 value receiver를 사용하는 것 또한 편리한 선택지란다.](https://stackoverflow.com/questions/27775376/value-receiver-vs-pointer-receiver-in-golang). [뭘써도 되도록 일관성 있게 쓰는 것이 좋다](https://golang.org/doc/faq)
 
 - 아래의 예제처럼 value receiver(v Vertex)로 Vertex 값을 받으면, Vertex값의 복사복을 만들어서 작업을 하는 효과가 발생한다. v.Scale(10)의 결과인 v.X = 3*10, v.Y = 4*10 그 결과 향후 v.X, v.Y가 지속적으로 30과 40으로 유지되는 것이 아니다. v.Abs()를 할 때는 다시 v.X와 v.Y는 3과 4이고 그 결과 Abs(제곱합의 평균)은 5가 나온다!    
 - 만약 v.X, v.Y가 지속적으로 30과 40으로 유지시키고 싶다면, 다시 말해 아예 v.X, v.Y를 Scale() 작업 이후의 값으로 고정시키고 싶다면 간단하게 Asterisk(*)를 넣어주면 된다. 그 경우 결과값은 sqrt((30)^2+(40)^2) = 50이다! 
 
 
  ```go
  package main
  import(
  "fmt"
  "math"
  )
  type Vertex struct{
      X,Y float64	
  }
  
  func (v Vertex) Abs() float64{
      return math.Sqrt(v.X*v.X + v.Y*v.Y)
  }
  
  func (v Vertex) Scale(f float64){ // 여기를 포인터 리시버인 (v *Vertex)로 변경하면 결과 값이 50이 나온다!
      v.X = v.X*f
      v.Y = v.Y*f	 
  }
  
  func main(){
  v := Vertex{3,4}
  v.Scale(10)
  fmt.Println(v.Abs())
  }
 
  ```
    

  
 - 비트연산 부호(<<): 멋져보이고 싶을 때 사용하는 비트연산 부호 << 자리수를 왼쪽으로 옮길 수 있다, >> 하면 자리수를 오른쪽으로 옮길 수 있다. 
  ```go
func main(){
 var a int8 = 3 // 3의 이진수로 표현하면 11 
 fmt.Printf("%08b\n",a) //%08은 여덟자리로 표현해주세요라는 것 11 -> 00000011
 fmt.Printf("%08b\n",a<<1) // 00000110
 fmt.Printf("%08b\n",a<<2) // 00001100
 fmt.Printf("%08b\n",a<<3) // 00011000
 fmt.Printf("%08b\n",a<<4) // 00110000
 fmt.Printf("%08b\n",a<<5) // 01100000
 
 var a int32 = 256
 fmt.Printf("%08b\n",a>>1) //10000000
 fmt.Printf("%08b\n",a>>2) //01000000
 fmt.Printf("%08b\n",a>>3) //00100000
 fmt.Printf("%08b\n",a>>4) //00010000
 fmt.Printf("%08b\n",a>>5) //00001000
 fmt.Printf("%08b\n",a>>6) //00000100
 fmt.Printf("%08b\n",a>>7) //00000010
}
 ```
 ### 7.3. 함수심화: 단순자료형, 문자열다중집항, 포인트리시버, 공개비공개 <a name = "73_func"></a> 
 ### 8. 구조체 <a name = "8_struct"></a> 
 
 
 ### 9. 인터페이스 <a name = "9_interface"></a> 
 
 ### 미니프로젝트1
1. nil 하고 router; http가 내장이라서 따로 정의해줄 필요가 없어서 nil, mux router는 외장이니깐, 따로 적어줌 
2. encoder(),decoder() 차이
3. &person인지
4. *http.Request 인지 http.Request

    
