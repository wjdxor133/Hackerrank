## 문제 설명

Given five positive integers, find the minimum and maximum values that can be calculated by summing exactly four of the five integers. Then print the respective minimum and maximum values as a single line of two space-separated long integers.

**Example**

The minimum sum is  and the maximum sum is . The function prints

```
16 24

```

**Function Description**

Complete the *miniMaxSum* function in the editor below.

miniMaxSum has the following parameter(s):

- _arr_: an array of  integers

**Print**

Print two space-separated integers on one line: the minimum sum and the maximum sum of  of  elements.

**Input Format**

A single line of five space-separated integers.

**Constraints**

**Output Format**

Print two space-separated long integers denoting the respective minimum and maximum values that can be calculated by summing exactly *four* of the five integers. (The output can be greater than a 32 bit integer.)

**Sample Input**

`1 2 3 4 5`

**Sample Output**

`10 14`

**Explanation**

The numbers are , , , , and . Calculate the following sums using four of the five integers:

1. Sum everything except , the sum is .
2. Sum everything except , the sum is .
3. Sum everything except , the sum is .
4. Sum everything except , the sum is .
5. Sum everything except , the sum is .

**Hints:** Beware of integer overflow! Use 64-bit Integer.

---

Need help to get started? Try the [Solve Me First](https://www.hackerrank.com/challenges/solve-me-first) problem

## 내가 짠 코드

```jsx
function miniMaxSum(arr) {
  // Write your code here
  let sumArr = [0, 0];
  const sortArr = [...arr.sort((a, b) => a - b)];
  for (let i = 0; i < sortArr.length - 1; i++) {
    sumArr[0] += sortArr[i];
  }

  for (let i = 1; i < sortArr.length; i++) {
    sumArr[1] += sortArr[i];
  }

  console.log(`${sumArr[0]} ${sumArr[1]}`);
}
```

## 문제 풀이

- 이번 문제는 주어진 배열에서 최소값, 최대값을 구해서 `"최소값 최대값"` 공백이 들어간 형태로 console.log()로 출력하는 문제이다.

**STEP1**

- 먼저 주어진 배열의 항목들을 `sort()`를 사용해 정렬한다.

```jsx
arr[(7, 69, 2, 221, 8974)];

// 오름차순 정렬
const sortArr = [...arr.sort((a, b) => a - b)];

// 정렬 후
sortArr[(2, 7, 69, 221, 8974)];
```

**STEP2**

- 정렬 후 최소값, 최대값을 구하는 방법이 존재한다.
- 최소값은 가장 큰 값을 제외한 수들만 더하면 최소값이 되고, 최대값은 가장 작은 수를 제외한 수만 더하면 최대값이 된다.

```jsx
for (let i = 0; i < sortArr.length - 1; i++) {
  sumArr[0] += sortArr[i];
}

for (let i = 1; i < sortArr.length; i++) {
  sumArr[1] += sortArr[i];
}
```

- 최대값, 최소값을 구하면 최종적으로 ```(백틱)`을 사용해 출력한다.

## ✔️ 참고

[Mini-Max Sum | HackerRank](https://www.hackerrank.com/challenges/mini-max-sum/problem)
