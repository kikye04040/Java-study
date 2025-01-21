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
        System.out.println(person2.name);  조
