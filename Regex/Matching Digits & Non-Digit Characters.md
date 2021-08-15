## 문제 설명

![matching-digits-non-digit-character-English](https://user-images.githubusercontent.com/47416686/129470515-2a71c85b-e719-4e08-8c5c-979e1fd3106c.jpg)

![matching-digits-non-digit-character-English2](https://user-images.githubusercontent.com/47416686/129470513-65944593-4e8e-42d0-ac23-e4c8e4ae5eeb.jpg)

## 문제 풀이

- 숫자 → `\d`
- 문자 → `\D`
- { `개수` }

## 내가 짠 코드

```jsx
// 입력
// 06-11-2015

var Regex_Pattern = /\d{2}\D\d{2}\D\d{4}/;

function processData(Test_String) {
  //Enter your code here

  console.log(!!Test_String.match(Regex_Pattern));
}
```

## ✔️ 참고

[Matching Digits & Non-Digit Characters | HackerRank](https://www.hackerrank.com/challenges/matching-digits-non-digit-character/problem)
