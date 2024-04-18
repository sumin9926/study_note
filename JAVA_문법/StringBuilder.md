
### 생성자
```java
StringBuilder sb=new StringBuilder(); //객체 선언
```
```java
StringBuilder sb=new StringBuilder("hello"); //문자열 바로 넣기도 가능
```

### 주요 메소드
|                               메소드                               |                                    설명                                     |
| :-------------------------------------------------------------: | :-----------------------------------------------------------------------: |
|                     **.append(String str)**                     |                                  문자열 추가                                   |
|               **.insert(int offset, String str)**               |                             offset 위치에 str 추가                             |
|              **.replace(index,index,String str)**               |                 첫번째와 두번째 파라미터로 받는 숫자 인덱스에 위치한<br> 문자열을 대체                 |
| **.substring(int start)**<br>**.substring(int start, int end)** |          파라미터가 하나라면 해당 인덱스부터 끝까지, <br>두개라면 시작점과 끝점-1 까지 인덱싱(출력)           |
|                  **.deleteCharAt(int index)**                   |                             인덱스에 위치한 문자 하나 삭제                             |
|                 .**delete(int start, int end)**                 |                         start 부터 end-1 까지의 문자 삭제                          |
|                         **.toString()**                         |                                String으로 변환                                |
|                         **.reverse()**                          |                              해당 문자 전체를 뒤집는다.                              |
|               **.setCharAt(int index, String s)**               |                            index 위치의 문자를 s로 변경                            |
|                   <br>**.setLength(int len)**                   | 문자열 길이 조정.<br> 현재 문자열보다 길게 조정하면 공백으로 채워짐, <br>현재 문자열보다 짧게 조정하면 나머지 문자는 삭제 |
```java
import java.lang.StringBuilder; 

public class sb { 
	public static void main(String[] args) throws IOException{ 
		StringBuilder sb = new StringBuilder("aaa"); 
		
		// 문자열 추가
		System.out.println(sb.append("bbb")); // aaabbb 
		System.out.println(sb.append(4)); // aaabbb4 
		
		// 문자열 삽입 
		System.out.println(sb.insert(2, "ccc")); // aacccabbb4 
		
		// 문자열 치환, 문자열 교체 
		System.out.println(sb.replace(3, 6, "ye")); // aacyebbb4 
		
		// 인덱싱, 문자열 자르기 
		System.out.println(sb.substring(5)); // bbb4 
		System.out.println(sb.substring(3, 7)); // yebb 
		
		// 문자 삭제 
		System.out.println(sb.deleteCharAt(3)); // aacebbb4 
		
		// 문자열 삭제 
		System.out.println(sb.delete(3, sb.length())); // aac 
		
		// 문자열 변환 
		System.out.println(sb.toString()); // aac 
		
		// 문자열 뒤집기 
		System.out.println(sb.reverse()); // caa 
		
		// 문자 대체, 문자 교체, 문자 치환 
		sb.setCharAt(1, 'b'); 
		System.out.println(sb); // cba 
	} 
}
```