
>**선언**
```java
import java.util.Queue;
import java.util.LinkedList;

Queue<자료형> 변수명=new LinkedList<>(); //사용자가 정한 자료형만 사용 가능
Queue 변수명=new LinkedList<>(); //어떤 자료형이든 사용 가능(복합적으로 사용 ok)
```


>**메서드**
#### 1. 삽입
```java
//반환값(boolean). 성공: ture 반환 ; 실패: Exception 발생
q.add(value); 

//반환값(boolean). 성공: ture 반환 ; 실패: false 반환
q.offer(value);
```

#### 2. 삭제
```java
//반환값(삭제된 value=맨 앞의 값). 공백 큐는 Exception("NoSuchElementException") 발생 
q.remove();

//반환값(boolean). 삭제 성공: true 반환 ; 삭제할 값 미존재: false 반환 
q.remove(삭제할 value);

//반환값(삭제된 value=맨 앞의 값). 공백 큐는 null반환
q.poll();
```

#### 3. 맨 앞의 값 출력(삭제x)
```java
//반환값(head value). 공백 큐는 Exception("NoSuchElementException") 발생
q.element();

//반환값(head value). 공백 큐는 null반환
q.peek();
```

#### 4. 큐 초기화(공백 큐)
```java
q.clear(); //반환값 없음
```

#### 5. 큐 크기
```java
q.size(); //큐 내부 요소의 개수 반환(int)
```

#### 6. 공백 큐인지 확인
```java
//반환값(boolean). 공백: ture 반환 ; 공백 아님: false 반환
q.isEmpty();
```