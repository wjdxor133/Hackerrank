## 문제 설명

![kangaroo-English](https://user-images.githubusercontent.com/47416686/124389622-fab93380-dd22-11eb-8dbe-8a1a3923d784.jpg)

![kangaroo-English2](https://user-images.githubusercontent.com/47416686/124389619-f856d980-dd22-11eb-9695-553b5d5f64fa.jpg)

## 문제 풀이

### 🔎 접근 방식

- `x1` : 첫번째 캥거루의 시작 위치 , 정수
- `v1` : 첫번째 캥거루가 한번당 뛰는 거리 , 정수
- `x2` : 두번째 캥거루의 시작 위치 , 정수
- `v2` : 두번째 캥거루가 한번당 뛰는 거리 , 정수

`첫번째 캥거루의 시작위치(x1)`는 `두번째 캥거루의 시작위치(x2)`보다 뒤에 있다.

따라서 `첫번째 캥거루의 점프하는 거리(v1)`가 `두번째 캥거루의 점프하는 거리(v2)`보다 적다면 무조건 NO 이다.

만약 아니라면 계속 위치 좌표에 점프하는 값을 더하여 두 캥거루의 위치가 같다면 YES 를,

그 순간 첫번째 캥거루가 두번째 캥거루보다 앞지른다면 NO 를 반환하면 된다.

## 내가 짠 코드

```jsx
function kangaroo(x1, v1, x2, v2) {
  // Write your code here
  while (true) {
    if (v1 <= v2) {
      return "NO";
    }

    x1 += v1;
    x2 += v2;

    if (x1 === x2) {
      return "YES";
    }

    if (x1 > x2) {
      return "NO";
    }
  }
}
```

## ✔️ 참고

[Number Line Jumps | HackerRank](https://www.hackerrank.com/challenges/kangaroo/problem)
