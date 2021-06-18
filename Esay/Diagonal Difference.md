## 문제 설명

Given a square matrix, calculate the absolute difference between the sums of its diagonals.

For example, the square matrix  is shown below:

```
1 2 3
4 5 6
9 8 9

```

The left-to-right diagonal = . The right to left diagonal = . Their absolute difference is .

**Function description**

Complete the  function in the editor below.

diagonalDifference takes the following parameter:

- _int arr[n][m]_: an array of integers

**Return**

- _int_: the absolute diagonal difference

**Input Format**

The first line contains a single integer, , the number of rows and columns in the square matrix .Each of the next  lines describes a row, , and consists of  space-separated integers .

**Constraints**

-

**Output Format**

Return the absolute difference between the sums of the matrix's two diagonals as a single integer.

**Sample Input**

`3 11 2 4 4 5 6 10 8 -12`

**Sample Output**

`15`

**Explanation**

The primary diagonal is:

```
11
   5
     -12

```

Sum across the primary diagonal: 11 + 5 - 12 = 4

The secondary diagonal is:

```
     4
   5
10

```

Sum across the secondary diagonal: 4 + 5 + 10 = 19Difference: |4 - 19| = 15

**Note:** |x| is the [absolute value](https://www.mathsisfun.com/numbers/absolute-value.html) of x

## 내가 짠 코드

```jsx
function diagonalDifference(arr) {
  // Write your code here
  let leftToRghtDgnl = 0;
  let rightToleftDgnl = 0;
  for (let i = 0; i < arr.length; i++) {
    leftToRghtDgnl += arr[i][i];
    rightToleftDgnl += arr[i][arr.length - 1 - i];
  }
  return Math.abs(leftToRghtDgnl - rghtToleftDgnl);
}
```

## 문제 풀이

- 이 문제는 정사각형 행렬이 주어지면 대각선 합계 간의 절대 차이를 계산합니다.

**STEP1**

- 왼쪽에서 오른쪽으로 가는 대각선 → leftToRghtDgnl 선언
- 반대로 오른쪽에서 왼쪽으로 가는 대각선 → rightToleftDgnl를 선언
- 이제 반복문을 통해 해당 하는 원소를 더한다.

```jsx
// 예를 들면,
1 2 3
4 5 6
9 8 9

왼쪽에서 오른쪽 대각선 = 1 + 5 + 9 = 15
오른쪽에서 왼쪽 대각선 = 3 + 5 + 9 = 17
```

**STEP2**

- 두 대각선의 값을 구했으면, 둘의 절대적인 차이의 값을 구해야 한다.
- 그 말은 즉, 절대값을 구해야한다.
- `'절대값'`이란 수직선 위의 점이 수직선 위의 원점에서 얼마나 떨어졌나를 나타내는 말이다.
- 절대값은 음수면 그 숫자에 음수를 붙여서 양수로 만들어 주어야 하는 것이 특징이다.
- 최종적으로 두 대각선의 차이값을 구하고 자바스크립트에서 절대값을 구하는 메소드 `Math.abs()`를 사용해서 반환해준다.

## ✔️ 참고

[Diagonal Difference | HackerRank](https://www.hackerrank.com/challenges/diagonal-difference/problem)

[절대값 계산, 절대값 구하기](https://nous-temperature.tistory.com/431)

[[Node.js] Javascript: 절대값 구하기 (Math.abs)](https://miiingo.tistory.com/271)
