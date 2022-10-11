
# Stack
 - LIFO(Last In, First Out)
 - 스택은 "쌓다"라는 의미로, 데이터를 **차곡차곡 쌓아 올린 형태** 의 자료구조이다.

### Stack의 사용 사례
>  웹 브라우저 방문 기록 (뒤로 가기)
> 실행 취소(undo)
> 역순 문자열 만들기
> 후위 표기법 계산


### Class로 구현하기
```jsx
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}

class Stack {
  constructor() {
    this.first = null;
    this.last = null;
    this.size = 0;
  }
  push(value) {
    let newNode = new Node(value);
    if (!this.first) {
      this.first = newNode;
      this.last = newNode;
    } else {
      let temp = this.first;
      this.first = newNode;
      this.first.next = temp;
    }
    return ++this.size;
  }

  // stack의 pop - 맨 뒤의 요소를 제거하는 것
  pop() {
    if (!this.first) return null;
    let temp = this.first;
    if (this.first === this.last) {
      this.last = null;
    }
    this.first = this.first.next;
    this.size--;
    return temp.value;
  }
}
```


## ✅  내일 할 일
- 큐(Queue) 개념 정리하기
- 스택 관련 알고리즘 문제 오전시간에 풀기
- 제로베이스 알고리즘 문제 최소 2문제 정리하기

