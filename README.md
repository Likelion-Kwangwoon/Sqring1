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
# 연산자

## 산술 연산

1. + : 더하기
2. - : 빼기
3. * : 곱하기
4. / : 몫 반환하는 나누기
> 정수형 10/20 의 값은 0 , 실수형 10/20의 값은 0.5
5. % : 나머지 반환하는 나누기 연산자

* 문자열이 아닌 데이터와 문자열을 + 연산자를 이용해 병합하면 다른 데이터를 문자열로 인식하여 합쳐서 반환

## 비교 연산
- <, >, ==, <=, >=, != 과 같은 비교 연산자를 사용하여 true, false 반환
- = 과 == 의 차이
  - = : 대입 연산자
  - == : 비교 연산자

* 참조형은 비교할 수 없기 때문에 string은 등호가 아닌 equals로 비교

## 논리 연산자

1. AND 연산자 (&&)
 - 여러 조건 모두 만족 시 true, 조건 하나라도 불충족 시 false
2. OR 연산자 ( || )
 - 조건 중 하나만 만족해도 true
3. NOT 연산자 ( ! )
 - 사용한 boolean 값에 반대되는 값 반환

## 대입 연산자

- = : 등호를 사용하여 대입

## 증감 연산자

> 반환되는 시점으로 구분
- a 먼저 출력 후 연산
 - a++
 - a--
- a 연산 후 출력
 - ++a
 - --a

# 조건문

## IF
```java
if (조건식){
    ~
 }
 else{
    }
```

- 다중조건문 (조건 만족하는 최초 분기만 실행)
```java
if (조건식){
 }
  else if{
  }
  else{
  }
```
## Switch

> 결과로 매치되는 데이터가 무엇인지 각각의 case로 구분 출력
```java
int a = 10;
  Switch(식 ex a+1){
    case 10: 
       System.out.println("a+1 == 10");
       break;
    case 11:
       System.out.println("a+1 == 11");
       break;
  }
```

- case는 조건을 만족해도 계속 내려가면서 실행
- case 하위에 break를 써서 빠져나올 수 있게 해야함

# 반복문

## For
```java
for (int 형태의 초기화된 변수; 조건식; 증감식){
    System.out.println(변수);
}
```
- 무한루프가 발생하지 않도록 조건식 작성

## while

- 외부에 초기화된 변수 배치
```java
while(조건식){
    System.out.println(변수);
    증감식;
  }
```
-조건식 확인 후 실행

## do while
```java
do{
    System.out.println(변수);
    증감식;
} while(조건식);
```
- 실행 후 조건식 확인

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

# Chapter9 (서영)
## 함수(method)
 - 어떠한 값이 넘겨지거나 아무 값도 넘겨지지 않았을 때
 - 작업을 수행한 후 
 - 반환하거나 혹은 반환하지 않고 종료

1. 입력 O, 출력(반환) O
```java
int mod (int a, int b) {           // int와 
    int result = a % b;
    return result; // 반환해서 사용   // 의 result의 형태가 같아야 함
}
```

2. 입력 O, 출력(반환) X
```java
void printNum (int a) {
    System.out.println(a); // 콘솔에 출력 O, 메모리에 저장 X
}
```

3. 입력 X, 출력(반환) O
```java
String greeting() {    // 입력값이 없으므로 ()안에 아무것도 안넣음
    return "Hello!";   // return으로 반환은 함
}
```

4. 입력 X, 출력(반환) X
```java
void greeting_2() {               // 입력 X
    System.out.println("Hello!")  // 출력만하고 데이터 휘발
}
```
예시 1
```java
public static void main(String[] args) {
    int mod_result = mod(3, 2);    // mod : 나머지 구하는 연산자
    System.out.println(mod_result);
}
```
-> 1

예시 2
```java
public static void main(String[] args) {
    String str = greeitng();
    System.out.println(str);
}
```
-> Hello!

## 함수 - 자료 구조 형태
```java
public static void main(String[] args) {
    static void printListElements(ArrayList list) {
            for (int i = 0; i < list.size(); i++) {
                System.out.println(list.get(i));
            }
    }
}
```
--> 불필요한 반복 작업, 조건문이 길어질 때 -> 함수로 구현

```java
public static void main(String[] args) {
    ArrayList list_1 = new ArrayList<>;
    list_1.add(10);
    list_1.add(100);

    printListElements(list_1);
}
```
-> 10, 100

---
# Chapter 10

## 실습 - 회원가입 프로그램
### 회원가입 처음
```java
public static void main(String[] args) {
        System.out.println("=============");
        System.out.println("회원등록");
        System.out.println("=============");  // 프로그램 제목을 나타내는 것을 꾸며줌

        boolean register = false;
        Scanner sc = new Scanner(System.in);

        while(!register) {  // !register : true
            System.out.println("회원가입을 하시겠습니까?\ny : 진행  N : 취소");
            System.out.print(">> ");  // 문자를 계행하지 않고 사용자가 입력한 문자 그대로를 출력하게 함(ln지우기).
            String register_input = sc.nextLine(); // (scanner)우리가 만들었던 객체에서 nextLine 함수를 통해서 사용자의 입력을 받음. -> 대기
            if (register_input.equalsIgnoreCase("y")) {   
                register = true;  // !register가 false이므로 while문 반복
                System.out.println("=============");
                System.out.println("회원가입이 진행됩니다.");
                System.out.println("=============");
            } else if (register_input.equalsIgnoreCase("n")) {
                System.out.println("=============");
                System.out.println("회원가입이 종료됩니다.");
                System.out.println("=============");
                System.exit(0);  // 0 : 정상 종료
            } else {
                System.out.println("입력값을 확인해주세요."); // y, n 이외에 다른 값을 입력했을 때
            }
        }

        }
```

### 회원가입 중 ID, PW, 이름, 생년월일, 이메일 생성
```java
    ArrayList users = new ArrayList();
        
        while (true) {     
                HashMap user = HashMap(); // HashMap : 한명의 user을 담을 때 사용 
            //ID
            System.out.print("ID :  ");
            String username = sc.nextLine();
            //PW
            String password = "";
            while (true) {  
                System.outprint("PW:  ");
                pasword = sc.nextLine();
                System.out.print("PW 확인 :  ");
                String password_confirm = sc.nextLine();

                if (password.equals(password_confirm)) {
                    break;
                } else {
                    System.out.println("=============");
                    System.out.println("패스워드가 일치하지 않습니다.");
                    System.out.println("패스워드를 다시 입력해주세요.");
                    System.out.println("=============");
                }
            }

            //이름
            System.out.print("성명 :  ");
            String name = sc.nextLine();

            //생년월일(6자리)
            String birth_date = "";
            while (true) {
                System.out.print("생년월일(6자리) :  ");
                birth_date = sc.nextLine();
                if(birth_date.length()==6) {
                    break;
                } else {
                    System.out.println("=============");
                    System.out.println("생년월일 자릿수가 올바르지 않습니다.");
                    System.out.println("생년월일을 다시 입력해주세요.");
                    System.out.println("=============");
                }
            }

            //이메일
            System.out.print("이메일 :  ");
            String email = sc.nextLine(); 
        }
            
```

### 회원가입 마지막
```java
 ArrayList users = new ArrayList();

        user.put("username", username);
        user.put("password", password);
        user.put("nave", name);
        user.put("birth_date", birth_date);
        user.put("email", email);

        user.add(user);

        System.out.println("------------------");
        System.out.println(user.get("name" + "님, 가입을 환영합니다"));
        System.out.println("ID는 "user.get("username") + "입니다.");
        System.out.println("------------------");

        System.out.println("회원가입을 이어서 진행하시겠습니까?\ny : 진행  N : 취소");
        System.out.print(">> ");  
        String register_again = sc.nextLine();

        if (register_again.equlasIgnorecase("y")) {
            ;
        } else if (register_again.equalsIgnoreCase("n")) {
            System.exit(0);
        }
```
---

# Chapter 11
## 객체지향 프로그래밍
- 객체지향 프로그래밍 참고 사이트
> https://jongminfire.dev/%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D%EC%9D%B4%EB%9E%80

## 클래스
> 객체 지향 프로그래밍의 추상화 개념 구현
> 클래스는 속성 나타내는 멤버(member), 기능을 표현하는 메소드(method)
```java
public class BankAccount{
  // 멤버변수
  int bankCode;
  int accountNo;
  String owner;
  int balance;
  boolean isDormant;
  int password;

  // 메소드
  void inquiry(){} // 잔액 조회
  void deposit(){} // 계좌 입금
  void withdraw(){} // 계좌 출금
}
```


## 접근제어자
![image](https://user-images.githubusercontent.com/101550897/236931578-327a1f6f-8afa-46fb-9f97-ade1e03cfeca.png)

- public
> 패키지, 클래스 제한이 없음

- private
> 같은 클래스에서만 접근 가능 

- protected
> 같은 패키지에서만 접근이 가능 

- default
> 같은 패키지, 해당 클래스를 상속 받은 다른 패키지의 자손 클래스에서 접근 가능. 
> 접근제어자를 설정하지 않았을 때 값이 default로 설정 

## 상속
```java
  public class Person {
    private String name;
    private int age;
  }

  public class Student extends Person{
    private String 
  }
  public class Professor extends Pers on{
    ...
  }
  
```
### Overloading
> 부모 클래스에서 상속받은 메서드에서 파라미터를 변경
 1. 매개변수의 개수가 달라야함
 2. 매개변수의 타입이 달라야함 
```java
  void inquiry(double currencyRate)
  void inquiry(int currencyRate)
  void inquiry(int i_currencyRate, double d_currencyRate)

```
### Overriding
> 부모 클래스에서 상속받은 메서드의 내용을 재정의
```java
  public class BankAccount{
    ...
  // 메소드
  void inquiry(){} // 잔액 조회
  void deposit(){} // 계좌 입금
  void withdraw(){} // 계좌 출금
}
public class DollorAccount{
    ...
  // 메소드
  void inquiry(){
    System.out.println("계좌 출금")
  }
}
```

>>오른쪽 마우스 -> Generater -> Getter/Setter -> private 멤버 변수 접근 함수 생성 가능
![getter_setter](https://user-images.githubusercontent.com/101550897/236928509-727bce03-b083-448c-9959-36f4a273cf38.png)



---
# Chapter 12
## 예외 처리
- 예외(Exception): 코드 실행 단계에서 발생하는 예상할 수 있는 에러
```java
int a = 10;
int b= 0;
int c= a/b;
```
- 위 코드는 0으로 나눌 수 없기 때문에 에러가 뜬다.

```java
try {
   arrayList.get(10); //에러가 발생할 가능성이 있는 코드를 넣기
}
catch(IndexOutOfBoundsException ioe){} 
// 예상되는 예외가 특정될 때

catch(IllegalArgumentException iae){} 

catch(Exception e){}
// 예상되는 예외 나열 후 마지막은 최상위의 Exception을 하는 것이 좋음
// 처리되지 않은 예외들 처리 가능

finally{
      // 위와 상관없이 무조건 실행됨
}
```

---
# Chapter 13
## 클라이언트와 서버의 만남
### Web의 등장

- 일방향적으로 정보를 제공받던 사용자들이 직접 정보를 생산,공유

### 클라이언트와 서버

- 클라이언트: 브라우저를 통해서 요청을 보내는 주체 
- 서버 : 요청에 대한 응답을 하는 주체

## HTTP 와 URL
### http : HyperText Transfer Protocol , 하이퍼 텍스트 전송 규칙
### 클라이언트와 서버가 http로 소통한다.
### url : Uniform Resource Locator , 인터넷에 있는 각종 자원들의 주소 체계

### 구조
#### https:// www.google.com/search?q=techit

- https:// : 프로토콜(통신 규칙, http,https, ftp 등) 
- www.google.com : 호스트(서버의 주소)
- /search : 경로, 호스트 내 서비스 위치, 서비스 별로 분할 (ex 검색, 회원 등)
- ?q=techit : 쿼리 문자열(Query String) , ? 문자로 시작, &로 연결 , 키/값 쌍으로 구성
* 사용자가 쿼리를 임의로 붙여서 만들 수는 없다

---

## 💿쿠키와 세션
### 쿠키와 세션을 왜 사용하나요?
- HTTP 환경은 “connectionless, stateless” 한 특성을 가지기 때문에 서버는 클라이언트가 누구인지 매번 확인해야 합니다. 이를 위해 쿠키와 세션 사용합니다.
#### Connectionless
- 클라이언트가 요청을 한 후 응답을 받으면 그 연결을 끊어버리는 특징
#### Stateless
- 통신이 끝나면 상태를 유지하지 않는 특징

### 🍪쿠키란?
> - 클라이언트 로컬에 저장되어 있는 키/값 형태의 작은 데이터 파일
> - 사용자 인증이 유효한 시간 명시, 유효 시간이 정해지면 브라우저가 종료되어도 인증 유지
> - 클라이언트의 상태 정보를 로컬에 저장했다가 참조
> - 최대 300개의 쿠키 저장 가능, 도메인 당 20개의 값, 하나의 쿠키 당 4KB까지 저장

### 쿠키의 구성요소
- 이름
- 값
- 유효시간
- 도메인: 쿠키를 전송 할 도메인
- 경로: 쿠키를 전송 할 요청 경로

### 쿠키 동작 방식
1. 클라이언트가 페이지를 요청
2. 서버에서 쿠키 생성
3. HTTP 헤더에 쿠키를 포함시켜 응답
4. 브라우저가 종료되어도 쿠키 만료 기간이 있다면 클라이언트에서 보관
5. 같은 요청 시 HTTP 헤더에 쿠키를 함께 보냄
6. 서버에서 쿠키를 읽어 이전 상태 정보를 변경 할 필요가 있을 때 쿠키를 업데이트 해 변경된 쿠키를 HTTP 헤더에 포함시켜 응답

#### 사용 예
> - 로그인 시 “아이디와 비밀번호 저장하시겠습니까?”
> - 쇼핑몰 장바구니 기능
> - 자동 로그인 시 “오늘 더 이상 이 창을 보지 않음” 등

### 🍫세션이란?
> -  세션은 쿠키를 기반하고 있음. 그러나 쿠키는 사용자 정보 파일을 브라우저에 저장, 세션은 서버 측에서 관리
> - 서버에서는 클라이언트 구분을 위해 세션 ID를 부여하고 웹 브라우저가 서버에 접속해서 브라우저를 종료할 때까지 인증상태 유지
> - 접속 시간 제한 가능
> - 쿠키보다 보안은 좋으나, 사용자 많아질 수록 서버 메모리 부하

### 세션 동작 방식
1. 클라이언트가 서버 접속 시 세션 ID 발급
2. 클라이언트는 세션 ID에 대해 쿠키를 사용해 저장
3. 클라이언트는 서버에 요청할 때, 이 쿠키 세션 ID를 같이 서버에 전달해 요청
4. 서버는 세션 ID를 전달 받아 세션에 있는 클라이언트 정보 가져와 사용
5. 클라이언트 정보를 가지고 서버 요청 처리, 응답

### 세션 특징
> - 각 클라이언트에 고유 ID부여
> - 세션 ID로 클라이언트를 구분해 클라이언트 요구에 맞는 서비스 제공
> - 보안 면에서 쿠키보다 우수
> -  사용자 많아질 수록 서버 메모리 부하

#### 사용 예
> - 로그인처럼 보안 상 중요 작업 수행 시 사용

### 쿠키와 세션의 차이?
- 쿠키 세션은 비슷함. 세션도 결국 쿠키 사용.
- 정보 저장 위치 : 쿠키 -> 브라우저, 세션 -> 서버
- 보안 : 세션 > 쿠키
- 속도 : 세션 < 쿠키

### 🍭세션이 더 빠른데 굳이 왜 쿠키를 사용할까요???
> 세션은 서버의 자원을 사용해서 무분별하게 만들면 서버의 메모리 과부하를 야기할 수 있습니다. 이렇게 되면, 속도가 느려지기 때문에 빠른 속도를 요구하는 업무에서는 쿠키가 유리하기도 합니다.
---

## IP, Port, DNS

- 네트워크
> 두 대 이상의 컴퓨터가 연결되어 있는 체계
- 스위치
> 여러 컴퓨터들을 하나의 동일한 네트워크망 안에 묶는 역할
> 다른 네트워크에 접근할 수 없음
- 라우터 = 공유기
> 스위치의 기능 포함, 서로 다른 네트워크 간의 통신 허용

### IP

- IP(Internet Protocol)
> 컴퓨터 간 데이터를 주고받는 네트워크 계층의 규약
- IP 주소
> - 네트워크에서 컴퓨터가 부여받는 고유한 주소
> - IPv4: 32비트, 메인으로 사용
> - IPv6: 128비트

![IP 주소](https://github.com/leegy21/image/assets/102893824/937d4f8d-f563-44fe-b29d-787d6340b102)

- 0.0.0.0 ~ 255.255.255.255 의 범위

#### 공인 IP vs 사설 IP 
- 공인 IP
> - 전체 인터넷 망에서 고유하게 식별 가능한 주소
> - SK,KT 등의 ISP(인터넷 서비스 제공자)가 공유기에 공인 IP를 할당

- 사설 IP
> - 가정의 LAN과 같은 네트워크에서 할당되는 주소, 컴퓨터에서 조회되는 IP
> - 공유기가 구성하는 새로운 네트워크 IP를 다양한 기기들이 각각 할당 받음

![공인사설 ip](https://github.com/leegy21/image/assets/102893824/78dbc121-d881-480f-8fca-a8c8e4d8ed97)
- 하나의 공인 IP에서 수많은 사설 IP 할당 가능

- 127.0.0.1
> = local host
> 컴퓨터 관점에서 자기 자신을 가리키기 위해 약속된 IP주소
> 내 컴퓨터에서만 유효

### Port

- 하나의 컴퓨터에서 실행되고 있는 다양한 서비스를 구분하는 역할
> HTTP -80
> HTTPS - 443
> SMTP - 25
> FRP- 21
> - IANA 에서 더 많은 서비스와 Port의 맵핑을 볼 수 있음

### DNS

- DNS(Domain Name Server) : URL을 해석하여 IP주소로 반환하는 서버
- 국가, 기업 등이 운영
- 전세계 DNS는 연결되어 있어 장애 발생 시 막대한 피해 발생

---