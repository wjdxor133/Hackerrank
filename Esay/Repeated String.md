## 문제 설명

![repeated-string-English](https://user-images.githubusercontent.com/47416686/128146875-76498960-74cf-497c-a9a3-ba907645a7ea.png)

## 문제 풀이

하 영어 문제는 항상 문제 이해가 오래걸린다.

원래는 주어진 문자열의 제일 첫 번째 문자를 n까지 반복한 문자열 안에서 몇개인지 개수를 반환하는 문제인 줄 알았다.

하지만..

> a라는 문자가 반복되는 횟수를 구하는 문제

`s: 'aba'` , `n: 10`

1. n을 주어진 문자열 길이로 나눈 몫을 구한다. → `반복 횟수`
2. n을 주어진 문자열 길이로 나눈 나머지를 구한다. → `반복하고 난 후 나머지 문자열 길이`
3. `match()`를 사용해 `기존 문자열의 a의 개수`를 구한다. → '`a`b`a`'
4. `기존 문자열 aba` _ `반복 횟수` → 'aba' _ 3 → '`a`b`aa`b`aa`b`a`'
5. n은 10이고 문자열의 길이는 9이다.
6. 나머지 문자에서 a가 포함되면 a의 개수를 더하고 아니면 더하지 않는다.

## 내가 짠 코드

```jsx
function repeatedString(s, n) {
  // Write your code here

  // 반복 횟수
  const repeatCnt = Math.floor(n / s.length);

  // 반복 후 나머지 문자 길이
  const restStrLen = n % s.length;

  // s의 a 개수
  const aMathes = (s.match(/a/g) || []).length;

  // 반복 횟수에 따라 증가하는 a의 개수
  let repeatA = repeatCnt * aMathes;

  // 나머지 문자열의 a의 개수
  repeatA += (s.substring(0, restStrLen).match(/a/g) || []).length;

  return repeatA;
}
```

## ✔️ 참고

[Repeated String | HackerRank](https://www.hackerrank.com/challenges/repeated-string/problem)

[[HackerRank][Javascript] Repeated String](https://egg-programmer.tistory.com/252)

[Discussion on Repeated String Challenge](https://www.hackerrank.com/challenges/repeated-string/forum/comments/499141)
