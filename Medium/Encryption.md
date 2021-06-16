## 문제 설명

An English text needs to be encrypted using the following encryption scheme.First, the spaces are removed from the text. Let  be the length of this text.Then, characters are written into a grid, whose rows and columns have the following constraints:

**Example**

After removing spaces, the string is  characters long.  is between  and , so it is written in the form of a grid with 7 rows and 8 columns.

```
ifmanwas
meanttos
tayonthe
groundgo
dwouldha
vegivenu
sroots

```

- Ensure that
- If multiple grids satisfy the above conditions, choose the one with the minimum area, i.e. .

The encoded message is obtained by displaying the characters of each column, with a space between column texts. The encoded message for the grid above is:

`imtgdvs fearwer mayoogo anouuio ntnnlvt wttddes aohghn sseoau`

Create a function to encode a message.

**Function Description**

Complete the *encryption* function in the editor below.

encryption has the following parameter(s):

- *string s:* a string to encrypt

**Returns**

- *string:* the encrypted string

**Input Format**

One line of text, the string

**Constraints**

contains characters in the range ascii[a-z] and space, ascii(32).

### 입출력 예

**Sample Input**

```
haveaniceday

```

**Sample Output 0**

```
hae and via ecy

```

**Explanation 0**

,  is between  and .Rewritten with  rows and  columns:

```
have
anic
eday

```

**Sample Input 1**

```
feedthedog

```

**Sample Output 1**

```
fto ehg ee dd

```

**Explanation 1**

,  is between  and .Rewritten with  rows and  columns:

```
feed
thed
og

```

**Sample Input 2**

```
chillout

```

**Sample Output 2**

```
clu hlt io

```

**Explanation 2**

,  is between  and .Rewritten with  columns and  rows ( so we have to use .)

```
chi
llo
ut
```

## 내가 짠 코드

```jsx
function encryption(s) {
  // Write your code here
  let noSpace = s.replace(/\s/g, "");
  let row = Math.floor(Math.sqrt(noSpace.length));
  let col = Math.ceil(Math.sqrt(noSpace.length));
  if (row * col < noSpace.length) {
    row += 1;
  }
  let newStr = "";
  for (let i = 0; i < col; i++) {
    let jump = 0;
    while (i + jump < noSpace.length) {
      newStr += noSpace[i + jump];
      jump += col;
    }
    newStr += " ";
  }
  return newStr;
}
```

## 문제 풀이

- 이 문제는 주어진 문자열의 공백을 제거한 후 길이를 구해서, 그 길이의 제곱근을 통해 행과 열의 그리드 형태로 주어진 규칙에 암호화해서 반환하는 문제이다.

**STEP1**

- 우선 주어진 문자열 `replace()` 와 `정규식 표현`으로 s의 공백을 제거한다.

```jsx
s -> have anice day
noSpace haveaniceday
```

**STEP2**

- 행과 열을 구하기 위해 `Math.sqrt()`을 사용해 문자열의 길이 값으로 제곱근을 구한다.
- 단 행과 열은 제곱근 사이의 수여야 하기 때문에
- row는 `Math.floor()`를 해주고, col은 `Math.ceil()`를 해준다.

```jsx
s length 12
row 3
col 4
```

- 단 row \* col 값이 s의 길이보다 작으면 row + 1를 해준다.

**STEP3**

- 최종적으로 반환할 문자열 newStr을 만들고, `for문` 을 통해 col만큼 순회를 한다.
- 미리 구한 row값을 활용하는 대신, 중간에 `while문` 사용해 col 자리의 수만을 뽑아서 주어진 문자열의 길이 이전 만큼만 뽑아서 newStr에 추가한다.
- 만약 문자열의 길이를 넘어가면 공백을 추가하고 다음 자리의 수로 이동한다.
- col의 수 만큼 순회하면 최종적으로 값을 반환한다.

## ✔️ 참고

[Simple Array Sum | HackerRank](https://www.hackerrank.com/challenges/simple-array-sum/problem)

[[JS] 자바스크립트 공백제거(replace,trim)](https://dpdpwl.tistory.com/113)

[[Javascript] 반올림(round), 올림(ceil), 내림(floor) - 소수점, 음수,자리수 지정](https://hianna.tistory.com/446)

[Math.sqrt() - JavaScript | MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt)
