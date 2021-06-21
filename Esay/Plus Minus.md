## 문제 설명

Given an array of integers, calculate the ratios of its elements that are *positive*, *negative*, and *zero*. Print the decimal value of each fraction on a new line with  places after the decimal.

**Note:** This challenge introduces precision problems. The test cases are scaled to six decimal places, though answers with absolute error of up to  are acceptable.

**Example**

There are  elements, two positive, two negative and one zero. Their ratios are ,  and . Results are printed as:

```
0.400000
0.400000
0.200000

```

**Function Description**

Complete the *plusMinus* function in the editor below.

plusMinus has the following parameter(s):

- _int arr[n]_: an array of integers

**Print**Print the ratios of positive, negative and zero values in the array. Each value should be printed on a separate line with  digits after the decimal. The function should not return a value.

**Input Format**

The first line contains an integer, , the size of the array.The second line contains  space-separated integers that describe .

**Constraints**

**Output Format**

**Print** the following  lines, each to  decimals:

1. proportion of positive values
2. proportion of negative values
3. proportion of zeros

**Sample Input**

`STDIN Function

---

6 arr[] size n = 6
-4 3 -9 0 4 1 arr = [-4, 3, -9, 0, 4, 1]`

**Sample Output**

`0.500000 0.333333 0.166667`

**Explanation**

There are  positive numbers,  negative numbers, and  zero in the array.The proportions of occurrence are positive: , negative:  and zeros: .

Change Theme

## 내가 짠 코드

```jsx
function plusMinus(arr) {
  // Write your code here
  let newArr = [0, 0, 0];

  for (let i = 0; i < arr.length; i++) {
    if (arr[i] > 0) {
      newArr[0] += 1;
    } else if (arr[i] < 0) {
      newArr[1] += 1;
    } else if (arr[i] === 0) {
      newArr[2] += 1;
    }
  }

  const ratioArr = newArr.map((num) => (num / arr.length).toFixed(6));

  for (let i = 0; i < ratioArr.length; i++) {
    console.log(ratioArr[i]);
  }
}
```

## 문제 풀이

- 이번 문제는 주어진 배열에서 양수, 음수, 0의 비율을 반환하는 문제이다.

**STEP1**

- 새 배열을 담을 변수를 선언한다.
- 주어진 배열에서 for문을 통해 모든 원소를 순회한다.
- 순회하는 동안 if문을 사용해서 양수, 음수, 0일 때 조건을 줘서 해당하는 수의 개수를 새 배열에 순서대로 담는다.

```jsx
// arr [ -4, 3, -9, 0, 4, 1 ]
let newArr = [0, 0, 0];

for (let i = 0; i < arr.length; i++) {
  if (arr[i] > 0) {
    newArr[0] += 1;
  } else if (arr[i] < 0) {
    newArr[1] += 1;
  } else if (arr[i] === 0) {
    newArr[2] += 1;
  }
}

// 출력 ->  newArr [ 3, 2, 1 ]
```

**STEP2**

- 이제 양수의 개수, 음수의 개수, 0의 개수를 배열의 길이로 나눠 비율을 구한다.
- 대신 소수점 6자리까지의 비율이어야 한다.
- `toFixed()`를 사용해서 소수점 6자리로 자른다.

```jsx
const ratioArr = newArr.map((num) => (num / arr.length).toFixed(6));

// ratioArr [ '0.500000', '0.333333', '0.166667' ]
```

**SETP3**

- 이제 비율이 담긴 배열을 다시 for문을 통해 console.log()로 출력한다.

```jsx
for (let i = 0; i < ratioArr.length; i++) {
  console.log(ratioArr[i]);
}

/* 
	0.500000
	0.333333
	0.166667
*/
```

## ✔️ 참고

[Plus Minus | HackerRank](https://www.hackerrank.com/challenges/plus-minus/problem)

[[javascript] 소수점 자리수 지정(자르기) toFixed()](https://squll1.tistory.com/entry/javascript-%EC%86%8C%EC%88%98%EC%A0%90-%EC%9E%90%EB%A6%AC%EC%88%98-%EC%A7%80%EC%A0%95%EC%9E%90%EB%A5%B4%EA%B8%B0)
