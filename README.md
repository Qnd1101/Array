# 배열을 이용한 max값 출력

## 알고리즘
학생들의 키(height)를 입력받아 누가 가장 키가 큰가를 알 수 있는 코드

## 코드 해석
1. 학생 수를 사용자가 입력한다.
2. 학생 수 만큼 배열을 생성한다.
3. 저장 되어있는 

## 메인 메소드 Java Code
```java
package sungil2023_03_algo;

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
package sungil2023_03_algo;

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

## 출력 화면
![image](https://user-images.githubusercontent.com/107795830/224591815-0bf3a5cf-72cf-452b-abaa-a87dd53351ec.png)
