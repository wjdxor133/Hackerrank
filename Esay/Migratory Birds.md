## 문제 설명

![migratory-birds-English](https://user-images.githubusercontent.com/47416686/126586583-807fbcf2-88cc-4762-a8e5-39b84b988533.jpg)

![migratory-birds-English2](https://user-images.githubusercontent.com/47416686/126586581-bb1c5507-662f-494b-b23e-db4c7956b574.jpg)

## 문제 풀이

문제는 주어진 배열 `arr`이 있다.

여기서 `중복된 원소들을 추출`해야 한다.

그 중복된 원소들 중 `가장 많이 중복된 수`를 추출한다.

그러고 나서 만약, 가장 많이 중복된 수 중에서 여러 개가 있다면 `가장 낮은 수를 반환`하는 문제이다.

빅오 표기법 `O(N)` 알고리즘 접근으로 `reduce()`, `for문`을 사용해서 구했다.

## 내가 짠 코드

```jsx
function migratoryBirds(arr) {
  // Write your code here
  const newArr = [];
  let max = 0;

  const obj = arr.reduce((acc, cur) => {
    acc[cur] = ++acc[cur] || 1;
    return acc;
  }, {});

  max = Math.max(...Object.values(obj));

  for (let key in obj) {
    if (obj[key] === max) {
      newArr.push(key);
    }
  }

  return Math.min(...newArr);
}
```

## ✔️ 참고

[Migratory Birds | HackerRank](https://www.hackerrank.com/challenges/migratory-birds/problem)

[javascript reduce() 함수 파헤치기](https://2dubbing.tistory.com/55)

[Javascript 객체(object)의 키(key)와 값(value)을 배열로 얻기](http://www.gisdeveloper.co.kr/?p=11005)
