"데이터 타입"
// 주로 쓰이는 데이터 타입은 Number와 String이 있다. //
public class Datatype{
    public static void main(String[] args) {
        System.out.println(6); // Number
        System.out.println("six"); // String
         
        System.out.println("6"); // String 6
         
        System.out.println(6+6); // 12
        System.out.println("6"+"6"); // 66
         
        System.out.println(6*6); // 36
//      System.out.println("6"*"6");
         
        System.out.println("1111".length()); // 4
//      System.out.println(1111.length());
    }
}
"숫자와 연산"
//숫자 연산 +, -, *,/를 이용하여 식을 만들어 계산할수 있다. 
public class Number {
 
    public static void main(String[] args) {
        // Operator
        System.out.println(6 + 2); // 8
        System.out.println(6 - 2); // 4
        System.out.println(6 * 2); // 12
        System.out.println(6 / 2); // 3
 
        System.out.println(Math.PI); // 3.141592653589793
        System.out.println(Math.floor(Math.PI)); // floor는 소수점을 없앤다는 뜻
        System.out.println(Math.ceil(Math.PI)); // ceil은 소수점 첫째자리수를 올림한다는 의미
         
         
    }
 
}
"문자열의 표현"
//문자열(string), 문자(character)
//문자열: 문자의 나열 , 문자는 따옴표("") 안에 입력하여 표현, 한 개의 문자만 포함가능!
//이스케이프 기호는 \ 사용, 특정문자와 결합하여 제어문자로 가능, 쌍따옴표와 같은 특수한 문자와 결합하여 특수한 문자가 일반 문자라고 나타내주는 역할이다.
//줄바꿈 = \n
public class StringApp {
 
    public static void main(String[] args) {
         
        // Character VS String 
        System.out.println("Hello World"); // String
        System.out.println('H'); // Character
        System.out.println("H"); 
     
        System.out.println("Hello "
                + "World");
         
        // new line /n의 n을 뜻함
        System.out.println("Hello \nWorld");
         
        // escape
        System.out.println("Hello \"World\"");// Hello "World"
    }
 
}
"문자열 다루기"
//replace를 이용해서 name ㅡ> duru로 바꾸는 것
public class StringOperation {
 
    public static void main(String[] args) {
         
        System.out.println("Hello World".length()); // 11
        System.out.println("Hello, [[[name]]] ... bye. ".replace("[[[name]]]", "duru"));
 
    }
 
}
 