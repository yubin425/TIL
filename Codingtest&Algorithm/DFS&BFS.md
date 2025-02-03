# BFS&DFS

## 큐/스택/재귀함수

### 스택 자료구조
- 먼저 들어 온 데이터가 나중에 나가는 방식의 자료구조 (선입후출)
- 입구와 출구가 동일한 형태라고 생각하면 된다. 

```java
import java.util.Stack;

Stack<Integer> s = new Stack<>();

s.push(1);
s.pop(2);

while(!s.empty()){
    System.out.println(s.peek() + " "); //그냥 출력만하고 pop은 안하는 경우 peek
    s.pop();
}

```

### 큐 자료구조
- 먼저 들어 온 데이터가 먼저 나가는 형식(선입선출)
- 입구와 출구가 모두 존재하는 터널과 같은 형태

```java
import java.util.Queue;
import java.util.LinkedList;

Queue<Integer> q = new LinkedList<>();
q.offer(1); //삽입
q.poll(); //삭제
while(!s.empty()){
    System.out.println(s.poll() + " "); 
}
```
- queue와 stack 둘다 자바 실무에서는 deque를 사용하기를 권장하는 것 같다. 

### 재귀 함수 
- 자기 자신을 다시 호출하는 함수
  