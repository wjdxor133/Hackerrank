## 문제 설명

![apple-and-orange-English](https://user-images.githubusercontent.com/47416686/124349437-ef361180-dc29-11eb-8ad1-98c2f57d36c6.jpg)

![apple-and-orange-English-2](https://user-images.githubusercontent.com/47416686/124349438-f2c99880-dc29-11eb-81a6-13bb89375970.jpg)

## 문제 풀이

### 🔎 접근 방식

- _`s`_ : 정수, Sam의 집 위치 시작점.
- _`t`_ : 정수, Sam의 집 위치의 끝 위치.
- _`a`_ : 정수, 사과 나무의 위치.
- _`b`_ : 정수, 오렌지 나무의 위치.
- _`apples`_ : 정수 배열, 각 사과가 나무에서 떨어지는 거리.
- _`oranges`_ : 정수 배열, 각 오렌지가 나무에서 떨어지는 거리.

`s ~ t` 사이의 수는 `집 면적을 의미`한다.

`s` ≤ **떨어진 사과의 위치 + 사과 나무의 위치** ≤ `t`

`s` ≤ **떨어진 오렌지의 위치 + 오렌지 나무의 위치** ≤ `t`

결론은 집 면적 안에 사과나 오렌지가 있다면 해당하는 `사과, 오렌지 개수를 출력하는 문제`이다.

## 내가 짠 코드

```jsx
function countApplesAndOranges(s, t, a, b, apples, oranges) {
  // Write your code here
  const fallApples = apples.filter((apple) => {
    const nearApple = apple + a;
    if (s <= nearApple && nearApple <= t) {
      return nearApple;
    }
  }).length;

  const fallOranges = oranges.filter((orange) => {
    const nearOrange = orange + b;
    if (s <= nearOrange && nearOrange <= t) {
      return nearOrange;
    }
  }).length;

  console.log(fallApples);
  console.log(fallOranges);
}
```

## ✔️ 참고

[Apple and Orange | HackerRank](https://www.hackerrank.com/challenges/apple-and-orange/problem)
