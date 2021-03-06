# 1. set classpath 에 대하여 설명하시오

set classpath란 class의 경로를 설정해주는 것을 말한다 <br>
(claspath는 자바가상머신의 경로탐색)
<br>

# 2. 절대경로와 상대경로에 대하여 설명하시오

- 절대경로란 JVM이 컴파일을 할 때 경로를 가장 최상위부터 찾아 실행하는 것
```java
C : \PackacgeStudy>set classpath=.;C:\PackageStudy\Myclass
```
- 상대경로란 JVM이 컴파일을 할 때 경로를 현재 디렉토리(자기자신)를 기준으로 찾아 실행하는 것
```java
C : \PackacgeStusy>set classpath=.;\Myclass
                                //↑ .이 현재디렉토리를 의미 한다
```
<br>

# 3. . 과 .. 의 차이는?

**.**  은 **'현재'** 디렉토리를 의미 <br>
**..** 은 **'이전'** 디렉토리를 의미 (상위폴더로 거슬러 올라가서 경로를 찾아줘 라고 이해하면 됨) 
```java

>cd. // 현재 디렉토리로 이동
>cd.. // 이전 디렉토리로 이동
>cd java_area // java_area로 이동

* cd = change directory
```

<br>

# 4. package의 용도는?
package는 하나의 폴더라고 생각하면 되는데 package안에는 여러개의 클래스를 둘 수 있지만 같은 이름의 클래스파일을 두는 것은 물리적으로 불가능하다 <br>
따라서 package를 만듦으로써 그런 물리적인 충돌을 막을 수 있다 <br>
(package의 이름을 따로 만들어주지 않으면 package는 default 패키지로 자동 생성된다)
```java 
// 다른 패키지의 클래스 파일을 사용하는 방법

"1. import한 후에 사용 (scanner같은거 import할때 주의)"
	**import com.bat.Circle;**           //이상한 주소에서 import하면 안된다.
	//import com.wxfx.smart.*;       //*은 이 패키지에 있는 전체를 가져오는 것을 의미
	**Circle circle = new Circle();**    //import했기 때문에 경로를 작성할 필요가 없다.
 
	/*
	하지만 두 경로의 Circle을 모두 이용할 경우 두 클래스를 모두 import하면 객체 생성시에 
	문제가 생기기 때문에 꼭 필요한 파일만 import해야한다. 
	*/

"2. 경로를 모두 작성"
	**com.bat.Circle circle = new com.bat.Circle();**
```


<br>

# 5. package 의 기본적인 명명법(이름짓는법)은?
패키지는 고객님의 회사 도메인을 사용해 작성하고 팀명까지 기재해 작성한다<br>
```java
www.bit.com / 팀명: Management Team

▶ com.bit.Management Team
// 도메인 역순으로 작성
```

# 6. 정보은닉에 대하여 설명하시오

클래스의 외부접근에 대해 제한없이 허용하게 되면 같은 이름의 변수나 클래스에 대한 충돌이 발생해 <br> 컴퓨터가 어떠한 클래스 안에 변수나 함수를 사용하는지에 대해 알아들을 수 없다 <br> 
따라서 이러한 충돌을 막기 위해 **클래스의 외부허용 접근에 대한 제한**을 두게 하는것을 **정보은닉**이라고 한다 <br> 

<br>

# 7. 접근제한자 4가지 종류에 대하여 설명하시오
정보은닉의 유형에는 크게 4가지로 분류할 수 있고 4가지는 **public, protected, default, private** 이 있다 

<br>

# 8.  .class 에서 붙일수 있는 접근 제한자 2개를 설명하고, 해당 접근제한자의 사용 목적은?

```java
    public : "다른" 패키지에서의 클래스 변수나 함수 사용 가능 
    default : "같은" 패키지안에서의클래스 변수나 함수 사용 가능 

*   public / default 클래스에 붙여 사용 가능
    public / protected / default / private 변수나 함수에 붙여 사용 가능
    // public 과 default만 클래스에 추가적으로 붙여 사용 가능한 것 
```
<br>

# 9. 가위, 바위, 보 게임 작성하시오
```java
package java_quiz_trainning01;

import java.util.Scanner;

public class javaOne {

	public static void main(String[] args) {
		// 가위바위보

		
		while(true) {
			
			System.out.println("가위바위보를 입력하세요");
			Game game = new Game();
			game.myturn();
			game.gameVS();
			
			System.out.println("계속하시겠습니까?");
			
			Scanner sc2 = new Scanner(System.in);
			char answer = sc2.next().charAt(0);
			
			if(answer == 'y' || answer == 'Y' || answer == '예') {
				continue;
			} else {
				break;
			}			
		}
	}
}

class Game {
	
	String myNum;
	int comNum;
	
	int mygame= 0;
	
	public void myturn() {
		
		Scanner sc = new Scanner(System.in);
		myNum = sc.next();
		switch(myNum) {
			case "가위":
				mygame = 1;
				break;
			case "바위": 
				mygame = 2;
				break;
			default:
				mygame = 3;
				break;
		}
		
		sc.close();
	}

	public void gameVS() {
		
		comNum  = (int)(Math.random()*3)+1;
		
		if(mygame == comNum) {
			System.out.println("무승부");
		} else if(mygame > comNum) {
			System.out.println("유저 승리!");
		} else {
			System.out.println("컴퓨터 승리!");
		}
	}	
}
```

<br>

# 9. 아래와 같이 계산기 프로그램을 작성하시오
```java
10 + 9   // 입력을 한칸씩 띄우도록 할것
10 + 9 = 19
계속하시겠습니까?
10 - 7
10 - 7 = 3
계속하시겠습니까?
```

```java
// Answer (me)
import java.util.Scanner;

public class NumMain {

	public static void main(String[] args) {
	
		Scanner scanner = null;
		
		while(true) {
		int num1, num2;
		
		scanner = new Scanner(System.in);
		System.out.println("연산할 숫자를 입력하세요");
		
		num1 = scanner.nextInt();
		String plus = scanner.next();
		num2 = scanner.nextInt();
		
		
		if(plus.equals(" + ") || plus.equals("+"))
			System.out.println(num1 + " + " + num2 + " = " + (num1 + num2));
		
		else if(plus.equals(" - ") || plus.equals("-"))
			System.out.println(num1 + " - " + num2 + " = " + (num1 - num2));
		
		System.out.println("계속하시겠습니까? (Y/N)");
		
		String answer = scanner.next();
		
		if(answer.equals("Y") || answer.equals("y"))
			continue;
		else
			break;
		} scanner.close();
	} 

}
```
```java
//Answer(teacher)  tip) while문 돌리는 기능까지는 함수에 넣을 필요가 없다; 
		  	고객이 있는걸 가지고쓰는거기 때문에 함수는 가져와쓸수있는 기능까지만 있으면된다

import java.util.Scanner;

public class NumMain2 {

	public static void main(String[] args) {
		
		while(true) {
			Scanner sc = new Scanner(System.in);
			System.out.println("숫자를 입력하세요");
			
			int num1 = sc.nextInt();
			char ch = sc.next().charAt(0); //연산기호에 대해서는 한개니까 char로 해도 상관없음
			int num2 = sc.nextInt();
			int result = 0;
		
			switch(ch) {
				case '+': {
					result = num1 + num2;
					break;
				}
				case '-': {
					result = num1 - num2;
					break;
				}
				case '*': {
					result = num1 * num2;
					break;
				}
				case '/': {
					result = num1 / num2;
					break;
				}
			}
			
			System.out.println(num1 + " " + ch + " " + num2 + " = " + result);
			
			System.out.println("계속하시겠습니까?(Y/N)");
			
			char c = sc.next().charAt(0);
			if(c == 'Y' || c == 'y')
				continue;
			else
				break;
		}

	}

}
```
```java
//Answer(teacher) - 위 코드 class활용 

>> main class

import java.util.Scanner;

public class NumMain2 {

	public static void main(String[] args) {
		
		Calculator calculator = new Calculator();
		
		while(true) {
			Scanner sc = new Scanner(System.in);
			System.out.println("숫자를 입력하세요");
			
			int num1 = sc.nextInt();
			char ch = sc.next().charAt(0); //연산기호에 대해서는 한개니까 char로 해도 상관없음
			int num2 = sc.nextInt();
			
			calculator.setNum1(num1); // Calculator 클래스의 set함수 호출 
			calculator.setCh(ch);
			calculator.setNum2(num2);
			
			/* Calculator calculator = new Calculator(num1, ch, num2); 처음할때 위에 디폴트 생성자 없고 이 함수 이용했음 
			위 방법은 set함수이용하는거고 이거는 생성자의 값을 넣어서 사용
			뭐가 더 좋은방법인가? 
			☞ 이 방법은 한번 실행하고 나며 객체를 또 생성 생성 생성 반복하는것(객체여러개로 메모리가 계속 쌓임)
			set함수는 하나의 객체에서 실행을 반복하는것의 차이
			따라서 set함수를 사용하는것이 메모리적인 부분에서 사용하는게 좋다
			(단, c언어에서는 메모리를 개발자가 관리했는데 자바에서는 JVM이 관리하기 때문에
			 필요없다 판단될때 알아서 정리한다 따라서 객체생성에 대해서 신경을 쓰지않아도되지만
			관리는 못하는 케이스도 있기 때문에 set함수를 이용하는게 GOOD!) */
			calculator.run();
			
			System.out.println("계속하시겠습니까?(Y/N)");
			
			char c = sc.next().charAt(0);
			if(c == 'Y' || c == 'y')
				continue;
			else
				break;
		}

	}

}
===========================================================================
>> calculator class

public class Calculator {
	
	private int num1;
	private char ch;
	private int num2;
	
	public int getNum1() {
		return num1;
	}

	public void setNum1(int num1) {
		this.num1 = num1;
	}

	public char getCh() {
		return ch;
	}

	public void setCh(char ch) {
		this.ch = ch;
	}

	public int getNum2() {
		return num2;
	}

	public void setNum2(int num2) {
		this.num2 = num2;
	}

	Calculator(int num1, char ch, int num2) {
		this.num1 = num1;
		this.ch = ch;
		this.num2 = num2;
	}
	
	public Calculator() {
		// 디폴트 생성자 만들어줌 "생성자가 하나라도 있으면 자동으로 만들어주지않기 때문에 만들어야함"
	}

	public void run() {
		int result = 0;

		switch(ch) {
			case '+': {
				result = num1 + num2;
				break;
			}
			case '-': {
				result = num1 - num2;
				break;
			}
			case '*': {
				result = num1 * num2;
				break;
			}
			case '/': {
				result = num1 / num2;
				break;
			}
		}
		
		System.out.println(num1 + " " + ch + " " + num2 + " = " + result);
	}

}
```


---
# ▶  java basic08 정리 참고


