## 문제 설명

Given a time in [-hour AM/PM format](https://en.wikipedia.org/wiki/12-hour_clock), convert it to military (24-hour) time.

Note: - 12:00:00AM on a 12-hour clock is 00:00:00 on a 24-hour clock.- 12:00:00PM on a 12-hour clock is 12:00:00 on a 24-hour clock.

**Example**

- s = '12:01:00PM'

  Return '12:01:00'.

- s = '12:01:00AM'

  Return '00:01:00'.

**Function Description**

Complete the *timeConversion* function in the editor below. It should return a new string representing the input time in 24 hour format.

timeConversion has the following parameter(s):

- _string s_: a time in  hour format

**Returns**

- _string_: the time in  hour format

**Input Format**

A single string  that represents a time in -hour clock format (i.e.:  or ).

**Constraints**

- All input times are valid

**Sample Input 0**

`07:05:45PM`

**Sample Output 0**

`19:05:45`

## 내가 짠 코드

```jsx
function timeConversion(s) {
  // Write your code here
  let time = Number(s.substring(0, 2));
  const timeConversion = s.substring(s.length - 2);
  let resultTime = s.substring(2, s.length - 2);

  if (timeConversion === "PM") {
    if (time < 12) {
      time += 12;
    }
    resultTime = `${time}${resultTime}`;
  } else if (timeConversion === "AM") {
    if (time >= 12) {
      time -= 12;
    }
    resultTime = `${String(time).padStart(2, 0)}${resultTime}`;
  }

  return resultTime;
}
```

## 문제 풀이

- 이번 문제는 "PM", "AM"에 따라 앞에 시간을 표시하는 문제이다.

**STEP1**

- 우선 먼저 `substring()`을 사용해서 앞에 시간과 뒤에 오전, 오후를 나타내는 문자를 추출한다.
- 대신 앞에 추출한 시간은 `Number()`로 정수로 형변환 해준다.
- 추출하고 나머지 문자열도 따로 담아둔다.

```jsx
s = "07:05:45PM";

let time = Number(s.substring(0, 2));
const timeConversion = s.substring(s.length - 2);
let resultTime = s.substring(2, s.length-2);

// 출력
time 7
timeConversion PM
resultTime :05:45
```

**STEP2**

- 이제 두가지 조건으로 나눠서 구분 해야한다.
- "PM" 일 때, time 12보다 작으면 +12 해주고, ```(백틱)`을 사용해 시간 문자열을 다시 만들어준다.
- 반대로, "AM" 일 때, time이 12보다 크거나 같으면 -12를 해주고 똑같이 문자열을 다시 만들어준다.
- 대신 정수로 형변환 했었기 때문에 시간에는 앞에 0이 없을 것이다.
- `String()`을 사용해서 시간을 다시 문자열로 만들고 `padStart()`를 사용해 앞에 한자리 수 일 경우 0을 채워준다.

```jsx
if (timeConversion === "PM") {
  if (time < 12) {
    time += 12;
  }

  resultTime = `${time}${resultTime}`;
} else if (timeConversion === "AM") {
  if (time >= 12) {
    time -= 12;
  }

  resultTime = `${String(time).padStart(2, 0)}${resultTime}`;
}
```

## ✔️ 참고

[Time Conversion | HackerRank](https://www.hackerrank.com/challenges/time-conversion/problem)
