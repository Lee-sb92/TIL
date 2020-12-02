# 1. 아래가 의도하지 않은 결과를 나타내는 이유를 설명하시오
```java
char ch = '가';
System.out.println(ch + '\n') 
======================================================================================
▶ 44042
```
- 연산을 할 때 char는 메모리에 '가'라는 문자를 올리는게 아니라 '가'에 해당하는 숫자코드를 올리게 된다 따라서 '가'의 문자가 숫자로 바뀌어(인코딩) 출력된 결과 
'\n' 도 마찬가지 ('가'와 같은 원리로 이루어짐) 그래서 + 연산을 해서 결과값이 숫자로 
```java
// '가'를 출력하기 위한 방법 

char ch = '가';
System.out.println(ch);
System.out.println(ch + "\n"); /* 1. 연산을 하게되면 컴퓨터는 데이터타입을 결정해 다르면 한쪽으로 맞춘다
				  2."\n" -> String타입 따라서 char vs String : String을 char쪽으로 맞출 수 없으니까 String으로 맞춘다
				  3. 따라서 ch를 출력할때 " " 를 붙여서 가 를 출력하는것 ("가" + "\n")으로
				  4. ex) System.out.println(7 +  8 + "\n") → 15 (개행) why? 7+8을 더한 15에 " " + 개행 */
=======================================================================================
▶ 가
```

<br>

# 2. 변수의 scope 는?

변수의 scope는 영역 or 범위를 의미한다 <br>
{중괄호} 안에서 즉 함수 내에서 사용되는 범위 안에서 유효하며 변수는 같은 영역안에서 같은 이름을 사용할 수 없다

<br>

# 3. 지역변수란? 
지역변수란 지역안에서 유효한 변수를 의미하며 그 지역은 변수가 선언된 함수 안을 뜻한다 <br>
지역변수는 그 변수를 벗어나면 다른 함수에 영향을 미치지 않는다 <br> (지역변수가 아닌 예외적인 변수는 인스턴스 변수가 있다)

<br>

# 4. 펙토리얼을 구하는 재귀 함수를 만드시오
```java

public static void main(String[] args) {
	System.out.println(factorial(4));
}
		
		
public static int factorial(int n) {
	if(n==0) 
		return 1;
	else 
		return n*factorial(n-1);	
}
```

# 5. 클래스의 구성요소는 무엇인가
클래스는 데이터와 기능으로 구성되어있다 
- 데이터 : 변수 + 상수 +  함수
- 기능: 함수를 컨트롤 하는 것 <br>

클래스는 2가지의 의미를 지닌다 
1. 코딩상의 클래스 (클래스명.java)
2. 컴파일 (클래스명.class) : JVM이 알아들을 수 있게 JVM언어로 바꾸어주는 것

<br>

# 6. 원의 넓이는 구하는 프로그램을 아래와 같이 작성하시오
## - 원클래스를 만들것
## - 메인 메소드를 가진 다른 클래스에서 원 객체를 생성할것
```java
// 원클래스 

public class Circle {
	
	int radius;
	
	public double getRadius() {
		return radius;
	}
	
	public void setRadius(int radius) {
		this.radius = radius;
	}
	
	public double getCirclaArea() {
		return radius*radius*Math.PI;
	}

}


// 원 객체 실행

public class CircleMain {

	public static void main(String[] args) {
		
		Circle circle = new Circle();
		circle.setRadius(7);
		System.out.println("원의 넓이는: " + circle.getCirclaArea());
	}

}
================================================
▶ 원의 넓이는: 153.93804002589985
```

<br>

# 7. 객체란 무엇인가?
객체(instance)는 '클래스'라는 틀을 통해 만들어낸 실체를 말한다 <br>
객체생성이란 .class를 메모리에 올리는 행위 
```java
Circle circle = new Circle
// circle이라는 변수가 Circle이라는 함수의 주소를 가리키고 있는 상태를 객체라한다
```

<br>

# 8. 아래의 클래스에 대하여, 메모리 그림을 그리시오
```java
Rectangle rec = new Rectangle();
 
public class Rectangle {
	int height;
	int width;
	
	public int getHeight() {
		return height;
	}
	
	public void setHeight(int height) {
		this.height = height;
	}
	
	public int getWidth() {
		return width;
	}
	
	public void setWidth(int width) {
		this.width = width;
	}
	
	public int getArea() {
		return width * height;
	}
	
}
```
![객체원리 그림03](https://user-images.githubusercontent.com/74290204/100724670-79a16300-3406-11eb-8861-ef575dd1b28e.png)


<br>

# 9. 클래스와 객체의 차이는 무엇인가?
클래스는 변수와 함수를 담는 하나의 큰 틀이라면 객체는 그 클래스를 메모리에 올리는 행위 / 클래스는 하나를 생성하고 객체는 여러개를 생성가능 why? 객체는 클래스의 주소를 참조만 할뿐이니까 
<br>

# 10.아래의 프로그램을 작성하시오
## - 1 부터 num 까지 합을 구하는 class 를 작성하도록 하시오
```java
public static void main(String[] args) {
	int sum = 0;
		
	for(int i =1; i <=100; i++) {
		sum = sum + i;
	} System.out.println(sum);
}
=========================================
▶  5050
``` 
<br>

# 11. 아래의 클래스를 작성하시오
```java
//Quiz

StraPrint strPrint = new StarPrint();

strPrint.printTriangle(3); 
System.out.println();
strPrint.printReverseTriangle(3); 
===============================
*
**
***

***
**
*
```
```java
//Answer

>> starPrint 클래스 생성

public class StarPrint {
	int n;
	
	public void printTriangle(int n) {
		for(int i = 1; i <= n; i++) {
			for(int j = 1; j <= i; j++) {
				System.out.print("*");
			}System.out.println();
		}
	}
	
	public void printReverseTriangle(int n) {
		for(int i = 1; i <= n; i++) {
			for(int j = n; j >= i; j--) {
				System.out.print("*");
				
			}System.out.println();
		}
	}
}

>> 메인 클래스에서 실행

public static void main(String[] args) {
		
		StarPrint strPrint = new StarPrint();

		strPrint.printTriangle(3); 
		System.out.println();
		strPrint.printReverseTriangle(3); 
	
	}
 ```
 # 12. 아래의 클래스를 작성하시오
```java
Gugudan gugudan = new Gugudan();
gugudan.printGugu(10);  //1단부터 10단까지 출력
gugudan.printGugu(20);  //1단부터 20단까지 출력
```

```java

>> Gugudan 클래스 생성

public class Gugudan {

int n;
	
    public void printGugu (int n) {
	    for(int i = 1; i <= n; i++) {
            for(int j = 1; j <= 9; j++) {
                System.out.println(i + " * " + j + " = " + (i*j));
            }
        }
	}
	
}
```
# 13. 아래의 BankAccount 객체에 대하여 그림을 그리시오
```java
BankAccount ref1 = new BankAccount(); 
BankAccount ref2 = ref1;
```
![객체원리 그림04](https://user-images.githubusercontent.com/74290204/100728507-fafaf480-340a-11eb-9fc9-35c2e36116ad.png)

* ref2는 ref1이 참조하는 주소를 그대로 참조한다 (B.A의 첫번째 주소 참조) <br>
 단 ref2는 출력이 되면 방이 사라지고 ref1이 참조하는 주소를 참조하기 때문에 출력결과값에 영향을 미친다
 -------------------------------------
 # ▶  java basic06 정리 참고
