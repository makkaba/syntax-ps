# JavaScript For P.S.

# 1.Array

- 배열의 길이

```
A = [1,2,3,4]
for (var i =0; i<A.length; i++){
//DoSomething();
}
```
- 배열에서 원소 찾기

```
var result = stack.indexOf(2200);
if(result == -1){
	console.log("not found");
}else{
	console.log("found in "+result+"th index");
}
```

- 배열 만들기

```
var arr = new Array();
var arr = [];
```

- 2차원 배열 만들기

```
var dp = new Array(num);
for(var i =0; i<num; i++){
    dp[i] = new Array(3).fill(0);
}
```


- 밀어넣기

```
arr.push("f");
```

- 배열 합치기

```

A = [1,2,3];
B = [4,5];
var C = A.concat(B);
console.log(C);

//[1,2,3,4,5]
```

- 값으로 초기화

```
[1, 2, 3].fill(4)
/// [4,4,4]
```

- 필터링

```
function isBigEnough(value) {
  return value >= 10;
}
var filtered = [12, 5, 8, 130, 44].filter(isBigEnough);
// filtered 는 [12, 130, 44]
```
콜백을 통과한 요소만 모아서 리턴해줌


- 포함 여부

```
var a = [1, 2, 3];
a.includes(4);
//false
```

- stack처럼 사용하기

```
var popped = arr.pop();
arr.push('newone');
```

- 배열의 일부 가져오기

```
var fruits = ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango'];
var citrus = fruits.slice(1, 3);

// ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
// ['Orange','Lemon']

fruits.slice(1);
//['Orange', 'Lemon', 'Apple', 'Mango']
//1번부터 끝까지
```
시작점, 끝점(포함안됨)

- 특정 엘리먼트 삭제하기

```
arr.splice(idx, 1);
//idx번째부터 1개를 삭제한다
```

- 정렬

```
arr.sort();
```


- 배열의 합

```
var sum = [1,2,3,55].reduce(function(a, b){
	return a+b;
});
```

- 배열의 최대값

```
var arr= [1,2,3,4,5];
Math.max(...arr);
//환경에 따라 작동하지 않는 경우가 있으니 아래 코드를 더 권장합니다.

//Or
//최대값
var max = array.reduce( function (previous, current) { 
	return previous > current ? previous:current;
});

//최소값
var min = array.reduce( function (previous, current) { 
	return previous > current ? current:previous;
});
```

- 배열의 값만 가져와서 초기화하기

```
//ex)i번째 원소를 끝으로 하는 수열의 최대값에서 메모이제이션 배열의 초기값을 각 엘리먼트의 값으로 한다면 
//cf) boj 11055
var arr2 = arr1.slice();
var arr2 = [...arr1];
//두번째 방법은 환경에 따라 작동하지 않을 수 있으니 첫번째 방법을 추천합니다.
```

- 숫자를 받아야 하는데 문자로 받아진 경우

```
//arr = ['1', '2', '3']

new_arr = arr.map(function(i){
    return parseInt(i, 10);
})

//Or, 애초에 split을 할 수 있다면
new_arr = arr.split(' ').map(function(i){
    return parseInt(i, 10);
})


```


# Object

주어진 배열의 값을 가지고 특정 조건의 갯수를 세어보라던가,
캐시 구조에 담아보라던가 등의 문제는 자칫하면 O(n*2)의 복잡도로 계산하기 쉽다.
특히나, python이나 javascript 처럼 기본함수가 잘 갖춰져 있는 경우
인지하지 못한채 쓰는 경우가 많게 된다.

```
ex) 
for i in range(len(arr)):
	if a in arr:
		print("found")
	else:
		print("not found")
```
		
이때는 자바스크립트에서는 json 형태로 넣은 뒤 처리하면 좀 더 쉽다. O(N)으로 처리 가능하다.

```
cache = {};
for(var i=0; i<A.length; i++){
    if(A[i] in cache){
        cache[A[i]]++;
    }else{
        cache[A[i]] = 1;
    }
}
```

# String

주로 1,2번에 편성되는 문제들은 스트링을 다루는 문제들이 많다.

- 형 변환하기(숫자<->문자열)

```javascript
var result = Number('123');
var result = String(123);
```

- 형 변환하기(문자열<->배열)

```
var s = "helloworld";
var a = s.split("");
//["h", "e", "l", "l"...]
var ss = a.join("");
//helloworld

```

- 판단하기

```
var Regex = /^\d+$/;
var isNum = Regex.test(str);

var Regex = /^[a-zA-Z]+$/;
var isAlphabet = Regex.test(str);

var Regex = /^[a-zA-Z0-9_]+$/;
var isDigitAlphabet = Regex.test(str);

```

- 이진수
(여러가지 방법이 있겠지만)

```
var bin = Number(42).toString(2);
//101010
var dec = parseInt(bin, 2);
//42
```

- 문자열 수정하기

python, cpp 스타일 X

```
var str = 'dfdfggg';
str[3] = 'T';
//not working!
```

- 문자열 합치기

```
str = s1 + s2;
```

```
'abc'.repeat(2);    
// 'abcabc'
```

- 대소문자

```
'ALPHABET'.toLowerCase(); 
'alphabet'.toUpperCase(); 
// 'alphabet'
// 'ALPHABET'
```

- 부분 문자

```
str.substr(0, 2);
```
0부터 2개

- 아스키값

```
var res = String.fromCharCode(65);
//A

var n = str.charCodeAt(0);
//72

```

# Number
숫자 계산

- 몫만 구하기

```
Math.floor(7/2);
//3
```

# Graph Theory & Dynamic Programming

- 2차원 배열

n*m 크기의 배열 인풋

```



```

n*m 크기의 메모이제이션용 배열

```
var a = new Array(m).fill(0)
var b = []
for(var i =0; i<n; i++){
b.push(a);
}

```

# ETC

숫자의 범위가 1-100 이정도가 아니고 
100,000이 넘는다면 dp라고 생각해도 무방.


## 구름 IDE

테스트케이스 갯수를 입력받고 
2차원 배열 인풋을 받을 때

```
const readline = require("readline");
const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

T = 0;
isFirst = true;
arr = [];

rl.on("line", function(line) {
    if(isFirst){
        T = line;
        isFirst = false;
        return;
    }
    var temp = line.split(' ').map(function(num){ return parseInt(num,10);});
    arr.push(temp);
    T--;
    
    if(!isFirst && T==0){
        rl.close();
    }
    
    
}).on("close", function() {
    
    solution(arr);
  process.exit();
});

function solution(arr){
    console.log(arr);
}
```
테스트케이스 갯수를 받고, 1차원 배열을 받을 때

```
const readline = require("readline");
const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

T = 0;
isFirst = true;
arr = [];

rl.on("line", function(line) {
    if(isFirst){
        T = line;
        isFirst = false;
        return;
    }
    arr = line.split(' ').map(function(num){ return parseInt(num, 10)});
    rl.close();
}).on("close", function() {
    
    solution(arr, T);
  process.exit();
});

```