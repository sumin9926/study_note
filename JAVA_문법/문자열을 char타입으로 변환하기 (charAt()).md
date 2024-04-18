
`Scanner`는 `char`타입으로는 입력 받을 수 없고 `String`타입으로만 입력 받을 수 있다.
`String`타입으로 저장된 ==문자열을 `char`타입으로 변환==하기 위해 `charAt()`를 사용하면 된다.

#### charAt( )
* `String`타입으로 저장된 문자열 중 **한 글자**만 선택해서 `char`타입으로 변환해줌
```java
String str=new Stirng();
char c='';

str="hello";
//str문자열에서 0번째 문자를 char 타입으로 변환
c=str.charAt(0); //charAt()의 괄호 안 숫자는 index번호. 

System.out.print(c);
```
↪결과: `h`
