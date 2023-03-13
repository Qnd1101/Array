# 자바를 이용해 배열 알고리즘 구현

### 1. 자바로 구현한 가장 큰 값 출력
### 2. ArrayEqual (입력을 받은 배열의 길이와 배열 안에 있는 값이 같은지 확인하는 자바 배열 알고리즘)

## 1. 자바로 구현한 가장 큰 값 출력

### 알고리즘
학생들의 키(height)를 입력받아 누가 가장 키가 큰가를 알 수 있는 코드인데,   
학생 수를 먼저 입력받고, 학생 수 만큼 반복하여 자신의 키(height)을 입력하여   
그 중 가장 키가 큰 학생의 키(height)를 출력하는 알고리즘 이다.

## 메인 메소드 Java Code
```java
import java.util.Scanner;
public class Array {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		System.out.println("****화면출력****");
		System.out.println("학생들의 키를 입력하고 최댓값을 출력하시오.");
		System.out.print("사람 수 : ");
		int n = sc.nextInt();
		
		int[] height = new int[n];
		int max = height[0];
		
		for(int i = 0; i < n; i++) {
			System.out.printf("height[%d] : ", i);
			height[i] = sc.nextInt();
			if(height[i] > max) max = height[i];
		}
		System.out.printf("최댓값은 %d 입니다.", max);
	}
}
```

## 함수를 이용한 Java Code
```java
import java.util.Scanner;
public class Array {
	static int max(int n, int[] height) {
		int max = height[0];
		
		for(int i = 0; i < n; i++) {
			if(height[i] > max) max = height[i];
		}
		return max;
	}
	
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		System.out.println("****화면출력****");
		System.out.println("학생들의 키를 입력하고 최댓값을 출력하시오.");
		System.out.print("사람 수 : ");
		int n = sc.nextInt();
		
		int[] height = new int[n];
		
		for(int i = 0; i < n; i++) {
			System.out.printf("height[%d] : ", i);
			height[i] = sc.nextInt();
		}
		System.out.printf("최댓값은 %d 입니다.", max(n, height));
	}
}
````

### 출력 화면
![image](https://user-images.githubusercontent.com/107795830/224591815-0bf3a5cf-72cf-452b-abaa-a87dd53351ec.png)

# 2. ArrayEqual (입력을 받은 배열의 길이와 배열 안에 있는 값이 같은지 확인하는 자바 배열 알고리즘)

### 알고리즘
#### boolean 종류의 equals 메소드를 사용하여 a와 b를 입력 받아서 길이가 같은지 확인하고,    
#### 같지 않을 경우 false를 반환하여 "배열 a와 b는 같지 안습니다"를 출력하고,  
#### 같다면 계속해서 진행한다. 그 다음 조건은 a와 b의 값이 같은지 확인하고 같지 않을 경우 false를 반환하여 똑같이        
#### "배열 a와 b는 같지 안습니다"를 출력하고, 값이 같을 경우 true를 반환하여 "배열 a와 b는 같습니다." 를 출력한다.      

## 코드 설명
``` java
System.out.print("배열 a의 길이: ");
int na = sc.nextInt();
int[] a = new int[na];
``` 
### 1.  a의 길이를 입력하고 입력한 만큼 배열 방을 만들어준다.
```java
for(int i = 0; i < na; i++) {
    System.out.printf("a[%d] : ", i);
    a[i] = sc.nextInt();
}
```
### 2.  a에 값을 넣어준다.   
```java
System.out.print("배열 b의 길이: ");
int nb = sc.nextInt();
int[] b = new int[nb];
```
### 3.  b의 길이를 입력하고 입력한 만큼 배열 방을 만들어준다.  
```java
for(int i = 0; i < nb; i++) {
    System.out.printf("b[%d] : ", i);
    b[i] = sc.nextInt();
}
```
### 4.  b에 값을 넣어준다.    
```java
System.out.println("배열 a와 b는 " + (equals(a, b) ? "같습니다." : "같지 않습니다."));
```
### 5.  boolean 타입의 equals메소드에 파라미터를 넘겨준다.    
```java
if(a.length != b.length) {
    return false; // 서로 길이가 같지 않을 떄 false를 반환	
}  
```
### 6.  a와 b의 길이가 다르면 false를 반환  
```java
for(int i = 0; i < a.length; i++) {
    if(a[i] != b[i]) {
	return false; // 서로 값이 같지 않을 때 false를 반환
    }
}
```
### 7.  a와 b의 값이 다르면 false를 반환    
```java
return true; // 조건문에 한번도 걸리지 않았다면 true를 반환
```
### 8.  아무것도 걸리지 않았으므로 true를 반환
```java
System.out.println("배열 a와 b는 " + (equals(a, b) ? "같습니다." : "같지 않습니다."));
// equals라는 메소드에 a와 b를 파라미터로 넘겨서 
// true를 반환받거나 false를 반환 받아서
// true일 경우 > "같습니다." | false일 경우 > "같지 않습니다."
```
### 9.  equals 메소드에서 값을 받아와서 조건을 검사하고 출력한다.
## Java Code
```java
import java.util.Scanner;
public class Equal {
	static boolean equals(int[] a, int[] b) {
		if(a.length != b.length) {    // 6
			return false; // 서로 길이가 같지 않을 떄 false를 반환	
		}
		for(int i = 0; i < a.length; i++) {
			if(a[i] != b[i]) {      // 7
				return false; // 서로 값이 같지 않을 때 false를 반환
			}
		}
		return true; // 조건문에 한번도 걸리지 않았다면 true를 반환  // 8
	}
	
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		System.out.print("배열 a의 길이: ");
		int na = sc.nextInt();    // 1
		int[] a = new int[na];
		
		for(int i = 0; i < na; i++) {
			System.out.printf("a[%d] : ", i);
			a[i] = sc.nextInt();    // 2
		}
		
		System.out.print("배열 b의 길이: ");
		int nb = sc.nextInt();    // 3
		int[] b = new int[nb];
		
		for(int i = 0; i < nb; i++) {
			System.out.printf("b[%d] : ", i);
			b[i] = sc.nextInt();    // 4
		}
		System.out.println("배열 a와 b는 " + (equals(a, b) ? "같습니다." : "같지 않습니다."));  // 5, 9
		// equals라는 메소드에 a와 b를 파라미터로 넘겨서 
		// true를 반환받거나 false를 반환 받아서
		// true일 경우 > "같습니다." | false일 경우 > "같지 않습니다."
		
		sc.close();
	}
}
```
### 같은 경우 출력 화면
![image](https://user-images.githubusercontent.com/107795830/224597399-f78b73f9-ec36-4c8c-990a-3e1938b4c0bd.png)
### 같지 않을 경우 출력 화면
![image](https://user-images.githubusercontent.com/107795830/224597458-ecf7235e-9d54-4e0c-9e57-f519d5dff30f.png)

