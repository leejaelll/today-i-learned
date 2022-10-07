# DFS를 이용한 알고리즘 문제 풀이

### 문제: 1부터 N까지의 원소를 갖는 집합의 부분집합 구하기

입력 설명   
첫 번째 줄에 자연수 N(1 ≤ N ≤ 10)이 주어집니다. 

출력 설명   
첫 번째 줄부터 각 줄에 하나씩 부분집합을 출력예제와 같은 순서로 출력한다.

풀이 과정 코드
```jsx
function solution(n) {
  let answer = [];
  let checkArray = Array.from({ length: n }, () => 0);

  function DFS(depth) {
    if (depth === n + 1) {
      let temp = "";
      for (let i = 1; i <= n; i++) {
        // 1로 들어온 것들만 출력하기
        if (checkArray[i] === 1) temp += i + " ";
      }
      if (temp.length >= 1) answer.push(temp.trim());
    } else {
      // 집합에 포함시킨다.
      checkArray[depth] = 1;
      DFS(depth + 1);
      // 집합에 포함시키지 않는다.
      checkArray[depth] = 0;
      DFS(depth + 1);
    }
  }

  DFS(1); // DFS는 1부터 시작한다.
  return answer;
}
```

## ✅ 내일 할 일
1. 클래스(노드)를 활용한 DFS 풀이법으로 오늘 풀어본 문제 다시 풀어보기
