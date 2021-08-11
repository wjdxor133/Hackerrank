## 문제 설명

![library-fine-English](https://user-images.githubusercontent.com/47416686/128958283-e96ce2e4-8944-426f-a120-f20a09b272dc.jpg)

![library-fine-English2](https://user-images.githubusercontent.com/47416686/128958208-4342f162-3341-4114-9d38-17fff4a6d4b9.jpg)

## 문제 풀이

### 입력

**d1, m1, y1**: 반납하는 일,월,년도 , 모두 정수**d2, m2, y2**: 예정된 반납 일,월 , 년도 , 모두 정수

### 출력

1. 만약 예정된 반납일 이전 또는 반납일에 제출하면 지불 금액 없음
2. 만약 예정된 반납일 보다 늦지만 같은 달에 제출하면 "15(d2-d1)" 만큼 지불
3. 만약 예정된 반납일 보다 늦지만 같은 년도에 제출하면 "500(m2-m1)" 만큼 지불
4. 만약 예정된 년도보다 늦게 제출하면 10000 지불

## 내가 짠 코드

```jsx
function libraryFine(d1, m1, y1, d2, m2, y2) {
  // Write your code here

  // 반납한 연도 < 반납 예정일 연도
  if (y1 < y2) {
    return 0;
  }

  // 반납한 연도 > 반납 예정일 연도 -> 반납을 년도 단위로 안해버림..
  if (y1 > y2) {
    return 10000;
  }

  // 반납한 달 < 반납 예정 달
  if (m1 < m2) {
    return 0;
  }

  // 반납한 달 > 반납 예정 달 -> 초과
  if (m1 > m2) {
    return (m1 - m2) * 500;
  }

  // 반납하는 날 <= 반납 예정일
  if (d1 <= d2) {
    return 0;
  }

  // 반납하는 날 > 반납 예정일 -> 초과
  if (d1 > d2) {
    return (d1 - d2) * 15;
  }
}
```

## ✔️ 참고

[Library Fine | HackerRank](https://www.hackerrank.com/challenges/library-fine/problem)
