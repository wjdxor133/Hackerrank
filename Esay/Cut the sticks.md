## 문제 설명

![cut-the-sticks-English](https://user-images.githubusercontent.com/47416686/130173573-b742a67a-a4d7-4f7d-978a-a36f821c391a.jpg)

![cut-the-sticks-English2](https://user-images.githubusercontent.com/47416686/130173572-21727e99-01b1-4616-bc78-b639b188086f.jpg)

## 문제 풀이

1. 막대기들에서 가장 작은 길이를 구한다.
2. 위에서 구한 길이로 각 막대길의 길이를 잘라낸다.

   단, 길이가 0 이하이면 배열(리스트)에서 제외

3. 남은 막대의 개수를 결과로 출력하고,리스트에는 남은 막대기의 길이를 표시
4. 위의 과정 ①~③ 반복하며 남은 막대기가 없어질 때까지 반복

- 1단계) [5 4 4 `2` `2` 8]에서 가장 작은 길이 = `2` | 자른 막대기 개수 = **6개**

- 2단계) [3 `2` `2` _ _ 6]에서 가장 작은 길이 = `2` | 자른 막대기 개수 = **4개**

- 3단계) [`1` _ _ _ _ 4]에서 가장 작은 길이 = `1` | 자른 막대기 개수 = **2개**

- 4단계) [_ _ _ _ _ `3`]에서 가장 작은 길이 = `3` | 자른 막대기 개수 = **1개**

## 내가 짠 코드

```jsx
function cutTheSticks(arr) {
  // Write your code here
  const result = [];

  while (arr.length) {
    result.push(arr.length);
    const min = Math.min(...arr);
    arr = [...arr.filter((el) => el - min)];
  }

  return result;
}
```

## ✔️ 참고

[Cut the sticks | HackerRank](https://www.hackerrank.com/challenges/cut-the-sticks/problem)
