# 코드인터뷰용 문법 JAVA (중단: 스트링 다루기가 너무 거지같다. 길이가 정해지지 않은 수들을 입력받아서 배열로 만들고 그거를 스트링으로 바꾸기도 하고 그런 과정 )
### 주요 라이브러리 소환
```
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;
```

### 입력
문제에서는 다음과 같은 형태의 인풋이 많이 주어진다.

1) 인풋의 갯수를 알 때   
for문을 갯수만큼 돌리면서 입력받을 수 있다.

``` bash
6
1 2 3 4 10 11
```


```
Scanner in = new Scanner(System.in);
int n = in.nextInt();
int[] arr = new int[n];
for(int i = 0; i < n; i++){
    arr[i] = in.nextInt();
}
```

2) 인풋의 갯수를 모를 때

한 줄로 주어질때만 가능.
  
```
1 2 3 4 5 6 4 5 3
```

```
ArrayList<Integer> temp = new ArrayList<>();
Scanner in = new Scanner(System.in);
String text = in.nextLine();
StringTokenizer st = new StringTokenizer(text," ");
while(st.hasMoreTokens()){
	temp.add(Integer.parseInt(st.nextToken()));
}

```

### 출력
```
System.out.println(n);
```

### 초기화
```
for(int i; i<n; i++){
	Arrays.fill(MEMO[i], -1);
}

//OR

static boolean[][] visited;
visited = new boolean[N+1][M+1];

```
### 무시 조건
and가 너무 많을 땐 반대 조건을 continue로 거르는 것이 더 좋을 수 있다.

```
if(yy < 1 || yy > M || xx < 1 || xx > N || a[yy][xx] <= a[y][x]) continue;
```

## 그래프 이론
### 2차원 배열 크기
```
int n = arr.length;
int m = arr[0].length();

```
### 4방향 탐색
```
static int[] dy = new int[] {-1,0,1,0};
//혹은
static int[] dx = {0,-1,0,1};
for(int i=0; i<n; i++){
	int yy = y+dy[i];
	int xx = x+dx[i];
}
```
### visited 초기화
```
arr = new int[4][5];
for(int[] row: arr) {
	Arrays.fill(row, -1);
}
```
### 2차원 배열 프린트
```
for(int i=0; i<3;i++) {
	for(int j=0; j<3; j++) {
		System.out.print(arr[i][j]);
	}
	System.out.println();
}
```


## 스트링
#### 문자열 생성
```
String s2 = "World";
```
#### 문자열 비교
```
s1.equals(s3)
s1.equalsIgnoreCase(s3)
```
#### 문자열 인덱스
```
System.out.println(s1.charAt(3));
```
#### 문자열 자르기
```
//0-5까지
s4.substring(0, 6);
//12부터 끝까지
s4.substring(12);
```
#### 문자열 합치기
```
return s1+s2;

s1.concat(s2);
```

#### 포함하고 있니?
```
s4.contains(s1);
```

#### 문자열을 문자 어레이로
```
//Character 클래스로 알파벳인지 숫자인지 기본적인 것을 체크가능
Character.isLetterOrDigit(c)
Character.isWhitespace(c)
```

## 배열

### 맥스, 민
```
Math.min(sum, cur);
```

### 정렬하기
```
ArrayList<Integer> arr = new ArrayList<Integer>();
arr = ...;
Collection.sort(arr);

```

### 무한대
```
Integer.MAX_VALUE;
```

#### 배열 수정하기
```
dp[y][x] = result;
```

#### 한개만 쏙 빼고 봉합하기
```

```

#### 길이
```
String[] arr = {"dd", "dfdf"};
```

### 정렬하기

Comparator 사용
```
Arrays.sort(arr, new Comparator<Integer>() {
	public int compare(Integer a, Integer b) {
		//두자리 수이면 일의자리만 취한다
		if(a > 9) {
			a = a/10;
		}
		if(b > 9) {
			b = b/10;
		}
		
		if(a > b) {
		//이 크면 앞선다
			return -1;
		}else {
		//이 조건이면 뒤로 간다
			return 1;
		}
	}
});
```



## 리스트

## 딕셔너리?
단어와 빈도를 짝으로 만들어서 
빈도를 기준으로 sort 하는 방법?