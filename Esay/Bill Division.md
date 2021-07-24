## 문제 설명

![bon-appetit-English](https://user-images.githubusercontent.com/47416686/126869773-d8b85e4e-0ba6-4713-94fc-e3d19f1a9ed9.jpg)

![bon-appetit-English2](https://user-images.githubusercontent.com/47416686/126869771-29b9b98b-811d-42a0-a21e-fe0d4d8cce4d.jpg)

## 문제 풀이

문제는 주어진 배열 `bill`이 있다.

또 배열에서 뺄 원소의 위치를 나타내는 `k`,

빼고난 후 원소들의 합의 절반 값이 `b`와 같으면 "Bon Appetit"를 반환하고, 다르면 b - 구한 합을 반환한다.

1. 주어진 배열 `bill`에서 **splice()**를 사용해 `k`번째 인덱스를 제거한다. → 시간복잡도 `O(N)`
2. 나머지 원소들의 합을 **reduce()**를 사용해서 구한다.→ 시간복잡도 `O(N)`
3. 반환식 삼항 연산자를 통해서 조건에 맞는 값을 반환한다.

## 내가 짠 코드

```jsx
function bonAppetit(bill, k, b) {
  // Write your code here
  bill.splice(k, 1);
  const billSum =
    bill.reduce((acc, cur) => {
      return acc + cur;
    }, 0) / 2;

  const result = billSum === b ? "Bon Appetit" : b - billSum;
  console.log(result);
}
```

## ✔️ 참고

[Bill Division | HackerRank](https://www.hackerrank.com/challenges/bon-appetit/problem)
