## 문제 설명

Alice and Bob each created one problem for HackerRank. A reviewer rates the two challenges, awarding points on a scale from *1* to *100* for three categories: *problem clarity*, *originality*, and *difficulty*.

The rating for Alice's challenge is the triplet *a = (a[0], a[1], a[2])*, and the rating for Bob's challenge is the triplet *b = (b[0], b[1], b[2])*.

The task is to find their *comparison points* by comparing *a[0]* with *b[0]*, *a[1]* with *b[1]*, and *a[2]* with *b[2]*.

- If *a[i] > b[i]*, then Alice is awarded *1* point.
- If *a[i] < b[i]*, then Bob is awarded *1* point.
- If *a[i] = b[i]*, then neither person receives a point.

Comparison points is the total points a person earned.

Given *a* and *b*, determine their respective comparison points.

**Example**

_a = [1, 2, 3]b = [3, 2, 1]_

- For elements _0_, Bob is awarded a point because *a[0] .*

_For the equal elements a[1] and b[1], no points are earned.Finally, for elements 2, a[2] > b[2] so Alice receives a point._

\*The return array is [1, 1] with Alice's score first and Bob's second.
**Function Description**
Complete the function compareTriplets in the editor below.
compareTriplets has the following parameter(s):
• int a[3]: Alice's challenge rating
• int b[3]: Bob's challenge rating
**Return\***

- _int[2]_: Alice's score is in the first position, and Bob's score is in the second.

**Input Format**

The first line contains *3* space-separated integers, *a[0]*, *a[1]*, and *a[2]*, the respective values in triplet *a*.The second line contains *3* space-separated integers, *b[0]*, *b[1]*, and *b[2]*, the respective values in triplet *b*.

**Constraints**

- _1 ≤ a[i] ≤ 100_
- _1 ≤ b[i] ≤ 100_

**Sample Input 0**

`5 6 7 3 6 10`

**Sample Output 0**

`1 1`

**Explanation 0**

In this example:

-
-

Now, let's compare each individual score:

- , so Alice receives  point.
- , so nobody receives a point.
- , so Bob receives  point.

Alice's comparison score is , and Bob's comparison score is . Thus, we return the array .

**Sample Input 1**

`17 28 30 99 16 8`

**Sample Output 1**

`2 1`

**Explanation 1**

Comparing the  elements,  so Bob receives a point.Comparing the  and  elements,  and  so Alice receives two points.The return array is .

## 내가 짠 코드

```jsx
function compareTriplets(a, b) {
  // Write your code here
  const AliceBob = [0, 0];
  a.map(
    (num, i) =>
      num !== b[i] && (num > b[i] ? (AliceBob[0] += 1) : (AliceBob[1] += 1))
  );

  return AliceBob;
}
```

## 문제 풀이

- 이 문제는 a, b 두 배열이 주어진다.
- a는 Alice 팀, b는 Bob팀으로 결속시켜 두 팀의 수를 비교해서 스코어 점수 배열로 반환하는 문제이다.

**STEP1**

- 우선 각 팀의 점수를 표기하기 위해 AliceBob라는 배열을 만든다.
- AliceBob[0] → Alice팀(a), AliceBob[1] → Bob팀(b)

**STEP2**

- a와 b의 팀원은 항상 일치하기 때문에 a와 b 상관없이 아무거나 골라 `map()`을 돌린다.
- 항목 하나씩 비교를 하는데 만약 a의 항목의 수가 크면 AliceBob[0]에 +1를 하고, b의 항목이 크면 AliceBob[1]에 +1을 한다.
- 단, a의 항목의 수 === b의 항목의 수가 같으면 동작을 안하고 넘어가게 조건을 준다.
- 반복이 끝나면 최종값을 반환한다.

## ✔️ 참고

[Compare the Triplets | HackerRank](https://www.hackerrank.com/challenges/compare-the-triplets/problem)
