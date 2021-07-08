## 문제 설명

![breaking-best-and-worst-records-English](https://user-images.githubusercontent.com/47416686/124896174-2c2e4980-e018-11eb-8385-f9dd195a058d.jpg)

![breaking-best-and-worst-records-English2](https://user-images.githubusercontent.com/47416686/124896159-2a648600-e018-11eb-8447-c4d5dff7549c.jpg)

## 문제 풀이

## 내가 짠 코드

```jsx
function breakingRecords(scores) {
  // Write your code here
  let score = scores[0];
  let Hscore = scores[0];
  let Lsocore = scores[0];
  let Hcnt = 0;
  let Lcnt = 0;

  for (let i = 1; i < scores.length; i++) {
    if (scores[i] > Hscore) {
      Hscore = scores[i];
      Hcnt++;
    } else if (scores[i] < Lsocore) {
      Lsocore = scores[i];
      Lcnt++;
    }
  }

  return [Hcnt, Lcnt];
}
```

## ✔️ 참고

[Breaking the Records | HackerRank](https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem)
