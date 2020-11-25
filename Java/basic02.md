# 변수와 데이터타입(형)
* 변수 : 변하는 수 
* 변수에는 정수와 실수가 존재
    * 실수에는 오차가 존재
    ```java 
    double num1, num2;
    double result;
    num1 = 1.0000001;
    num2 = 2.0000001;
    result = num1 + num2;
    System.out.println(result); 

    3.0000001999999997
    ```
* 아스키코드(American Standard Code for Information Interchange) 
    * 아스키코드란 CPU가 문자를 그대로 읽을 수 없기 때문에 문자에 번호를 매겨 '약속'한 표준코드 / 문자와 숫자의 일대일 매칭 <br> ex) 'A' - 65 '1' - 39
    * blank , 기호 , 숫자 모두 문자에 속한다
    * 문자  → 숫자 : 인코딩 <br> 숫자 → 문자 : 디코딩 
* 데이터 타입 '형' : Primitive Type + 참조형 <br>
boolean (1byte) : 참 & 거짓 <br>
char (2byte) : 문자 <br>
byte(1byte), short(2byte), int(4byte), long(8byte) : 정수 <br>
float(4byte), double(8byte) : 실수  <br>
참조형(4byte) : 메모리 주소를 참조

```java
int num1 = 10;
int num2 = 20;
System.out.println(num1 < num2); 
System.out.println(num1 > num2); // 연산값이 맞는지 CPU한테 물어보고 대답을 받아서 출력되는 과정
================================
true
false
``` 
<br>

# 2의 보수법
* 2의 보수법은 음의 정수를 표현하는 방법 <br>
  1. 양의 이진수에서 1의 보수를 취함 (더해서 1을 만드는것; 1을 보수해준다) <br>
  2. 1의 보수를 취한 이진수에 1을 더함
  3. 나온 결과값 + 양의 이진수 = 0 <br>
  ex) int num1 = -10; (10에 대한 2의 보수법을 취한 값이 num에 들어간다)

# 실수
* 실수를 사용할때는 오차로 인해 float 보다 double을 사용하는게 BEST!!
* 실수와 정수는 왜 데이터타입을 나눠 사용하는가? <br>
  : 실수와 정수를 사용하는 표현 방법이 다르기 때문이다
* 실수에는 왜 오차가 존재하는가? <br>
  : 실수는 0~1 사이에도 수가 무한히 많고 셀 수 없는데 실수라는 무한한 수를 유한한 memory에 올리려고 하니 실수를 다 담아내는데 한계가 발생! 따라서 무한한 실수를 올리기 위한 방법으로 실수의 범위를 정하고 출력을 원하는 값의 근사값으로 표현하는 방법이 유일 
  → 오차가 발생하는 이유
  
  *** (주의) <br>
  float은 소수점 이하 6자리 / double은 소수점 이하 15자리까지 제대로 출력이 가능 but! 연산을 하게 되면 double이라 하더라도 소수점 이하 세자리에서부터 오류가 발생하기도한다

 # 상수
 1. 정의 <br>
 : 상수란 1번만 선언이 가능하고 변하지 않는 수 <br>
 선언을 하고 값을 주면 초기화의 값을 바꾸지 못함 / 변수 ↔ 상수 
    * 변수명은 모두 대문자로 사용
    * 변수 앞에 final (상수키워드) 이 붙는 것
 ```java
 final int MAX_SIZE = 100; 
 ```

 2. 초기화 <br>
 : 초기화란 값을 할당하고 처음으로 메모리에 할당하는 것을 말한다 
 ```java
 final double PI; //변수 선언 
 PI = 3.1415; // 변수 초기화
 ```
 3. 활용 <br>
 : 상수는 중간에 값을 변경하면 안되는 경우에 사용 (값들이 정해져있는 것들에 대해 사용한다) <br>
 
 4. 리터럴 <br>
 : 자료형을 기반으로 표현이 되는 상수 , 값을 다이렉트로 메모리 할당하는 것 <br> - 리터럴은 정수는 'int' 실수는 'double'을 디폴트로 메모리에 할당하기로 "약속"
 ```java
 System.out.println(3147483647 + 3147483647); 
 //error : 리터털은 정수를 기본타입 int로 약속했는데 범위를 int의 범위를 넘었기 때문에 long으로 명시를 해줘야함

 System.out.println(3147483647L + 3147483647L); 
 
 - 실수형은 오류가 나지는 않음 (4byte로 잡고싶다면 float 'f'로 표시)
 System.out.println(3.000007 + 3.000008); 
 System.out.println(3.000007D + 3.000008D); // 명시하고 싶으면 'D' 또는 'd' 삽입
```
# 이스케이스 시퀀스
 '\b' '\t' '\n' '\r' : 특수문자 
 ```java
System.out.println("AB" + '\b' + 'C' ); 
System.out.println("AB" + '\t' + 'C' ); 
System.out.println("AB" + '\n' + 'C' ); 
System.out.println("AB" + '\r' + 'C' ); 
======================================
AC
AB  C
AB
(enter)C
CB
(enter)
```
* 이클립스에서 오류 발생 (결과값이 제대로 출력안됨) → terminal → javac 클래스명.java → java 클래스명 ; 결과값 확인가능(처음 cmd창에서 했던거랑 동일)

# ★형 변환 (Casting)
```java
short num1 = 11;
short num2 = 22;
short result = num1 + num2;
System.out.println(result); //error

# 오류 해결01
short num1 = 11;
short num2 = 22;
short result = (short)(num1 + num2);
System.out.println(result);

#오류 해결02
short num1 = 11;
short num2 = 22;
int result = num1 + num2;
System.out.println(result); 
````
→ error가 일어나는 이유 : 하드웨어적인 문제 <br>
short는 4byte로 cpu와 메모리 사이에 선을 16개만 사용해도되지만 하드웨어 특성상 선을 32개를 전부 사용하게 됨 ∴ int 보다 작은 정수형을 '연산할때'는 32개의 선을 한번에 쓰기 때문에 int 로 잡게되는 것 (int 보다 작은 범위는 어차피 32개 선을 다 사용하기 때문에 int로 쓰는게 좋다★)
```java
int num1 = 11;
int num2 = 22;
int result = num1 + num2;
System.out.println(result);
```
1. 자동형변환
- ★★★★★ 대전제 : 연산을 할때는 데이터 타입이 '반드시' 같아야한다 ★★★★★ <br>
; 연산할때 데이터 타입이 다르면 '무조건' 데이터 타입을 맞춰줘야함!! 그런데 출력할때 에러가 안난다? → '자동형변환'이 일어났다는 것
```java
int num1 = 50;
long num2 = 357125745L;
System.out.println(num1 + num2);  /* long형으로 맞춰지는것 
int로 맞추려면 long을 잘라야되는데 그건 말이안됨 ∴ long으로 맞춰지는것 */

float b = 10.98f;
long c = 10;
long result = b + c;/* error why? 1. float의 범위가 long보다 넓다 
                                  2. 정수로 맞추면 실수의 범위 즉 소수점 뒤에 있는 값들을 날리고 출력되기 때문에 
                                  실수로 맞출수 밖에 없음 (자동형변환은 원래의 값을 보존하는쪽으로 변환됨)
```
2. 명시적형변환(강제형변환) <br>
: 개발자가 직접 강제로 형 변환 시키는 것
```java
double pi = 3.14;
int result = pi; // double로 맞춰야하는데 int로 result 값을 넣으려니 에러남 
System.out.println(result);

#오류 해결

double pi = 3.14;
int result = (int)pi; // int 강제로 형 변환 단, 결과는 소수점 날리고 3이 출력된다
System.out.println(result);
```
```java
int a = 3;
int b = 4;
		
double result = a/b;
System.out.println(result); 
===============================
 0.0 /* a와b는 정수이기 때문에 나눈값을 더블로 담아도 뒤에 소수점 날림
정확하게 하려면 둘 중 하나를 명시적형변환 즉, double로 만들어주면됨 */

#오류 해결01

int a = 3;
int b = 4;
		
double result = (double)a/b;
System.out.println(result);

#오류 해결02

int a = 3;
int b = 4;
		
double result = a/(double)b;
System.out.println(result);
================================
 0.75
```
# 이진수, 8진수, 10진수 표현법
123 (10진수) <br>
0123 (8진수) : 1*8² + 2*8¹ + 3*8 <br>
0x123 (16진수) : 1*16² + 2*16¹ + 3*16 <br>
byte seven = OB111 or ob111  이진수 = 7  


