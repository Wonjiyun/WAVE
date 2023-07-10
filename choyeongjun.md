0501
4-1**HelloWorld**
public class HelloWorldApp {
	public static void main(String[] args) {
		System.out.println("Hello Word!!");
	}
}

4-3**Java 동작원리**
Java Source code.java

        |(compile)

Java Application.class

        |(Run)

Java Virtual Machine

        |(Run)

      computer          

5-1**Hello Java World**
import javax.swing.*;   
import java.awt.Dimension;
import java.awt.Toolkit;
public class HelloWorldGUIApp{
    public static void main(String[] args){
        javax.swing.SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                JFrame frame = new JFrame("HelloWorld GUI");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setPreferredSize(new Dimension(800, 300)); //800의 수치를 400으로 변경하면 결과 창의 가로길이가 줄어듬
                JLabel label = new JLabel("Hello World!!", SwingConstants.RIGHT); /* RIGHT를 CENTER로 변경하면 결과 창에 나타나는 HelloWorld!! 단어가 가운데에 오는 것을 볼 수 있음*/
                frame.getContentPane().add(label);
                Dimension dim = Toolkit.getDefaultToolkit().getScreenSize();
                frame.setLocation(dim.width/2-400/2, dim.height/2-300/2);

                frame.pack();
                frame.setVisible(true);
            }
        });
    }
}

5-2**사물을 자바로 제어하기**
import com.pi4j.io.gpio.GpioController;
import com.pi4j.io.gpio.GpioFactory;
import com.pi4j.io.gpio.GpioPinDigitalOutput;
import com.pi4j.io.gpio.PinState;
import com.pi4j.io.gpio.RaspiPin;

public class HelloWorldRaspberryPi {

	public static void main(String[] args) throws InterruptedException {

		final GpioController gpio = GpioFactory.getInstance();
		final GpioPinDigitalOutput pin = gpio.provisionDigitalOutputPin(RaspiPin.GPIO_01, "PinLED", PinState.LOW);
		final int SHORT_INTERVAL = 200; //0.2초를 의미함
		final int LONG_INTERVAL = SHORT_INTERVAL * 3;
		final int LETTER_INTERVAL = SHORT_INTERVAL * 7;

		while (true) {
			// H
			pin.high();//high는 불이 켜지는 동작
			Thread.sleep(SHORT_INTERVAL);
			pin.low();//low는 불이 꺼지는 동작
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(LETTER_INTERVAL);

			// e
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(LETTER_INTERVAL);

			// l
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);

			pin.high();
			Thread.sleep(LONG_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);

			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(LONG_INTERVAL);

			// l
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);

			pin.high();
			Thread.sleep(LONG_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);

			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(SHORT_INTERVAL);
			pin.high();
			Thread.sleep(SHORT_INTERVAL);
			pin.low();
			Thread.sleep(LONG_INTERVAL);
		}
	}
}

===============================================

0502
6-1
데이터의 여러가지 종류가 있고 그 종류에 따라 수행할 수 있는 연산이 달라진다.

6-2**데이터타입**
public class Datatype{
    public static void main(String[] args) {
        System.out.println(6); // Number
        System.out.println("six"); // String
         
        System.out.println("6"); // String 6
         
        System.out.println(6+6); // 12  단순 더하기 연산처리
        System.out.println("6"+"6"); // 66  각각 문자열로 묶여있으면 결합연산자로 사용됨
         
        System.out.println(6*6); // 36
//      System.out.println("6"*"6"); //문자열은 곱하기 연산을 할 수가 없다
         
        System.out.println("1111".length()); // 4
//      System.out.println(1111.length()); // error
    }
}

6-3**데이터연산**
public class Number {
 
    public static void main(String[] args) {
        // Operator
        System.out.println(6 + 2); // 8
        System.out.println(6 - 2); // 4
        System.out.println(6 * 2); // 12
        System.out.println(6 / 2); // 3
 
        System.out.println(Math.PI); // 3.141592653589793
        System.out.println(Math.floor(Math.PI)); // 3.0  floor은 내림표현으로 소수점을 잘라버림
        System.out.println(Math.ceil(Math.PI)); // 4.0  ceil은 올림표현으로 실수 +1을 하면 됨  ex) Math.ceil(5.1);
                                                                                                // 6
         
    }
 
}

6-4**문자열의 표현**
public class StringApp {
 
    public static void main(String[] args) {
         
        // Character VS String 
        System.out.println("Hello World"); // String 문자열(Character들의 집합체)
        System.out.println('H'); // Character 한 글자를 표현하는 데이터 타입
        System.out.println("H"); // String
     
        System.out.println("Hello "
                + "World"); // 문자열과 문자열이 더해진 것(줄바꿈 안됨)
         
        // new line
        System.out.println("Hello \nWorld"); // 줄바꿈
         
        // escape
        System.out.println("Hello \"World\"");// Hello "World"      " 앞에 \를 넣어 줌으로써 "World"를 표현할 수 있게 됨
    }
 
}

6-5**문자열 다루기**
public class StringOperation {
 
    public static void main(String[] args) {
         
        System.out.println("Hello World".length()); // 11   length를 사용하면 문자열 내부의 글자 수를 파악할 수 있음
        System.out.println("Hello, [[[name]]] ... bye. ".replace("[[[name]]]", "duru")); /* replace - 특정 문자열을 다른 문자열로 교체하는 명령 내릴 수 있음*/
 
    }
 
}

===============================================

0503
8-1**변수의 정의(Variable)**
public class Variable {
 
    public static void main(String[] args) {
         
        int a = 1; // Number -> integer(정수) 
        System.out.println(a);
         
        double b = 1.1; // real number(실수) -> double 
        System.out.println(b);
         
        String c = "Hello World"; // 문자열
        System.out.println(c);
    }
 
}

8-2**변수의 효용**
public class Letter {
 
    public static void main(String[] args) {
        String name = "leezche";
        System.out.println("Hello, "+name+" ... "+name+" ... egoing ... bye");  // 개인적으로 C언어에서 scanf와 비슷한 원리라 생각함
         
        double VAT = 10.0;
        System.out.println(VAT); 

        //남들이봐도 쉽게 알아볼 수 있게 코딩을 이쁘게 해야함

    }
 
}

8-3**Casting**
public class Casting {
 
    public static void main(String[] args) {
         
        double a = 1.1;
        double b = 1;  // double을 사용했기 때문에 1.0 으로 출력            자동화
        double b2 = (double) 1; //                                        수동화 
         
        System.out.println(b);
         
        // int c = 1.1; 
        double d = 1.1; 
        int e = (int) 1.1; // (int)를 사용해 줌으로써 1.1 -> 1로 변경한 후 int e 에 적용. 즉, int e = 1; 과 동일한 의미
        System.out.println(e);
         
        // 1 to String 
        String f = Integer.toString(1);
        System.out.println(f.getClass());
 
 
    }
 
}

9-3**IoT 프로그램 만들기**
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHome {
 
    public static void main(String[] args) {
         
        String id = "JAVA APT 507";
         
        // Elevator call 
        Elevator myElevator = new Elevator(id);
        myElevator.callForUp(1);
         
        // Security off 
        Security mySecurity = new Security(id);
        mySecurity.off();
         
        // Light on
        Lighting hallLamp = new Lighting(id+" / Hall Lamp");
        hallLamp.on();
         
        Lighting floorLamp = new Lighting(id+" / floorLamp");
        floorLamp.on();
 
    }
 
}

===============================================

0504
11-1**입력과 출력**
import javax.swing.JOptionPane;
 
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
 
    public static void main(String[] args) {
         
        String id = JOptionPane.showInputDialog("Enter a ID"); // JOptionPane의 showInputDialog를 이용하여 정보를 String 데이터로 받음
        String bright = JOptionPane.showInputDialog("Enter a Bright level"); // 밝기또한 마찬가지
         
        // Elevator call 
        Elevator myElevator = new Elevator(id);
        myElevator.callForUp(1);
         
        // Security off 
        Security mySecurity = new Security(id);
        mySecurity.off();
         
        // Light on
        Lighting hallLamp = new Lighting(id+" / Hall Lamp");
        hallLamp.on();
         
        Lighting floorLamp = new Lighting(id+" / floorLamp");
        floorLamp.on();
         
        DimmingLights moodLamp = new DimmingLights(id+" moodLamp");
        moodLamp.setBright(Double.parseDouble(bright));
        moodLamp.on();
 
    }
 
}

11-2**arguments&parameter**
main 메소드의 args 파라미터를 이용하여 코드내의 값을 편하게 설정할 수 있음
public static void main(String[] args){
        String id = args[0];
        String bright = args[1];
}
argument 값을 다양하게 사용하여 결과값을 알아볼 수 있음
args는 문자열 배열로 여러개의 String 데이터가 들어있을 수 있음
인덱스는 0부터 시작함

===============================================

2023-05-08
-------------

* API(Application Programming Interface)

  자바 프로그램을 만들고 사용할 때의 단계 -> Computer - OS - Java - (API)Java Program...

  Application - 도구(System, Date, Math..)의 응용에 주목

  Program - 작업들의 시간적 순서에 주목

  자바 프로그램은 또 다른 자바 프로그램에서 사용될 수도 있고, 다른 프로그램에서 사용할 수 있도록 만들어둔 장치 역시 API이다.

* UI(User Interface)
  사용자가 우리가 만든 프로그램을 사용할 수 있도록 만들어둔 장치

* 자바 - 문서
  메소드(Method), 변수(Variable) < 클래스(Class) < 패키지(Package)
  메소드(Method) : floor, ceil...

* 인스턴스(Instance)

<pre><code>
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.PrintWriter; // 이게 없으면 작동x
public class InstanceApp {
 
    public static void main(String[] args) throws IOException{
         
        PrintWriter p1 = new PrintWriter("result1.txt");
        // PrintWriter 클래스의 이름을 p1으로 설정함.
        // new 키워드를 통한 인스턴스를 생성
        p1.write("Hello 1");
        p1.close();
         
        PrintWriter p2 = new PrintWriter("result2.txt");
        p2.write("Hello 2");
        p2.close();

    }
        // 생성자(Constructors)가 없으면 1회용 이다. (math)
		// 생성자가 있으면 생성자를 이용해 인스턴스를 만드는 것이 허용 되어있다.
}
</code></pre>

* 상속(Inheritance)

<pre><code>
java.lang.Object			 // 전체
	java.io.Writer  		 // Object 에게 상속받음
		jave.io.PrintWriter  // Writer 에게 상속받음
</code></pre>

* AccountingApp

<pre><code>
public class AccountingApp {

	public static void main(String[] args) {
		
		System.out.println("Value of supply : " +10000.0);
        System.out.println("VAT : " +(10000.0*0.1));
        System.out.println("Total : " +(10000.0+(10000.0*0.1)));
        System.out.println("Expense : " +(10000.0*0.3));
        System.out.println("Income : " +(10000.0-(10000.0*0.3)));
        System.out.println("Dividend 1 : " +(10000.0-(10000.0*0.3))*0.5);
        System.out.println("Dividend 2 : " +(10000.0-(10000.0*0.3))*0.3);
        System.out.println("Dividend 3 : " +(10000.0-(10000.0*0.3))*0.2);

        // Edit -> Find/Replace -> 숫자 10000.0을 12345.0으로 바꿀 수 있다
	}

}
</code></pre>

* 이전 프로그램에 변수 도입

<pre><code>
public class AccountingApp {
 
    public static void main(String[] args) {
 
        double valueOfSupply = 10000.0;
        double vatRate = 0.1;
        double expenseRate = 0.3;
        double vat = valueOfSupply * vatRate;
        double total = valueOfSupply + vat;
        double expense = valueOfSupply * expenseRate;
        double income = valueOfSupply - expense;
        double dividend1 = income * 0.5;
        double dividend2 = income * 0.3;
        double dividend3 = income * 0.2;
 
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + vat);
        System.out.println("Total : " + total);
        System.out.println("Expense : " + expense);
        System.out.println("Income : " + income);
        System.out.println("Dividend 1 : " + dividend1);
        System.out.println("Dividend 2 : " + dividend2);
        System.out.println("Dividend 3 : " + dividend3);
 
    }
 
}
</code></pre>

***

2023-05-09
-------------

* 조건문

<pre><code>
if(income > 10000.0) {
    dividend1 = income * 0.5;
    dividend2 = income * 0.3;
    dividend3 = income * 0.2;
} else {
    dividend1 = income * 0.4;
    dividend2 = income * 0.2;
    dividend3 = income * 0.1;
}
</code></pre>

* 배열

<pre><code>
double rate1 = 0.5;
double rate2 = 0.3;
double rate3 = 0.2;
        
double dividend1 = income * rate1;
double dividend2 = income * rate2;
double dividend3 = income * rate3;
//변수가 많으면 변수가 더럽혀질 가능성이 커진다는 문제점이 있다. 세 개의 변수가 서로 같은 성격의 데이터라는 것이 분명하지 않다.

double[] dividendRates = new double[3];
// double형 데이터로 이루어진 배열이다.
// double형의 데이터를 3개를 담을 수 있는 수납상자
dividendRates[0] = 0.5;
dividendRates[1] = 0.3;
dividendRates[2] = 0.2;
        
double dividend1 = income * dividendRates[0];
double dividend2 = income * dividendRates[1];
double dividend3 = income * dividendRates[2];
</code></pre>

* 반복문

<pre><code>
int i = 0;
while(i < dividendRates.length) {
    System.out.println("Dividend : " + (income*dividendRates[i]) );
    i = i + 1;
}
</code></pre>

* 메소드
  
  메소드는 서로 연관된 코드를 그룹핑 해서 이름을 붙인 정리정돈의 상자이다.

<pre><code>
  public class AccountingMethodApp {
    public static double valueOfSupply;
    public static double vatRate;
    public static double expenseRate;
    public static void main(String[] args) { 
    // void main 밖으로 꺼내 전역변수로 설정한다.
        valueOfSupply = 10000.0;
        vatRate = 0.1;
        expenseRate = 0.3;
        print();
    }
 
    public static void print() {
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + getVAT());
        System.out.println("Total : " + getTotal());
        System.out.println("Expense : " + getExpense());
        System.out.println("Income : " + getIncome());
        System.out.println("Dividend 1 : " + getDiviend1());
        System.out.println("Dividend 2 : " + getDiviend2());
        System.out.println("Dividend 3 : " + getDiviend3());
    }
 
    public static double getDiviend1() {
        return getIncome() * 0.5;
    }
    public static double getDiviend2() {
        return getIncome() * 0.3;
    }
    public static double getDiviend3() {
        return getIncome() * 0.2;
    }
 
    public static double getIncome() {
        return valueOfSupply - getExpense();
    }
 
    public static double getExpense() {
        return valueOfSupply * expenseRate;
    }
 
    public static double getTotal() {
        return valueOfSupply + getVAT();
    } 
 
    public static double getVAT() {
        return valueOfSupply * vatRate;
    }
 
}
</code></pre>

* 클래스

<pre><code>
class Accounting{
    public static double valueOfSupply;
    public static double vatRate;
    public static double expenseRate;
    public static void print() {
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + getVAT());
        System.out.println("Total : " + getTotal());
        System.out.println("Expense : " + getExpense());
        System.out.println("Income : " + getIncome());
        System.out.println("Dividend 1 : " + getDiviend1());
        System.out.println("Dividend 2 : " + getDiviend2());
        System.out.println("Dividend 3 : " + getDiviend3());
    }
 
    public static double getDiviend1() {
        return getIncome() * 0.5;
    }
    public static double getDiviend2() {
        return getIncome() * 0.3;
    }
    public static double getDiviend3() {
        return getIncome() * 0.2;
    }
 
    public static double getIncome() {
        return valueOfSupply - getExpense();
    }
 
    public static double getExpense() {
        return valueOfSupply * expenseRate;
    }
 
    public static double getTotal() {
        return valueOfSupply + getVAT();
    } 
 
    public static double getVAT() {
        return valueOfSupply * vatRate;
    }
}
public class AccountingClassApp {
     
    public static void main(String[] args) {
        Accounting.valueOfSupply = 10000.0;
        Accounting.vatRate = 0.1;
        Accounting.expenseRate = 0.3;
        Accounting.print();
        // anotherVariable = ...;
        // anotherMethod = ...;
    }
}
</code></pre>

* 인스턴스

  하나의 클래스를 복제해서 서로 다른 데이터의 값과 서로 같은 메소드를 가진 복제본을 만드는 것이다.

<pre><code>
public class AccountingClassApp {
	
	public static void main(String[] args) {
		Accounting.valueOfSupply = 10000.0;
		Accounting.vatRate = 0.1;
		Accounting.expenseRate = 0.3;	
		Accounting.print();
		//...
		Accounting.valueOfSupply = 20000.0;
		Accounting.vatRate = 0.05;
		Accounting.expenseRate = 0.2;	
		Accounting.print();
		//...
		
		Accounting.valueOfSupply = 20000.0;
		Accounting.vatRate = 0.05;
		Accounting.expenseRate = 0.2;	
		Accounting.print();
		
	}
}
// 이 과정이 빈번하게 발샐한다고 한다면 이렇게 클래스의 내부적인 상태를 바꾸는 행위가 버그를 우발할 가능성이 매우 높다. 
</code></pre>

***

2023-05-10
-------------

* Boolean Datatype

<pre><code>
public class BooleanApp{
 
    public static void main(String[] args) {
         
        System.out.println("One");
        System.out.println(1);
         
        System.out.println(true); // 첫번째 데이터 타입
        System.out.println(false); // 두번째 데이터 타입
         
        String foo = "Hello world";
        // String true = "Hello world"; reserved word

        // '.contains' 메소드를 사용하면 return 값으로 그 문자열의 입력값으로 전달할 어떤 값이 들어있다면 True를, 없다면 False를 리턴한다.  
        System.out.println(foo.contains("world")); // foo 안에 값이 있으므로 return : true
        System.out.println(foo.contains("egoing")); // foo 안에 값이 없으므로 return : false
 
    }
}
</code></pre>

* 비교연산자

<pre><code>
public class ComparisonOperatorApp {
 
    public static void main(String[] args) {
         
        System.out.println(1 > 1);  // false
        System.out.println(1 == 1); // true
        System.out.println(1 < 1);  // false
        System.out.println(1 >= 1); // true
         
    }
 
}
</code></pre>

* 조건문 형식

  (조건식)에는 'Boolean'타입만 들어갈 수 있다. 

  조건문은 중첩할 수 있고, if와 else는 하나의 조건문에 한 번만 들어갈 수 있지만, else if는 여러 개가 들어갈 수 있다.

<pre><code>
public class IfApp {
 
    public static void main(String[] args) {
 
        System.out.println("a");
        if(false) {
            System.out.println(1);
        } else if(true) {
            System.out.println(2);
        } else {
            System.out.println(3);
        } // 위 조건문의 출력값은 2가 된다.
        System.out.println("b");
 
    }
 
}
</code></pre>

* 조건문 응용 1

<pre><code>
public class AuthApp {
 
    public static void main(String[] args) {
         
        String id = "egoing";
        String inputId = args[0];
         
        System.out.println("Hi."); // Hi. 출력
         
        //if(inputId == id) 와 같이 사용한다면 의도치 않은 결과를 가져올 수 있다. 

        if(inputId.equals(id)) {                     // String 객체에서는 equals 메소드를 제공하고 있다. 
            System.out.println("Master!");           // 같다면 Master! 출력
        } else {
            System.out.println("Who are you?");      // 아니라면 Who are you? 출력
        }
    }

}
</code></pre>

* 조건문 응용 2

<pre><code>
public class AuthApp {
 
    public static void main(String[] args) {
         
        String id = "egoing";
        String inputId = args[0];
         
        String pass = "1111";  // 비밀번호 1111
        String inputPass = args[1];
         
        System.out.println("Hi.");
         
        if(inputId.equals(id) && inputPass.equals(pass)) {   // 논리연산자 &&를 통해서 아이디와 패스워드 둘 다 맞아야 Master! 출력하게 함.
            System.out.println("Master!");
        } else {
            System.out.println("Who are you?");              // 아이디와 패스워드 둘 중 하나라도 틀렸다면 Who are you? 출력
        }       
 
    }
 
}
</code></pre>

* == vs equals

  원시(더이상 쪼갤수 없는.. primitive) 데이터 타입 : boolean, byte, char, short, int, long, float, double
  원시 데이터 타입의 변수는 선언되면 메모리(Stack)에 공간이 할당되며, 그 메모리 공간 안에 실제 값이 들어가게 된다. 
  그래서 원시 데이터의 경우 == 연산자는 변수가 가리키는 값을 토대로 비교하게 된다.

  클래스(non primitive..)는 new 키워드를 통한 인스턴스가 만들어지는 시점에
  또다른 메모리 구역(Heap)에서 새로운 공간을 할당하여 값을 저장하고, 변수는 그 값이 저장된 메모리의 주소를 가리키게 된다.

  결론 : primitive 데이터 타입 -> == 연산자 사용 
        non primitive 데이터 타입 -> equals 사용

* 논리연산자
  
  && : AND 둘 중 하나라도 false면 false
  || : OR 둘 중 하나라도 true면 true
  !  : NOT ex)  System.out.println(!true); // false 
<pre><code>
public class AuthApp2 {
 
    public static void main(String[] args) {
         
        String id = "egoing";
        String inputId = args[0];
         
        String pass = "1111";
        String pass2 = "2222";
        String inputPass = args[1];
         
        System.out.println("Hi.");
        boolean isRightPass = (inputPass.equals(pass) || inputPass.equals(pass2));  // 둘중 하나라도 true면 true 반환
        if(inputId.equals(id) && isRightPass ) {
            System.out.println("Master!");
        } else {
            System.out.println("Who are you?");
        }       
 
    }
 
}
</code></pre>

* 반복문
  'while'문에는 'if'문처럼 'boolean' 타입의 조건식을 기입해야한다.
  'for'문은 사용자가 직접 반복횟수를 지정시킬 때 용이하다.
  i++ 는 i = i + 1과 같다.
  'while'문은 자유도가 높고 'for'문은 사용자가 반복횟수를 지정할 수 있기에 자유도가 낮다.

<pre><code>
public class LoopApp {
 
    public static void main(String[] args) {
         
        System.out.println(1);
        System.out.println("=== while ===");
        int i = 0;
        //..
        while(i < 3) {
            System.out.println(2);
            System.out.println(3);
            //i = i + 1;
            //..
            i++;
        }
        System.out.println("=== for ===");
        for(int j=0; j < 3; j++) {
            System.out.println(2);
            System.out.println(3);
        }
         
        System.out.println(4);
 
    }
 
}
</code></pre>

* 배열

  배열은 반복문과 뗄 수 없는 사이이다.
  배열을 선언할 때는 변수 타입명 뒤에 빈 [ ] 대괄호를 입력하고 변수 이름을 입력한다.
  초기화를 할 경우에는 new 키워드를 이용하여 [ ] 대괄호 안에 요소의 개수를 입력한다.
  리터럴로 입력할 수 있는 데이터 타입의 경우, { } 중괄호 안에 요소를 리터럴로 입력할 수 있다.
  배열은 인덱스를 통해 접근하고 인덱스는 [ ] 대괄호 안에 입력합니다.

<pre><code>
public class ArrayApp {
 
    public static void main(String[] args) {
         
        // egoing, jinhuck, youbin 
        // String users = "egoing, jinhuck, youbin";
        String[] users = new String[3];
        users[0] = "egoing";
        users[1] = "jinhuck";
        users[2] = "youbin";
         
        System.out.println(users[1]);
        System.out.println(users.length);
         
        int[] scores = {10, 100, 100}; // 원소, element
        System.out.println(scores[1]);
        System.out.println(scores.length);
 
    }
 
}
</code></pre>

* 반복문 + 배열

<pre><code>
public class LoopArray {
 
    public static void main(String[] args) {
        /*
         <li>egoing</li>
         <li>jinhuck</li>
         <li>youbin</li>
         */
         
        String[] users = new String[3];
        users[0] = "egoing";
        users[1] = "jinhuck";
        users[2] = "youbin";
         
        for(int i=0; i < users.length; i++) {
            System.out.println(users[i]+",");
        }
         // int i = 0;으로 초기화 시킨 뒤 i가 users.length. 즉, 배열의 요소 개수보다 작을때 반복하여 i값을 1씩 증가시킨다.
    }    // 조건식에서 length를 사용하게 되면 직접 배열의 요소 개수를 입력하지 않아도 되는 편리성을 가지게 된다.
 
}
</code></pre>

***

2023-05-11
-------------

* 제어문 종합응용 1

<pre><code>
public class AuthApp3 {
 
    public static void main(String[] args) {
         
        String[] users = {"egoing", "jinhuck", "youbin"};
        String inputId = args[0];
         
        boolean isLogined = false;
        for(int i=0; i< users.length; i++) {
            String currentId = users[i];
            if(currentId.equals(inputId)) {
                isLogined = true;
                break;  // 반복문 종료
            }
        }
        System.out.println("Hi,"); 
        if(isLogined) {
            System.out.println("Master!!");
        } else {
            System.out.println("Who are you?");
        }
 
    }
 
}
</code></pre>

* 제어문 종합응용 2

<pre><code>
public class AuthApp3 {
 
    public static void main(String[] args) {
         
        //String[] users = {"egoing", "jinhuck", "youbin"};
        String[][] users = { // 이차원 배열을 이용하여 하나의 배열에 각각의 원소를 두개씩 넣었다.
                {"egoing", "1111"},
                {"jinhuck", "2222"},
                {"youbin", "3333"}
        };
        String inputId = args[0];
        String inputPass = args[1];
         
        boolean isLogined = false;
        for(int i=0; i< users.length; i++) {
            String[] current = users[i];
            if(
                    current[0].equals(inputId) && 
                    current[1].equals(inputPass)
            ) {
                isLogined = true;
                break;
            }
        }
        System.out.println("Hi,");
        if(isLogined) {
            System.out.println("Master!!");
        } else {
            System.out.println("Who are you?");
        }
 
    }
 
}
</code></pre>

* 이미 익숙한 메소드

<pre><code>
public class FirstMethod {
 
    public static void main(String[] args) { // 어떠한 명령을 더 내리지 않아도 main 메소드를 실행한다. 즉, main의 본문을 사용 중인 것.
         
        System.out.println("Hello Method");
        System.out.println(Math.floor(1.1)); // Math 클래스의  floor 메소드로 인해 1.0이 출력됨
 
    }
 
}
</code></pre>

* 메소드의 기본 형식

  의미없는 반복을 실행하는 경우 메소드를 이용한다면 쉽게 같은 코드를 재사용하고, 유지보수를 쉽게 할 수 있다.

<pre><code>
public class WhyMethod {
     
    public static void main(String[] args) {
         
        // 100000000
        printTwoTimesA();
        // 100000000
        printTwoTimesA();
        // 100000000
        printTwoTimesA();
               
    }
 
    public static void printTwoTimesA() {
        System.out.println("-");
        System.out.println("a");
        System.out.println("a");
    }
 
}
</code></pre>

* 메소드의 입력

<pre><code>
public class WhyMethod {
     
    public static void main(String[] args) { // 1. main메소드가 있어야 실행 2. string[] : 문자열 배열 3. 자바가 실행할 때 입력값을 받는 역할을 하는게 args이다.
         
                        // (a, -) : 인자(argument)
            printTwoTimes("a", "-");
            // 100000000
            printTwoTimes("a", "*");
            // 100000000
            printTwoTimes("a", "&");
            printTwoTimes("b", "!");
 
    }
                                    // (text, delimiter) : 매개변수(parameter) 
    public static void printTwoTimes(String text, String delimiter) {
        System.out.println(delimiter);
        System.out.println(text);
        System.out.println(text);
    }
 
}
</code></pre>

* 메소드의 출력

<pre><code>
public class OutputMethod {
     
    public static String a() { // return의 a가 문자열이기때문에 void가 아닌 String로 받는다. 여기서 return값이 없는 메소드를 만들 때에는 void를 사용한다. 
        // ... 
        return "a"; // return : 1. 뒤에있는 값이 그 메소드의 실행결과가 된다. 2. 종료시키는 역할을 한다.
    }
     
    public static int one() {  // return의 1이 숫자열이기때문에 String가 아닌 int로 받는다.
        return 1;
        //...
    }
 
    public static void main(String[] args) {
 
        System.out.println(a());
        System.out.println(one());
         
    }
 
}
</code></pre>

* 메소드의 활용

<pre><code>
public class AccountingApp {

	public static void main(String[] args) {
		double valueOfSupply = 10000.0; // 공급가액
		double vatRate = 0.1; // 부가가치세율
		double vat = valueOfSupply * vatRate; // 부가세
		double total = valueOfSupply + vat; // 합계
		
		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + vat);
		System.out.println("Total : " + total);

        // main 메소드 바깥으로 지역변수화 되어 있는 valueOfSupply와 vatRate, vat, total 변수들을 빼내어 전역변수화 시킨다.
	}
}
</code></pre>

<pre><code>
public class AccountingApp {
    public static double valueOfSupply = 10000.0; // 공급가액

    public static double vatRate = 0.1; // 부가가치세율
 
    public static double getVAT() {
        return valueOfSupply * vatRate; // 부가세
    }
     
    public static double getTotal() {
        return valueOfSupply + getVAT(); // 합계
    }
 
    public static void main(String[] args) {
 
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + getVAT());
        System.out.println("Total : " + getTotal());
    }
}
</code></pre>

* 클래스, OOP(객체 지향 프로그래밍)
  
  클래스 : 비슷한 연관된 일을 하는 메소드와 변수들을 묶어 그룹으로 만든 것.   
  인스턴스 : 클래스를 틀로 하여 실제로 프로그램에서 동작하는 객체들.   
  위와 같은 클래스와 인스턴스 들과 같은 객체를 뼈대로 해서 프로그램을 만들어 가는 방식을 객체지향 프로그래밍(OOP, Object Oriented Programming)이라고 한다.

* Access Level Modifiers
  
<pre><code>
public class AccessLevelModifiersMethod { //접근제어자 public의 자리에 public, protected, default, private 라는 값이 올 수 있다.(동작에는 지장없음)
    // public = 모든 클래스에서 실행 된다. (웬만하면 public을 사용하면 된다.)
	// private = 같은 클래스 안에서만 사용할 수 있다.
    private static void hi() {
		System.out.println("Hi");
	}
	public static void main(String[] args) {
		hi();
	}
}            
</code></pre>

<pre><code>
class Greeting {
	private static void hi() {
		System.out.println("Hi");
	}
}

public class AccessLevelModifiersMethod {

	public static void main(String[] args) {
		Greeting.hi();
	}
} // 오류 : hi는 Greeting 클래스 밖에서 직접 접근해서 사용할 수 없기 때문(private 제약조건)
</code></pre>   

* Static

  Static이란 키워드가 붙은 메소드는 클래스의 메소드다.
  Static이란 키워드가 붙지 않은 메소드는 인스턴스의 메소드다.  
  메소드가 인스턴스 소속일때는 static을 빼주어야 한다.
  메소드가 클래스 소속일때는 static이 존재하여야 한다.

<pre><code>
class Print{
    public String delimiter;
    public void a() {
        System.out.println(this.delimiter);
        System.out.println("a");
        System.out.println("a");
    }
    public void b() {
        System.out.println(this.delimiter);
        System.out.println("b");
        System.out.println("b");
         
    }
    public static void c(String delimiter) {
        System.out.println(delimiter);
        System.out.println("b");
        System.out.println("b");
    }
}
public class staticMethod {
     
    public static void main(String[] args) {
        // Print.a("-");
        // Print.b("-");
         
        // instance
        Print t1 = new Print();
        t1.delimiter = "-";
        t1.a();
        t1.b();
        Print.c("$");
         
         
        // Print.a("*");
        // Print.b("*");
         
        Print t2 = new Print();
        t2.delimiter = "*";
        t2.a();
        t2.b();
    }
}
</code></pre>

***

2023-05-12
-------------

* 메소드와 절차적 프로그래밍

  메소드는 언어마다 메소드, 함수, 서브루틴, 프로시저라는 이름으로 불린다.
  이러한 메소드를 중심으로 프로그램을 만들어 나가는 프로그래밍을 절차적 프로그래밍이라고 한다.

* 클래스와 객체지향 프로그래밍

  객체지향 프로그래밍 : 변수와 메소드를 모은 수납상자와 같은 클래스를 이용하여 프로그램을 정돈시켜 프로그램의 구조를 만들어 가는 방식이다.
  객체 지향 언어 : 위와 같은 방식은 언어차원에서 지원하는 프로그래밍 언어이다. 

* 남의 클래스 남의 인스턴스

<pre><code>
import java.io.FileWriter;
import java.io.IOException;
 
public class OthersOOP {
 
    public static void main(String[] args) throws IOException {
        // class : System, Math, FileWriter
        // instance : f1, f2
         
        System.out.println(Math.PI);
        System.out.println(Math.floor(1.8));
        System.out.println(Math.ceil(1.8));
         
        FileWriter f1 = new FileWriter("data.txt");
        f1.write("Hello");
        f1.write(" Java");
         
         
        FileWriter f2 = new FileWriter("data2.txt");
        f2.write("Hello");
        f2.write(" Java2");
        f2.close();
         
        f1.write("!!!");
        f1.close();
    }
}
</code></pre>
  Math Class : 수학적 계산을 도와주는 여러 메소드를 포함
  floor, ceil 메소드, 클래스 변수(PI)   
  자연상수 E, 삼각함수, 제곱, 로그, 절대값, 난수, 반올림 등의 기능들을 할 수 있는 여러 메소드와 변수 포함
  이러한 메소드와 변수는 인스턴스를 생성하지 않아도 클래스에서 직접 호출할 수 있음

* 변수와 메소드

<pre><code>
public class MyOOP {

	public static void main(String[] args) {
		String delimiter = "----";
		printA(delimiter);
		printA(delimiter);
		printB(delimiter);
		printB(delimiter);
		
		delimiter = "****";
		printA(delimiter);
		printA(delimiter);
		printB(delimiter);
		printB(delimiter);
	}

	public static void printA(String delimiter) {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	public static void printB(String delimiter) {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
}
</code></pre>
  위 코드에서 String delimiter는 변수의 인자값을 바꾸는 변수선언이다.   
  메소드 안에서 정의된 변수는 메소드안에서만 사용할 수 있다.   
  이때 print 소속의 변수를 선언하면 아래 코드와 같다.

<pre><code>
class Print {
	public static String delimiter = "";
	public static void printA() {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	public static void printB() {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
	public static void printAll() {
		printA();
		printA();
		printB();
		printB();
	}
}
public class MyOOP {
	
	public static void main(String[] args) {
		Print.delimiter = "----";
		Print.printAll();
		
		Print.delimiter = "****";
		Print.printAll();
	}	
}
</code></pre>

* 클래스의 존재 이유와 기본형식

  클래스의 장점 : 관련있는 변수들과 메소드를 묶어서 정리정돈을 할 수 있게 한다.   
  우리는 위 코드에서  PrintA(), PrintB() 식으로 프린트문을 실행했다. 이를 더 편하게 하려면 Print.A, Print.B 이런식으로 변경해주면 된다. 이는 Print에 속한 A라는 뜻이다.
  Print.A 처럼 쓰면 굳이 메소드의 이름을 PrintA라고 적지 않고 A라고만 적어도 Print 객체의 A메소드이기 때문에 A를 출력한다는 의미를 쉽게 유추할 수 있다.

* 클래스의 형식

  클래스는 한파일에 여러 개를 넣을 수 있지만 접근제어자 Public은 Java 파일과 같은 이름의 클래스에 하나만 붙일 수 있다.   
  소스 코드를 컴파일할 때 그 안에 들어 있는 클래스는 아래와 같이 따로따로 하나씩 class 파일로 만들어진다.   
<pre><code>
    MyOOP.class // 실행을 담당하는 main 메소드가 들어있는 MyOOP.class
    Print.class // 프로그램의 실질적인 액션을 담당하는 Print.class
    (폴더)src
    MYOOP.java
</code></pre>
  따라서 한 파일안에 여러 클래스가 등장할 수 있지만 여러 클래스를 각각 하나의 java 파일로 만들게 되면 프로그램 기능별로 쪼개어 소스 코드를 별도 저장할 수 있다.

* 인스턴스

  클래스 : 어떠한 형틀 
  인스턴스 : 형틀로 찍어낸 실체   
  객체를 인스턴스로 만들면 그 인스턴스를 바꾼다 하더라도 다른 인스턴스는 영향을 받지 않음   
  클래스를 복제하는 키워드 : new   
<pre><code>
class Print {
	public String delimiter = "";
	public void A() {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	public void B() {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
}
public class MyOOP {
	
	public static void main(String[] args) {
		Print p1 = new Print();
		p1.delimiter = "----";
		Print p2 = new Print();
		p2.delimiter = "****";
		
		p1.A();
		p2.A();
		p1.B();
		p2.B();	
	}	
}
</code></pre>
  위 코드에서 A()와 B() 속에 있는 코드를 실행시킬려면, MyOOP 클래스의 main에서 Print 클래스를 객체화 시켜 p1,p2이라는 변수를 선언하고 이를 "new" 를 사용해 Print()를 복제한 복제본을 만들어서 각각의 복제본을 내부적으로 다른데이터(딜리버리)를 유지하게 하여 코드를 깔끔하고 중복을 제거하는 결과를 얻게되었다.

***

2023-05-15
-------------

* static

<pre><code>
class Foo{
    public static String classVar = " i class var ";
    public String instanceVar = " i instance var ";  // 선언
    public  static  void   classMethod(){
        System.out.println(classVar);
    }
    public void instanceMethod(){
        System.out.println(classVar);
        System.out.println(instanceVar);
    }
}
public class WS {
    
    public static void main(String[] args){

        System.out.println(Foo.classVar);
        Foo.classMethod();
        
        Foo f1 = new Foo();
        Foo f2 = new Foo();

        System.out.println(f1.classVar);
        System.out.println(f1.instanceVar);
        
        f1.classVar = " changed by f1 ";  // 바꿈
        System.out.println(Foo.classVar);
        System.out.println(f2.classVar);  // 값을 공유하기 때문에 결과값이 달라짐
        
        f1.instanceVar = " changed by f1 ";
        System.out.println(f1.instanceVar);
        System.out.println(f2.instanceVar);

        // static 은 클래스의 변수
    }
}
</code></pre>

* 생성자와 this

<pre><code>
class Print{
    public String qq = "";
    public Print(String qq){
        this.qq = qq;
    }

    public  void A() {
        System.out.println(this.qq);
        System.out.println("A");
        System.out.println("A");
    }

    public  void B() {
        System.out.println(this.qq);
        System.out.println("B");
        System.out.println("B");
    }
}
public class WS {
    public static void main(String[] args) {

        Print p1 = new Print("-----");
        p1.A();
        p1.A();
        p1.B();
        p1.B();

        Print p2 = new Print("*****");
        p2.A();
        p2.A();
        p2.B();
        p2.B();
    }
}

</code></pre>

* 활용

<pre><code>
class Accounting{
    public double ValueOfSupply;
    public static double VATrate = 0.1;

    public Accounting(double ValueOfSupply) {
        this.ValueOfSupply = ValueOfSupply;
    }
    public double getVAT() {
        return ValueOfSupply * VATrate;
    }
    public double getTotal() {
        return ValueOfSupply + getVAT();
    }
}

public class WS {
    public static void main(String[] args) {

        Accounting a1 = new Accounting(10000.0);

        Accounting a2 = new Accounting(20000.0);

        System.out.println(" Vaule of supply :" + a1.ValueOfSupply);
        System.out.println(" Vaule of supply :" + a2.ValueOfSupply);

        System.out.println(" VAT : " + a1.getVAT());
        System.out.println(" VAT : " + a2.getVAT());

        System.out.println(" Total : " + a1.getTotal());
        System.out.println(" Total : " + a2.getTotal());
    }
}

</code></pre>

***

2023-05-16
-------------

* 기능의 개선과 발전

<pre><code>
class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
}
class Cal3 extends Cal{
	public int minus(int v1, int v2) {
		return v1 - v2;
	}
}

public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));
		System.out.println(c3.minus(2, 1));
	}
}
</code></pre>
  위 코드는 부모클래스가 가지고 있지 않은 기능을 추가했으며, 부모클래스가 가진 기능이지만 더 보태서 재정의(override)했다.

* Overriding, Overloading

<pre><code>
class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
	// Overloading
	public int sum(int v1, int v2, int v3) {
		return v1 + v2 + v3;
	}
}
</code></pre>

<pre><code>
class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
    public int sum(int v1, int v2, int v3) {
		return v1 + v2 + v3;
    }    
}
class Cal3 extends Cal{
	public int minus(int v1, int v2) {
		return v1 - v2;
	}
}

public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));
		System.out.println(c3.minus(2, 1));
	}
}
</code></pre>
  위 코드에서 오버로딩 동작을 하기위해 추가된 코드는 아래 코드와 같다.  
 
<pre><code>
public int sum(int v1, int v2, int v3) {
		return v1 + v2 + v3;
}
</code></pre> 
  만약 파라미터의 값을 세개를 추가해주고 싶다면 그 값의 개수와 동일한 코드를 부모클래스에서 찾아서 출력할 것이다.   
  오버라이딩은 같은 클래스에서 이루어질 수 없고, 상속 관계를 가진 클래스 사이에서 이루어질 수 있다.

* This Super

<pre><code>
class Cal{
    public int sum(int v1, int v2){
        return v1+v2;
    }
    public int sum(int v1, int v2, int v3) {
        return this.sum (v1, v2, v3);  // 자기 자신을 사용함
    }
}
class Cal3 extends Cal{
    public int minus(int v1, int v2){
        return  v1-v2;
    }
    public int sum(int v1, int v2){
        System.out.println("Cal3");
        return super.sum(v1, v2);  // 부모의 메소드를 사용함
    }
}

public  class WS {
    public static void main(String[] args){

        Cal c = new Cal();
        System.out.println(c.sum(2,1));

        Cal3 c3 = new Cal3();
        System.out.println(c3.minus(2,1));
        System.out.println(c3.sum(2,1));
    }
}
</code></pre>

* 상속과 생성자

<pre><code>
class Cal {
    int v1, v2;
    Cal(int v1, int v2){
        System.out.println("Cal init");
        this.v1 = v1; this.v2 = v2;
    }
    public int sum(){return  this.v1+v2;}
}
class Cal3 extends  Cal{
    Cal3(int v1, int v2){
        super(v1,v2);
        System.out.println("Cal3 init");
    }
    public int minus(){return this.v1-v2;}
}
public class WS {
    public static void main(String[] args){

        Cal c = new Cal(2,1);
        Cal3 c3 = new Cal3(2,1);
        System.out.println(c3.sum());
        System.out.println(c3.minus());
    }
}
</code></pre>

***

2023-05-17
-------------

* 인터페이스

  규격을 지정한다.   
  메소드에서 implements 인터페이스시에 해당 메소드에서는 인터페이스의 규격 메소드가 생성된다.

<pre><code>
interface Calculable {
	int sum(int v1, int v2);
}
class RealCal implements Calculable {

	public int sum(int v1, int v2) {
		return v1 + v2;
	}	
}
</code></pre>
  위 코드에서 interface로 Calculable을 만들고 내부에서 정수형 sum변수의 파라미터를 지정하였다.

* 인터페이스의 형식

<pre><code>
interface Calculable{
    double PI = 3.14;
    int sum(int v1, int v2);
}
interface Printable{
    void print();
}
class RealCal implements Calculable, Printable{

    public int sum(int v1, int v2) {
        return v1+v2;
    }
    public void print() {
        System.out.println("This is RealCal");
    }
}

public class WS {
    public static void main(String[] args){

        RealCal c = new RealCal();
        System.out.println(c.sum(1,2));
        c.print();
        System.out.println(c.PI);
    }
}
</code></pre>

* 다형성

* 다형성

  다형성 : 객체의 타입이 부모 클래스, 인터페이스, 자식 클래스 등 여러 형태인데도 인스턴스로 만든 객체와 같이 행동하는 것

<pre><code>
interface Calculable {
	double PI = 3.14;
	int sum(int v1, int v2);
}
interface Printable {
	void print();
}
class RealCal implements Calculable, Printable {

	public int sum(int v1, int v2) {
		return v1 + v2;
	}

	public void print() {
		System.out.println("this is RealCal!!!");
	}	
}

public class InterfaceApp {

	public static void main(String[] args) {
		Calculable c = new RealCal();
		System.out.println(c.sum(2, 1));
		c.print(); // Compile Error
		System.out.println(c.PI);
	}
}
</code></pre>
  RealCal 인스턴스를 Calculable 타입으로 선언하면, Printable 메소드를 사용할 수 없다.   
  Printable 타입으로 선언하면, Calculable 메소드를 사용할 수 없다.
  어떤 클래스가 데이터타입을 무엇으로 하느냐에 따라서 다양한 얼굴을 가지게 된다.

* 사용설명서 속의 인터페이스

  JAVA API속의 인터페이스

<pre><code>
import java.io.FileWriter;
import java.io.IOException;
import java.io.Writer;

public class FileWriterApp {
	public static void main(String[] args) throws IOException {
		Writer fileWriter = new FileWriter("filewriter.txt");
		fileWriter.write("data 1");
		fileWriter.write("data 2");
		fileWriter.write("data 3");

		fileWriter.close();
	}
}
</code></pre>
  FileWriter 인스턴스는 초기화할 때 파일에 접근해서 파일을 점유하고 있다는 표시를 한다.
  다 끝낸 후에는 close 메소드를 이용해서 현재 파일에 대한 점유를 끝낸다는 표시를 한다.

***

2023-05-18
-------------

* 예외의 발생

<pre><code>
public class ExceptionApp {
	public static void main(String[] args) throws ArithmeticException {
		System.out.println(1);
		System.out.println(2/0); // Run-Time Exception ArithmeticException
		System.out.println(3); 
	}
}
</code></pre>
  자바는 숫자를 0으로 나누는 경우 예외로 처리한다.   
  실제 실행을 시켜보면 ArithmeticException이라고 알려주고, 0으로 나누었다는 설명도 나오게 된다.   
  예외가 발생하는 이유는 프로그램이 실행하는 동안, 프로그램을 만들 사람들이 설계한 모양대로 운영되지 않았기 때문이다.

* 예외의 처리

<pre><code>
public class ExceptionApp {
	public static void main(String[] args) throws ArithmeticException {
		System.out.println(1);
		int[] scores = {10, 20, 30};

		try {
			System.out.println(2);
			System.out.println(scores[3]); //ArrayIndexOutOfBoundsException
			// 여기까지 실행 -> catch(ArrayIndexOutOfBoundsException e)문으로 이동
			System.out.println(3);
			System.out.println(2/0); //ArithmeticException
			System.out.println(4);
		} catch(ArithmeticException e) {
			System.out.println("잘못된 계산이네요.");
		} catch(ArrayIndexOutOfBoundsException e) {
			System.out.println("없는 값을 찾고 계시네요 ^^");
		}		
		System.out.println(5); 
	}
}
</code></pre>
  위 코드는 try catch문을 이용하여 예외를 처리하여 이상한 경우에도 끝까지 실행되는 튼튼한 프로그램이다.
  try catch 구문을 사용하면 프로그램이 유연하게 흘러간다.

* 예외의 우선순위
 
<pre><code>
public class ExceptionApp {
	public static void main(String[] args) throws ArithmeticException {
		System.out.println(1);
		int[] scores = {10, 20, 30};

		try {
			System.out.println(2);
			System.out.println(scores[3]); //ArrayIndexOutOfBoundsException
			System.out.println(3);
			System.out.println(2/0); //ArithmeticException
			System.out.println(4);
		} catch (ArithmeticException e) {
			System.out.println("계산이 잘못된 것 같아요.");
		} catch (Exception e) {
			System.out.println("뭔가 이상합니다. 오류가 발생했습니다. ");
		}	
		System.out.println(5); 
	}
}
</code></pre>
  ArithmeticException은 RuntimeException으로부터 상속받은 클래스.   
  또한 RuntimeException은 Exception 클래스로부터 상속받은 클래스.   
  여러 예외가 있더라도 Exception클래스를 이용해서 포괄적으로 처리 가능.   
  catch문의 위치가 중요하다.   
  try문에서 발생한 예외는 여러 개의 catch문을 순서대로 거쳐서 하나씩 확인한다.

* e의 비밀

  catch문의 변수 e는 인스턴스.   
  예외들의 인스턴스에는 예외가 발생한 원인, 어디서 발생했는지에 대한 정보들이 들어 있다.

* Checked exception vs Unchecked exception

  ArithmeticException, ArrayIndexOutOfBoundsException 같은 경우 는 try catch 문으로 잡아내지 않아서 프로그램이 뻗어도 컴파일해서 실행할 수 있었다. 이런 예외들을 Unchecked Exception라고 부른다.   
  try catch문 으로 잡아내지 않으면 프로그램이 컴파일 되지 않는 예외들을 Checked Exception라고 부른다.
  
<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class CheckedExceptionApp {

	public static void main(String[] args) {
		try {
			FileWriter f = new FileWriter("data.txt");
			f.write("Hello");
			f.close();
		} catch(IOException e) {
			e.printStackTrace();
		}
	}
}
</code></pre>
  IOException을 처리하지 않으면 컴파일이 되지 않는다.

* Finally, Resource

  대표적인 Resource : 파일, 네트워크, 데이터베이스   
  우리의 프로그램만을 위해 존재하지 않음.   
  파일의 경우 점유상태를 나타내기도 하고, 네트워크나 데이터베이스는 연결 상태를 유지한다. 그리고 우리가 필요한 작업을 끝내고 나서는 자원을 놓아주는 작업을 한다.

  Finally : 자원을 놓아주는 작업을 try문에 넣게 되면 예외가 발생했을 때 자원을 놓아주는 작업을 하지 못한다. 그래서 예외의 발생 유무에 관계없이 자원을 일단 잡았으면 놓아주는 작업을 실행해야 하는데 이때 사용하는 형식이 Finally문이다.

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class CheckedExceptionApp {

	public static void main(String[] args) {
		FileWriter f = null;
		try {
			f = new FileWriter("data.txt");
			f.write("Hello");
			// close를 하기 전에 예외가 발생한다면 close가 실행되지 않음
			// f.close();
		} catch(IOException e) {
			e.printStackTrace();
		} finally {
			if (f != null) {
				try {
					f.close();
				} catch (IOException e) {
					e.printStackTrace();
				}
			}			
		}
	}
}
</code></pre>

* Try-with-Resource

  try-with-resource 문을 이용하여 자원관리를 훨씬 단순하게 할 수 있다.   
  클래스가 AutoCloseable 인터페이스를 상속한다면 try-with-resource 문에 사용할 수 있다.

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class TryWithResource {

	public static void main(String[] args) {
		try (FileWriter f = new FileWriter("data.txt")) {
			f.write("Hello");
		} catch (IOException e) {
			e.printStackTrace();
		}
	}
}
</code></pre>

***

