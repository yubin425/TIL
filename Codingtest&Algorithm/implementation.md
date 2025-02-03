# 구현

### 구현: 머릿속에 있는 알고리즘을 소스코드로 바꾸는 과정
- 풀이를 떠올리는 건 쉽지만 소스코드로 옮기기 어려운 문제들이 많음
- 예) 알고리즘은 간단하지만 코드가 엄~~청 길거나 / 실수 연산과 소숫점을 다루거나 / 문자열을 기준에 맞춰 끊거나 / 특정 라이브러리를 활용해야함 
- **시뮬레이션 유형, 구현 유형, 완전 탐색 유형** 등이 포함됨

### 문제 1. 3이 들어간 시각을 모두 세어라
- 정수 N이 입력되면 00시 00분 00초부터 N시 59분 59초까지의 모든 시각 중에서 3이 하나라도 포함되는 모든 경우의 수를 구하는 프로그램을 작성하라.
  
1. 첫시도   
```java
import java.util.Scanner;

Scanner sc = new Scanner(System.in);
int n = sc.nextInt();
int count = 45*(5+10)+15*60;
int result = 0;

for(int i=0;i<=n;i++){
    if(i%10==3){
        result += 3600;
    }
    else{result += count;}
}

```
- 일일이 세면 너무 오래걸릴 것 같아서 그냥 count에다가 값을 때려넣어버렸다. 
- 답은 맞게 나오지만, 알고리즘 문제인만큼 이걸 원하진 않았을듯하다. 
- 이 문제는 24*60*60 = 86,400가지의 경우의 수밖에 없으므로, 그냥 **완전 탐색**으로 풀어도 괜찮다. 

2. 예시 답안
```java
import java.util.Scanner;
Scanner sc = new Scanner(System.in);
int n = sc.nextInt();
int count = 0;

for (int i = 0; i <= n; i++) {  // 시간
    for (int j = 0; j < 60; j++) {  // 분
        for (int k = 0; k < 60; k++) {  // 초
            if (i % 10 == 3 || i / 10 == 3 || j % 10 == 3 || j / 10 == 3 || k % 10 == 3 || k / 10 == 3) {
                count++;
            }
        }
    }
}

System.out.println(count);

```
- 1초에 2천만번(파이썬 기준) 계산이 가능하다고 생각하면 되므로, 삼중 루프문을 너무 두려워 할 필요는 없을 것 같다.
  
### 문제 2. 왕실의 나이트
- 행복 왕국의 왕실 정원은 8x8 좌표 평면이다. 특정 한 칸에 나이트가 서있으며, 나이트는 L자 형태로만 움직인다. 정원 밖으로는 나갈 수 없다.
- 나이트는 다음과 같은 경우로만 이동이 가능하다
  - 수평으로 두 칸 이동한 뒤에 수직으로 한 칸 이동
  - 수직으로 두 칸 이동한 뒤에 수평으로 한 칸 이동
- 나이트의 위치가 주어졌을 때, 나이트가 이동할 수 있는 경우의 수를 출력하여라.
  - 행 위치는 1~8로 표현되며, 열 위치는 a~h로 표현된다. 
  - 입력 예시 : a1 
  - 풀이 시간 20분 | 시간 제한 1초 | 메모리 제한 128mb

```java
import java.util.Scanner;

Scanner sc = new Scanner(System.in);
String pos = sc.nextLine();
int x = pos.charAt(0) - 'a'+1;
int y = pos.charAt(1) - '0';

int[] dx = {2,2,1,1,-2,-2,-1,-1}
int[] dy = {1,-1,2,-2,1,-1,2,-1}

int count = 0;

for(int i=1;i<9;i++){
    for(int j=1;j<9;j++){
        for(int k=0;k<8;k++){
            if( x + dx[k]>0 && x + dx[k]<=8 && y+ dy[k]>0 && y + dy[k]<=8){ 
                count++;
            }
        }
        
    }
}

System.out.println(count);

```

### 문제 3. 문자열 재정렬
- 알파벳 대문자와 숫자(0~9)로만 구성된 문자열이 입력으로 주어진다. 이때 모든 알파벳을 오름차순으로 정렬하여 이어서 출력하고, 그 뒤에 모든 숫자를 더한 값을 이어서 출력하라. 

> 물론 ASCII 코드로 알파멧 대문자는 65~90까지, 소문자는 97~122까지 이므로 아스키 코드를 활용하는 것도 가능하지만, Character.isAlpahbetic()이라는 메소드가 있다고 한다. 활용하자.

```java
import java.util.Scanner;
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        ArrayList<Character> cr = new ArrayList<>();
        int sum = 0;

        for (char c : str.toCharArray()) {
            if (Character.isAlphabetic(c)) {
                cr.add(c);  // put -> add 변경
            } else {
                sum += c - '0';  // 숫자로 변환 후 더하기
            }
        }

        Collections.sort(cr);  // 알파벳 정렬

        for (char ch : cr) {  
            System.out.print(ch);  // 알파벳 출력
        }
        System.out.println(sum);  // 숫자 합 출력
    }
}

```