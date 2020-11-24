# JAVA 설치 <br>
* 패스변경하는 방법 
  - 제어판 → 시스템 및 보안  → 시스템  → 고급 시스템 설정  → 고급  → 환경변수  → path 편집 - 기존 경로 값 뒤 ;(세미콜론) 폴더경로 ctrl c + ctrl v

<br>

# "Hello Java" ; 이클립스말고 cmd로 출력하기
1. 파일명(클래스명과 동일).java 파일을 만든다 : 소스코딩
2. cd 경로 붙여넣기
3. javac 파일명.java : 컴파일을 한다(컴파일을 하면 .class가 생성됨)
4. java 출력결과 : 클래스를 실행시킨다

- cd ; Change Directory

<br>

# CPU & Memory
* 설치
  * 정의 : .exe(0101덩어리) 를 어딘가에 저장 <br>(하드디스크에 저장됨) 
* Memory가 왜 필요한가?
  * 설치한 프로그램을 실행하려면 .exe를 CPU에게 보내야하고 보내기 전에  .exe를 main memory의 특정공간에 올려야하기 때문임
  * memory의 주소는 중복되면 X <br> 따라서 OS(Operating System:.exe를 memory에 올리는 주체)이 memory를 관리한다 
      * ex) java파일을 실행 → java파일을 Main Memory에 올림 → Memory가 CPU에게 전송
