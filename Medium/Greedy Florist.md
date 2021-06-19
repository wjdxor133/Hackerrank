## 문제 설명

A group of friends want to buy a bouquet of flowers. The florist wants to maximize his number of *new* customers and the money he makes. To do this, he decides he'll multiply the price of each flower by the number of that customer's previously purchased flowers plus . The first flower will be original price, , the next will be  and so on.

Given the size of the group of friends, the number of flowers they want to purchase and the original prices of the flowers, determine the minimum cost to purchase all of the flowers. The number of flowers they want equals the length of the  array.

**Example**

The length of , so they want to buy  flowers total. Each will buy one of the flowers priced  at the original price. Having each purchased  flower, the first flower in the list, , will now cost . The total cost is .

**Function Description**

Complete the *getMinimumCost* function in the editor below.

getMinimumCost has the following parameter(s):

- *int c[n]:* the original price of each flower
- *int k:* the number of friends

**Returns**- *int:* the minimum cost to purchase all flowers

**Input Format**

The first line contains two space-separated integers  and , the number of flowers and the number of friends.The second line contains  space-separated positive integers , the original price of each flower.

**Constraints**

-
-
-
-

**Sample Input 0**

`3 3 2 5 6`

**Sample Output 0**

`13`

**Explanation 0**

There are  flowers with costs  and  people in the group. If each person buys one flower, the total cost of prices paid is  dollars. Thus, we print  as our answer.

**Sample Input 1**

`3 2 2 5 6`

**Sample Output 1**

`15`

**Explanation 1**

There are  flowers with costs  and  people in the group. We can minimize the total purchase cost like so:

1. The first person purchases  flowers in order of decreasing price; this means they buy the more expensive flower () first at price  dollars and the less expensive flower () second at price  dollars.
2. The second person buys the most expensive flower at price  dollars.

We then print the sum of these purchases, which is , as our answer.

**Sample Input 2**

`5 3 1 3 5 7 9`

**Sample Output 2**

`29`

**Explanation 2**

The friends buy flowers for ,  and ,  and  for a cost of .

Change Theme

## 내가 짠 코드

```jsx
function getMinimumCost(k, c) {
  let flowersPirce = 0;
  let cnt = 0;
  c.sort((a, b) => b - a);

  for (let i = 0; i < c.length; i++) {
    flowersPirce += (cnt + 1) * c[i];
    if (i === k - 1) {
      cnt += 1;
      i = -1;
      c.splice(0, k);
    }
  }

  return flowersPirce;
}
```

## 문제 풀이

- 사실 이 문제를 처음 봤을 때 이해하기까지 시간이 많이 걸렸다.
- 플로리스트가 자신의 이윤을 극대화 하기 위해서 원래 꽃의 갯수에 1을 더하여 파는 식이다.

예를 들면,
`k`는 친구 인원수 k = 3이면
`n`은 꽃의 갯수 n = 8,
`c`는 꽃 가격 c = [1, 2, 3, 4, 5, 6, 7, 8]

- 여기서 플로리스트가 이익을 얻기 위해서는 먼저 꽃을 사는 인원들이 비싼 꽃송이들을 차례대로 골라야 한다.
- 즉 세 명이 모두 구매하게 될때는 원가의 모든 꽃을 구매할 수 있다는 뜻이다.
- 단, 그 이후에 꽃 송이들은 인원수 당 +1씩 증가되어 가격이 커지게 된다.
- 예시) [8, 7, 6] → (0 + 1) _ 꽃 가격, [5, 4, 3] → (1 + 1) _ 꽃 가격, [2, 1] → (2 + 1) \* 꽃 가격

**STEP1**

- 먼저 꽃을 사는 인원들이 가장 비싼 가격의 꽃송이를 고를 수 있게 `sort()`를 사용해서 내림차순 정렬을 해준다.

```jsx
c = [2, 5, 6];

// 내림차순 정렬
c.sort((a, b) => b - a);

// 결과
c -> [6, 5, 2];
```

**STEP2**

- 이제 꽃 가격을 담을 변수 flowersPirce와 인원수 기준에 따라 꽃 가격을 증가시키는 변수 cnt를 선언해준다.
- for 문을 통해서 꽃 가격 배열을 순회한다.
- 인원 수가 3이기 때문에 가장 비싼 꽃 송이 3개를 먼저 골라서 더해준다.
- 단, 인원수가 3이 되었을 때, `splice()` 을 사용해 해당 인원 수 만큼 꽃송이를 빼버린다.

```jsx
cnt += 1; // 꽃 가격 증가시켜주는 변수
i = -1; // 다시 맨 앞부터 순회
c.splice(0, k); // 3송이 씩 집어가기 때문에 3개씩 빼버림
```

- 최종적으로 모든 loop이 돌았을 때, 모두 더한 꽃송이 값을 반환해준다.

## ✔️ 참고

[Greedy Florist | HackerRank](https://www.hackerrank.com/challenges/greedy-florist/problem)
