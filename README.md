# Spring1
> Spring1 스터디
--------

## Member
> 조현호 윤혜정 이가영 최서영

---

## Date
> 매주 화요일 오전 10시

---
# Chapter 5
## 변수와 자료형 - 변수
- 정수형 변수 : int num
- 실수형 변수 : double width
- 참조형 변수 : String content

### [변수 규칙]
 1. 1개의 변수 -> 1개의 값만 할당 가능
 2. 변수에 저장된 값 -> 재할당을 통해 변경 가능
 3. 값의 형태에 맞는 자료형을 사용
 4. 변수명은 소문자로 시작
 5. 대소문자 구분, 공백 포함 불가능
 6. 자바 예약어 사용 불가 {ex) int int = 1, int double = 1…}
 
## 변수와 자료형 - 기본형
> [정수형]
 1. byte (1 byte = 8 bits)
 2. short (2 bytes)
 3. int (4 bytes)
 4. long (8 bytes)
 >  [실수형]
 1. double (8 bytes)
 2. float (4 bytes)
 > [문자형]
 1. char (2 bytes)
 2. 아스키코드
 3. 유니코드
 > [논리형]
 1. boolean (1 byte) : 1과 0은 사용 불가능
 
 ## <변수와 자료형 - 참조형>
- 참조형 데이터의 값 : '힙 메모리 영역'에 생성
- 변수에 대입되는 값 : '힙 메모리 영역의 주소값'
 ex) String a = new String(origianl:"Hello!"); : new를 적음으로서 무조건 새로운 주소를 만들어 줌

 ## <변수와 자료형 - 상수>
  - 상수(constants, final variables) : 한 번 값이 할당하면 재할당 불가능
  - final : 고정적으로 사용해야 하는 값을 프로그램 상단에 상수로 선언해서 사용하기
  
 ## <변수와 자료형 - 형변환>
 byte < short < int < long <<< float < double
 ```java
 ex 1)  
 int a = 128;
 short b = a;
 System.out.println(b); //  에러남 (int가 short보다 더 크기 때문에)
 ex 2)
 byte c= 128;
 System.out.println(c); // 에러남 (byte 범위 안에 들어가지 못하므로 가장 작은 값으로 출력)
 ```
  - 나타낼 수 있는 범위가 다른 것끼리 계산하면 (뭐)를 (뭐)로 바꾼 다고 선언해야 함
  - (short), (e+f) …
 
 
 ex 1) 
 ```java
 int d = 10;
 short e = 20;
 short f = (short) (e+f);
 System.out.println(g); : 30
```

## <변수와 자료형 - String>
### 문자열 객체(객체 : 힙 메모리 영역, 변수 : 힙 메모리 영역의 주소)
  - str 문자열 객체와 비교 대상의 내용이 같은 지 참 거짓 결정 
  - 값 비교할 때 등호 사용 대한 equals 사용
  ```java 
  if (str.equals(str_2)) {
	System.out.println(“str.equals(str_2)”);
  }
  ```
  - 비교해서 참인지 거짓인지 판단한 것이 결과 값

--- 

## <문자열 병합>
1. '+' 연산자
```java
  String str_1 = “Hello, ”;
  String str_2 = “World!”;
  System.out.println(str_1 + “ ” + str_2);
```
>결과값 : Hello, World!

2. StringBuilder
 - 임시 객체를 만들지 않고 Hello World 생성 가능
 - 속도 빠르고 메모리 효율적
 - String : 수정 불가능, Builder : 수정 가능
 
## <문자열 슬라이스>
```java
ex)          //   0 123 4 56
String str_1 = "이름: 김자바";
String str_name = str_1.substring(4, 7);  // (0, 0)의 앞은 시작 숫자, 뒤는 끝나는 숫자 뒷 숫자
System.out.println(str_name);
```
> 결과값 : 김자바

## <문자열 대소문자 변환>
 - 대문자와 소문자 구분
 - equlasIgnoreCase : 대소문자를 무시하고 값을 비교함

## <공백 제거>
1. 양쪽 끝 공백  
 - trim : 양쪽 끝 공백만 제거 가능
2. 문자열 중간 공백
 - replace(어떤 문자를 어떤 문자로 치환) : 양쪽 끝 공백 뿐만이 아닌 중간 공백이 다 사라짐

## <변수와 자료형 - 콘솔 입출력>
```java
Scanner sc = new Scanner(Ststem.in);
    System.out.println(“아이디를 입력해주세요. >>”);
String username = sc.nextLine();
    System.out.println(“생년월일을 입력해주세요. >>”);
int birthDate = sc.nextLine();
    System.out.printf(“%s %d”, username, birthDate);
// %s : username, %d : birthdate, print(ln) : ln 안 적으면 바로바로 입력 가능, \n : 다음 줄에 입력, \t : spacebar
```

---

# Chapter 8
  ## 배열
  - 동일한 자료형(Data Type)의 데이터를 연속된 공간에 저장
  - 자료형[] 변수 = {데이터1, 데이터2, 데이터3, ... };
  - 한 번 생성된 배열은 길이 고정

  ### 배열 선언 1
``` java
  int[] intArr; // int형 배열
  char[] charArr; // char형 배열
  String[] days = { "월", "화", "수", "목", "금", "토", "일" };
```

  ### 배열 선언 2
``` java
  Type[] arr = new Type[length];
```

  ### 반복문에서 활용
``` java
for(int i=0; i < days.length, i++)
  System.out.println(days[i]);

for(int i : days)
  System.out.println(i);
```
---

  ## 리스트
  - 순서 구분하며 중복을 허용한다.
  - Vetor, ArrayList, LinkedList 가 있으며 이 중  ArrayList가 가장 활용성이 좋다.
  - 리스트의 경우 자료를 넣는 만큼 자동적으로 크기 확장

  ### 선언부
  ``` java
  import java.util.ArrayList;
  ArrayList list = new ArrayList(리스트의 길이) //객체이기 때문에 자료형에 관계없이 모두 저장 가능
  ```

  ### 리스트 함수
  ``` java
  list.add(data) // data 삽입
  list.get(data) // 리스트 내의 data를 가져옴
  list.size() // list의 길이 리턴
  list.remove(data) // data 삭제
  ```
  ### 활용
  ``` java
  ArrayList<자료형> list = new ArrayList(list.length) // => 지정한 자료형만 저장 가능
  list.size(); list.get(i)
  for(int i=0;i<list.size();i++{
    System.out.println(list.get(i));
  ```

---

## 맵
- 해싱(Hashing)된 맵(Map)
- 키-값의 쌍을 요소로 가지는 데이터의 집합, 순서를 구분하지 않음
- 키값은 중복불가, 값은 중복 가능
- (key, value)를 묶어 item이라고 말함

### 해쉬맵 선언
``` java
import java.util.HashMap;

HashMap map = new HashMap(); // 
map.put("age",30);
map.put("mbti", "INFP");

System.out.println(map.get("age"));
```

### 해쉬맵 함수
``` java
  map.put(key, value) // data 삽입
  map.get(key) // key에 해당하는 value값
  map.containsKey(key) // key가 있는지 조사 후 참, 거짓 리턴
  map.remove(key) // key값에 해당하는 item 삭제 후 value값 리턴
```

### sorting map
- LinkedHashMap은 입력된 순서대로 데이터를 저장
- TreeMap은 입력된 key의 오름차순 순서로 데이터를 저장

---

# Chapter9
## 함수(메서드)?
> 자바는 다른 언어와 달리 함수라는 것이 따로 존재하지는 않고 클래스내에! 존재한다.
> 이러한 클래스 내의 함수를 메서드라고 부른다.
> 하나의 작업단위를 이루는 코드를 한 묶음으로 만들어서 재사용할 수 있도록 만든 것
> 어떠한 값이 넘겨지거나 아무 값도 넘겨지지 않았을 때 작업을 수행한 후 반환하거나 혹은 반환하지 않고 종료

### 자바 메서드의 구조
```java
리턴자료형 메서드명(입력자료형1 매개변수1, 입력자료형2 매개변수2, …){
	…
	return 리턴값; // 리턴자료형이 void인 경우 return 문이 필요없다.
}
```

1. 입력 O, 출력 O
```java
static int mod (int a, int b){
  int result = a % b;
  return result;
}
```

2. 입력 O, 출력(반환) X
```java
static void printNum(int a){ // 여기서 a는 매개변수!
  System.out.println(a);
}
```

3. 입력 X, 출력(반환) O
```java
static String greeting(){
  return "Hello!";
}
```

4. 입력 X, 출력(반환) X
```java
static void greeting_2(){
  System.out.println("Hello!);
}
```

5. 자료구조 형태 (리스트ver.)
```java
static void printListElements(ArrayList List){
  for (int i = 0; i < List.size(); i++){
    System.out.println(List.get(i));
  }
}
```

- 메인함수
```java
public static void main(String[] args){

  int mod_result = mod(3, 2); // 여기서 3, 2는 인수!
  Sysyem.out.println(mod_result); // 1
  
  printNum(10); // 10
  
  String str = greeting();
  Sysyem.out.println(str); //Hello -> 얘는 str에 반환값이 저장되어있음
  
  greeting_2(); // Hello -> 얘는 저장되지 않고 그냥 출력 중..
  
  ArrayList list_1 = new ArrayList<>();
  list_1.add(10);
  list_1.add(100);
  
  printListElements(list_1); // 10 \n 100

}
```

### 매개변수와 인수
> 매개변수는 ‘Parameter’라고 하며 메서드에 전달된 값을 저장하는 변수를 말한다.
> 인수는 ‘Arguments’라고 하며 메서드에 전달하는 값을 말한다.

---