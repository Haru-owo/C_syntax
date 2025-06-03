# C언어 기초 문법

## 목차
1. [C언어 소개와 개발환경](#1-c언어-소개와-개발환경)
2. [기본 프로그램 구조](#2-기본-프로그램-구조)
3. [데이터 타입과 변수](#3-데이터-타입과-변수)
4. [상수와 전처리기](#4-상수와-전처리기)
5. [연산자](#5-연산자)
6. [제어문](#6-제어문)
7. [배열](#7-배열)
8. [포인터](#8-포인터)
9. [함수](#9-함수)
10. [구조체](#10-구조체)
11. [실습 예제](#11-실습-예제)
12. [학습 체크리스트](#12-학습-체크리스트)

---

## 1. C언어 소개와 개발환경

### 1.1 C언어란?
C언어는 1972년 벨 연구소에서 개발된 범용 프로그래밍 언어입니다. 다음과 같은 특징을 가집니다:

- **절차지향 언어**: 함수 중심의 프로그래밍
- **저수준 제어 가능**: 메모리와 하드웨어 직접 제어
- **이식성**: 다양한 플랫폼에서 실행 가능
- **효율성**: 빠른 실행 속도와 작은 메모리 사용량

### 1.2 개발환경 설정
C언어 프로그래밍을 위해 필요한 도구:
- **컴파일러**: GCC, Clang, Visual Studio
- **IDE**: Code::Blocks, Dev-C++, Visual Studio Code
- **디버거**: GDB, Visual Studio Debugger

---

## 2. 기본 프로그램 구조

### 2.1 Hello World 프로그램

```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

**구성 요소 설명:**
- `#include <stdio.h>`: 표준 입출력 라이브러리 포함
- `int main()`: 프로그램의 시작점
- `printf()`: 화면 출력 함수
- `return 0;`: 프로그램 정상 종료

### 2.2 기본 문법 규칙

#### 세미콜론 (;)
- 모든 문장은 세미콜론으로 끝남
- 블록문 ({ })은 세미콜론 불필요

#### 중괄호 ({ })
- 코드 블록 구분
- 함수, if문, for문 등에서 사용

#### 들여쓰기
- 코드 가독성 향상
- 보통 4칸 공백 또는 탭 사용

#### 주석
```c
// 한 줄 주석

/*
   여러 줄 주석
   여러 줄에 걸쳐 작성 가능
*/
```

---

## 3. 데이터 타입과 변수

### 3.1 기본 데이터 타입

| 데이터 타입 | 크기 | 범위 | 포맷 지정자 | 예제 |
|------------|------|------|-------------|------|
| char | 1바이트 | -128 ~ 127 | %c | 'A' |
| int | 4바이트 | -2,147,483,648 ~ 2,147,483,647 | %d | 123456 |
| float | 4바이트 | ±3.4E±38 | %f | 3.14f |
| double | 8바이트 | ±1.7E±308 | %lf | 3.14159265 |

### 3.2 변수 선언과 초기화

```c
#include <stdio.h>

int main() {
    // 변수 선언
    int age;
    char grade;
    float height;
    double pi;
    
    // 변수 초기화
    age = 25;
    grade = 'A';
    height = 175.5f;
    pi = 3.14159265;
    
    // 선언과 초기화 동시에
    int score = 95;
    
    // 출력
    printf("나이: %d\n", age);
    printf("학점: %c\n", grade);
    printf("키: %.1f\n", height);
    printf("점수: %d\n", score);
    
    return 0;
}
```

### 3.3 변수 명명 규칙
- 영문자, 숫자, 언더스코어(_)만 사용
- 첫 글자는 영문자 또는 언더스코어
- 대소문자 구분
- 예약어 사용 불가

---

## 4. 상수와 전처리기

### 4.1 상수 정의

```c
#include <stdio.h>
#define PI 3.14159
#define MAX_SIZE 100

int main() {
    const int DAYS_IN_WEEK = 7;
    
    printf("원주율: %f\n", PI);
    printf("최대 크기: %d\n", MAX_SIZE);
    printf("일주일: %d일\n", DAYS_IN_WEEK);
    
    return 0;
}
```

### 4.2 전처리기 지시문
- `#include`: 헤더 파일 포함
- `#define`: 매크로 정의
- `#ifdef`, `#ifndef`: 조건부 컴파일

---

## 5. 연산자

### 5.1 산술 연산자

```c
#include <stdio.h>

int main() {
    int a = 10, b = 3;
    
    printf("a + b = %d\n", a + b);  // 덧셈: 13
    printf("a - b = %d\n", a - b);  // 뺄셈: 7
    printf("a * b = %d\n", a * b);  // 곱셈: 30
    printf("a / b = %d\n", a / b);  // 나눗셈: 3
    printf("a %% b = %d\n", a % b); // 나머지: 1
    
    return 0;
}
```

### 5.2 증감 연산자

```c
#include <stdio.h>

int main() {
    int x = 5;
    
    printf("x = %d\n", x);        // 5
    printf("++x = %d\n", ++x);    // 6 (전위)
    printf("x++ = %d\n", x++);    // 6 (후위)
    printf("x = %d\n", x);        // 7
    
    return 0;
}
```

### 5.3 관계 연산자

```c
#include <stdio.h>

int main() {
    int a = 10, b = 20;
    
    printf("a < b: %d\n", a < b);   // 1 (참)
    printf("a > b: %d\n", a > b);   // 0 (거짓)
    printf("a == b: %d\n", a == b); // 0 (거짓)
    printf("a != b: %d\n", a != b); // 1 (참)
    
    return 0;
}
```

### 5.4 논리 연산자

```c
#include <stdio.h>

int main() {
    int x = 1, y = 0;
    
    printf("x && y: %d\n", x && y); // 0 (AND)
    printf("x || y: %d\n", x || y); // 1 (OR)
    printf("!x: %d\n", !x);         // 0 (NOT)
    
    return 0;
}
```

---

## 6. 제어문

### 6.1 if-else문

```c
#include <stdio.h>

int main() {
    int score = 85;
    
    if (score >= 90) {
        printf("A학점\n");
    } else if (score >= 80) {
        printf("B학점\n");
    } else if (score >= 70) {
        printf("C학점\n");
    } else {
        printf("재수강\n");
    }
    
    return 0;
}
```

### 6.2 switch문

```c
#include <stdio.h>

int main() {
    char grade = 'B';
    
    switch (grade) {
        case 'A':
            printf("우수\n");
            break;
        case 'B':
            printf("양호\n");
            break;
        case 'C':
            printf("보통\n");
            break;
        default:
            printf("노력하세요\n");
    }
    
    return 0;
}
```

### 6.3 for문

```c
#include <stdio.h>

int main() {
    int sum = 0;
    
    for (int i = 1; i <= 10; i++) {
        sum += i;
        printf("i=%d, sum=%d\n", i, sum);
    }
    
    printf("1부터 10까지의 합: %d\n", sum);
    return 0;
}
```

### 6.4 while문

```c
#include <stdio.h>

int main() {
    int num = 1;
    
    while (num <= 5) {
        printf("%d\n", num);
        num++;
    }
    
    return 0;
}
```

---

## 7. 배열

### 7.1 1차원 배열

```c
#include <stdio.h>

int main() {
    int numbers[5] = {10, 20, 30, 40, 50};
    int sum = 0;
    
    printf("배열 요소 출력:\n");
    for (int i = 0; i < 5; i++) {
        printf("numbers[%d] = %d\n", i, numbers[i]);
        sum += numbers[i];
    }
    
    printf("배열 합계: %d\n", sum);
    return 0;
}
```

### 7.2 2차원 배열

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    printf("3x3 행렬:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
    
    return 0;
}
```

---

## 8. 포인터

### 8.1 포인터 기본 개념

```c
#include <stdio.h>

int main() {
    int x = 10;
    int *ptr = &x;
    
    printf("변수 x의 값: %d\n", x);
    printf("변수 x의 주소: %p\n", &x);
    printf("포인터 ptr의 값: %p\n", ptr);
    printf("포인터 ptr이 가리키는 값: %d\n", *ptr);
    
    // 포인터로 값 변경
    *ptr = 20;
    printf("포인터로 값 변경 후 x: %d\n", x);
    
    return 0;
}
```

### 8.2 포인터와 배열

```c
#include <stdio.h>

int main() {
    int arr[5] = {1, 2, 3, 4, 5};
    int *ptr = arr;
    
    printf("배열과 포인터:\n");
    for (int i = 0; i < 5; i++) {
        printf("arr[%d] = %d, *(ptr+%d) = %d\n", 
               i, arr[i], i, *(ptr + i));
    }
    
    return 0;
}
```

---

## 9. 함수

### 9.1 기본 함수

```c
#include <stdio.h>

void greet() {
    printf("안녕하세요!\n");
    printf("C언어 함수 예제입니다.\n");
}

int main() {
    greet();
    greet();
    return 0;
}
```

### 9.2 매개변수가 있는 함수

```c
#include <stdio.h>

void printInfo(char name[], int age) {
    printf("이름: %s\n", name);
    printf("나이: %d세\n", age);
}

int main() {
    printInfo("홍길동", 25);
    printInfo("김철수", 30);
    return 0;
}
```

### 9.3 반환값이 있는 함수

```c
#include <stdio.h>

int add(int a, int b) {
    return a + b;
}

double average(int a, int b, int c) {
    return (a + b + c) / 3.0;
}

int main() {
    int result = add(10, 20);
    printf("10 + 20 = %d\n", result);
    
    double avg = average(80, 90, 85);
    printf("평균: %.1f\n", avg);
    
    return 0;
}
```

### 9.4 재귀 함수

```c
#include <stdio.h>

int factorial(int n) {
    if (n <= 1) {
        return 1;
    }
    return n * factorial(n - 1);
}

int main() {
    int num = 5;
    int result = factorial(num);
    printf("%d! = %d\n", num, result);
    return 0;
}
```

---

## 10. 구조체

### 10.1 기본 구조체

```c
#include <stdio.h>
#include <string.h>

struct Student {
    char name[50];
    int age;
    double gpa;
};

int main() {
    struct Student s1;
    
    strcpy(s1.name, "김학생");
    s1.age = 20;
    s1.gpa = 3.75;
    
    printf("학생 정보:\n");
    printf("이름: %s\n", s1.name);
    printf("나이: %d세\n", s1.age);
    printf("학점: %.2f\n", s1.gpa);
    
    return 0;
}
```

### 10.2 구조체 배열

```c
#include <stdio.h>
#include <string.h>

struct Student {
    char name[50];
    int age;
    double gpa;
};

int main() {
    struct Student students[3];
    
    strcpy(students[0].name, "김철수");
    students[0].age = 20;
    students[0].gpa = 3.5;
    
    strcpy(students[1].name, "이영희");
    students[1].age = 19;
    students[1].gpa = 3.8;
    
    strcpy(students[2].name, "박민수");
    students[2].age = 21;
    students[2].gpa = 3.2;
    
    for (int i = 0; i < 3; i++) {
        printf("학생 %d: %s, %d세, GPA %.1f\n", 
               i+1, students[i].name, students[i].age, students[i].gpa);
    }
    
    return 0;
}
```

---

## 11. 실습 예제

### 실습 1: 성적 관리 프로그램
```c
#include <stdio.h>

int main() {
    int scores[5];
    int sum = 0;
    double average;
    
    printf("5명의 점수를 입력하세요:\n");
    for (int i = 0; i < 5; i++) {
        printf("학생 %d: ", i + 1);
        scanf("%d", &scores[i]);
        sum += scores[i];
    }
    
    average = sum / 5.0;
    
    printf("\n=== 결과 ===\n");
    printf("총합: %d\n", sum);
    printf("평균: %.2f\n", average);
    
    return 0;
}
```

### 실습 2: 간단한 계산기
```c
#include <stdio.h>

double calculate(double a, double b, char op) {
    switch (op) {
        case '+': return a + b;
        case '-': return a - b;
        case '*': return a * b;
        case '/': return b != 0 ? a / b : 0;
        default: return 0;
    }
}

int main() {
    double num1, num2, result;
    char operator;
    
    printf("계산식을 입력하세요 (예: 10 + 5): ");
    scanf("%lf %c %lf", &num1, &operator, &num2);
    
    result = calculate(num1, num2, operator);
    printf("결과: %.2f\n", result);
    
    return 0;
}
```

---

## 12. 학습 체크리스트

- [ ] Hello World 프로그램 작성
- [ ] 데이터 타입과 변수 선언
- [ ] 상수와 전처리기 지시문
- [ ] 산술, 관계, 논리 연산자
- [ ] if-else 조건문
- [ ] switch-case 다중 선택
- [ ] for, while 반복문
- [ ] 1차원, 다차원 배열
- [ ] 포인터 기본 개념
- [ ] 포인터와 배열 관계
- [ ] 함수 정의와 호출
- [ ] 재귀 함수
- [ ] 구조체 정의와 사용
- [ ] 구조체 포인터와 배열
- [ ] 동적 메모리 할당
- [ ] 파일 입출력
- [ ] 문자열 처리
- [ ] 비트 연산

---

## 추가 학습 자료

### 권장 실습
1. 다양한 예제 코드 직접 작성
2. 에러 메시지 해석 연습
3. 디버깅 도구 활용
4. 코드 리뷰 및 최적화

### 다음 단계
- 고급 포인터 (이중 포인터, 함수 포인터)
- 링크드 리스트, 스택, 큐 등 자료구조
- 파일 처리와 시스템 프로그래밍
- C++ 또는 다른 언어로 확장

---
