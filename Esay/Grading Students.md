## 문제 설명

<img width="537" alt="Grading Students" src="https://user-images.githubusercontent.com/47416686/123376277-32a6d500-d5c5-11eb-9a34-8e503cdda995.png">

## 입출력

**Sample Input 0**

`4 73 67 38 33`

**Sample Output 0**

`75 67 40 33`

<img width="573" alt="Grading Students 입출력" src="https://user-images.githubusercontent.com/47416686/123376269-2f134e00-d5c5-11eb-8e10-4406ca5267ac.png">

## 문제 풀이

**접근 방법**

HackerLand 대학은 다음과 같은 성적 정책이 있습니다.

- 모든 학생은 0~100의 성적을 받습니다.
- 어떤 성적이든 40점 미만이면 낙제점입니다.

Sam은 HackerLand대학의 교수입니다. 다음 규칙에 따라 각 학생의 성적(grade)을 올림 합니다.

- 성적이 성적보다 큰 5의 배수 값과의 차이가 3보다 작은 경우 5의 배수 값으로 올림 합니다.
- `성적이 38보다 작으면 결과가 여전히 실패한 성적이므로 올림을 하지 않습니다.`

예를 들어, grade = 84는 85로 올림 됩니다. 그러나 grade = 29는 올림 되지 않습니다. 올림해도 40보다 작기 때문입니다.
Sam의 n명의 학생들의 각각의 등급 값이 주어지면 반올림 프로세스를 자동화하는 코드를 작성하시오.

```jsx
// 모든 학생은 0 ~ 100의 성적을 받는다.
grades [ 73, 67, 38, 33 ]

// 1번째 학생
첫 번째 학생의 점수는 73점
73점보다 큰 5의 배수의 값은 75점,
75점 - 73점 = 2점
2는 3보다 작기 때문에 5의 배수 점수 값 75점으로 올린다.

// 2번째 학생
두 번째 학생의 점수는 67점
67점보다 큰 5의 배수의 값은 70점,
70점 - 67점 = 3점
3은 3이랑 같기 때문에 원래 성적 그대로 67점으로 유지한다.

// 3번째 학생
세 번째 학생의 점수는 38점
38점보다 큰 5의 배수의 값은 40점,
40점 - 38점 = 2점
2는 3보다 작기 때문에 5의 배수 점수 값 40점으로 올린다.

// 4번째 학생
네 번째 학생의 점수는 33점
성적이 38보다 작으면 결과가 여전히 실패한 성적이므로 올림을 하지 않습니다. 라는 조건이 있기 때문에
여기서 33점은 38점보다 낮기 때문에 성적 그대로 33점을 유지한다.

```

- 사실 38점보다 작으면 성적을 올림하지 않는다는 조건 대신 40점보다 작으면으로 생각한 나머지 푸는데 시간이 꾀나 걸렸다.. 😂

## 내가 짠 코드

```jsx
function gradingStudents(grades) {
  // Write your code here
  for (let i = 0; i < grades.length; i++) {
    if (grades[i] < 38) {
      continue;
    } else {
      for (let j = 5; j <= 100; j += 5) {
        if (j - 5 <= grades[i] && grades[i] <= j && Math.abs(j - grades[i]) < 3)
          grades[i] = j;
      }
    }
  }

  return grades;
}
```

- `Math.abs()` 를 사용한 이유는 오로지 두 수의 차이 값만을 고려해서 음수를 제외하고 비교하기 위해서 사용했다.

## ✔️ 참고

[Grading Students | HackerRank](https://www.hackerrank.com/challenges/grading/problem)
