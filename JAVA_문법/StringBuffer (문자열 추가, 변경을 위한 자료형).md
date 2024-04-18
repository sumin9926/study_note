
### 1. append( )
* `StringBuffer`자료형은 `append()` 메서드를 사용해 문자열을 계속해서 추가할 수 있다.
```java
StringBuffer sb = new StringBuffer();  // StringBuffer 객체 sb 생성
sb.append("hello");
sb.append(" ");
sb.append("jump to java");
String result = sb.toString(); //StringBuffer를 String 자료형으로 변경
System.out.println(result);  // "hello jump to java" 출력
```
   ↪결과: `hello jump to java`

---
🔥**무조건 `StringBuffer`를 사용하는 것이 좋을까?**

> [!NOTE]
> 상황에 따라 다르다. 
> `StringBuffer` 자료형은 `String` 자료형보다 무거운 편에 속한다. 
>` new StringBuffer()`로 객체를 생성하면` String`을 사용할 때보다 메모리 사용량도 많고 속도도 느리다.  따라서 문자열을 추가하거나 변경하는 작업이 많으면 `StringBuffer`를, 적으면 `String`을 사용하는 것이 유리하다.


🔥 **`StringBuilder` 알아보기 (`StringBuffer`와 비슷한 자료형)**
* [[StringBuilder]]는 StringBuffer와 비슷한 자료형으로, 사용법도 같다.
```java
StringBuilder sb = new StringBuilder();
sb.append("hello");
sb.append(" ");
sb.append("jump to java");
String result = sb.toString();
System.out.println(result);
```
* StringBuffer는 멀티 스레드 환경에서 안전하고, StringBuilder는 StringBuffer보다 성능이 우수하다.


### 2. insert
* 특정 위치에 원하는 문자열을 삽입할 수 있다.
```java
StringBuffer sb = new StringBuffer();
sb.append("jump to java");
sb.insert(0, "hello "); //0번째 위치에 문자열 "hello" 삽입
System.out.println(sb.toString());
```
   ↪결과: `hello jump to java`


### 3. substring
* String 자료형의 substring 메서드와 동일
* substring(시작 위치, 끝 위치)와 같이 사용
* StringBuffer 객체의 시작 위치에서 끝 위치까지의 문자를 뽑아냄
```java
StringBuffer sb = new StringBuffer();
sb.append("Hello jump to java");
System.out.println(sb.substring(0, 4)); //0~4번 위치의 문자 출력
```
  ↪결과: `Hell`
  