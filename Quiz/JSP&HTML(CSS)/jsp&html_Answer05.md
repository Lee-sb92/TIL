# 1. css 에서의 display 종류와 속성에 대하여 설명하시오
- block : 크기 지정이 가능하고 선언한 크기에 대해 공간을 차지함, 자동개행이 이루어짐! 
- inline : 크기를 지정해도 속성이 적용되지 않는다, 자동 개행이 이루어지지 않기 때문에 영역을 block처럼 차지하지 않음
- inline-block : inline요소 + block요소 , inline처럼 자동개행이 이루어지지 않지만 block처럼 크기 설정이 가능하다(크기를 설정한만큼 영역을 차지한다)
- none : 아예 화면에 출력하지 않는다 (보여주지 않는 것) 

# 2. px 과 em 의 차이는?
: 크기가 고정(절대단위)이냐 상대적이냐(상대단위)의 차이 
- px : 고정된 크기 단위 (장치에 따라 사이즈 **변경이 불가능**), 고정된 값 출력
	- 
	- 주로 컴퓨터 화면에서 사용
- em : 상대적인 크기 단위 (장치에 따라 사이즈 **변경이 가능**), 부모 요소나 다른 요소의 크기에 영향을 받아 상대적으로 크기가 변함
	- 주로 웹문서에서 사용
	- 1em = 12pt = 16px = 100%
	- em : M의 크기를 뜻함

>> 절대단위(px, pt, cm, mm, in, pc) / 상대단위(em, rem, %)

# 3. inline-block 태그의 종류는?
< button > , < select >, < input >, < textarea > <br>
▶ 태그 종류(block,inline) 링크 참조
- https://www.w3schools.com/css/css_display_visibility.asp
- https://calmdawnstudio.tistory.com/51

# 4. opacity 속성의 사용법은?
: opacity - 불투명도 설정하는 속성
>> [문법] opacity : 값 (값의 허용 범위 0~1 / default값=1)

# 5. display:none 과 visibility:hidden 의 차이는?
- display:none → 화면 출력을 아예 하지 않는 것 (영역설정X)
- visibility:hidden → 화면 출력을 하지 않지만 영역은 설정하는 것 (빈공간으로 보이지만 사실상 공간차지O)

# 6. https://www.youtube.com/watch?v=O-n1EjDEuIc 시청하기

# 7. 동적문서와 정적문서의 차이는?
- 동적문서 : 사용자로부터 받은 정보를 웹서버가 그대로 출력하는 것 / html
- 정적문서 : 사용자로부터 받은 정보를 토대로 **기능을 추가하여 출력하는 것** / jsp 

# 8. 아래 JSP 태그에 대해 설명하시오
## 지시자 / 주석 / 선언 / 표현식 / 스크립트릿 / 액션태그 
- 지시자 : 페이지 속성 <%@   %>
- 주석 : <%  --> , // , /* */ 
- 선언 : <%!   %>
- 표현식(출력) : <%=   %>
- 스크립트릿(java코드) : <%   %>
- 액션태그 : < jsp:action > < /jsp:action >

---
# Quiz 

## 1. 아래를 Servlet으로 작성하시오 (1,2번 테이블 정렬이 안되는데..)
![q1](https://user-images.githubusercontent.com/74290204/103401786-b12e3700-4b8d-11eb-9b9e-727e415471d7.PNG)

```java
package ex1231;

import java.io.IOException;
import java.io.PrintWriter;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

/**
 * Servlet implementation class oneInput
 */
@WebServlet("/oneInput")
public class oneInput extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    /**
     * @see HttpServlet#HttpServlet()
     */
    public oneInput() {
        super();
        // TODO Auto-generated constructor stub
    }

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
			request.setCharacterEncoding("UTF-8");
			/* response.setContentType("text/html;charset=EUC-KR"); */
			response.setContentType("text/html; charset=UTF-8");
			PrintWriter dan = response.getWriter();
			
			dan.println("<html><head><title></title></style></head>");
			dan.println("<body><h1>구구단 출력</h1>");
			
			for(int i = 2; i <10; i++) {
				dan.println("<table border='1'><tr>");
				for(int j =1; j <10; j++) {
					dan.println("<td border='1'>");
					dan.println( i + "*" + j + "=" + (i*j));
				}dan.println("<br></td>");
			}
			
			dan.println("</tr></table></body></html>");
	}

	/**
	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		// TODO Auto-generated method stub
		doGet(request, response);
	}
}
```
<br>

## 2. 1번 문제를 jsp로 작성하시오 
```jsp
<%@ page language="java" contentType="text/html; charset=EUC-KR"
    pageEncoding="EUC-KR"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
</head>
<body>
	<h1>구구단 출력</h1>
	
			<%
				for(int i = 2; i <10; i++) {
			%>      <table border="1"> // 행을 for문 돌릴때마다 하나씩 만들어야 되서 for문 안으로 들어와야함 
					<tr>
			<% 		
					for(int j = 1; j <10; j++) {
			%>
				<td border="1">
			<% 		
					out.println(i + "*" + j + "=" + (i*j));
					}out.println("<br></td>");
				}
			%> 
		</tr>
	</table>
</body>
</html>
```