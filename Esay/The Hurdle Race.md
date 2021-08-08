## 문제 설명

![the-hurdle-race-English](https://user-images.githubusercontent.com/47416686/128635895-b10de1c6-7dac-4c4b-8463-1f8a255874f8.jpg)

![the-hurdle-race-English2](https://user-images.githubusercontent.com/47416686/128635891-652195d2-b390-40b0-ab66-45e01e2b2c53.jpg)

## 문제 풀이

이 문제는 가장 큰 수를 뽑아서 주어진 k 값 작으면 0을 반환하고, 크면 max - k를 반환한다.

## 내가 짠 코드

```jsx
function hurdleRace(k, height) {
  // Write your code here
  const max = Math.max(...height);

  return k > max ? 0 : max - k;
}
```

## ✔️ 참고

[The Hurdle Race | HackerRank](https://www.hackerrank.com/challenges/the-hurdle-race/problem)
