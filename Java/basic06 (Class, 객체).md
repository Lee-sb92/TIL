
#  ★★★★★ 클래스 / 객체 ★★★★★
## @ 클래스
- 클래스(class)란 데이터와 기능 을 모아놓은 것 (변수와 함수의 구성)
    -  데이터 : 변수와 함수로 구성 / 기능 : 변수 컨트롤
- 클래스의 의미 
  1. 코딩상의 클래스 (Rectangle.java) 
  2. 컴파일 (Rectangle.class) -JVM이 읽어들임

- class 이름의 첫 글자 '대문자' 사용
- 함수명의 첫 글자는 '소문자' / 합성어의 첫 글자는 '대문자' ; ex) powerOfTwo
```java
// Rectangle 은 두 개의 변수 가로,세로 가지고있음 (height, width)


>> Rectangle이라는 class 생성 (함수생성)

public class Rectangle { /
	int height;
	int width;
	
	public int getHeight() { // getter함수(get변수명): 값을 가져오는것 
    	return height;
	}
	
	public void setHeight(int height) { // setter함수(set변수명): 파라미터를 통해 함수의 값을 전해주는것
		this.height = height; // this는 자기자신을 가리킨다
	}
	
	public int getWidth() {
		return width;
		
	}
	public void setWidth(int width) {
		this.width = width;
	}
	
	/* get&set은 변수마다 늘 만들어주는 짝꿍같은것 
    [alt + shife + s -> generate getters and stters (함수 생성 단축키) or 
    우클릭 -> source -> generate getters and stters ( ) ] */

	public int getArea() {
		return height * width;
	}
}

>> main 함수에서 Rectangle class 호출 (함수사용)

public class RecMain {

	public static void main(String[] args) {
		Rectangle rec = new Rectangle();
		rec.setHeight(10); // rec이 참조하고 있는 Rectangle 클래스에서 set함수를 실행시켜라
		rec.setWidth(10);
		
		System.out.println("사각형 넓이는: " + rec.getArea());

		rec.setHeight(5);
		rec.setWidth(5);
==========================================================================
▶ 사각형 넓이는: 100 
```

<br>

## @ 객체 

* 기본 8개의 데이터 타입(형) = 프리미티브 타입(primitive type) : boolean~double / 9개의 데이터 타입 = 프리미티브 타입 + 참조형(클래스명)
* new ; 객체 생성 키워드
```java
Rectangle rec = new Rectangle{();
// int a; 와 똑같음 따라서 rec은 Rectangle이라는 형을 타입으로하는 변수
```

* 참조형 ; 클래스명을 데이터타입으로 하고 주소를 담는 형 
  1. 크기 : 4byte (why? 자바는 32bit 시스템이다 따라서 메모리에서 JVM으로 한번에 보내는 주소의 최대값이 2의 32승이기 때문)
  2. 용도 : 메모리에 올린 첫 번째 주소를 참조한다

```java

>> Circle class

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

>> Main class

public static void main(String[] args) {

    Circle circle = new Circle();

    circle.setRadius(7); // 객체의 함수접근은 .으로 접근한다 
		
	System.out.println("원의 넓이는: " +circle.getCirclaArea());
}
```

▶ 위 코드 실행원리 
![객체원리 그림01](https://user-images.githubusercontent.com/74290204/100729220-d6ebe300-340b-11eb-8c2a-2d6dbcc8cf61.png)

 ### 위 과정을 객체라 한다 
 : 객체생성(=인스턴스 생성) ; .clss를 메모리로 올리는 행위
 * 함수는 기본 크기를 4byte로 잡기 때문에 위의 사진에서 4byte로 잡혀있는 것 <br>
 
 ```java
 Circle circle1 = new Circle();
 Circle circle2 = new Circle();
 Circle circle3 = new Circle();
 Circle circle4 = new Circle();
 Circle circle5 = new Circle();
 /* .class를 여러개 만드는 것이 아니라 하나의 .class를 복사해서 사용하는것 (주소를 참고하는 것 뿐이니까) 
 단! 각각의 주소는 다 다르게 방을 잡아서 설정 */
 ```
 
 ```java

>> BankAccount.class 생성

 public class BankAccount {
	
	int balance = 0; // 계좌를 담는데 int면 큰일남(long으로) 근데 연습문제니까 int로
	
	public int deposit(int amount) {
		balance += amount;
		return balance;
	}
	
	public int withdraw(int amount) {
		balance -= amount;
		return balance;
	}
	
	public int checkMyBalance() {
		System.out.println("잔액 : " + balance);
		return balance;
	}

>> BankAccount.class 호출

public static void main(String[] args) {
		
		BankAccount ref1 = new BankAccount();
		BankAccount ref2 = ref1   // ref2는 ref1이 참조하는 주소를 참조
		
		ref1.deposit(3000);
		ref2.deposit(2000);
		ref1.withdraw(400);
		ref2.withdraw(300);
		ref1.checkMyBalance(); 
		ref2.checkMyBalance();
=====================================================================
▶ 
잔액 : 4300
잔액 : 4300		
```
▶ 위 코드 실행원리 
![객체원리 그림02](https://user-images.githubusercontent.com/74290204/100729396-10245300-340c-11eb-8d51-b6c2def1aeb8.png)

// 실행되고나면 ref2는 방이 사라짐(OS에서 메모리 관리) 
위에서 보듯이 주소를 같은 주소를 참고하기 때문에 결과값에 영향을 미친다 

