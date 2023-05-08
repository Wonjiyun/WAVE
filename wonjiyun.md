<h1>5월 1일 boostcorse 쉽게 배우는 자바1 1, 2, 3, 4, 5<h1>
<h2>2-1</h2>

<pre><code>
public class MyClass {
    public static void main(String args[]) {
        System.out.println("Hello World!");
    }
}

#결과: Hello World!
</code></pre>

<pre><code>
public class MyClass {
    public static void main(String args[]) {
        System.out.println("Hello "+args[0]);
    }
}

#결과: Hello egoing
</code></pre>

<pre><code>
public class MyClass {
    public static void main(String args[]) {
        System.out.println("Hello "+args[0]+", "+args[1]);
    }
}

#결과: Hello egoing, leezche
</code></pre>

<h2>4-3</h2>

* source: 원천
* code
* language
*-> 같은 대상을 바라보는 관점에 따라 다르게 사용되는 언어* 

* application
* program
*-> 같은 대상을 바라보는 관점에 따라 다르게 표현하는 언어* 

<h3>자바의 동작원리</h3>
Java Soure code(.java):사람이 이해할 수 있음, 기계는 이해하지 못함
                            |
    complie: 기계가 source code를이해할 수 있게 변환하는 과정
                            |
    Java Application(.class):.class라는 확장자를 가진 파일
                            |
                           run
                            |
                  Java Virtual Machine
                            |
                           run
                            |
                         computer


<h2>5-1</h2>
<h3>데스크톱 애플리케이션 만드는 코드</h3>
11번째 줄 코드 제외나머지 부분은 데스크탑 창을 구성하기 위한 부분들
<pre><code>
import javax.swing.*;   
import java.awt.Dimension;
import java.awt.Toolkit;
public class HelloWorldGUIApp{
    public static void main(String[] args){
        javax.swing.SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                JFrame frame = new JFrame("HelloWorld GUI");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setPreferredSize(new Dimension(800, 300)); //800을 400으로 수정하면 창의 너비가 2배 작아진 것을 확인할 수 있음
                JLabel label = new JLabel("Hello World!!", SwingConstants.CENTER); //작은 윈도우에 Hello World!!를 나타내주는 코드, CENTER을 RIGHT로 바꾸면 창의 오른쪽에 나타나는 것을 확인할 수 있음
                frame.getContentPane().add(label);
                Dimension dim = Toolkit.getDefaultToolkit().getScreenSize();
                frame.setLocation(dim.width/2-400/2, dim.height/2-300/2);

                frame.pack();
                frame.setVisible(true);
            }
        });
    }
}
</code></pre>

<h2>5-2</h2>
<h3>사물을 자바로 제어하기</h3>
<pre><code>
import com.pi4j.io.gpio.GpioController;
import com.pi4j.io.gpio.GpioFactory;
import com.pi4j.io.gpio.GpioPinDigitalOutput;
import com.pi4j.io.gpio.PinState;
import com.pi4j.io.gpio.RaspiPin;

public class HelloWorldRaspberryPi {

	public static void main(String[] args) throws InterruptedException {

		final GpioController gpio = GpioFactory.getInstance();
		final GpioPinDigitalOutput pin = gpio.provisionDigitalOutputPin(RaspiPin.GPIO_01, "PinLED", PinState.LOW);
		final int SHORT_INTERVAL = 200;
		final int LONG_INTERVAL = SHORT_INTERVAL * 3;
		final int LETTER_INTERVAL = SHORT_INTERVAL * 7;

		while (true) {
			// H
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
</code></pre>

<h1>5월 2일 boostcorse 쉽게 배우는 자바1 6, 7<h1>
<h2>6-1</h2>
<h3>데이터와 연산</h3>

data & operation

* Number
* String 
* 영상/소리 등등

컴퓨터의 데이터에 따른 처리 방식

* 숫자의 경우 +, -, /, * ..
* 문자열의 경우 길이를 호출, 특정 구간 제거, 특정 문자열 유무 검사 ..
* 영상/소리 등등

<h2>6-2</h2>
<h3>데이터 타입</h3>
<pre><code>
public class Datatype{
	public static void main(String[] args) {
		System.out.println(6); // Number
		System.out.println("six"); // String
		
		System.out.println("6"); // String 6
		
		System.out.println(6+6); // 12
		System.out.println("6"+"6"); // 66 
		
		System.out.println(6*6); // 36
		System.out.println("6"*"6"); // error
		
		System.out.println("1111".length()); // 4 
		System.out.println(1111.length()); // error
	}
} 
</code></pre>

<h2>6-3</h2>
<h3>숫자와 연산</h3>
Math.floor: 내림
Math.ceil: 올림
<pre><code>
public class Number {

	public static void main(String[] args) {
		//Operator
		System.out.println(6+2); // 8
		System.out.println(6-2); // 4
		System.out.println(6*2); // 12
		System.out.println(6/2); // 3
		
		//eclipse에서의 수학적 연산 Math.
		System.out.println(Math.PI); //3.141592653589793
		System.out.println(Math.floor(Math.PI)); // 3.0
		System.out.println(Math.ceil(Math.PI)); // 4.0
	}
}
</code></pre>

<h2>6-4</h2>
<h3>문자열의 표현</h3>
Character VS String
<pre><code>
public class StringApp {

	public static void main(String[] args) {
		
		System.out.println("Hello World!"); // String: 여러 개의 character
		System.out.println('H'); // character: 한 글자
		System.out.println("H"); //String
		
	}
}
</code></pre>
new line
<pre><code>
public class StringApp {

	public static void main(String[] args) {
		
		System.out.println("Hello 
				 World");        		//error
		
		System.out.println("Hello "		// Hello World
				+ "World!"); 
		
		System.out.println("Hello \nWorld!"); // Hello 줄바꿈 World!
		
		// escape
		System.out.println("Hello \"World!\""); // Hello "World!"
		
	}
}
</code></pre>
escape
<pre><code>
public class StringApp {

	public static void main(String[] args) {

		System.out.println("Hello \"World!\""); // Hello "World!"
		
	}
}
</code></pre>

<h2>6-5</h2>
<h3>문자열 다루기</h3>
<pre><code>
public class StringOperation {

	public static void main(String[] args) {
		
		System.out.println("Hello World".length()); // 11
		System.out.println("Hello, leezche ... bye".replace("leezche", "egoing")); // Hello, egoing ... bye
		System.out.println("Hello, [[[name]]] ... bye".replace("[[[name]]]", "egoing")); // Hello, egoing ... bye
		
	}
}
</code></pre>

<h1>5월 3일 boostcorse 쉽게 배우는 자바1 8, 9, 10<h1>
<h2>8-1</h2>
<h3>변수의 정의</h3>

변수는 값의 이름을 부여하는 것   

**Number -> integer(정수)**
<pre><code>
public class Variable {

	public static void main(String[] args) {
		
		a=1; //error 
		int a = 1;
		System.out.println(a); // 1
	}
}
</code></pre>
**Number -> real number(실수) -> double**
<pre><code>
public class Variable {

	public static void main(String[] args) {
		
		int b = 1.1;  //error
		double b = 1.1;
		System.out.println(b); // 1.1
	}
}
</code></pre>
**String(문자열)**
<pre><code>
public class Variable {

	public static void main(String[] args) {

		int c = "Hello World";  //error
		String c = "Hello World";
	}
}
</code></pre>

**데이터 타입을 지정하는 이유**
* 변수의 데이터 타입을 바로바로 판단할 수 있기 때문   

**Data type - Default Value(for fields)**
* byte - 0
* short - 0
* int - 0
* long - 0L
* float - 0.0f
* double - 0.0d
* char - '\u0000'
* String (or any object) - null
* boolean - false

**kinds of variables**
* Instance Variables(Non-Static Fields)
* Class Variables(Static Fields)
* Local Variables
* Parameters

<h2>8-2</h2>
<h3>변수의 효용</h3>

**변수의 재사용**
<pre><code>
public class Letter {

	public static void main(String[] args) {
		
		String name ="egoing";
		System.out.println("Hello, "+name+" ... "+name+" ... egoing ... bye");
	}
}
</code></pre>
**코드의 가독성**
<pre><code>
public class Letter {

	public static void main(String[] args) {
		
		double VAT = 10.0;
		System.out.println(VAT);
	}
}
</code></pre>

<h2>8-3</h2>
<h3>데이터 타입의 변환 - casting</h3>

<pre><code>
public class Casting {

	public static void main(String[] args) {
		
		double a = 1.1;
		double b = 1; 
		double b2 = (double) 1; // 1.0 : 위와 같음
		System.out.println(b); // 1.0 -> 1인 정수가 실수인 1.0으로 convert. 손실이 없기에 가능
		
		int c = 1.1;  //error 손실 발생
		double d = 1.1;
		int e = (int) 1.1; // 손실 발생하므로 명시적으로 형 변환 필요
		
		System.out.println(d); // 1.1
		System.out.println(e);  // 1 -> 1.1인 실수를 1인 정수로 강제로 변환하여 소수점 사라짐(손실)

		// 1 to String
		String f = Integer.toString(1);
		System.out.println(f); // 1 : 문자열 1
		System.out.println(f.getClass()); //변수가 어떤 데이터 타입을 갖고 있는지
	}
}
</code></pre>

<h2>9-1</h2>
<h3>프로그래밍이란 무엇인가</h3>
프로그램이란 시간에 따라 실행할 작업들의 순서를 의미한다.
이렇게 시간에 따라 컴퓨터가 정해진 순서에 작업을 실행하게 된다면 우린 업무를 자동적으로 처리할 수 있게 된다.
컴퓨터 언어를 이용해서 프로그램을 만드는 것은 업무의 자동화된 처리를 위해서라 할 수 있다.

<h2>9-3</h2>
<h3>IOT 프로그램 만들기</h3>

<pre><code>
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Security;
import org.opentutorials.iot.Lighting;

public class OkJavaGoInHome {

	public static void main(String[] args) {
		
		// Elevator call
		Elevator myElevator = new Elevator("JAVA APT 507");
		myElevator.callForUp(1); //JAVA APT 507 -> Elevator callForUp stopFloor : 1
		
		// Security off
		Security MySecurity = new Security("JAVA APT 507");
		MySecurity.off(); //JAVA APT 507 -> Security off
		
		// Light on
		Lighting hallLamp = new Lighting("JAVA APT 507 / Hall Lamp");
		hallLamp.on(); //JAVA APT 507 / Hall Lamp -> Lighting on
		
		Lighting floorLamp = new Lighting("JAVA APT 507 / floor Lamp");
		floorLamp.on(); //JAVA APT 507 / floor Lamp -> Lighting on
	}
}

</code></pre>
반복적으로 사용되는 값의 경우 변수로 지정하여 재사용할 수 있고 의미있는 이름을 지정하여 코드의 가독성을 높일 수 있음
<pre><code>
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Security;
import org.opentutorials.iot.Lighting;

public class OkJavaGoInHome {

	public static void main(String[] args) {
		
		// Elevator call
		Elevator myElevator = new Elevator("JAVA APT 507");
		myElevator.callForUp(1); //JAVA APT 507 -> Elevator callForUp stopFloor : 1
		
		// Security off
		Security MySecurity = new Security("JAVA APT 507");
		MySecurity.off(); //JAVA APT 507 -> Security off
		
		// Light on
		Lighting hallLamp = new Lighting("JAVA APT 507 / Hall Lamp");
		hallLamp.on(); //JAVA APT 507 / Hall Lamp -> Lighting on
		
		Lighting floorLamp = new Lighting("JAVA APT 507 / floor Lamp");
		floorLamp.on(); //JAVA APT 507 / floor Lamp -> Lighting on
	}
}
</code></pre>

<h2>10</h2>
<h3>디버거</h3>

**브레이크 포인트 지정하기**
코드 편집 창에서 줄 번호 왼편에서 더블클릭하면 브레이크 포인트가 지정된다
브레이크 포인트를 지정한 상태에서 디버거를 실행하게 되면 브레이크 포인트까지 코드가 실행되고
그 이후로 실행이 일지정지된다. 

**step over**
다음 줄에 브레이크 포인트가 생성되어 그 지점까지만 코드가 실행

**resume**
다음 브레이크 포인트까지 실행되고, 더 이상 브레이크 포인트가 없다면 끝까지 실행

**variable**
우측 탭에서 변수들 확인할 수 있음

**step into**
코드의 자세한 실행 과정을 들여다볼 수 있음
다시 원래의 코드로 돌아가고자 할 경우엔 step return 클릭

<h2>11-1</h2>
<h3>입력과 출력</h3>

프로그램은 입력정보를 받아서 출력을 하는 것이라 할 수 있다. 입력 정보는 문자열, 숫자 등의 아규먼트가 될 수도 있고, 파일, 네트워크를 통해 받은 정보, 소리, 다른 프로그램에서 출력된 정보 등이 될 수 있다. 출력 정보도 화면에 출력하는 형태가 될 수 있고, 파일에 쓸 수도 있고, 소리로 내보낼 수도 있다. 또 다른 프로그램을 출력할 수도 있다. 

<pre><code>
import javax.swing.JOptionPane;

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Security;
import org.opentutorials.iot.Lighting;

public class OkJavaGoInHomeinput {

	public static void main(String[] args) {
		
		String id = JOptionPane.showInputDialog("Enter a id");
		String bright = JOptionPane.showInputDialog("Enter a Bright level");
		
		// Elevator call
		Elevator myElevator = new Elevator(id);
		myElevator.callForUp(1); //JAVA APT 507 -> Elevator callForUp stopFloor : 1
		
		// Security off
		Security MySecurity = new Security(id);
		MySecurity.off(); //JAVA APT 507 -> Security off
		
		// Light on
		Lighting hallLamp = new Lighting(id+" / Hall Lamp");
		hallLamp.on(); //JAVA APT 507 / Hall Lamp -> Lighting on
		
		Lighting floorLamp = new Lighting(id+" / floor Lamp");
		floorLamp.on(); //JAVA APT 507 / floor Lamp -> Lighting on
		
		DimmingLights moodLamp = new DimmingLights(id+" moodLamp");
		moodLamp.setBright(bright); //error -> string이라서 에러가 난다 double로 바꿔줘야 함
		moodLamp.setBright(Double.parseDouble(bright)); //string인 bright가 double로 바뀜
		moodLamp.on();
	}
}
</code></pre>

<h2>11-2</h2>
<h3>입력과 출력 - arguments & parameter</h3>

**아규먼트를 입력받아 프로그램 실행시키기**
* main 메소드의 args 파라미터를 이용해서 입력값을 받는 방법 
* Run 버튼의 팝업 버튼을 클릭해 Run Configurations 메뉴 클릭 
* Argument 탭에서 program arguments에 ''로 묶어서 값 입력
* args는 문자열 배열(array)로 여러 개의 string 데이터가 들어있을 수 있다 인덱스를 통해 배열의 데이터를 꺼내 쓸 수 있고, 인덱스는 0번부터 시작
<pre><code>
public class OkJavaGoInHomeinput {

	public static void main(String[] args) {
		
		String id = args[0];
		String bright = args[1];
		}
}
</code></pre>

<h2>12-1</h2>
<h3>직접 컴파일-실행 - 소개</h3>

**이클립스 없이 자바로 프로그래밍을 하려면 자파 파일을 스스로 컴파일 할 수 있어야 하고 컴파일한 클래스 파일을 실행하는 과정을 거쳐야 한다 이 과정은 운영체제에 대한 많은 지식이 필요하다**   
* Compile
* Run
* Input

<h2>13-1</h2>
<h3>자바 문서 보는 법 - API vs UI</h3>

자바 프로그램을 만들 때 자바의 도구들을 응용하여 우리가 원하는 작업을 시간적 순서에 따라 동작하도록 만들었다. 작업들의 시간적 순서에 주목해서 우리는 프로그램(Program)이라 부리고, 도구의 응용에 주목해서 우리는 애플리케이션(Application)이라고 부른다.   

자바는 자바의 도구들을 응용해서 사용하기 위해서 일정한 조작 장치를 구성하였는데, 이것을 자바 API(Application Programming Interface)라고 한다.   

이렇게 만들어진 자바 프로그램은 사용자가 사용할 수 있다. 이때 사용자가 자바 프로그램을 사용할 수 있도록 만들어둔 장치들을 UI(User Interface)라고 한다.

<h2>13-2</h2>
<h3>자바 문서 보는 법 - 패키지, 클래스, 변수, 메소드</h3>

**패키지, 클래스, 변수, 메소드**
클래스 안에는 PI와 같은 변수, floor, ceil과 같은 메소드들이 포함되어 있다. 패키지는 이러한 클래스들을 하나의 묶음으로 정리한 것이다.

<h2>13-3</h2>
<h3>자바 문서 보는 법 - 클래스</h3>

<pre><code>
public class ClassApp {

	public static void main(String[] args) {
		
		System.out.println(Math.PI);
		System.out.println(Math.floor(1.6));
		System.out.println(Math.ceil(1.6));
	}
}
</code></pre>

<h2>13-4</h2>
<h3>자바 문서 보는 법 - 인스턴스</h3>

**인스턴스란**   
인스턴스는 클래스를 컴퓨터 상에서 실체화한 것이다.   

**인스턴스를 만드는 이유**   
인스턴스틑 객체를 다양한 상태에서 사용하고, 기능을 재사용할 경우가 많은 상황에서 유용한 방식이다.

<pre><code>
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.PrintWriter;
public class InstanceApp {

	public static void main(String[] args) throws IOException {
		
		PrintWriter p1 = new PrintWriter("result1.txt");
		p1.write("Hello 1");
		p1.close();
		
		PrintWriter p2 = new PrintWriter("result2.txt");
		p2.write("Hello 2");
		p2.close();
	}
}
</code></pre>

<h2>13-5</h2>
<h3>자바 문서 보는 법 - 상속</h3>

**클래스의 상속관계**   
클래스 간에는 서로 계층적인 관계를 갖고 있을 수 있다. 들여쓰기되어 표현된 각각의 클래스 간의 관계는 상속 관계를 나타낸다. PrintWriter 클래스는 Writer 클래스에서 상속을 받았고, Writer 클래스는 Object 클래스로부터 상속을 받았다는 것을 나타낸다.


**클래스 간의 상속관계의 특성**   
자식에 해당하는 클래스는 부모에 해당하는 클래스의 모든 변수와 메소드를 사용할 수 있다. 

<h2>14-2</h2>
<h3>나의 앱 만들기_기본 기능 구현</h3>

<pre><code>
public class AccountingApp {

	public static void main(String[] args) {
		
		System.out.println("Value of supply: "+10000.0);
		System.out.println("VAT: "+10000.0*0.1);
		System.out.println("Total: "+(10000.0+10000.0*0.1));
		System.out.println("Expense: "+(10000.0*0.3));
		System.out.println("Income: "+(10000.0 - 10000.0*0.3));
		System.out.println("Income: "+(10000.0 - 10000.0*0.3)*0.5);
		System.out.println("Income: "+(10000.0 - 10000.0*0.3)*0.3);
		System.out.println("Income: "+(10000.0 - 10000.0*0.3)*0.2);
	}

}
</code></pre>

<h2>14-3</h2>
<h3>나의 앱 만들기_변수 도입</h3>
특정 값을 지역 변수로 바꾸기 위해 Extract Local Variable 기능 이용하기
<pre><code>
public class AccountingApp {

	public static void main(String[] args) {
		
		double valueOfSupply = 12345.0;
		double vatRate = 0.1;
		double expenseRate=0.3;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply+vat;
		double expense = valueOfSupply*expenseRate;
		double income = valueOfSupply - expense;
		double dividend1 = income*0.5;
		double dividend2 = income*0.3;
		double dividend3 = income*0.2;
		
		System.out.println("Value of supply: "+valueOfSupply);
		System.out.println("VAT: "+vat);
		System.out.println("Total: "+total);
		System.out.println("Expense: "+expense);
		System.out.println("Income: "+income);
		System.out.println("Dividend1: "+ dividend1);
		System.out.println("Dividend2: "+ dividend2);
		System.out.println("Dividend3: "+ dividend3);
	}
}
</code></pre>

<h2>14-4</h2>
<h3>나의 앱 만들기_입력값 도입</h3>

<pre><code>
public class AccountingApp {

	public static void main(String[] args) {
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate=0.3;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply+vat;
		double expense = valueOfSupply*expenseRate;
		double income = valueOfSupply - expense;
		double dividend1 = income*0.5;
		double dividend2 = income*0.3;
		double dividend3 = income*0.2;
		
		System.out.println("Value of supply: "+valueOfSupply);
		System.out.println("VAT: "+vat);
		System.out.println("Total: "+total);
		System.out.println("Expense: "+expense);
		System.out.println("Income: "+income);
		System.out.println("Dividend1: "+ dividend1);
		System.out.println("Dividend2: "+ dividend2);
		System.out.println("Dividend3: "+ dividend3);
	}
}