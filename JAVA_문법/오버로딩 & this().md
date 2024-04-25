
`this()`: 자기 자신의 **생성자**를 호출할 수 있다.
```JAVA
class Member{
Sting name;
int age;
int grade;

Member(String name, int age, int grade){ //생성자1
	System.out.println("생성자 호출 name="+name+", age="+age+", grade="+grade);
	this.name=name;
	this.age=age;
	this.grade=grade;
}

Member(String name, int age){ //생성자2
	this(name, age, 50); //this()를 활용하여 생성자1 호출
}
}
```
