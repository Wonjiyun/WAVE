> 0502
>> Chapter 6

>>> 6-2 . 
>>> 데이터 타입
<pre><code>
public class Datatype{
    public static void main(Stringp[] args) {
        System.out.println(6); // 숫자
        System.out.println("six"); // 문자
        System.out.println("6"); 
        // 사람이 보기엔 숫자 이지만 문자처리.

        System.out.println(6+6); // 12 출력
        System.out.println("6"+"6"); 
        // 문자처리로 66출력 (결합연산자)

        System.out.println(6*6); // 36 출력
        System.out.println("6"*"6"); 
        // 오류가 뜸. 문자열은 곱해지지 않는다.

        System.out.println("1111".length()); 
        // 문자열의 길이를 알려준다. 따라서 출력값은 4가 나옴.

        System.out.println(1111.length()); 
        // 오류가 뜸. 숫자에 대한 길이를 알려주는 구문은 없음.
    }
}
</code></pre>

# 결과 : 6 six 6 12 66 36 4
>>> 6-3 . 
>>> 숫자와 연산
<pre><code>
public class Number {
 
    public static void main(String[] args) {
        //연산자 = Operator
        System.out.println(6 + 2); // 8 더하기
        System.out.println(6 - 2); // 4 뺴기
        System.out.println(6 * 2); // 12 곱하기
        System.out.println(6 / 2); // 3 나누기
 
        System.out.println(Math.PI); // 3.141592653589793
        System.out.println(Math.floor(Math.PI)); 
        // 소수점을 없앤다
        System.out.println(Math.ceil(Math.PI)); 
        // 3.14에 1이 있으면 그 앞에 값을 올려버린다.
    }
}
</code></pre>

# 결과 : 8, 4, 12, 3, 3.141592653589793, 3, 4
>>> 6-4 . 
>>> 문자열의 표현
<pre><code>
public class StringApp {
 
    public static void main(String[] args) {
         
        // Character VS String 
        System.out.println("Hello World"); // 문자열 표현 ("")
        System.out.println('H'); 
        // 문자 표현 ('') *작은 따옴표는 사용할 필요가 없음.
        System.out.println("H"); 
     
        System.out.println("Hello " 
                + "World"); // Hello와 World를 더해주는 구문임.
         
        // new line 약자 = \n
        System.out.println("Hello \nWorld");
        // 줄바꿈을 할때는 \n을 사용해야 함.
         
        // escape
        System.out.println("Hello \"World\"");// Hello "World"
        // 이스케이프 기호는 줄바꿈 기호나 쌍따옴표와 같은 특수한 기호를 문자열에 넣기 위해 사용함.
    }
}
</code></pre>

# 결과 : Hello World, H, Hello World, Hello, World, Hello "World"
>>> 6-5 . 
>>> 문자열 다루기
<pre><code>
public class StringOperation {
 
    public static void main(String[] args) {
         
        System.out.println("Hello World".length()); 
        // 11, 문자열의 길이 출력 (.length())

        System.out.println("Hello, [[[name]]] ... bye. ".replace("[[[name]]]", "duru"));
        //문자열의 특정 문자열을 다른 문자열로 교체 (.replace())
        //위 구문에선 [[[name]]] 을 duru 라는 이름으로 교체함.
    }
}
</code></pre>

# 결과 : 11, Hello, duru ... bye.
>> Chapter 7

>>> 7 . 
>>> 작심삼일공학

>>>> ①작심삼일이 되면 잠시 공부를 중단해라.

>>>> ②배운 것들을 곰곰히 되새겨 보면서 내 삶의 문제들과 연관지어 보고 실제로 한번 해결하기 위해 노력해보아라.

>> Chapter 6 println 응용
<pre><code>
public class FirstClass {
    public static void main(String[] args) {
        System.out.println("[내 정보]\n");
        System.out.println("이름 : 정인호\n");
        System.out.println("나이 : 23\n");
        System.out.println("학교 : 동의대학교\n");
        System.out.println("학과 : 산업융합시스템공학부\n");
        System.out.println("학번 : 20202395\n");
    }
}
</code></pre> 