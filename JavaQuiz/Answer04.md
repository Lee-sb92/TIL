# 1. 연산자의 결합방향과 우선순위에 대하여 설명하시오
- 결합방향은 순차적으로 ( 왼쪽에서 오른쪽 →) 이루어지지만 대입은 역순(←)으로 이루어진다 <br>
연산을 할때는 우선순위라는게 존재한다 <br>
+,- 는 우선순위 없이 순차적으로 계산되지만 * / 등이 같이 결합되어있을경우 * / 를 우선적으로 처리한다 
```java
    int num = 5 + 3 * 7 ; //  3*7을 하고 5를 더해준다 
```
  - 또한, * / 보다 더 먼저 처리해야 할것은 (  ) 이다 <br>
즉, 우선순위는 (   )  >  *  /  >  + -  <br>
 - (주의) 증감연산자를 이용할때는 증감연산자를 먼저 처리해준 후 다른 연산들을 처리한다
```java
    int x = 3;
    int y = x-- + 3 + x--;
    System.out.println(y);
========================
    ▶ 7
```
<br>

# 2. 1 초과 100 미만인가? 를 코딩해라
```java
int a = 11;
boolean result;
		
result = (a > 1) && (a < 100);
System.out.println(result);
=========================		
▶ true
```
<br>

# 3. 2의 배수 또는 3의 배수를 코딩해라
```java
int a = 33;
boolean result;
		
result = (a % 2 == 0) || (a % 3 == 0);
System.out.println(result);
==========================
▶ true
```

<br>

# 4. && 와  || 설명하시오
- && 는 and연산자 <br>
|| 는 or 연산자 <br>
<br>
: &&는 조건문의 결과가 모두 true여야 true값을 출력하고 한가지라도 부합하지 않는다면 false를 출력한다 <br>
||는 조건문의 결과가 하나라도 만족한다면 true 조건문 모두 false 여야 false를 출력한다 <br>
★ 단, 결과값을 출력할때 &&는 첫번째의 조건문이 false를 ||는 앞에 조건문이 true로 판별이 판별이 되면 뒤에 조건문을 거치지않는다
```java
    int num1 = 0;
    int num2 = 0;
    boolean result;
		
    result = ((num1 += 10) <0 ) && ((num2 += 10) > 0);
	    System.out.println("result = " + result);
	    System.out.println("num1 = " + num1);
	    System.out.println("num2 = " + num2 +'\n');
		
    result = ((num1 += 10) > 0) || ((num2 += 10) > 0);
	    System.out.println("result = " + result);
	    System.out.println("num1 = " + num1);
	    System.out.println("num2 = " + num2);
=========================================================
    ▶  result = false
	    num1 = 10
	    num2 = 0

	    result = true
	    num1 = 20
	    num2 = 0
```
<br>

# 5. 아래가 에러가 나는 이유를 설명하고, 수정하시오
```java
short num1
short num = -num
```

num은 지금 어떠한값도 갖고 있지않다 <br>
2byte 공간만 가지고 있는 num이라는 방만 존재할뿐 num이라는 방안에는 초기화가 되지않음 <br>
따라서 값도 없는 공간에 -를 붙이니 수식이 아예틀림 <br>
num에 값을 대입해줘서 수정 <br>
```java
// 수정
▶  short num = 3;
    short num1 = (short)-num;
```
- ★ 여기서 주의할점은 형변환이다. 우리가 눈으로 보기에는 연산이 이루어지고 있지 않아보이지만 -num 은 -1*num이다 <br>
따라서 연산이 이루어졌기때문에 num은 int형으로 바뀌게되고 형변환을 시켜줘야한다
<br>

# 6. 전위증가 연산자와 후위증가 연산자의 차이는?
- 전위증가(++num)는 다이렉트로 값을 +1증가 시키고 후위증가(num++)는 실행코드의 단위가 끝난 후 값을 +1 증가시킨다 <br>
같은 1을 증가시키지만 실행에 있어서 차이가 있다  <br>
주의할점은 후위연산자는 결과값이 증가되는 지점이 상황마다 다르기 때문에 코드를 분석할때나 코딩할때 주의해야한다 
```java
    int num  = 7;
    int result;
		
    result = (++num) -5; // num값 8 → 8-5를 result에 대입 (1이 바로 증가)
    System.out.println(result); // 3 출력
		
    result = (num++) -5; // num값 8 → 8-5 '3'result에 3 대입 후 num값 8+1 ; 9 (대입이 먼저 일어나고 증가) 
    System.out.println(result);  // 3 출력
```
<br>

# 7. 비트연산자 4가지를 설명하시오
- 비트연산자는 비트단위로 연산하는 것을 말한다 <br>
&: 비트단위의 and 연산자 <br>
^: 비트단위의 XOR 연산자 → 비트연산할때 같으면 '0' 다르면 '1' <br>
| : 비트단위의 or연산자  <br>
~ : not이라고 생각하면된다 → 비트 부호를 반대로 바꾼다 <br>

* -1은 비트단위로 표현하면 11111111 / 1은 00000000 


<br>

# 8. 쉬프트 연산자에 대하여 설명하시오
- '<<' ; 뾰족한 곳으로 이동 (오른쪽에서 왼쪽으로) 값은 2배가 증가한다 
- '>>' ; 뾰족한 곳으로 이동 (왼쪽에서 오른쪽으로) 값은 2로 나눈값으로 감소한다

<br>

# 9. 전위연산자와 후위연산자에 대하여 설명하시오
- 전위연산자는 연산할때 바로 값의 증감이 이루어지는 것 <br>
후위연산자는 연산할때 바로 값의 증감이 이루어지지 않고 실행코드의 단위가 끝난 후 증감이 이루어진다 <br>
전위연산자와 후위연산자는 값을 증가&감소시키는 행위 자체는 똑같지만 '언제' 증가&감소가 이루어지는가 다르다 
<br>

# 10. 아래의 출력값을 예측하시오
```java
class AssignSteResult {
    public static void main(String[] args) {
        int num1 = 10, num2 = 20, num3 = 30;
        num1 = num2 = num3;

        System.out.println(num1);	
        System.out.println(num2);
        System.out.println(num3);
    }
}
```

▶ 30 / 30 / 30 (num1 , num2, num3 모두 값은 30) <br>
<br>
why?  연산자는 결합 방향이 오른쪽에서 왼쪽으로 진행된다 <br>
따라서 위의 문장은 다음과 같다 <br>
num1 = (num2 = num3);        

<br>

# 11. 아래의 출력값을 예측하시오
```java
class SCE {
    public static void main(String[] args) {
        int num1 = 0; 
        int num2 = 0;
        boolean result;

        num1 += 10;
        num2 += 10;        
        result = (num1 < 0) && (num2 > 0);

        System.out.println("result = " + result);
        System.out.println("num1 = " + num1);
        System.out.println("num2 = " + num2 + '\n');
		
        num1 += 10;
        num2 += 10;        
        result = (num1 > 0) || (num2 > 0);

        System.out.println("result = " + result);
        System.out.println("num1 = " + num1);
        System.out.println("num2 = " + num2);
    }
}
```
▶  
result = false <br> 
num1 = 10 <br>
num2 = 10 <br>
<br>
result = true <br>
num1 = 20 <br>
num2 = 20 <br>

<br>

# 12. 아래의 출력값을 예측하시오
```java
class AddNum {
    public static void main(String[] args) {
        int result = 3 + 6;    
        System.out.println("3 + 6 = " + result);
        
        result += 9; 
        System.out.println("3 + 6 + 9 = " + result);
        
        result += 12;
        System.out.println("3 + 6 + 9 + 12 = " + result);
    }
}
```
▶ 	
3 + 6 =  9 <br>
3 + 6 + 9 = 18 <br>
3 + 6 + 9 + 12 = 30 

