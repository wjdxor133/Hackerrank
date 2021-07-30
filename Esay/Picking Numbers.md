## 문제 설명

![picking-numbers-English](https://user-images.githubusercontent.com/47416686/127592722-07f5e7f8-c013-42dd-9094-cf7635e30c0c.png)

## 문제 풀이

역시 영어로 된 문제여서 문제를 이해하는데 시간이 엄청 걸렸다.

여기서의 핵심은 현재 원소 - 다음 원소의 값이 2미만 일때, 가장 길이가 큰 배열의 길이를 반환하는 문제이다.

예를 들면,

1 3 3 4 5 6

1. 1 - 3의 차이는 절대값 기준으로 2
   - `1` 3 3 4 5 6
   - 2미만이어야 하기 때문에 조건이 일치하지 않는다.
   - 이때 배열의 길이는 1
2. 바로 3으로 넘어가서 3 - 3의 차이는 0
   - 2미만이기 때문에 계속 순회한다.
3. 그러다 3과 5가 만나게 되는데 이때 3 - 5의 차이는 2
   - 2미만이 아니기 때문에 조건이 일치하지 않게 된다.
   - 1 `3` `3` `4` 5 6
   - 이때 배열의 길이는 3

이런식으로 접근을 해서 배열의 길이를 따로 저장해둔다.

최종적으로 `Math.max()`를 사용해서 `배열의 길이 중 가장 큰 수`를 반환한다.

단, 테스트 케이스에서 걸렸던 부분은 모든 원소의 수가 일치 할때는 초기에 주어졌던 배열의 길이를 반환해야 한다.

## 내가 짠 코드

```jsx
function pickingNumbers(a) {
  // Write your code here
  a.sort((a, b) => a - b);
  let start = a[0]; // 시작 원소
  let cnt = 0; // 원소 개수
  let reset = 0; // 초기화 개수
  let len = []; // 배열 길이

  for (let i = 1; i < a.length; i++) {
    cnt += 1;
    if (a[i] - start > 1) {
      start = a[i];
      len.push(cnt);
      reset += 1;
      cnt = 0;
    }
  }

  return reset === 0 ? a.length : Math.max(...len);
}
```

## ✔️ 참고

[Picking Numbers | HackerRank](https://www.hackerrank.com/challenges/picking-numbers/problem)

[HackerRank Solution: Picking Numbers in C++](https://www.youtube.com/watch?v=GUi8L7MbEYY)
