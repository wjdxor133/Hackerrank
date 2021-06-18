## 문제 설명

In this challenge, you are required to calculate and print the sum of the elements in an array, keeping in mind that some of those integers may be quite large.

**Function Description**

Complete the *aVeryBigSum* function in the editor below. It must return the sum of all array elements.

aVeryBigSum has the following parameter(s):

- _int ar[n]_: an array of integers .

**Return**

- _long_: the sum of all array elements

**Input Format**

The first line of the input consists of an integer .The next line contains  space-separated integers contained in the array.

**Output Format**

Return the integer sum of the elements in the array.

**Constraints**

**Sample Input**

```
5
1000000001 1000000002 1000000003 1000000004 1000000005

```

**Output**

```
5000000015

```

**Note:**

The range of the 32-bit integer is .

When we add several integer values, the resulting sum might exceed the above range. You might need to use long int C/C++/Java to store such sums.

## 내가 짠 코드

```jsx
function aVeryBigSum(ar) {
  // Write your code here
  let sum = 0;
  ar.map((item) => (sum += item));

  return sum;
}
```

## 문제 풀이

- 이 문제는 단순히 주어진 수의 합을 구하는 간단한 문제이다.

**STEP1**

- 먼저 주어진 수의 합을 담은 sum이라는 변수를 선언한다.
- 주어진 수가 담긴 ar 배열에 항목을 하나씩 꺼내서 sum 이라는 변수에 모두 더한다.

## ✔️ 참고

[A Very Big Sum | HackerRank](https://www.hackerrank.com/challenges/a-very-big-sum/problem)
