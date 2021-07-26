## 문제 설명

![sock-merchant-English](https://user-images.githubusercontent.com/47416686/126972069-a172162b-eef3-4162-a58a-3d832c265701.jpg)

![sock-merchant-English2](https://user-images.githubusercontent.com/47416686/126972065-e0594ad2-4174-4528-8822-942cf2db96e3.jpg)

## 문제 풀이

이 문제는 주어진 배열 ar에서 일치하는 `일치하는 두 수의 한 쌍의 개수`를 구하는 문제이다.

먼저 `sort()` 를 사용해서 오름차순으로 정렬한다.

정렬 후, 앞의 원소부터 순서대로 하나씩 꺼내서 일치하는 한 쌍을 찾는다. → `O(N)`

찾으면 `splice()`를 사용해 일치하는 한 쌍을 배열에서 지우고, 개수를 하나씩 추가한다. → `O(N)`

이 과정을 반복해서 최종 개수를 반환한다.

## 내가 짠 코드

```jsx
function sockMerchant(n, ar) {
  // Write your code here
  let cnt = 0;
  ar.sort((a, b) => a - b);

  for (let i = 0; i < ar.length; i++) {
    if (ar[i] === ar[i + 1]) {
      ar.splice(i, 2);
      cnt += 1;
      i = -1;
    }
  }

  return cnt;
}
```

## ✔️ 참고

[Sales by Match | HackerRank](https://www.hackerrank.com/challenges/sock-merchant/problem)
