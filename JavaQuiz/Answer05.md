# 1. 조건문의 3가지 종류를 나열하고 설명하시오
조건문에는 for , while , do~while이 있다 
이러한 조건문들은 '조건'이 있어야만 실행가능하다
 - 문법 <br>
 1. for(변수선언&초기화;, 조건;, 증감;) {실행}
 ```java
 for(int i = 1;, i <=3, i++) {
     System.out.println(" Hello " + i);	
    }
=======================================
▶ 
Hello 1
Hello 2
Hello 3
```
2. while(조건) {반복하는 영역}
```java
int num = 0;

while(num <= 3) {
    System.out.println("Hello" + num);
    num++;
}
========================================
▶ 결과는 위 for문이랑 동일
```
3. do{실행} ~ while(조건) {반복하는 영역}
```java
int num = 0;
		
do {
	System.out.println("Hello" + num);
	num++;
}while(num <= 3);
========================================
▶ 결과는 위 예제들과 같음
```

※ while과 do while문의 차이가 있다면 while문은 조건이 만족되지 못하면 실행하지 않지만 do while문은 조건이 만족하지 않더라도 반드시 '한 번'은 실행되고 종료한다

<br>

# 2. 아래의 프로그램을 짜시오
 ## - 국어:80 수학:80 영어:60 평균을 출력하고 평균에 따른 '수우미양가'를 출력하시오 
```java
public static void main(String[] args) {
	int kor = 90;
	int math = 80;
	int eng = 60;
		
	int total = kor + math + eng;
	double avg = total / 3.0;
		
	System.out.println("3과목의 총점은: " + total);
	System.out.println("3과목의 평균은: " + avg);
		
	if(avg >= 90) {
		System.out.println("평균: " + avg + " '수'입니다");
	}else if(avg >= 80) {
		System.out.println("평균: " + avg + " '우'입니다");
	}else if(avg >= 70) {
		System.out.println("평균: " + avg + " '미'입니다");
	}else if(avg >= 60) {
		System.out.println("평균: " + avg + " '양'입니다");
	}else {
		System.out.println("평균: " + avg + " '가'입니다");
		}
	}
=============================================================
▶ 
3과목의 총점은: 230
3과목의 평균은: 76.66666666666667
평균: 76.66666666666667 '미'입니다
/* ★ 주의할점은 평균값을 구할때 double로 구한다는 것과 형변환(나는 여기서 3.0이라는 소수점을 부여해서 만들어줌)이 일어난다는 걸 캐치해야한다 ★ */
```
 ## - int num = 33 할당후 해당 숫자 짝수면 짝수 입니다 출력. 홀수면 홀수 출력
 ```java
 public static void main(String[] args) {
	int num = 33;
	if(num % 2 == 0) {
		System.out.println(num + "은 짝수 입니다");
	}
	else {
		System.out.println(num + "은 홀수 입니다");
	}		
}
=============================================================
▶ 33은 홀수 입니다
```

 ## - int num = 66 할당 후 2의 배수 이고 3의 배수이면, 해당 수를 출력하고 아니면  2의 배수 이고 3의 배수 가 아닙니다 출력
 ```java
 public static void main(String[] args) {
	int num = 66;
	if((num % 2 == 0)&&(num % 3 ==0)) {
		System.out.println(num);
	}
	else {
		System.out.println(num + "은 2의 배수이고 3의 배수가 아닙니다");
	}		
}
=============================================================
▶ 66
```
 ## - 80, 33 ,55 의 최대값을 출력하시오
 ```java
 // 방법 1
public static void main(String[] args) {
    int a = 80;
	int b = 33;
	int c = 55;
	int max = 0;
		
	if((a>b)&&(a>c)) {
		max = a;
	}else if((b>c)&&(b>a)) {
		max = b;
	}else {
		max = c;
	}
	System.out.println(max);
}
======================================================
// 방법 2
public static void main(String[] args) {
    int a = 80;
	int b = 33;
	int c = 55;
	int max = 0;
		
	if(a>b) {
		if(a>c) {
			max = a;
		}else {
			max =c;
		}
		max = a;
	    }
	else {
		if(b>c) {
			max = b;
		} else {
			max = c;
		}
	}
	System.out.println(max);	
}
======================================================
// 방법 3
public static void main(String[] args) {
	int a = 80;
	int b = 33;
	int c = 55;
		
	int max = a;
		
	if(b > max) 
		max = b;
	if(c > max) 
		max = c;
	System.out.println(max);
}

======================================================
// 방법 4 (삼항연산자이용)
public static void main(String[] args) {
	int a = 80;
	int b = 33;
	int c = 55;
		
	int max;
	max = a > b ? (a > c ? a : (b > c ? b : c)): b;
	System.out.println(max);
		
}
```
<br>

# 3. switch 문에서 '걸어서 하늘까지' 를 설명하시오
switch문은 break를 만나기 전까지 모든 실행문이 출력된다 
```java
int n = 3;
		
switch(n) {
	case 1:  
		System.out.println("Hello");
	case 2:  
		System.out.println("Java");
			case 3:  
		System.out.println("Ok");
			default:  
		System.out.println("Bye~");			
} System.out.println("Again Java");

▶  Ok 
    Bye~
    Again Java
//여기서 출력되는 값은 n이 3이기 때문에 3부터 시작해서 밑에 실행문이 다 실행된다 why? break가 없기 때문에

======================================================================
int n = 3;
		
switch(n) {
	case 1:  
		System.out.println("Hello");
	case 2:  
		System.out.println("Java");
	case 3:  
		System.out.println("Ok");
		break;
	default:  
		System.out.println("Bye~");
			
}
System.out.println("Again Java");
// ▶ 여기서 출력되는 값은 break를 만나 Ok , Again Java만 출력
```
- (switch문에서는 정수값만 오지만 String도 올 수 있다: String도 하나의 인스턴스로 이루어진 하나의 '값'이기 때문에 가능하다) 
- switch문에서의 default는 if문에서의 else와 동일한 성질
- break는 결국 실행 종료의 의미

<br>

# 4. - int num = -10 을 할당후 해당 정수에 대한 절대값을 출력하는 프로그램을 작성하시오
```java
int num = -10 ;
		
if(num < 0) {
	num = -num;
}
System.out.println(num);
======================================================================
▶  10
```

<br>

# 5. 반복문에서 while 문과 do while 문의 차이는?
while과 do while문의 차이가 있다면 while문은 조건이 만족되지 못하면 실행하지 않지만 do while문은 조건이 만족하지 않더라도 반드시 '한 번'은 실행되고 종료한다

<br>

# 6. for 문에서 for 문이 실행되는 순서를 설명하시오.
 1.변수의 선언과 초기화 <br>
 2.조건문 비교 <br>
 3.실행 <br>
 4.변수값 증감 <br>
```java
for(int i = 0; →; i++){
    System.out.prinln("Hello" + i);
}
/* int i = 0  → i <=100 → System.out.prinln("Hello" + i) → i++ → i <=100 → System.out.prinln("Hello" + i) → i++
조건이 만족할때까지 역삼각형으로 조건문 반복 단, 변수의 선언과 초기화는 한번만 이루어진다 */
```
<br>

# 7. 9단을 출력하는 프로그램을 만드시오.(while 문 사용할것)
```java
int i = 1;
		
while(i < 10) {
	int j = 2;		
	while(j < 10) {
		System.out.println(i + " * " + j + " = " +(i * j));
		j++;	
	}	
	i++;	
}
```		
<br>

# 8. 1부터 100까지의 합을 구하시오
```java
int sum = 0;
		
for(int i = 1; i <= 100; i++) {
	sum = sum + i;
}
System.out.println(sum);
=========================================
▶  5050
```
	
<br>

# 9. 1부터 100까지의 홀수들의 합을 구하시오
```java
int sum = 0;

for(int i = 1; i <= 100; i++) {
	if(i % 2 != 0) {
		sum = sum + i;
	}	
}
System.out.println(sum);
=========================================
▶  2500
```
<br>

# 10. 반복문에서의 break 와 continue 를 설명하시오
반복문에서의 break는 실행종료 continue는 실행을 계속하라는 의미이다 <br>
break를 사용하지 않는다면 반복문에서 무한루프를 돌 가능성이 크다 <br>
따라서 실행을 종료시키고 싶다면 break를 통해 실행 종료를 시켜줘야한다 
<br>

# 11. 아래를 프로그래밍 하시오.
  ## - 1과 1000 사이의 숫자중 3의 배수 이자 5의 배수인 첫번재 수는?
```java
int num;

for(int i = 1; i <= 1000; i++) {
	if((i % 3 != 0) || (i % 5 != 0)) {
 		continue;
	} else {
		num = i;
		System.out.println(num);
		break;
	}			
}
=========================================
▶  15
```
  ## - 1과 1000 사이의 숫자중 2의 배수 이자 3의 배수인 수는 모두 몇개인가?
```java
int count = 0;

for(int i = 1; i <= 100; i++) {
	if((i % 2 == 0) && (i % 3 ==0)) {
		count++;
	}else {
		continue;
	}
} System.out.println(count);
=========================================
▶  16
```
<br>

# 12. 화폐매수 구하기
  ## 126500 의 금액을 한국화폐으로 바꾸었을 때 각각 몇 개의 화폐가 필요한지 계산해서 출력하라
```java
int m500,m100,m50,m10,m5,m1;
int money = 126500;
int temp;
		
m500 = money /50000;
temp = money - (m500*50000);
		
m100 = temp / 10000;
temp = temp - (m100*10000);
		
m50 = temp / 5000;
temp = temp - (m50*5000);

m10 = temp / 1000;
temp = temp - (m10*1000);
		
m5 = temp / 500;
temp = temp - (m5*500);
		
m1 = temp / 100;
temp = temp - (m1*100);
		
System.out.println("50,000원권: " + m500 + "장");
System.out.println("10,000원권: " + m100 + "장");
System.out.println("5,000원권: " + m50 + "장");
System.out.println("1,000원권: " + m10 + "장");
System.out.println("500원: " + m5 + "개");
System.out.println("100원: " + m1 + "개");
=============================================================
▶  
50,000원권: 2장
10,000원권: 2장
5,000원권: 1장
1,000원권: 1장
500원: 1개
100원: 0개
```

		

