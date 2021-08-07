## 문제 설명

![beautiful-triplets-English](https://user-images.githubusercontent.com/47416686/128596467-17a22422-96a4-4ce5-aa01-6473c199f129.jpg)

![beautiful-triplets-English2](https://user-images.githubusercontent.com/47416686/128596465-95ea173f-53c1-463b-92f9-caa03a5e52e7.jpg)

## 문제 풀이

주어진 배열에서 d만큼의 차이가 나는 3쌍의 수(i, i + d, i + d \* 2)를 차례로 구해서 반환하는 문제이다.

## 내가 짠 코드

```jsx
function beautifulTriplets(d, arr) {
  // Write your code here
  let result = 0;

  for (let el of arr) {
    if (arr.includes(el + d) && arr.includes(el + d * 2)) {
      result++;
    }
  }

  return result;
}
```

## ✔️ 참고

[Beautiful Triplets | HackerRank](https://www.hackerrank.com/challenges/beautiful-triplets/problem)
