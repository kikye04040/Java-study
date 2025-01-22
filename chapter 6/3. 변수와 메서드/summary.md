## 3-1 선언위치에 따른 변수의 종류

```
class Variavles {
	int iv; // 인스턴스 변수
	static int cv; // 클래스 변수 (static 변수, 공유 변수)
	
	void method() {
		int lv = 0; // 지역변수
	}
}
```
선언 위치에 따라 변수의 종류가 달라짐

------

1. **인스턴스 변수** : 인스턴스마다 고유한 상태를 유지해야 하는 속성의 경우 사용
```
public class Person {
    // 인스턴스 변수
    String name;

    public Person(String name) {
        this.name = name;  // 객체마다 name 값이 다를 수 있음
    }
}

public class Main {
    public static void main(String[] args) {
        Person person1 = new Person("Alice");
        Person person2 = new Person("Bob");

        System.out.println(person1.name);  // Alice
        System.out.println(person2.name);  // Bob
    }
}
```
예시처럼 클래스로 생성된 객체마다 서로 다른 고유한 name이라는 속성을 가져야 하기 때문에 인스턴스 변수로 저장

2. **클래스 변수** : 클래스 자체에 속하는 변수로, 모든 객체가 공유하는 변수
```
public class Counter {
    // 클래스 변수 (static)
    static int count = 0;

    public Counter() {
        count++;  // 모든 객체가 count를 공유
    }
}

public class Main {
    public static void main(String[] args) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();

        System.out.println(Counter.count);  // 2
    }
}
```
예시처럼 클래스로 생성된 객체들 사이에 공통된 데이터를 저장하거나 상태를 공유할 때 사용

3. **지역변수** : 메서드, 생성자 또는 내부 블록에서 선언된 변수로, 해당 스코프 내에서만 사용 가능하며 호출이 끝나면 소멸

------

## 3-3 메서드

**메서드**란?
- 특정 작업을 수행하는 일련의 문장들

메서드를 사용하는 이유
- 높은 재사용성
- 중복된 코드의 제거
- 프로그램의 구조화

------

## 3-4 메서드의 선언과 구현

메서드는 **선언부**와 **구현부**로 나뉘고,
```
int add(int x, int y) {
	int result = x + y;
	return result;
}
```
예시처럼
1. 반환타입
2. 함수병 (자바에서는 주로 camel case로 표현)
3. 매개변수 선언
으로 구분할 수 있음

이때 **반환값의 타입**(result의 자료형인 int)이 **선언부의 반환타입**(int)과 일치해야 함

------

## 3-5 메서드의 호출

메서드를 실행할 때에는
```
int result = add(3, 5);
```
예시처럼 사용해주면 되고, add 뒤의 값을 3, 5처럼 **반환타입이 같거나, 자동 형변환이 가능한 값을 입력**해야함

------

## 3-6 return문

반환자료형이 void인 경우는 return문을 굳이 쓰지 않아도 자동으로 포함되지만

그 외의 자료형일 경우에는 무조건 return문과 반환값을 작성해야 함

매개변수의 유효성 검사도 항상 점검해야 할 사항

------

## 3-7 JVM의 메모리 구조

ㅊ
