> 2023-05-03
> Chapter 8
>> Chapter 8-1 변수의 정의
<pre><code>
public class Variable {
    public static void main(Static[] args) {
        int a = 1; // a는 정수 1이다.
        System.out.println(a);
        
        int b = 1.1; // 1.1은 정수(x) ERROR.
        double c = 1.1; // 1.1은 실수(o) -> c는 실수 1.1이다.
        System.out.println(c);
        String d = "Hello World"; 
        // "Hello World"는 문자열 d에 저장됨.
        System.out.println(d);
    }
}
</code></pre>
# 결과 : 1, 1.1, Hello World
>> Chapter 8-2 변수의 효용
<pre><code>
public class Letter {
    public static void main(String[] args) {
        String name = "leezche"; 
        // "leezche"는 문자열 name에 저장됨
        System.out.println("Hello, "+name+" ... "+name+" ... egoing ... bye");
        double VAT = 10.0;
        System.out.println(VAT);
    }
}
</code></pre>
# 결과 : Hello, leezche ... leezche ... egoing ... bye
>> Chapter 8-3 데이터 타입의 변환 - casting
<pre><code>
public class Casting {
    public static void main(String[] args) {
        double a = 1.1;
        double b = 1; 
        // 정수 1을 실수 1로 바꾸고 b에 담아서 출력 시 1.0이 나옴, 손실이 일어나지 않음
        double b2 = (double) 1; 
        // 강제로 1을 실수로 변환하여 1.0 출력.
        System.out.println(b);
        int c = 1.1; 
        // ERROR. 
        double d = 1.1;
        int e = (int)1.1; 
        // 강제로 1.1을 정수로 변환하여 1 출력, 손실이 일어남
        
        System.out.println(e);
        String f = Integer.toString(1); 
        // 1이 출력 되지만 실제로 1은 문자열이다.
        System.out.println(f.getClass()); 
        // .getClass()를 이용하여 출력 시 값의 데이터타입을 함께 출력.
    }
}
</code></pre>
# 결과 : 1.0, 1, 1, class java.lang.String
> Chapter 9
>> Chapter 9-1 프로그래밍이란 무엇인가
<pre><code>
public class Program {
    public static void main(String[] args) {
         
        System.out.println(1); // 1 출력
        System.out.println(2); // 2 출력
        System.out.println(3); // 3 출력
    }
}
</code></pre>
# 결과 : 1, 2, 3
> 프로그래밍을 하는 이유는 자동화 하기 위함.
> 컴퓨터 프로그래밍을 이용하여 사람이 잘 못하는 일을 기계에게 위임하여 자동화할 수 있음. (이런 작업을 하는 언어중 가장 유명한 언어가 JAVA.)
>> Chapter 9-2 프로그램 만들기 - IoT 라이브러리 설치하기
<pre><code>
public class programming {   
}
</code></pre>
> 방법 : iot 사물을 제어할 수 있는 프로그램을 작성하기 위해서 외부 패키지를 다운받아 org 폴더를 programming 프로젝트에 드래그 앤 드랍 시킨다.
>> Chapter 9-3 IoT 프로그램 만들기
<pre><code>
import org.opentutorials.iot.Elevator; 
// org폴더 > opentutorials > iot > Elevator를 import 함. 
import org.opentutorials.iot.Lighting;
// org폴더 > opentutorials > iot > Lighting를 import 함.
import org.opentutorials.iot.Security;
// org폴더 > opentutorials > iot > Security를 import 함.
public class programming {
    public static void main(String[] args) {
        String id = "JAVA APT 507"; 
        // 동작은 같지만 중복이 제거됨.
         
        // Elevator call 
        Elevator myElevator = new Elevator(id);
        // Elevator는 데이터 타입, myElevator는 변수
        myElevator.callForUp(1); 
        // 1층으로 엘레베이터를 보내라는 명령문
         
        // Security off 
        Security mySecurity = new Security(id);
        mySecurity.off();
         
        // Light on
        Lighting hallLamp = new Lighting(id+" / Hall Lamp");
        hallLamp.on();
        //hallLamp 의 불을 킨다.
         
        Lighting floorLamp = new Lighting(id+" / floor Lamp");
        floorLamp.on();
        //floorLamp 의 불을 킨다.
    }
}
</code></pre>
# 결과 : JAVA APT 507 -> Elevator callForUp stopFloor : 1
# JAVA APT 507 -> Security off
# JAVA APT 507 / Hall Lamp -> Lighting on
# JAVA APT 507 / floorLamp -> Lighting on
> Chapter 10 - 디버거
>> 이클립스에서 디버그 하는 방법은 우측상단 Run java 버튼 옆 아래 화살표를 눌러 Debug java를 클릭하면 된다.
>> 이클립스에서 브레이크 포인트를 지정하는 방법은 코드 편집창에서 줄 번호 왼편을 더블클릭하여 브레이크 포인트를 지정할 수 있다.
>> 브레이크 포인트를 지정하고 디버거를 실행하면 브레이크 포인트까지 코드가 실행되며 그 이후로 실행이 정지된다.
>> 브레이크 포인트를 해제 하는 방법은 지정했던 브레이크 포인트를 다시 클릭하면 해제할 수 있다.
>> 이클립스에서 우측의 Variable 탭에서 변수들을 확인할 수 있다.
>> Step Into 버튼을 클릭하면 코드의 자세한 실행과정(메소드)를 볼 수 있다.
>> 다시 원래의 코드로 돌아가고자 할 경우에는 Step Return 버튼을 클릭하여 돌아갈 수 있다.

>> (0503) 8, 9, 10 ENDS