## 문제 설명

![counting-valleys-English](https://user-images.githubusercontent.com/47416686/126890402-cccbabf7-985e-4090-a55f-c44046aa9aa2.png)

## 문제 풀이

이번 문제는 `Valley일 때의 수`를 구하는 문제이다.

가뜩이나 영어인데 문제 이해가 너무 어려웠던.. esay하지 않았던 문제였다.

깊이를 나타내는 `'U'`, `'D'`로 이뤄진 `path 문자열`이 존재한다.

`U` 는 +1를 나타내고, `D`는 -1를 나타낸다.

Valley가 되는 기준은 `마지막 U(음수 값)`로 `sea level(0이 될때)`까지 올라와야 완성!

산에서 sea level까지 가는건 허용이 되지 않는 것 같다.

## 내가 짠 코드

```jsx
function countingValleys(steps, path) {
  // Write your code here
  let level = 0;
  let valley = 0;

  for (let el of path) {
    el === "U" ? ++level : --level;
    if (el === "U" && level === 0) {
      valley += 1;
    }
  }

  return valley;
}
```

## ✔️ 참고

[Counting Valleys | HackerRank](https://www.hackerrank.com/challenges/counting-valleys/problem)
