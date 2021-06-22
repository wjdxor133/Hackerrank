## 문제 설명

Staircase detail

This is a staircase of size :

```
   #
  ##
 ###
####

```

Its base and height are both equal to . It is drawn using `#` symbols and spaces. *The last line is not preceded by any spaces.*

Write a program that prints a staircase of size .

**Function Description**

Complete the *staircase* function in the editor below.

staircase has the following parameter(s):

- _int n_: an integer

**Print**

Print a staircase as described above.

**Input Format**

A single integer, , denoting the size of the staircase.

**Constraints**

.

**Output Format**

Print a staircase of size  using `#` symbols and spaces.

**Note**: The last line must have  spaces in it.

**Sample Input**

`6`

**Sample Output**

     `#
    ##

###

####

#####

######`

**Explanation**

The staircase is right-aligned, composed of `#` symbols and spaces, and has a height and width of .

## 내가 짠 코드

```jsx
function staircase(n) {
  // Write your code here
  for (let i = 1; i <= n; i++) {
    let str = "";
    for (let j = 0; j < i; j++) {
      str += "#";
    }
    console.log(str.padStart(n, " "));
  }
}
```

## 문제 풀이

- 이번 문제는 # 모양의 계단을 만드는 문제이다.
- 계단은 오른쪽으로 정렬되고 #기호와 공백으로 구성되며 높이와 너비는 주어진 n값과 같습니다

**STEP1**

- 먼저 for문을 통해 왼쪽 정렬된 계단을 만든다.

```jsx
for(let i = 1; i <= n; i++) {
	let str = "";
	for(let j = 0; j < i; j++) {
			str += "#";
	}
}

// 출력
#
##
###
####
#####
######

```

**STEP2**

- 왼쪽 정렬 된 계간을 앞부분에 `padStart()`를 사용해서 공백으로 채워 오른쪽 정렬로 맞춰 출력해준다.

```jsx
for(let i = 1; i <= n; i++) {
	let str = "";
	for(let j = 0; j < i; j++) {
			str += "#";
	}
	console.log(str.padStart(n, " "));
}

// 출력
		 #
    ##
   ###
  ####
 #####
######
```

## ✔️ 참고

[Staircase | HackerRank](https://www.hackerrank.com/challenges/staircase/problem)

[String.prototype.padStart() - JavaScript | MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/padStart)
