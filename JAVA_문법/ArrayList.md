+ Arraylist는 재귀호출을 활용하 for-each문으로 사용할 수 있다.
```java
ArrayList<Integer> g=new ArrayList<>();
for(int i=0; i<5; i++){
	g.add(i);
}

public void dfs(int v){
for(int x: g.get(v)){ //재귀호출 사용해야함.
	System.out.println(x);
	dfs(x);
   }
}
```

+ 인접리스트로 활용
```java
ArrayList<ArrayList<Integer>> g = new ArrayList<ArrayList<Integer>>();
```