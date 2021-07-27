## 문제 설명

![electronics-shop-English](https://user-images.githubusercontent.com/47416686/127125122-5fe5b7df-fa7f-4476-b48e-5adf312e133a.jpg)

![electronics-shop-English2](https://user-images.githubusercontent.com/47416686/127125114-2bde53f6-efc0-43c2-a0a0-1b793f2262b0.jpg)

## 문제 풀이

이 문제는 주어진 예산 안에서 가장 큰 수를 구하는 문제이다.

예산 `b`, 키보드 `keyboards`, use `drives` 를 의미한다.

키보드와 use의 합을 구하고 예산에 가장 근접한 수를 반환하면 된다.

1. 이중 for문을 통해서 키보드와 use의 합을 구하는데, 예산보다 작은 합의 경우만 따로 분리해서 `bList`라는 배열에 추가한다. → `이중 for문`을 사용했기 때문에 `O(N^) 알고리즘`
2. 배열에 추가하면 `Math.max()`를 사용해서 가장 큰 수를 반환한다.
3. 단, 비어있을 경우 -1을 반환하도록 삼항 연산자로 처리한다.

## 내가 짠 코드

```jsx
function getMoneySpent(keyboards, drives, b) {
  /*
   * Write your code here.
   */

  const bList = [];

  for (let i = 0; i < keyboards.length; i++) {
    for (let j = 0; j < drives.length; j++) {
      if (keyboards[i] + drives[j] <= b) {
        bList.push(keyboards[i] + drives[j]);
      }
    }
  }

  const result = bList.length !== 0 ? Math.max(...bList) : -1;

  return result;
}
```

## ✔️ 참고

[Electronics Shop | HackerRank](https://www.hackerrank.com/challenges/electronics-shop/problem)
