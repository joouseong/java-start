# JAVA

## 9월 22일
### 1. 주석(comment)
**주석의 종류**
* 한 줄 주석(single line comment)
  * //기호로 시작하며 이 기호 이후의 모든 텍스트는 주석 처리
* 여러 줄 주석(multi line comment)
  * /* 로 시작 */로 끝나며 이 사이의 모든 텍스트는 주석 처리

CommentJava
``` java
public class CommentJava {

    public static void main(String[] args) { //psvm 이라는 단축어를 사용하여 편리하게 생성
        System.out.println("Hello java1"); //sout이라는 단축어 사용 //hello java1을 출력합니다
        //System.out.println("hello java2");

        /*
        System.out.println("hello java3");
        System.out.println("hello java4");
        */

        // 한 줄 주석(single line comment)
        /*
           여러 줄 주석(multi line comment)
        */
    }
}
```
실행 결과
> Hello java1

### 자바란?
**자바 표준 스펙과 구현**<br>
자바는 **표준 스펙**과 **구현**으로 나눌 수 있음
* 자바 표준 스펙
  * 자바는 이렇게 만들어야 한다는 설계도이며, 문서
  * 이 표준 스펙을 기반으로 여러 회사에서 실제 작동하는 자바를 만듦
  * 자바 표준 스펙은 자바 커뮤니티 프로세스(JCP)를 통해 관리
* 다양한 자바 구현
  * 여러 회사에서 자바 표준 스펙에 맞추어 실제 작동하는 자바 프로그램을 개발
  * 각각 장단점이 있음. 예를 들어 Amazon Corretto는 AWS에 최적화 되어 있음
  * 각 회사들은 대부분 윈도우, MAC 리눅스 같이 다양한 OS에서 작동하는 버전의 자바도 함께 제공
* 자바 구현들은 모두 표준 스펙에 맞도록 개발되어 있음. 따라서 오라클 Open JDK를 사용하다가 Amazon Corretto 자바로 변경해도 대부분 문제 없이 작동

<br>

**컴파일과 실행**<br>
자바 프로그램은 컴파일과 실행 단계를 거침
* `Hello.java`와 같은 자바 소스 코드를 개발자가 작성
* 자바 컴파일러를 사용해 소스 코드를 컴파일
  * 자바가 제공하는 `javac` 라는 프로그램 사용
  * `.java` -> `.class` 파일 생성
  * 자바 소스 코드를 바이트 코드로 변환하여 JVM에서 더 빠르게 실행될 수 있게 최적화& 문법 오류 검출
* 자바 프로그램 실행
  * 자바가 제공하는 java라는 프로그램 사용
  * JVM이 실행되며 프로그램 작동

<br>

**IDE와 자바**<br>
인텔리제이를 통한 자바 설치 관리
* 인텔리제이는 내부에 자바를 편리하게 설치&관리할 수 있는 기능 제공

<br>

**인텔리제이를 통한 자바 컴파일, 실행 과정**
* 컴파일
  * 자바 코드를 컴파일 하려면 javac 라는 프로그램을 직접 사용해야 함, 인텔리제이는 자바 코드를 실행할 때 이 과정을 자동 처리
    * 예) `javac Hello.java`
  * 인텔리제이 화면에서 프로젝트에 있는 out 폴더에 가면 컴파일된 `.class` 파일이 존재
* 실행
  * 자바를 실행하려면 java 라는 프로그램 사용, 이때 컴파일된 `.class` 파일을 지정
  * 예) java Hello, 참고로 확장자는 제외
* 인텔리제이에서 자바 코드를 실행하면 컴파일과 실행을 모두 한번에 처리

<br>

**자바와 운영체제 독립성**<br>
일반적인 프로그램
* 일반적인 프로그램은 다른 운영체제에서 실행 X
* 예를 들어 윈도우 프로그램은 MAC이나 리눅스에서 작동 X
* 왜냐하면 각 OS마다 사용하는 명령어가 다르기 때문

자바 프로그램
* 자바 프로그램은 자바가 설치된 모든 OS에서 실행 가능
* 자바 개발자는 자바에만 맞추어 개발하면 됨. OS 호환성 문제는 자바가 해결.

자바 개발과 운영 환경
* 개발할 때 자바와 서버에서 실행할 때 다른 자바를 사용 가능
* 개발자들은 개발의 편의를 위해 윈도우나 MAC OS를 주로 사용
* 서버는 주로 리눅스를 사용. 만약 AWS를 사용한다면 Amazon Corretto 자바를 AWS 리눅스 서버에 설치
* 자바의 운영체제 독립성 덕분에 각각의 환경에 맞추어 자바 설치 가능

### 2. 변수
**패키지(package)**
* 이번에는 처음으로 패키지를 만듦
* 패키지는 쉽게 말해 자바 파일을 구분하기 위한 폴더로 이해하면 됨
* variable 이라는 패키지를 만들었다면, 해당 패키지에 들어가는 자바 파일 첫줄에 package variable; 와 같이 소속된 패키지를 선언해주어야 함
* 자바 파일이 위치하는 패키지와 package variable 선언 위치가 같아야 함

<br>

**변수 타입**
* int: 정수를 다룸. 예) 1, 100, 1000
* double: 실수를 다룸. 예) 0.2, 1.5
* boolean: 불리언 타입. true, false 값만 사용 가능. 주로 참과 거짓을 판단하는 곳에 사용
* char: 문자 하나를 다룰 때 사용. 작은따옴표(')로 감싸야 함. 예) 'A', '가'
* String: 문자열을 다룸. 큰따옴표 사용. 예) "Hello Java"
> 참고: String은 첫 글자가 대문자로 시작하는 특별 타입.

**자신의 타입에 맞는 데이터 사용**
각 변수는 지정한 타입에 맞는 값을 사용해야 함

<br>

**리터럴**
코드에서 개발자가 직접 적은 100, 10.5, true, 'A', "Hello Java" 와 같은 고정된 값을 리터럴이라 함
```java
int a = 100; //정수 리터럴
double b = 10.5; //실수 리터럴
boolean c = true; //불리언 리터럴
char d = 'A'; //문자 하나 리터럴? 캐릭터 리터럴?
String e = "Hello Java"; //문자열 리터럴? 스트링 리터럴?
```
변수의 값은 변할 수 있으나 리터럴은 개발자가 직접 입력한 고정된 값. 따라서 리터럴 자체는 변하지 않음
> 참고: 리터럴(literal)이라는 단어의 어원이 문자 또는 글자를 의미

<br>

## 9월 23일

**변수 타입2**
```java
package variable;

public class Var8 {

    public static void main(String[] args) {
        //정수
        byte b = 127; // -128 ~ 127
        short s = 32767; // -32768 ~ 32767
        int i = 2147483647; // -2,147,483,648 ~ 2,147,483,647 (약 21억)

        // -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807
        long l =9223372036854775807L;

        //실수
        float f = 10.0f;
        double d = 10.0;
    }
}
```
메모리를 많이 사용할수록 큰 숫자 표현 가능 <br>
변수를 선언하면 표현 범위에 따라 메모리 공간을 차지. 필요에 맞도록 다양한 타입 제공

<br>

**변수와 메모리 공간 크기**
* `byte` - 2<sup>8<sup/>
* `short` - 2<sup>16<sup/>
* `int` - 2<sup>32<sup/>
* `long` - 2<sup>64<sup/>

번외
* `boolean`: true, false (1byte)
* `char`: 문자 하나(1byte)
* `String`: 문자열(동적으로 달라짐)

<br>

**리터럴 티입 지정**
* 정수 리터럴 `int` 기본 사용, `int` 범위를 넘어가면 L을 붙여 정수 리터럴을 `long`으로 변경
* 실수 리터럴 `double` 기본 사용, `float`을 사용하려면 f를 붙여 `float` 형으로 지정

<br>

**다음 타입은 실무에서 거의 사용하지 않는다**
* `byte`: 표현 길이가 너무 작음.
  * but 파일을 바이트 단위로 다루기 때문에 파일 전송, 파일 복사 등에 사용
* `short`: 표현 길이가 너무 작음
* `float`: 표현 길이와 정밀도 낮음
* `char`: 문자 하나를 표현하는 일은 거의 없음
> 참고: 메모리 용량은 매우 저렴. 따라서 메모리 용량을 약간 절약하기 보다는 개발 속도나 효율에 초점을 맞후는 것이 더 효과적

<br>

**자주 사용하는 타입**
* 정수-`int`, `long`: 기본 타입인 `int` 사용. if 21억이 넘을 것 같으면 `long` 사용
  * 파일을 다룰 때는 `byte` 사용
* 실수-`double`: 실수는 고민하지 말고 `double` 사용
* 불린형-`boolean`: true, false 참 거짓을 표현. 조건문에서 자주 사용
* 문자열-`String`: 문자 하나든 문자열이든 모두 `String` 사용이 편리

자주 사용하는 타입을 제외하고 실무에서 나머지를 사용하는 경우는 거의 없음. 그나마 파일 전송시 `byte` 사용하는 정도

<br>

### 변수 명명 규칙
자바에서 변수의 이름을 짓는데는 규칙과 관례 존재 <br>
**규칙은 필수**. 규칙을 지키지 않으면 컴파일 오류 발생 <br>
**관례는 필수는 아니지만 전세계 개발자가 해당 관례를 따름**

**규칙**
* 숫자로 시작 X
  * but 숫자 포함 가능
* 공백 X
* 예약어를 변수 이름으로 사용 X
* 변수 이름에는 영문자, 숫자, $, 밑줄(_)만 사용 가능

**관례**
* 소문자로 시작하는 낙타 표기법
  * 소문자로 시작하는 것이 일반적. 여러 단어로 이루어진 변수 이름의 경우, 첫 번째 단어는 소문자로 시작<br> 그 이후의 각 단어는 대문자로 시작
  * 예) `orderDetail`, `myAccount`

<br>

**자바 언어의 관례를 한번에 정리** <br>
**클래스는 대문자로 시작, 나머지는 소문자로 시작**
* 클래스 이름 첫 글자는 대문자, 나머지는 모두 소문자로 시작. 여기에 낙타 표기법 적용
* 예) 클래스는 첫 글자 대문자, 나머지는 모두 소문자 시작 + 낙타 표기법
  * 클래스: `Person`, `OrderDetail`
  * 변수를 포함한 나머지: `firstName`, `userAccount`
* 예외 2가지
  * 상수는 모두 대문자 사용, 언더바로 구분
    * `USER_LIMIT`
  * 패키지는 모두 소문자 사용
    * `org.spring.boot`

**참고**: 변수 이름은 의미와 용도를 명확하게 설명해야 함
* `a`, `b`: 이런 변수는 용도 설명 X. 단순 예제에서만 사용 권장
* `studentCount`, `maxScore`, `userAccount`, `orderCount`: 용도 명확하게 설명

## 9월 29일
### 연산자

**연산자 종류**
* 산술 연산자
* 증감 연산자
* 비교 연산자
* 논리 연산자
* 대입 연산자
* 삼항 연산자

**연산자와 피연산자**
> 3 + 4 <br>
> a + b
* 연산자: 연산 기호
* 피연산자: 연산 대상

**산술 연산자**
```java
package operator;

public class Operator1 {

    public static void main(String[] args) {
        //변수 초기화
        int a = 5;
        int b = 2;

        // 덧셈
        int sum = a + b;
        System.out.println("a + b = " + sum); // 결과: 7
        // 뺄셈
        int diff = a - b;
        System.out.println("a - b = " + diff); // 결과: 3
        // 곱셈
        int multi = a * b;
        System.out.println("a * b = " + multi); // 결과: 10
        // 나눗셈
        int div = a / b;
        System.out.println("a / b = " + div); // 결과: 2
        // 나머지
        int mod = a % b;
        System.out.println("a % b = " + mod); // 결과: 1
    }
}
```

**문자열 더하기**
```java
public class Operator2 {

    public static void main(String[] args) {
        //문자열과 문자열 더하기
        String result1 = "hello " + "world";
        System.out.println(result1);

        //문자열과 문자열 더하기2
        String s1 = "string1";
        String s2 = "string2";
        String result2 = s1 + s2;
        System.out.println(result2);

        //문자열과 숫자 더하기1
        String result3 = "a + b = " + 10;
        System.out.println(result3);

        //문자열과 숫자 더하기2
        int num = 20;
        String str = "a + b = ";
        String result4 = str + num;
        System.out.println(result4);
    }
}
```

**연산자 우선순위**
```java
package operator;

public class Operator3 {

    public static void main(String[] args) {
        int sum1 = 1 + 2 * 3;
        int sum2 = (1 + 2) * 3;

        System.out.println("sum1 = " + sum1);
        System.out.println("sum2 = " + sum2);
    }
}
```
```java
package operator;

public class Operator4 {

    public static void main(String[] args) {
        int sum3 = 2 * 2 + 3 * 3;
        int sum4 = (2 * 2) + 3 * 3; // sum3과 같지만 가독성 up
        System.out.println("sum3 = " + sum3);
        System.out.println("sum4 = " + sum4);
    }
}
```

**연산자 우선순위 암기법**
1. 괄호()
2. 단항 연산자
3. 산술 연산자
4. shift 연산자
5. 비교 연산자
6. 등식 연산자
7. 비트 연산자
8. 논리 연산자
9. 삼항 연산자
10. 대입 연산자

다 외우지 않고 딱 2가지만 기억하기
1. 상식선에서 우선순위 사용
2. 애매하면 괄호() 사용

정리
* 연산자 우선순위는 상식선에서 생각, 애매하면 괄호 사용
* 복잡하면 명확하게 괄호 사용
* 개발에서 가장 중요한 것은 단순함과 명확함

**증감 연산자**
```java
package operator;

public class OperatorAdd1 {

    public static void main(String[] args) {
        int a = 0;

        a = a + 1;
        System.out.println("a = " + a); // 1

        a = a + 1;
        System.out.println("a = " + a); // 2

        // 증감 연산자
        ++a; // a = a + 1
        System.out.println("a = " + a); // 3

        ++a;
        System.out.println("a = " + a); // 4
    }
}
```

**전위, 후위 증감연산자**
```java
package operator;

public class OperatorAdd2 {
    public static void main(String[] args) {
        //전위 증감 연산자
        int a = 1;
        int b = 0;
        
        b = ++a; // a의 값을 먼저 증가시키고(전위), 그 결과를 b에 대입
        System.out.println("a = " + a + ", b = " + b);

        //후위 증감 연산자
        a = 1; // a 값 초기화
        b = 0; // b 값 초기화

        b = a++; // a의 현재 값을 b에 먼저 대입, 그 후 a 값을 증가(후위)
        System.out.println("a = " + a + ", b = " + b);
    }
}
```

**비교 연산자**
* `==`: 동등성
* `!=`: 불일치
* `>`: 크다
* `<`: 작다
* `>=`: 크거나 같다
* `<=`: 작거나 같다

```java
package operator;

public class Comp1 {
    public static void main(String[] args) {
        int a = 2;
        int b = 3;

        System.out.println(a == b);
        System.out.println(a != b);
        System.out.println(a > b);
        System.out.println(a < b);
        System.out.println(a >= b);
        System.out.println(a <= b);

        // 결과를 boolean 변수에 담을 수 있음
        boolean result = a == b;
        System.out.println(result);
    }
}
```

**문자열 비교**
```java
package operator;

public class Comp2 {
  public static void main(String[] args) {
    String str1 = "문자열1";
    String str2 = "문자열2"; //ctrl+d 현재 열 복붙 자동

    boolean result1 = "hello".equals("hello"); // 레터럴 비교
    boolean result2 = str1.equals("문자열1"); // 문자열 변수, 레터럴 비교
    boolean result3 = str1.equals(str2); // 문자열 변수 비교

    System.out.println(result1);
    System.out.println(result2);
    System.out.println(result3); //ctrl+shift+enter 문장 자동완성(; 만들어줌)
  }
}
```

**논리 연산자**
* `&&`(그리고): 모두 참이면 참, 하나라도 거짓이면 거짓
* `||`(또는): 하나라도 참이면 참, 둘다 거짓이면 거짓
* `!`(부정): 참이면 거짓을, 거짓이면 참
```java
package operator;

public class Logical1 {
  public static void main(String[] args) {
    System.out.println("&&: AND 연산");
    System.out.println(true && true);
    System.out.println(true && false);
    System.out.println(false && false);

    System.out.println("|| OR 연산");
    System.out.println(true && true);
    System.out.println(true && false);
    System.out.println(false && false);

    System.out.println("! 연산");
    System.out.println(!true);
    System.out.println(!false);

    System.out.println("변수 활용");
    boolean a = true;
    boolean b = false;
    System.out.println(a && b);
    System.out.println(a || b);
    System.out.println(!a);
    System.out.println(!b);
  }
}
```

**논리 연산자 활용**
```java
package operator;

public class Logical2 {

    public static void main(String[] args) {
        int a = 15;
        // a는 10보다 크고 20보다 작다
        boolean result = a > 10 && a < 20; //(a>10)&&(a<20)
        //boolean result = 10 < a && a < 20; //(a>10)&&(a<20)

        System.out.println("result = " + result);
    }
}
```

**대입 연산자**

축약(복합)대입 연산자
* `+=`, `-=`, `*=`, `/=`, `%=`
* `i = i + 3` > `i += 3`
* `i = i * 4` > `i *= 4`
```java
package operator;

public class Assign1 {

  public static void main(String[] args) {
    int a = 5;
    a += 3; // 8 ( 5 + 3): a = a + 3
    a -= 2; // 6 ( 8 - 2): a = a - 2
    a *= 4; // 25 ( 6 * 4 ): a = a * 4
    a /= 3; //8 ( 24 / 3): a = a / 3
    a %= 5; // 3 ( 8 % 5 ): a = a % 5
    System.out.println(a);
  }
} 
```

**정리**

자주 사용하는 연산자
* 산술 연산자: `+`, `-`, `*`, `/`, `%`
* 증감 연산자: `++`, `--`
* 비교 연산자: `==`, `!=`, `>`, `<`, `>=`, `<=`
* 논리 연산자: `&&`, `||`, `!`
* 대입 연산자: `=`, `+=`, `-=`, `*=`, `/=`, `%=`

다음 연산자들도 자주 사용, 뒷 부분에서 학습
* 삼항 연산자: `? :`
* instanceof 연산자: 객체 타입 확인
* etc: `new`, `[]`(배열 인덱스), `.`(객체 멤버 접근), `()`(메소드 호출)

비트 연산자는 실무에서 거의 사용 X

## 11월 3일
### if문1 - if, else
**조건문 시작** <br>
특정 조건에 따라 다른 코드를 실행하는 것을 조건문이라 함
조건문에는 if문, switch문이 있음. 둘다 특정 조건에 따라 다른 코드를 실행

**if문** <br>
조건이 참인지 확인하고, 그 조건이 참일 경우 특정 코드 블록을 실행

```java
package cond;

public class If1 {
    public static void main(String[] args) {
        int age = 20; // 사용자 나이

        if (age >= 18){
            System.out.println("성인입니다");
        }
        if (age < 18){
            System.out.println("미성년자입니다");
        }
    }
}
```

**else문** <br>
if문에서 만족하는 조건이 없을 때 실행하는 코드를 제공
```java
package cond;

public class If2 {
    public static void main(String[] args) {
        int age = 20;

        if(age >= 18){
            System.out.println("성인입니다");
        } else {
            System.out.println("미성년자입니다");
        }
    }
}
```

### if문2 - else if
```java
package cond;

public class If3 {
    public static void main(String[] args) {
        int age = 14;

        if(age <= 7){
            System.out.println("미취학");
        }
        if(age >= 8 && age <= 13){
            System.out.println("초등학생");
        }
        if(age >= 14 && age <= 16){
            System.out.println("중학생");
        }
        if(age >= 17 && age <= 19){
            System.out.println("고등학생");
        }
        if(age >= 20){
            System.out.println("성인");
        }
    }
}
```
위 코드는 불필요한 조건 검사를 진행하고있고, 코드 효율성이 매우 떨어진다. <br>
이러한 코드에 else if 문을 사용하여 효율적으로 코드 작성 가능

**else if** <br>
앞선 if문의 조건이 거짓일 때 다음 조건을 검사
```java
package cond;

public class If4 {
    public static void main(String[] args) {
        int age = 23;
        
        if(age <= 7){
            System.out.println("미취학");
        } else if (age <= 13) {
            System.out.println("초등학생");
        } else if (age <= 16) {
            System.out.println("중학생");
        } else if (age <= 19) {
            System.out.println("고등학생");
        } else {
            System.out.println("성인");
        }
    }
}
```

### if문3 - if문과 else if문
if문에 else-if를 함게 사용하는 것은 서로 연관된 조건일 때 사용 <br>
but 서로 관련없는 독립 조건이면 if문을 각각 따로 사용해야 함
```java
package cond;

public class If5 {
    public static void main(String[] args) {
        int price = 10000; // 아이템 가격
        int age = 10; //나이
        int discount = 0;

        if(price >= 10000){
            discount = discount + 1000;
            System.out.println("10000원 이상 구매, 1000원 할인");
        }
        if (age <= 10){
            discount = discount + 1000;
            System.out.println("어린이 1000원 할인");
        }
        System.out.println("총 할인 금액: " + discount + "원");
    }
}
```
만약 else if문을 사용하면, 선행되는 if문이 이미 조건이 만족하여 if문을 빠져나오게 됨

### switch문
```java
package cond;

public class Switch1 {
    public static void main(String[] args) {
        int grade = 2;

        int coupon;
        if (grade == 1){
            coupon = 1000;
        } else if (grade == 2) {
            coupon = 2000;
        } else if (grade == 3) {
            coupon = 3000;
        } else {
            coupon = 500;
        }

        System.out.println("발급받은 쿠폰은 " + coupon);
    }
}
```
위와 같은 코드를 switch문을 사용하여 더 편리하게 사용할 수 있음
참고로 if문은 비교 연산자를 사용할 수 있지만, switch문은 단순히 값이 같은지만 비교
* 조건식의 결과 값이 어떤 `case`의 값과 깅ㄹ치하면 해당 `case`의 코드를 실행
* `break`문은 현재 실행 중인 코드를 끝내고 `switch`문을 빠져나가게 하는 역할
* 만약 `break`문이 없으면, 일치하는 `case`이후의 모든 `case`코드들이 순서대로 실행
* `default`는 조건식의 결과값이 모든 `case`의 값과 일치하지 않을 때 실행. if문의 else와 같음
* if, else-if, else 구조와 같음
```java
package cond;

public class Switch2 {
    public static void main(String[] args) {
        int grade = 2;

        int coupon;
        switch (grade){
            case 1:
                coupon = 1000;
                break;
            case 2:
                coupon = 2000;
                break;
            case 3:
                coupon = 3000;
                break;
            default:
                coupon = 500;
        }
        System.out.println("발급받은 쿠폰 " + coupon);
    }
}
```

**break문이 없으면?**
```java
package cond;

public class Switch3 {
    public static void main(String[] args) {
        int grade = 2;

        int coupon;
        switch (grade){
            case 1:
                coupon = 1000;
                break;
            case 2:
            case 3:
                coupon = 3000;
                break;
            default:
                coupon = 500;
        }
        System.out.println("발급받은 쿠폰 " + coupon);
    }
}
```
* grade가 2등급 -> 먼저 case2 실행
* but case2 에는 `break`문이 없어, 중단하지 않고 바로 다음에 있는 case3의 코드 실행
* `"발급받은 쿠폰 3000"`이 출력

**if문 vs switch문** <br>
switch는 참 거짓의 결과나 나오는 조건이 아닌, 단순 값만 가능
switch문은 조건식이 특정 case와 같은지만 체크, 쉽게 말해 값이 같은지만 확인하는 연산만 가능(문자도 가능)
but if문은 참 거짓의 결과가 나오는 조건식을 자유롭게 적을 수 있음

**자바 14 새로운 switch문** <br>
잘 사용하진 않지만 자바14부터 새로운 switch 문이 정식 도입
```java
package cond;

public class Switch4 {
    public static void main(String[] args) {
        int grade = 2;

        int coupon = switch (grade){
            case 1 -> 1000;
            case 2 -> 2000;
            case 3 -> 3000;
            default -> 500;
        };
        System.out.println("발급받은 쿠폰" + coupon);
    }
}
```

### 삼항 연산자
```java
package cond;

public class CondOp1 {
    public static void main(String[] args) {
        int age = 18;
        String status;
        if(age >= 18){
            status = "성인";
        } else {
            status = "미성년자";
        }
        System.out.println("age = " + age + " status = " + status);
    }
}
```
위 코드는 참과 거짓에 따라 `status` 변수의 값이 달라짐
단순히 참과 거짓에 따라 특정 값을 구하는 경우 **삼항 연산자** 또는 **조건 연산자**라고 불리는 `?:`연산자 사용 가능

```java
package cond;

public class CondOp2 {
    public static void main(String[] args) {
        int age = 18;
        String status = (age >= 18) ? "성인" : "미성년자";

        System.out.println("age = " + age + " status = " + status);
    }
}
```
* `조건`,`참_표현식`, `거짓_표현식` 이렇게 항이 3개
* if문처럼 코드 블럭을 넣을 수 있는 것이 아니라 단순한 표현식만 넣을 수 있음

