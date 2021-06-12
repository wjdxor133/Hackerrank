## 문제 설명

Reduce a string of lowercase characters in range `ascii[‘a’..’z’]`by doing a series of operations. In each operation, select a pair of adjacent letters that match, and delete them.

Delete as many characters as possible using this method and return the resulting string. If the final string is empty, return `Empty String`

**Example**.

`aab` shortens to `b` in one operation: remove the adjacent `a` characters.

Remove the two 'b' characters leaving 'aa'. Remove the two 'a' characters to leave ''. Return 'Empty String'.

**Function Description**

Complete the *superReducedString* function in the editor below.

superReducedString has the following parameter(s):

- *string s:* a string to reduce

**Returns**

- *string:* the reduced string or `Empty String`

**Input Format**

A single string, 8.

### 입출력 예

**Sample Input 0**

`aaabccddd`

**Sample Output 0**

`abd`

**Explanation 0**

Perform the following sequence of operations to get the final string:

```
aaabccddd → abccddd → abddd → abd

```

**Sample Input 1**

`aa`

**Sample Output 1**

`Empty String`

**Explanation 1**

`aa → Empty String`

**Sample Input 2**

`baab`

**Sample Output 2**

`Empty String`

**Explanation 2**

`baab → bb → Empty String`

## 내가 짠 코드

```jsx
function superReducedString(s) {
  // Write your code here
  const chrArr = s.split("");
  let result = "";
  for (let i = 0; i < chrArr.length; i++) {
    if (chrArr[i] === chrArr[i + 1]) {
      chrArr.splice(i, 2);
      i = -1;
    }
  }
  result = chrArr.join("");

  return result ? result : "Empty String";
}
```

## 문제 풀이

- 이 문제는 주어진 문자열에서 일치하는 인접한 문자 쌍을 선택하고 삭제하는 문제이다.

**STEP1**

- 문자열을 하나씩 비교하기 위해 `spilt('')` 을 사용해 배열로 변환한다.

```jsx
chrArr[("a", "a", "a", "b", "c", "c", "d", "d", "d")];
```

**STEP2**

- 배열 형태로 된 문자들을 `for문`을 통해 하나씩 loop을 돌린다.
- if 조건으로 바로 앞뒤 원소들을 비교하여 chrArr[i] === chrArr[i+1] 일치했을 때, `splice()`를 사용해 일치하는 앞뒤 원소들을 삭제한다.
- 삭제하고 나면 다시 맨 앞부터 loop을 돌려야 하기 때문에 i = -1을 해준다.

```jsx
chrArr[("a", "b", "d")];
```

**STEP3**

- 이제 배열 형태의 문자들을 `join('')`을 사용해 다시 문자열로 만들어준다.

```jsx
chrArr abd
```

- 이제 반환하기만 하면 되는데... 예외가 존재한다.
- chrArr의 값이 비어있다면 "Empty String" 을 반환해야 한다.
- 마지막으로 이 부분을 `삼항 연산자`를 통해 처리해서 반환해준다.

## ✔️ 참고

[Super Reduced String | HackerRank](https://www.hackerrank.com/challenges/reduced-string/problem)

[[JS/Array] slice()와 splice()의 차이점](https://im-developer.tistory.com/103)
