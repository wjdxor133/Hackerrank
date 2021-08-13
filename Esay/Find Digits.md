## 문제 설명

![find-digits-English](https://user-images.githubusercontent.com/47416686/129366534-a131bb3b-998d-4812-94b2-2ed06dbe6c8c.png)

## 문제 풀이

- 정수인 수를 문자열로 변환 후에 하나 씩 나눈다.
- 나눈 수를 하나씩 원래 정수인 수를 나눠서 나누어 떨어지는 수만 골라서 개수를 반환한다.

## 내가 짠 코드

```jsx
function findDigits(n) {
  // Write your code here
  const result = [...n.toString()].filter((val) => n % parseInt(val) == 0)
    .length;

  return result;
}
```

## ✔️ 참고

[Find Digits | HackerRank](https://www.hackerrank.com/challenges/find-digits/problem)
