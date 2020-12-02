
### EX
```java
// 1~100까지 소수 구하기
public static void main(String[] args){
  for(int i = 0, i <= 100, i++>){
    if(isPrimeNumber(i)) // 
      System.out.println(i);
  }
}
public static boolean isPrimeNumber  (int num) {          // boolean 타입이 오면 함수명 is 붙이고 시작
  if(num == 1) {
    return false;
  }
  for(int j = 2, 2 < num; j++) {
    if (num % j == 0) {
      return false;
    }
    return true;  // return 종료의 의미
  }
  
}
```
<br>

# null / String / 생성자 / Scanner

* null은 인스턴스의 관계를 끊어버림
* ref = null 만 선언해주면 오류남 ** 꼭 null을 체크하는 조건문을 줘야하고 null 은 참조형에서만 가능
* String :문자열이 String 인스턴스 클래스를 참조하는것 (따라서 우리가 보기에는 문자열을 나타내지만 함수를 보면 값으로 구성되어있다)

```java
if (ref == null) { return;}  //오류를 피하기 위한 조건문

int a = null // 이렇게 사용할 수 없음
```
* String ; 문자열을 다루는 class
```java
String name = "kim" ;
```

* 생성자 : class와 이름이 같은 함수 / 리턴값 (X) 
  * 리턴값이 없기 때문에 리턴타입 표시 X
```java
BankAccount = new BankAccount( ); // new 뒤에 붙는 걸 생성자라 부름
```

* ( ) 안에 함수인데 인자가 1개도 없고 함수를 따로 만들지 않았는데 호출하면 컴파일러에서 자동으로 넣어줌 '디폴트 생성자'
  * 디폴트 생성자는 개발자가 생성자를 한개라도 만들어놓으면 디폴트를 넣지 않기 때문에 오류 발생! 그래서 개발자가 디폴트 생성자를 따로 만들어줘야함 

* 생성자의 용도 
  * 값들의 초기화

* 생성자는 처음 값을 넣을때 
set은 값을 변경시킬때

```java
Scanner scanner = new Scanner(System.in); // (System.in) 키보드
int num = scanner.nextInt(); //실행 멈춤 콘솔창에 입력해주길 기다리는 상태
System.out.println("입력한 숫자는" + num); // 콘솔에 값을 입력해주고 나서 출력
```
* scanner 받을때 데이터 타입 맞춰줘야함
```java
String name = scanner.next(); // 
String name = scanner.nextLine();
int age = scanner.nextInt(); // int로 변수선언 하니까 scanner 뒤도 int
```
* scanner를 통한 반복문 활용 (yes / no)
```java
public static void main(String[] args{
  Scanner scanner;

  while(true) {
    scanner = new sacnner(System.in);
    System.out.print("이름: ");
    String name = sanner.next();

    System.out.print("나이: ");
    int age = scanner.nexyInt();

    Info info = new info (name, age); //
    info.show();

    System.out.println("계속하시겠습니까? (y/n)");

    char c = scanner.next().chaeAt(0);

    if(c == 'y' || c == 'Y') {
      continue;
    }
    else {
      break;
    }
    scanner close();
  
}
```

* 화폐 단위 개수 구하기
```java
public class Bill {
	
	int m500,m100,m50,m10,m5,m1;
	int temp;
	int money;
	
	public Bill(int money) {
		this.money = money;
	}
	
	public void printResult(){
		
		m500 = m500 / 50000;
		temp = money - (m500 * 50000);
		
		m100 = temp / 10000;
		temp = temp - (m100 * 10000);
		
		m50 = temp / 5000;
		temp = temp - (m50 * 5000);
		
		m10 = temp / 1000;
		temp = temp - (m10 * 1000);
		
		m5 = temp / 500;
		temp = temp - (m5 * 500);
		
		m1 = temp / 100;
		temp = temp - (m1 * 100);
		
		System.out.println("오만원권: " + m500 + "장");
		System.out.println("만원권: " + m100 + "장");
		System.out.println("오천원권: " + m50 + "장");
		System.out.println("천원권: " + m10 + "장");
		System.out.println("오백원: " + m5 + "장");
		System.out.println("백원: " + m1 + "장");
	}
	

public class Main02 {

	public static void main(String[] args) {
		
		Scanner scanner;
		while(true) {
			scanner = new Scanner(System.in);
			System.out.print("액수를 입력하세요: ");
			int money = scanner.nextInt();
			
			Bill moneyPrint = new Bill(money);
			moneyPrint.printResult();
			
			System.out.print("계속하시겠습니까? (y/n) ");
			System.out.println();
			
			char c = scanner.next().charAt(0);
			
			if(c == 'y' || c == 'Y')
				continue;
			else
				break;
		}
		scanner.close();
		
		}
```
