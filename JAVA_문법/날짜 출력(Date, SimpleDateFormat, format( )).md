
```JAVA
import java.text.SimpleDateFormat;  
import java.util.*;  
  
class Main {  
    public static void main(String[] args) {  
        Date today = new Date();  //Date 객체 생성
        SimpleDateFormat date=new SimpleDateFormat("yyyy-MM-dd"); //날짜 형식 지정
        SimpleDateFormat time=new SimpleDateFormat("hh:mm:ss a"); //시간 형식 지정
        System.out.println(date.format(today)); //지정한 형식으로 오늘 날짜 출력
        System.out.println(time.format(today)); //지정한 형식으로 현재 시간 출력
    }  
}
```


* **`Date` Class**
	* Package name: `java.util.Date` 
	* output: (example⇊)
	```java
	Date today = new Date();  //Date 객체 생성
	System.out.println(today); //오늘 날짜와 현재 시간 출력
	```
	↪`Thu Apr 25 22:32:01 KST 2024`


* **`SimpleDateFormat` Class**
	* Package name: `java.text.SimpleDateFormat`
	* output: (example⇊)
	```java
	Date today = new Date();//date 객체 생성 필수
	//y:연 m:월 d:일
	SimpleDateFormat date=new SimpleDateFormat("yyyy-MM-dd"); 
	//h:시 m:분 s:초 a:오전 오후  
	SimpleDateFormat time=new SimpleDateFormat("hh:mm:ss a"); 
    System.out.println(date.format(today));  
    System.out.println(time.format(today));  
	```
	↪`2024-04-25`
	↪`10:40:15 오후`
	```java
	SimpleDateFormat date=new SimpleDateFormat("yyyy/MM/dd");  //다양한 형식 예시
    System.out.println(date.format(today));  
	```
	↪`2024/04/25`
