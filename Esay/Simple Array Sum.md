## 문제 설명

Given an array of integers, find the sum of its elements.

For example, if the array , , so return .

**Function Description**

Complete the *simpleArraySum* function in the editor below. It must return the sum of the array elements as an integer.

simpleArraySum has the following parameter(s):

- _ar_: an array of integers

**Input Format**

The first line contains an integer, , denoting the size of the array.The second line contains  space-separated integers representing the array's elements.

**Constraints**

**Output Format**

Print the sum of the array's elements as a single integer.

### 입출력 예

**Sample Input**

`6 1 2 3 4 10 11`

**Sample Output**

`31`

## 내가 짠 코드

```jsx
function simpleArraySum(ar) {
  // Write your code here
  let sum = 0;
  ar.map((num) => (sum += num));
  return sum;
}
```

## 문제 풀이

- 이 문제는 간단히 주어진 배열의 원소를 모두 더해서 반환하는 문제이다.

**STEP1**

- 우선 배열 ar의 원소들의 합을 담을 변수 sum을 선언한다.
- `map()`을 사용해 모든 원소를 순회하고 sum에 순서대로 더한다.

```jsx
sum 1
sum 3
sum 6
sum 10
sum 20
sum 31
```

- 순회가 끝나면 최종적으로 모두 더한 값을 반환해준다.

## ✔️ 참고

[Simple Array Sum | HackerRank](https://www.hackerrank.com/challenges/simple-array-sum/problem)
