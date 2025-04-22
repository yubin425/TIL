# 📚 Java 코딩테스트 자료구조 & 유틸 클래스 정리

---

## ✅ 1. ArrayList

### 설명
- 가변 길이 배열 (크기가 자동으로 늘어남)
- 인덱스로 접근 가능

### 주요 메서드
```java
ArrayList<Integer> list = new ArrayList<>();
list.add(10);             // 추가
list.get(0);              // 접근
list.size();              // 크기 확인
list.remove(0);           // 삭제
```

---

## ✅ 2. Collections

### 설명
- 리스트 관련 유틸리티 제공

### 주요 메서드
```java
Collections.sort(list);        // 오름차순 정렬
Collections.reverse(list);     // 역순
Collections.max(list);         // 최대값
Collections.min(list);         // 최소값
Collections.shuffle(list);     // 랜덤 섞기
```

---

## ✅ 3. HashMap

### 설명
- (Key → Value) 쌍으로 저장
- 빠른 검색 / 카운팅에 적합

### 주요 메서드
```java
HashMap<String, Integer> map = new HashMap<>();
map.put("apple", 3);
map.get("apple");              // 3
map.containsKey("apple");      // true
map.remove("apple");
```

---

## ✅ 4. HashSet

### 설명
- 중복 제거, 빠른 존재 여부 확인

### 주요 메서드
```java
HashSet<Integer> set = new HashSet<>();
set.add(5);
set.contains(5);   // true
set.remove(5);
```

---

## ✅ 5. PriorityQueue (Heap)

### 설명
- 우선순위 큐: 자동 정렬됨 (기본은 오름차순 → min heap)

### 기본 사용법
```java
PriorityQueue<Integer> pq = new PriorityQueue<>(); // min heap
pq.add(5);
pq.add(2);
pq.poll();  // 2
```

### 내림차순 (max heap)
```java
PriorityQueue<Integer> maxPq = new PriorityQueue<>(Collections.reverseOrder());
```

---

## ✅ 6. Stack

### 설명
- LIFO (Last In, First Out)
- 되돌리기, 괄호 검사, DFS 등에서 사용

### 사용법
```java
Stack<Integer> stack = new Stack<>();
stack.push(1);
stack.pop();     // 1
stack.peek();    // 최상단 값 확인 (제거 안 함)
```

---

## ✅ 7. Deque

### 설명
- 양방향 큐: 양쪽에서 삽입/삭제 가능
- 슬라이딩 윈도우, 회전 큐 문제에서 활용

### 사용법
```java
Deque<Integer> dq = new ArrayDeque<>();
dq.addFirst(1);   // 앞에 삽입
dq.addLast(2);    // 뒤에 삽입
dq.removeFirst(); // 앞 제거
dq.removeLast();  // 뒤 제거
```

---

## ✅ 8. Arrays.sort & Collections.sort

### 배열 정렬
```java
int[] arr = {3, 1, 2};
Arrays.sort(arr); // 오름차순
```

### 리스트 정렬
```java
Collections.sort(list);  // 오름차순

// 내림차순
Collections.sort(list, Collections.reverseOrder());
```

---

## ✅ 9. Math 클래스

### 주요 메서드
```java
Math.max(a, b);      // 최대값
Math.min(a, b);      // 최소값
Math.abs(x);         // 절댓값
Math.pow(a, b);      // 제곱
Math.sqrt(x);        // 제곱근
Math.ceil(x);        // 올림
Math.floor(x);       // 내림
```

---

## 🔁 정리표

| 도구 | 주용도 | 시간복잡도 | 비고 |
|------|--------|-------------|------|
| ArrayList | 동적 배열 | 접근 O(1), 삽입/삭제 O(n) | 인덱스 접근 편함 |
| HashMap | Key → Value | 삽입/검색 O(1) | 빈도수 세기 등 |
| HashSet | 중복 제거 | 삽입/검색 O(1) | 방문 체크, 유일성 보장 |
| Stack | 후입선출 | 삽입/삭제 O(1) | 괄호, 되돌리기 |
| Deque | 양방향 큐 | 앞뒤 삽입/삭제 O(1) | 슬라이딩 윈도우 |
| PriorityQueue | 정렬된 삽입/삭제 | 삽입/삭제 O(logN) | 최솟값/최댓값 꺼내기 |
| Collections | 정렬, 뒤집기 등 | - | ArrayList 보조 도구 |
| Math | 수학 유틸 | - | pow, abs, max 등 제공 |
```