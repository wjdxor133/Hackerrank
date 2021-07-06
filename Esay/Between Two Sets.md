## 문제 설명

![between-two-sets-English](https://user-images.githubusercontent.com/47416686/124594823-3b3bbd00-de9b-11eb-9c80-a27ecaa73330.jpg)

![between-two-sets-English2](https://user-images.githubusercontent.com/47416686/124594818-3971f980-de9b-11eb-894e-c7346fb8ba75.jpg)

## 문제 풀이

### 🔎 접근 방식

- 첫 번째 array들의 `최소 공배수`를 구함.
- 두 번째 array들의 `최대 공약수`를 구함
- 최소 공배수의 배수 ( 최소 공배수 _ 1, 최소 공배수 _ 2...)를 해서 최대 공약수를 나누었을 때 나머지가 0인 인수들을 체크

2와 4의 공배수는 `4`, 8, 12, 16, 20, 24, 28, 32, 36,... 순으로 늘어납니다.

→ 최소 공배수는 `4`

16, 32, 96의 공약수는 1, 2, 4, 8, `16`입니다.

→ 최대 공약수는 `16`

**2와 4의 공배수**이면서 **16, 32, 96의 공약수**인 숫자는 `4, 8, 16`입니다.

## 내가 짠 코드

```jsx
function gcd(x, y) {
  if (y === 0) return x;

  return gcd(y, x % y);
}

function getTotalX(a, b) {
  // Write your code here

  // 배열 a의 최소공배수
  let lcm_A =
    (Math.max(...a) * Math.min(...a)) / gcd(Math.max(...a), Math.min(...a));

  // 배열 b의 최대공약수
  let gcd_B = gcd(Math.max(...b), Math.min(...b));

  let intsBetweenArrays = [];
  let newArrA = [];
  let finalArr = [];

  for (let i = lcm_A; i <= gcd_B; i++) {
    intsBetweenArrays.push(i);
  }

  // 배열 a의 2, 4의 공배수 인수 구하기
  for (let i = 0; i < intsBetweenArrays.length; i++) {
    if (a.every((num) => intsBetweenArrays[i] % num === 0)) {
      newArrA.push(intsBetweenArrays[i]);
    }
  }

  // 배열 b의 공약수 인수 구하기
  for (let i = 0; i < newArrA.length; i++) {
    if (b.every((num) => num % newArrA[i] === 0)) {
      finalArr.push(newArrA[i]);
    }
  }

  return finalArr.length;
}
```

## ✔️ 참고

[Between Two Sets | HackerRank](https://www.hackerrank.com/challenges/between-two-sets/problem)

[[Easy] Between Two Sets](https://ian90.tistory.com/73)

[유클리드 호제법(Uclidean algorithm)](https://sustainable-dev.tistory.com/36)

[hackerrank - Between Two Sets - Python3](https://junho85.pe.kr/1534)

[[2019.01.31] Between Two Sets](https://devalice.tistory.com/58)

[Discussion on Between Two Sets Challenge](https://www.hackerrank.com/challenges/between-two-sets/forum/comments/488585)
