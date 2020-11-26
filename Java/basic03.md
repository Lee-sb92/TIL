# 연산자
* 연산자란 연산을 위해 사용되는 기호 
  * +, -, *, / 등이 있다
* 연산자에는 우선순위가 존재하고 우선순위는 ( ) > * / > + - 순으로 처리된다
* 연산자 처리방식은 대입을 제외하고 '왼쪽→오른쪽' 순으로 처리된다
<br>

  ## 1. 복합연산자
: +=, -=, *=, /=, %=
```java
    int num;
    num = num +1;
    num += 1;

// 두 연산은 같은 연산 (개발자가 일일히 쓰는게 귀찮으니 고슬링 아저씨가 이렇게 허용해줌)
```

```java
    short num = 10;
    num = (short)(num + 77L); // 강제 형변환 ; 실무에서 좋은코드 아님 why? 강제로 형변환을 쓰면 오차 생길확률도 높고 정밀도가 떨어짐
    int rate = 3;
    rate = (int)(rate * 3.5); // double로 바뀌면서 강제형변환 해줘야함 ; int로 형변환해줬으니 뒤에 소수점 잘린다
    System.out.println(num);
    System.out.println(rate);
===================================================
    int num = 10;
    num += 77L;
    int rate = 3;
    rate *= 3.5;
    System.out.println(num);
    System.out.println(rate);

→ 복합대입연산자는 형변환이 필요하지 않다(***)
```

  ## 2. 관계연산자
  * 관계연산자 boolean 타입 <br>
  : 이 말인 즉슨 관계연산자에 대한 결과값 (cpu에한테서 돌아오는 값)은 boolean타입으로 결과값이 출력된다 
  ```java
    int num1 = 11;
    int num2 = 22;
    boolean result;

    result = !(num1 != 0); //  '!' 는 not~
    System.out.println("0인가?" + result);

==========================================

▶ 0인가? false
```
(관계연산자 연산할때 주의할점!!)
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
===================================================

▶  result = false
	num1 = 10
	num2 = 0

	result = true
	num1 = 20
	num2 = 0
```
★ 이런 현상이 발생하는 이유? <br>
&& ; 앞뒤 둘다 true 나와야 참인데 앞에 먼저 false 나오면 결과적으로 false 될수밖에 없음 <br>
따라서 앞이 false로 결론이 나면 뒤에는 계산을 아예 하지도 않음 <br>
|| ; 앞뒤 둘 중 하나만 맞음 true 따라서 앞에 먼저 true 나오면 뒤에 계산안함  --> 내가 이걸 자꾸 간과함 <br>
  * 결론 : && → 앞이 'true'면 뒷문장 PASS / || → 앞이 'false'면 뒷문장 PASS 

  ## 3. 부호연산자
  ```java
    short num1 = 7;
    short num2 = (short)(+num1); /* 형변환을 해줘야하는이유: 우리 눈에는 안보이지만 얘도 연산을 하고 있음 정확히는 1*num1 
                                                           따라서 int형으로 바뀌니 형변환을 해줘야한다*/
    short num3 = (short)(-num2);// (-1) * num2
```
## 4. 증감연산자
: num = num + 1 → '++n / n++' 같은 말 ; 1을 증가시키고 변수에 값을 대입한다 <br>
num = num - 1 → '--n / n--' 같은 말 ; 1을 감소시키고 변수에 값을 대입한다 
```java
    int num  = 7;
    int result;
		
    result = (++num) -5; // num값 8 → 8-5를 result에 대입 (1이 바로 증가)
    System.out.println(result); // 3 출력
		
    result = (num++) -5; // num값 7 → 7-5를 처리하고 +1  result에 '3' 대입 (연산이 먼저 일어나고 증가) 
    System.out.println(result);  // 3 출력
```

```java
//증감연산자 중 후위연산자01
    int num = 5;
    System.out.print((num++) + " ");
    System.out.print((num++) + " ");
    System.out.print(num + "\n");
		
    System.out.print((num--) + " ");
    System.out.print((num--) + " ");
    System.out.print(num);
========================================
 ▶ 5 6 7
    7 6 5
```
```java
//증감연산자 중 후위연산자02
    int num = 5;
    num--;
    System.out.println(num);
=========================================
▶ 4
```
★주의) <br>
케바케로 상황마다 다르지만 여기 소스코드에선 하나의 실행코드의 단위가 끝나고 난 뒤 ' ; ' + 1이 증가

```java
// 실행코드의 단위가 위와 다른경우 

    int x = 10;
    int y = x-- + 5 + --x;/* 연산자 우선순위가 다르다! 
                          (x--)&(--x)먼저 연산됨 {(10--)+ 5} + (9) 10과 5를 더하고 난 후 실행단위가 한번끝남 따라서 더하고 나서 -1 */
    System.out.println(y); 
==========================================
▶ 23
```
## 5. 비트연산자
: 비트단위로 연산하는 연산자 
  - 종류 <br>
    & : 비트단위의 and연산자 <br>
    | : 비트단위의 or연산자 <br>
    ＾ : 비트단위의 XOR 연산자 ; 같을 때 '0' 다를 때 '1' <br>
    ~ : 비트를 반전시켜서 얻는 연산자 not /  1 → 0 0 → 1 <br>
    
```java
    byte n1 = 5; //00000101
    byte n2 = 3; //00000011
    byte n3 = -1;//11111111 
		
    byte r1 = (byte)(n1 & n2); // 00000001
    byte r2 = (byte)(n1 | n2); // 00000111
    byte r3 = (byte)(n1 ^ n2); // 00000110
    byte r4 = (byte)(~n3); // 00000000
		
    System.out.println(r1); // 00000001 '1'
    System.out.println(r2); // 00000111 '7'
    System.out.println(r3); // 00000110 '6'
    System.out.println(r4); // 00000000 '0'

** 1의 비트는 00000000 -1의 비트는 11111111
```
## 6. 쉬프트연산자 (<<, >>)
: 데이터를 비트 단위로 이동시켜 값을 증감시키는 연산자
-쉬프트 연산자는 한칸이동하면 빈 공간은 '0'으로 채운고 제일 앞 비트는 버린다 <br>
이동하면서 밀리더라도 java는 -일경우 최상의 부호비트는 보존한다
```java
byte num;
		
    num = 2; //00000010
    System.out.println((byte)(num << 1) + " ");//00000100 : 뾰족한쪽으로(왼쪽으로) 1칸이동 ; 2¹증가
    System.out.println((byte)(num << 2) + " ");//00001000 : 뾰족한쪽으로(왼쪽으로) 2칸이동 ; 2²증가
    System.out.println((byte)(num << 3) + " ");//00010000 : 뾰족한쪽으로(왼쪽으로) 3칸이동 ; 2³증가
		
    num = 8; //00001000
    System.out.println((byte)(num >> 1) + " ");//00000100 : 뾰족한쪽으로(오른쪽으로) 1칸이동 ; 2로 나눈다
    System.out.println((byte)(num >> 2) + " ");//00000010 : 뾰족한쪽으로(오른쪽으로) 2칸이동
    System.out.println((byte)(num >> 3) + " ");//00000001 : 뾰족한쪽으로(오른쪽으로) 3칸이동
```
(주의)
```java
    int num;
		
    num = 2;
    System.out.println((num << 1) + " "); 
    System.out.println((num << 1) + " "); 
=========================================
▶ 4
   4
왜 똑같은 결과값이 출력되었는가?
대입을 한게 아니고 비트로 똑같이 연산해서 출력했을 뿐이기 때문
```

# 문제01)
```java
// 양수이면 true 음수이면 false
    int num = 1000;
    boolean result;
		
    result = num > 0;
    System.out.println(num + "은 음수입니까? " + result);
=============================================================
▶ 1000 은 음수입니까? false
```
    
