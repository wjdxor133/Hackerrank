## 문제 설명

You will be given a list of integers, , and a single integer . You must create an array of length  from elements of  such that its *unfairness* is minimized. Call that array . Unfairness of an array is calculated as

Where:- *max* denotes the largest integer in - *min* denotes the smallest integer in

**Example**

Pick any two elements, say .Testing for all pairs, the solution  provides the minimum unfairness.

**Note**: Integers in  may not be unique.

**Function Description**

Complete the *maxMin* function in the editor below.maxMin has the following parameter(s):

- *int k:* the number of elements to select
- _int arr[n]:_: an array of integers

**Returns**

- *int:* the minimum possible *unfairness*

**Input Format**

The first line contains an integer , the number of elements in array .The second line contains an integer .Each of the next  lines contains an integer  where .

**Constraints**

**Sample Input 0**

`7 3 10 100 300 200 1000 20 30`

**Sample Output 0**

`20`

**Explanation 0**

Here ; selecting the  integers , unfairness equals

```
max(10,20,30) - min(10,20,30) = 30 - 10 = 20

```

**Sample Input 1**

`10 4 1 2 3 4 10 20 30 40 100 200`

**Sample Output 1**

`3`

**Explanation 1**

Here ; selecting the  integers , unfairness equals

```
max(1,2,3,4) - min(1,2,3,4) = 4 - 1 = 3

```

**Sample Input 2**

`5 2 1 2 1 2 1`

**Sample Output 2**

`0`

**Explanation 2**

Here .  or  give the minimum unfairness of .

Change Theme

## 내가 짠 코드

```jsx
function maxMin(k, arr) {
  // Write your code here
  const sortArr = [...arr.sort((a, b) => a - b)];
  let resultArr = [];

  for (let i = 0; i + k <= sortArr.length; i++) {
    const max = sortArr[i + k - 1];
    const min = sortArr[i];
    resultArr.push(max - min);
  }
  const min = Math.min(...resultArr);

  return min;
}
```

## 문제 풀이

- 이번 문제 또한 이해하는데 시간이 엄청 걸렸다.
- 결국 이해하기 위해 구글 검색을 여러 차례 시도했다. 😂
- 문제를 완전히 이해하진 못했다 하지만 통과된 로직을 풀이해서 설명하자면,

N개의 수 중, 작은 수 부터 K씩 묶었을 때 묶은 값에서 최대값과 최소값의 차가 가장 작은 값을 구하라는 의미같다.

예를 들어, [1, 4, 7, 2] 라는 배열이 있다.
`k`는 아무 숫자를 뽑는 개수를 의미, k = 2이면

**STEP1**

- 먼저 정렬을 해준다.

```jsx
arr[(10, 100, 300, 200, 1000, 20, 30)];

// 오름차순 정렬
const sortArr = [...arr.sort((a, b) => a - b)];

// 결과
sortArr[(10, 20, 30, 100, 200, 300, 1000)];
```

**STEP2**

- for문을 통해서 반복문을 돌린다.
- k씩 묶었을 때 묶은 값에서 최대값과 최소값을 구하고, 뺀 값을 새 배열에 하나씩 넣는다.

```jsx
for (let i = 0; i + k <= sortArr.length; i++) {
  const max = sortArr[i + k - 1];
  const min = sortArr[i];
  resultArr.push(max - min);
}
```

**STEP3**

- 이제 차이 값 배열에서 `Math.min()`를 사용해 가장 작은 최소값을 추출해 반환한다.

```jsx
const min = Math.min(...resultArr);
```

## ✔️ 참고

[Max Min | HackerRank](https://www.hackerrank.com/challenges/angry-children/problem)

[[171228][HackerRank](C#)Max Min](https://sweetroute.tistory.com/entry/HackerRankMax-Min)
