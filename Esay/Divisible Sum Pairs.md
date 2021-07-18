## 문제 설명

![divisible-sum-pairs-English](https://user-images.githubusercontent.com/47416686/126068315-abacd908-dc03-47d5-8d3e-fb6c13ec67b2.jpg)

## 문제 풀이

문제에서 `ar 배열`과 `k값`이 주어진다.

ar 배열에서 원소 두개씩 꺼내고 나서 k로 나누어 떨어질 때의 수를 구하는 문제이다.

빅오 표기법 `O(n2)` 알고리즘 접근으로 `이중 for문`을 사용해서 구했다.

앞에 원소부터 차례대로 빼서 순서대로 더해 k의 값으로 나누어 떨어졌을 때, 그때 cnt라는 값에 +1을 해준다.

## 내가 짠 코드

```jsx
function divisibleSumPairs(n, k, ar) {
  // Write your code here
  let cnt = 0;

  for (let i = 0; i < ar.length; i++) {
    for (let j = i + 1; j < ar.length; j++) {
      if ((ar[i] + ar[j]) % k === 0) {
        cnt += 1;
      }
    }
  }

  return cnt;
}
```

## ✔️ 참고

[Divisible Sum Pairs | HackerRank](https://www.hackerrank.com/challenges/divisible-sum-pairs/problem)
