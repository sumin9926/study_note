[[DFS(깊이 우선 탐색)|DFS]] 차이점 참고

![[BFS 그래프 이미지.png|400]]

> [!tip] ==BFS(넓이 우선 탐색)==은 ==레벨 탐색==이라고도 한다.

>부모 노드(Level.0) 부터 말단 노드(Level.2)까지 왼쪽에서 오른쪽으로 순차 탐색.

```java
class Node{ 
    int data; 
    Node lt, rt; 
    public Node(int val) { 
        data=val; 
        lt=rt=null; 
    } 
} 
  
public class Main{ 
    Node root; 
    public void BFS(Node root){ 
		Queue<Node> Q=new LinkedList<>();
		Q.add(root);
		int L=0;
        while(!Q.isEmpty()){
            int len = Q.size();
			System.out.print(L+" : ");
            for(int i=0; i<len; i++){
                Node cur = Q.poll();
                System.out.print(cur.data+" ");
                if(cur.lt!=null) Q.add(cur.lt);
                if(cur.rt!=null) Q.add(cur.rt);
            }
			L++;
			System.out.println();
        }
    } 

```

+ **큐(Queue)** 를 활용하여 구현
+ **가장 짧은 경로**를 구할 때 사용(=최소 이동 간선 수 구하기 문제)
