# 1. 반복문 3가지의 무한루프 만드는 방법은?
## for(;;) { } / while(true) { } / do while(true) { }

<br>

# 2. 구구단 출력을 하시오
```java

for(int i = 2; i < 10; i++) {
	for(int j = 1; j < 10; j++) {
		System.out.println(i + " * " + j + " = " + (i*j));
		}
	}
```

<br>

# 3. 짝수단만 찍으시오
```java
// 방법 1 (가장 nice한 방법 ; 직관적이라서)

for(int i = 2; i < 10; i++) {

	if(i % 2 != 0) 
		continue;

	for(int j = 1; j < 10; j++) {
		System.out.println(i + " * " + j + " = " + (i*j));
	}
}

================================================================================================
// 방법 2

for(int i = 2; i < 10; i++) {

	for(int j = 1; j < 10; j++) {

		if(i % 2 == 0) {

			System.out.println(i + " * " + j + " = " + (i*j));
		}	
	}
}


================================================================================================
//방법 3

for(int i = 2; i < 10; i++) {

	if(i % 2 == 0) {

		for(int j = 1; j < 10; j++) {

			System.out.println(i + " * " + j + " = " + (i*j));
		}
	}		
}
```
<br>

# 4. 3의 배수인 단만 출력하시오
```java
for(int i = 2; i < 10; i++) {
	if(i % 3 != 0)
		continue;
			
	for(int j = 1; j < 10; j++) {
		System.out.println(i + " * " + j + " = " + (i*j));
	}
}
▶ 3,6,9단 출력

방법들 중에는 3번과 같은 방법들이 있음		
```
<br>

# 5. 아래의 Star를 찍으시오
## 5-1 )
★★★★★ <br>
★★★★★ <br>
★★★★★ <br>
★★★★★ <br>
★★★★★ <br>

```java
for(int i = 1; i <= 5; i++) {
	for(int j = 1; j <= 5; j++) {
		System.out.print("★");
	} System.out.println();
}
```

## 5-2)

★ <br>
★★ <br>
★★★ <br>
★★★★ <br>
★★★★★ <br>

```java
for(int i = 1; i <= 5; i++) {
	for(int j = 1; j <= j; j++) {
		System.out.print("★");
	} System.out.println();
}
// 1행일때 1개찍고 2행일때 2개찍고 하면되니까 i랑 같아지면서 별찍으면 됨
```

## 5-3)

★★★★★ <br>
★★★★ <br>
★★★ <br>
★★ <br>
★ <br>

```java

for(int i = 5; i >= 1; i--) {
	for(int j = 1; j <= i; j++) {
		System.out.print("★");
	} System.out.println();
}
```

## 5-4)

_________★ <br>
_______★★ <br>
_____★★★ <br>
___★★★★ <br>
_★★★★★ <br>

```java
// 방법 1

for(int i = 1; i <= 5; i++) {
	for(int j = 1; j <= i -1; j++) {
		System.out.print(" ");
	} 
	for(int j = 5; j >= i; j--) {
		System.out.print("★");
	}
    System.out.println();
}


================================================================================================
// 방법 2
for(int i = 5; i >= 1; i--) {
	for(int j = 5; j > i; j--) {
		System.out.print(" ");
	} 
	for(int j = 1; j <= i; j++) {
		System.out.print("*");
	}
	System.out.println();
}

```

## 5-5) ???????? 소스 봐도 모르겠음 ㅠㅠㅠ
____ ★  <br>
__ ★★★ <br>
_ ★★★★★ <br>
★★★★★★★ <br>

```java
for(int i = 0; i <5; i++) {
	for(int j = 4; j > i; j--) {
		System.out.print(" ");
	} 
	for(int j = 1; j <= i*2 +1; j++) {
		System.out.print("*");
	}
	System.out.println();
}
```
<br>

# 6. 함수는 어떻게 알아 볼수 있는가
 함수는 ( ) 대괄호를 보면 식별이 가능하다
 함수는 만들 줄 알아야하고 쓸 줄 알아야하는데 함수안에는 함수가 존재할 수 없으며 ( )안에는 매개변수가 오게 된다 <br> → 매개변수는 변수선언을 하고 바로 값을 할당할 수 없다 (초기화X) <br> 
 값을 할당(메모리에 올리는것)하는 것은 함수를 호출하는 쪽에서 가능하다 [값 = value]
 +매개변수(=파라미터=인자)는 여러개의 변수 선언이 가능

<br>

# 7. 함수는 어떻게 만드는가? (함수 정의)
```java
returnType 함수명 (parameter=매개변수=인자) 
	함수 호출 시 실행 될 내용;
}

/*
함수는 꼭 클래스 안에 만들어야한다 (메인함수 안에 만들지 말것)
함수명은 마음대로 지을 수 있음

Parameter = 인자, 매개변수. 파라미터에는 변수 선언이 온다.(메모리 할당)
파라미터에서 변수 초기화를 할 수 없다.
파라미터에는 변수의 선언이 여러개가 올 수도 있고, 없을 수도 있다.
*/


//retrunType이 void인 경우 -> 값을 반환하지 않음을 의미
void 함수명 (parameter) //Parameter  {
	함수 호출 시 실행 될 내용;
} 

//returnType이 void가 아닌 경우 (void가 아닌 9개의 데이터타입)
int 함수명 (parameter) //Parameter {
	함수 호출 시 실행 될 내용;
	return abcde;     //반드시 값의 반환이 있어야한다.
}
```
<br>

# 8. 함수는 어떻게 써먹는가?(함수 호출)
```java
함수명(value); <- 값으로 함수 호출  

//전달할 내용은 만들어진 함수의 파라미터의 데이터 타입과 일치해야한다
//메인함수의 경우는 만들고 정의하는것이며, 호출은 JVM이 자동으로 한다

1. 함수 호출 시 파라미터로 값(value)전달 
2. 함수 실행 시 메모리 방을 만들고, 함수의 실행이 끝나면 만들었던 방은 사라진다 (= 매개변수 소멸)
3. 새로운 함수를 호출하면 새로운 메모리 방을 만들고, 실행이 끝나면 똑같이 메모리 공간은 소멸
```
<br>

# 9. 아래의 함수를 만드시오

함수이름: starPrint <br> 
매개변수: type 1개 <br> 
기능: 매개변수에 3를 전달하면 3층 석탑, 5를 전달하면 5층석탑 <br> 
EX) 3전달시 3층석탑 <br> 
★ <br> 
★★ <br> 
★★★ <br> 

5전달시 5층석탑
★ <br> 
★★ <br> 
★★★ <br> 
★★★★ <br> 
★★★★★ <br> 

```java

// 3 넣은 결과

public static void main(String[] args) {
		
		starPrint(3);	
}
	
public static void starPrint(int num) {
		
        for(int i = 1; i <= num; i++) {
		    for(int j = 1; j <= i; j++) {
			    System.out.print("★");
		    }System.out.println();
	    }
    }
}

=================================================================
// 5 넣은 결과

public static void main(String[] args) {
		
		starPrint(5);	
}
	
public static void starPrint(int num) {
		
        for(int i = 1; i <= num; i++) {
		    for(int j = 1; j <= i; j++) {
			    System.out.print("★");
		    }System.out.println();
	    }
    }
}
```		
<br>

# 10. 아래의 함수를 만들고,해당함수를 호출하여 확인하시오
함수이름: getGrade() <br>
매개변수: double type 1개 <br>
리턴: 수 우 미 양 가 중 하나의 char 타입 <br>

```java

public static void main(String[] args) {
	
	int kor = 70;
	int math = 60;
	int eng = 90;
	 
	int total = math + kor + eng;
	double avg = total / 3.0;
	
	System.out.println(getGrade(avg))
}
public static char getGrade(double avg) {

	char a;   // '수우미양가' 를 담을 변수 선언
	 
	if(avg >= 90) {
		a = '수';
	}else if(avg >= 80) {
		a = '우';
	}else if(avg >=70) {
		a = '미';
	}else if(avg >= 60) {
		a = '양';
	}else {
		a = '가';
	}
		
	return a;
======================================================
▶ 미
```
	
<br>

# 11. 매개변수 하나를 받아 원의 넓이를 리턴하는 함수를 작성하시오
```java

// 1번 (me)
public static void main(String[] args) {
		
	circle(3.5);	
}
	
public static double circle(double r) {
		
	double circleRadius = r*r*Math.PI;

	System.out.println(circleRadius);
    
	return circleRadius;
}
=========================================
▶  21.991148575128552

// 2번 (teacher)
public static void main(String[] args) {

	double area = getCircleArea(10.0);
	System.out.println("원의 넓이는 " + area);
		
}
public static double getCircleArea(double r) {

	double area = r*r*Math.PI; // 아님 어차피 상수니까 final double PI = 3.14; 로 변수초기화 해줘도 가능
	return area;
=========================================
▶ 원의 넓이는 314.1592653589793
``` 
<br>

# 12. 매개변수 두개를 받아, 사각형의 넓이를 리턴하는 함수를 작성하시오
```java
public static void main(String[] args) {

	square(2.5, 3.5);	
}
	
public static double square(double width, double height) {
		
    double squareArea = width*height;

	System.out.println(squareArea);

	return squareArea;
}
=========================================
▶  8.75
```
 
