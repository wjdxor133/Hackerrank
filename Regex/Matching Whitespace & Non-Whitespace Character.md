## 문제 설명

![matching-whitespace-non-whitespace-character-English](https://user-images.githubusercontent.com/47416686/130174386-4ffde096-694e-4185-98b4-8dbfb0b7cac9.jpg)

## 문제 풀이

- 공백 구분 → `\s`
- `\S` 는 공백이 아닌 모든 문자와 일치합니다.

## 내가 짠 코드

```jsx
// 입력
// 12 11 15

var Regex_Pattern = /\S{2}\s\S{2}\s\S{2}/;

function processData(Test_String) {
  //Enter your code here

  console.log(!!Test_String.match(Regex_Pattern));
}
```

## ✔️ 참고

[Matching Whitespace & Non-Whitespace Character | HackerRank](https://www.hackerrank.com/challenges/matching-whitespace-non-whitespace-character/problem)
