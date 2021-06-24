## 문제 설명

You are in charge of the cake for a child's birthday. You have decided the cake will have one candle for each year of their total age. They will only be able to blow out the tallest of the candles. Count how many candles are tallest.

**Example**

The maximum height candles are  units high. There are  of them, so return .

**Function Description**

Complete the function `birthdayCakeCandles` in the editor below.

birthdayCakeCandles has the following parameter(s):

- _int candles[n]_: the candle heights

**Returns**

- _int_: the number of candles that are tallest

**Input Format**

The first line contains a single integer, , the size of .The second line contains  space-separated integers, where each integer  describes the height of .

**Constraints**

-
-

**Sample Input 0**

`4 3 2 1 3`

**Sample Output 0**

`2`

**Explanation 0**

Candle heights are . The tallest candles are  units, and there are  of them.

## 내가 짠 코드

```jsx
function birthdayCakeCandles(candles) {
  // Write your code here
  const max = Math.max(...candles);
  const maxCnt = candles.filter((candle) => candle === max).length;

  return maxCnt;
}
```

## 문제 풀이

- 이번 문제는 주어진 배열 원소 중에서 가장 큰수의 개수를 구하는 문제이다.

**STEP1**

- 우선 먼저 `Math.max()`를 사용해 배열 원소 중 가장 큰 수를 추출한다.

```jsx
candles = [3, 2, 1, 3];

// 최대값 추출
const max = Math.max(...candles);

// max : 3
```

**STEP2**

- 최대값을 구했으니 이제 `filter()`를 사용해서 maz값과 일치한 원소들만 추출한다.

```jsx
const maxCnt = candles.filter((candle) => candle === max).length;

// 개수를 반환 해야하기 때문에 length를 해준다.
maxCnt[(3, 3)].length;

// maxCnt : 2
```

## ✔️ 참고

[Birthday Cake Candles | HackerRank](https://www.hackerrank.com/challenges/birthday-cake-candles/problem)
