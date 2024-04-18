* `BufferedReader`은 입력 받은 데이터가 **String형식**으로 고정된다. (입력 받은 데이터를 원하는 타입으로 가공하는 작업이 필요함)
*  **개행문자(`\n`)** 만 경계로 인식한다.
* `Scanner`보다 속도가 훨씬 빠르다.
* `Scanner`와 `BufferedReader`의 속도 차이 비교↓↓↓
![[Pasted image 20240413144951.png]]

* 버퍼 사이즈 ↓↓↓

|  Scanner  |     BufferedReader     |
| :-------: | :--------------------: |
| 1024 char | 8192 char(16,384bytes) |

---

> **사용 방법**

#### **1. ==BufferedReader==**

* **입력**: `readLine()`사용
* **반환값이 String으로 고정**되어있다. 다른 타입으로 입력 받기 위해서 **형변환** 필수
* 데이터는 **개행문자 단위(Line 단위)** 로 나눠진다.
* 예외처리 필요 
  ↪(1) `readLine()`시 마다 `try/catch`문으로 감싸주기
  ↪(2) `throws IOException`활용 👍

##### ✏️**BufferedReader 사용법**
```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in)); // 선언 String s = br.readLine(); 
int i = Integer.parseInt(br.readLine()); //정수형으로 형변환
```
![[Pasted image 20240413234948.png|500]]

##### ✏️**Line 단위가 아닌 공백 단위로 데이터 가공하기**
↪`StringTokenizer`의 `nextToken()`함수 사용: 데이터를 공백 단위로 구분하여 **순서대로 호출** 
↪`String.split()` 사용: 데이터를 공백 단위로 끊어 **배열에 저장**
```java
//선언
BufferedReader br = new BufferedReader(new InputStreamReader(System.in)); 

// StringTokenizer 
StringTokenizer st = new StringTokenizer(br.readLine()); 
int N = Integer.parseInt(st.nextToken()); 
int M = Integer.parseInt(st.nextToken()); 

// String.split() 함수 
String arr[] = s.split(" ");
```

---
**🔥`StirngTokenier`에 대한 추가 설명**
```java
//1. 띄어쓰기 기준으로 문자열을 분리
StringTokenizer st = new StringTokenizer(문자열);

//2. 구분자를 기준으로 문자열을 분리
StringTokenizer st = new StringTokenizer(문자열, 구분자);

/* 3. 구분자를 기준으로 문자열을 분리할 때 구분자도 토큰으로 넣는다. (true)
 * 구분자를 분리된 문자열 토큰에 포함 시키지 않는다. (false)
 * (디폴트 : false)*/
StringTokenizer st = new StringTokenizer(문자열 , 구분자 , true/false);

출처: [https://dev-coco.tistory.com/94](https://dev-coco.tistory.com/94) [슬기로운 개발생활:티스토리]
```
![[Pasted image 20240414235822.png|500]]

---
**🔥`read()`에 대한 추가 설명**

* `read()`는 스트림의 문자를 **유니코드**로 읽어들인 뒤 int값으로 반환한다.
* `IOException`의 `throw`를 필수적으로 해줘야한다.
* 문자를 하나씩만 가져올 수 있고 **아스키 코드**로 변환해서 가져온다. 
```java 
import java.io.*;

public class Main{

public static void main(String[] args) throws IOException{
  for(int i=0; i<10; i++){
    int num=System.in.read();
    System.out.print(num+" / ");
  }
 }
 
}
```
↪입력:`1234`
↪결과: `49 / 50 / 51 / 52 / 10 / `
※여기서 `10 / `은 숫자`1234`입력을 위해 누른 `Enter`이다. 


> [!tip] ↓↓↓아스키코드 표
> ![[Pasted image 20240414002438.png]]


#### **2. ==BufferedWriter==**

* `System.out.println( )` 대신 사용
* `System.out.println( )`처럼 출력과 개행을 동시에 해주지 않기 때문에 **개행**을 위해선 따로 `newLine()`  혹은 `write("\n")`을 사용해야 한다.
* 사용 후 `flushi()` 혹은 `close()`를 해주어야 한다.
  ↪ `close()`: 출력 스트림을 아예 닫음
  ↪ `flushi()`: 스트림을 비움(출력 후 다른 것도 출력 가능)

##### ✏️**BufferedWriter 사용법**
```java
BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out)); //선언 
String str = "abcdef"; // 출력할 문자열 
bw.write(s); // 출력 
bw.newLine(); // 줄바꿈 
bw.flush(); // 남아있는 데이터 모두 출력 
bw.close();
```

![[Pasted image 20240413233140.png|500]]