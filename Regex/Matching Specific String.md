## 문제 설명

![matching-specific-string-English](https://user-images.githubusercontent.com/47416686/129468260-c67a8657-b275-4cd0-98d2-0e836931fc50.png)

## 문제 풀이

- hackerrank 라는 단어가 몇개 들어있는지 배열로 반환

## 내가 짠 코드

```jsx
// 입력
// hackerrank is hackerrank not HackerRank. so please use hackerrank
// always and not hackerrrank

var Regex_Pattern = "hackerrank";

function processData(Test_String) {
  //Enter your code here
  var Regex = new RegExp(Regex_Pattern, "g");
  var Array = Test_String.match(Regex);
  console.log("Number of matches :", Array.length);
}
```

## ✔️ 참고

[Matching Specific String | HackerRank](https://www.hackerrank.com/challenges/matching-specific-string/problem)
