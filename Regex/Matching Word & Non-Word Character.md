## 문제 설명

![matching-word-non-word-English](https://user-images.githubusercontent.com/47416686/130359613-f39c7966-ed10-4837-aa08-c263c2199bd6.jpg)

## 문제 풀이

- 특수문자 → `\W`
- 그냥 문자 → `\w`

## 내가 짠 코드

```jsx
// 입력
// www.hackerrank.com

var Regex_Pattern = /\w{3}\W\w{10}\W\w{3}/;

function processData(Test_String) {
  //Enter your code here

  console.log(!!Test_String.match(Regex_Pattern));
}
```

## ✔️ 참고

[Matching Word & Non-Word Character | HackerRank](https://www.hackerrank.com/challenges/matching-word-non-word/problem)
