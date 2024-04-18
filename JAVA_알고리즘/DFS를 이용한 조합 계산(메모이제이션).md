
>[[DFS(깊이 우선 탐색)|DFS]]를 사용하여 [[조합(nCɾ)]]을 계산할 수 있다.
```java
static int[][] mm=new int[100][100]; //넉넉하게 메모리제이션 배열 생성    
  
public int combi(int n, int r){  
	//'n개 중 n개를 뽑는 경우'와 'n개 중 0개를 뽑는 경우'의 수는 1이다.
    if(n==r || r==0) return 1; 
    
    //이미 이전에 구했던 값인 경우(메모이제이션에 값이 저장 되어있음)
    if(mm[n][r]!=0) return mm[n][r];  
    else{  //메모이제이션에 값이 저장되어있지 않아서 구해야함(메모이제이션에 저장하기)
        return mm[n][r]=combi(n-1, r-1)+combi(n-1, r);  //조합 공식 활용
    }  
}
```
