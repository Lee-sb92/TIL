# 조건문 ( if / else if )
## @ if
 - if(조건) { 실행영역 } ; 조건에는 반드시 'boolean'형 (true or false) 타입이 올 수 있는 조건이 와야함 
 ```java
 if(n1 > n2) {
     System.out.println("n1 > n2 is ture");
 }
 ```
 - if문 속에 문장이 하나일 경우 중괄호 { } 생략 가능 
 ```java
 if(n1 > n2)
    System.out.prinln("n1 > n2 is true");
```
- if else : 둘 중 한개는 반드시 '실행'함
```java
if(n1 == n2) {
    System.out.println("n1 == n2 is true")
} // 조건이 맞으면 실행
else {
    System.out.println("n1 == n2 is false")
} // 조건이 틀리면 실행
```
※ if문에서 else없이 if만 사용가능

  ## @ else if
  - else안에 if문이 또 들어가있는것과 같은 이치 
  - else if는 얼마든지 함수안에 추가 가능


* { } 영역 확인: 위치에 따라 결과 달라짐
---
# 삼항연산자 : 항이 세 개
- (조건문) ? 값1 : 값2 <br>
 (true? false?) ? true일때값 : false일때값
 ```java
 big = (n1 > n2) ? 5 : 4
 ===========================
▶ 5

int num = 66;
int big = ((num % 2 == 0) || (num % 7 == 0) ? 50 : 40);
    System.out.println(big);
 ===========================
▶ 50 ; 2의 배수를 만족하니까 true!!
```
---
# 난수 (임의의 정수)
```java
						    //몇개 	스타트값
int num = (int) (Math.random()* 6) + 1;

; 6개의 숫자를 랜덤으로 뽑고 시작은 1부터
```
- 적용ex) 1~6까지의 임의의 정수를 뽑아서 어떤 숫자가 나왔는지 출력하시오  
```java
int num = (int) (Math.random()* 6) + 1;
if(num == 1)
    System.out.prinln("1번입니다")
if(num == 2)
    System.out.prinln("2번입니다")
if(num == 3)
    System.out.prinln("4번입니다")
if(num == 4)
    System.out.prinln("4번입니다")
if(num == 5)
    System.out.prinln("5번입니다")
if(num == 6)
    System.out.prinln("6번입니다")
// 출력과정이 숫자가 랜덤으로 뽑히기때문에 출력결과도 랜덤결과에 따라 나타난다
```
---
# Switch / Break "switch에서 break까지
- switch(n) : n값은 기본적으로 '정수' / 실수로 들어오면 이 문법 쓸 수 X 
  - 단, 문자열을 담는 String은 가능(사실 String자체가 인스턴스이기 때문에 값으로 이루어진 함수라서 가능) 

    ```java
     switch(a) {
	    case "abc": 
		System.out.println("Simple Java");
			
	    default: 
		    System.out.println("Best Program Java");	
            } 
        System.out.println("Do you like Java?");    
        ```

- break : 실행 종료
 - default : 값을 주지 않거나 걸리는 실행문이 없을 때 출력되는 기본값 <br> 
(if elde구문에서 else와 비슷한 기능)

```java
int n = 1;
switch(n) {
    case 1:
        System.out.println("Hi Java");
    case 2:
        System.out.println("Ok");
    case 3:
        System.out.println("Bye");   
    default:
        System.out.println("Again Java");
} 
System.out.println("Good");
==============================================
▶  
Hi Java
Ok
Bye
Again Java
Good
/* break가 없기 때문에 다 출력되는 것! 
값을 1줬으니 1부터 (start지점이라고 생각하면됨) */
```
```java
int n = 1;
switch(n) {
    case 1:
        System.out.println("Hi Java");
    case 2:
        System.out.println("Ok");
         break; 
    case 3:
        System.out.println("Bye");  
    default:
        System.out.println("Again Java");
} 
System.out.println("Good");
==============================================
▶  
Hi Java
Ok
Good
/*  break가 걸려있기때문에  break 이후에 실행문은 출력하지않는다 
여기서 주의할건 값을 할당하지 않아도  break까지 실행문을 출력한다 */
```
# 반복문 ( for / while / do while )
  - 반복문은 조건문이 없으면 탈출할 수 X (반드시 조건문이 있어야함)
  - for문을 누가 더 잘이용하는지가 실력의 차이
  ## @ while 
  - 반복조건이 false일때까지 계속 실행
  ```java
  int num = 0;
  while(num < 5 ) {
      System.out.println("I like Java" + num);
      num++;
  } 
  ```

  ## @ do while  
  ```java
  int num = 0;		
  do {
	System.out.println("I like Java" + num);
	num++;
    }while(num < 5);
```
 => while문과 do while문의 차이 <br>
 while문은 조건문이 앞에 위치 do while문은 조건문이 끝에 위치한다 <br>
 따라서 while문은 조건문이 일치하지 않는다면 실행을 거치지않고 구문은 빠져나오게 되지만 do while문은 조건이 만족하지 않더라도 반드시 '한 번'은 실행을 거치게 된다 

  ## @ for 
  ; (세미콜론) -> 하나의 실행단위 
  ```java
  //1. 변수선언&초기화  2.반복조건  3.증감
  for(int i = 0;      i < 5;       i++) {
		//4.실행
	System.out.println("I love Java" + i);
}
```
★ for문의 실행순서 <br>
☞ 1.변수선언&초기화 → 2.반복조건 → 4. 실행 → 3.증감 → 2.반복조건 → 4. 실행 → 3.증감 <br>
: 조건을 만족시킬때까지 반복된다 (단, 변수선언&초기화는 처음 한번만 이루어진다/ 실행순서를 깃발모양으로 이루어진다고 기억!) <br>
 
 ※ 증감순서 주의 / for문 안에서의 변수는 for문 안에서만 유효하기 때문에 for문을 벗어나면 이용할 수 없기 때문에 for문을 실행한 후 이용하고 싶다면 for문 밖에서 선언해줘야한다 <br>즉 { } 실행영역을 잘 구분해서 사용!
 ```java
 //영희가 계좌에 500원을 넣으면 5일동안 이자 1원이 붙는다 
 int money = 500;
 
 for(int day = 1; day <= 5; day++) {
   money++;
 }
 System.out.println("영희의 통장 잔액은 : " + )
 ==============================================
▶  505
```

  ## * 반복문 → 무한루프 주의!
  - while(true) { }
  - for (;;) { }
  - do ~ while(true) { }

 ---
 # 반복&조건문을 활용한 문제

```java
// 1부터 100까지의 짝수합과 홀수합 구하기
 int a = 0;
 int b= 0;

 for(int i = 0, i<= 100, i++){
   if(i % 2 == 0){
     a = a + i;
   }
   else {
     b = b + i;
   }
 }
 System.out.println(a);
 System.out.println(b);
```

```java
/*1부터 100까지의 수 중에서 
짝수의 갯수와 홀수의 갯수 구하기*/
int evenCount = 0;
int oddCount = 0;

for(int i = 0, i <= 100, i++){
  if(i % 2 == 0){
    evenCount++;
  }
  else{
    oddCount++;
  }
System.out.println(evenCount);
System.out.println(oddCount);  
}
```

* 무한루프 주의하기 <br>
(breakf를 통해 무한루프 빠져나오기 & break는 조건문과 전혀 관련없음)
  * while_example
```java
int num = 0;
int count = 0;

while((num++) < 100){
  if((num % 5 != 0) || (num % 7 != 0))
  continue;
	count++;
		System.out.println(num);
} /* num++ 첫번째 실행이 끝난 후 증감 
따라서 0 < 100 하고 증감 if문에는 증감되고 들어가서 1로 조건문 비교 while과 for문은 좀 다름*/
```

```java
/* 6의배수이면 14의 배수인 가장 작은 
자연수 찾는 반복문 */

int num = 1;
		
while(true) {
	if(((num % 6) == 0) && ((num % 14) == 0))
		break;
	num++;
		}
```

```java
// 1 ~100 사이의 5의 배수이면서 7의 배수인 숫자와 개수 구하기
int num = 1;
int count = 0;

while((num++) < 100) {   
	if((num % 5 != 0) || (num % 7 != 0)) {
		continue;  
	}
	count++;
		System.out.println(num);		 
	}
	System.out.println("count: "+ count);	
  ```
