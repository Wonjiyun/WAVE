<h1>boostcorse 쉽게 배우는 자바1<h1>
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
</code></pre>

<h2>14-6</h2>
<h3>나의 앱 만들기_조건문</h3>

제어문은 프로그램의 실행 과정을 조건에 따라 바꾸는 것이다. 자바에는 두 가지 제어문이 있다. 조건문과 반복문이 있다.

<pre><code>
public class AccountingIFApp {

	public static void main(String[] args) {
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate=0.3;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply+vat;
		double expense = valueOfSupply*expenseRate;
		double income = valueOfSupply - expense;
		
		double dividend1;
		double dividend2;
		double dividend3;
		
		if(income>10000.0) {
			dividend1 = income*0.5;
			dividend2 = income*0.3;
			dividend3 = income*0.2;	
		}else {
			dividend1 = income*1;
			dividend2 = income*0;
			dividend3 = income*0;
		}
		
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

<h2>14-7</h2>
<h3>나의 앱 만들기_배열</h3>

args는 String 자료를 여러 개 담을 수 있는 문자열 배열이다. 배열은 같은 자료형을 여러 개 담을 수 있는 객체이다. 배열은 데이터 타입 옆에 대괄호[]를 붙여서 표현하고, 인스턴스를 만들 때는 배열의 길이를 지정하여 생성한다. 배열 내의 데이터는 인덱스를 이용하여 접근할 수 있고 인덱스는 0부터 시작한다.

<pre><code>
public class AccountingArrayApp {

	public static void main(String[] args) {
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate=0.3;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply+vat;
		double expense = valueOfSupply*expenseRate;
		double income = valueOfSupply - expense;
				
		double[] dividendRates = new double[3];
		dividendRates[0]=0.5;
		dividendRates[1]=0.3;
		dividendRates[2]=0.2;
		
		double dividend1=income*dividendRates[0];
		double dividend2=income*dividendRates[1];
		double dividend3=income*dividendRates[2];

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

<h2>14-8</h2>
<h3>나의 앱 만들기_반복문</h3>
반복문은 조건이 참인 한, 해당되는 구간을 계속 반복한다. 배열과 반복문을 함께 이용하면 프로그램을 훨씬 간결하게 만들 수 있다. While문은 괄호 안의 조건이 참인 한 블록 내의 작업을 계속 반복한다.
<pre><code>
public class AccountingArrayApp {

	public static void main(String[] args) {
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate=0.3;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply+vat;
		double expense = valueOfSupply*expenseRate;
		double income = valueOfSupply - expense;


		System.out.println("Value of supply: "+valueOfSupply);
		System.out.println("VAT: "+vat);
		System.out.println("Total: "+total);
		System.out.println("Expense: "+expense);
		System.out.println("Income: "+income);
		
		double[] dividendRates = new double[3];
		dividendRates[0]=0.5;
		dividendRates[1]=0.3;
		dividendRates[2]=0.2;
		
		int i=0;
		while(i<dividendRates.length) {
			System.out.println("Dividend1: "+ (income*dividendRates[i]));
			i=i+1;
		}
	}
}
</code></pre>

<h2>14-9</h2>
<h3>나의 앱 만들기_메소드</h3>


<pre><code>
public class AccountingMethodApp {
	
	public static double vauleOfSupply;
	public static double vatRate;
	public static double expenseRate;

	public static void main(String[] args) {
		
		vauleOfSupply = 10000;
		vatRate = 0.1;
		expenseRate = 0.3;
		
		print();

	}

	public static void print() {
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ getVAT() );
		System.out.println("Total : "+ getTotal() );
		System.out.println("Expense : "+ getExpense() );
		System.out.println("Income : "+ getIncome() );
		System.out.println("Dividend : "+ getDividend1() );
		System.out.println("Dividend : "+ getDividend2() );
		System.out.println("Dividend : "+ getDividend3() );
	}

	public static double getDividend1() {
		return getIncome() * 0.5;
	}
	
	public static double getDividend2() {
		return getIncome() * 0.3;
	}
	
	public static double getDividend3() {
		return getIncome() * 0.2;
	}

	public static double getIncome() {
		return vauleOfSupply-getExpense();
	}

	public static double getExpense() {
		return vauleOfSupply*expenseRate;
	}

	public static double getTotal() {
		return vauleOfSupply+getVAT();
	}

	private static double getVAT() {
		return vauleOfSupply*vatRate;
	}
}
</code></pre>

<h2>14-10</h2>
<h3>나의 앱 만들기_클래스</h3>

클래스는 서로 연관된 변수와 메소드를 그룹핑한 것이다. 
<pre><code>
class Accounting{
	public static double vauleOfSupply;
	public static double vatRate;
	public static double expenseRate;
	public static void print() {
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ getVAT() );
		System.out.println("Total : "+ getTotal() );
		System.out.println("Expense : "+ getExpense() );
		System.out.println("Income : "+ getIncome() );
		System.out.println("Dividend : "+ getDividend1() );
		System.out.println("Dividend : "+ getDividend2() );
		System.out.println("Dividend : "+ getDividend3() );
	}
	
	public static double getDividend1() {
		return getIncome() * 0.5;
	}
	
	public static double getDividend2() {
		return getIncome() * 0.3;
	}
	
	public static double getDividend3() {
		return getIncome() * 0.2;
	}

	public static double getIncome() {
		return vauleOfSupply-getExpense();
	}

	public static double getExpense() {
		return vauleOfSupply*expenseRate;
	}

	public static double getTotal() {
		return vauleOfSupply+getVAT();
	}

	private static double getVAT() {
		return vauleOfSupply*vatRate;
	}
	
}
public class AccountingClassApp {
	
	public static void main(String[] args) {
		
		Accounting.vauleOfSupply = 10000;
		Accounting.vatRate = 0.1;
		Accounting.expenseRate = 0.3;
		Accounting.print();
		//anotherVariable =...;
		//anotherMethod = ...;
	}
}
</code></pre>

<h2>14-10</h2>
<h3>나의 앱 만들기_클래스</h3>

인스턴스는 하나의 클래스를 복제해서 서로 다른 데이터의 값과 서로 같은 메소드를 가진 복제본을 만드는 것이다.
<pre><code>
class Accounting{
	public double vauleOfSupply;
	public double vatRate;
	public double expenseRate;
	public void print() {
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ getVAT() );
		System.out.println("Total : "+ getTotal() );
		System.out.println("Expense : "+ getExpense() );
		System.out.println("Income : "+ getIncome() );
		System.out.println("Dividend : "+ getDividend1() );
		System.out.println("Dividend : "+ getDividend2() );
		System.out.println("Dividend : "+ getDividend3() );
	}
	
	public double getDividend1() {
		return getIncome() * 0.5;
	}
	
	public double getDividend2() {
		return getIncome() * 0.3;
	}
	
	public double getDividend3() {
		return getIncome() * 0.2;
	}

	public double getIncome() {
		return vauleOfSupply-getExpense();
	}

	public double getExpense() {
		return vauleOfSupply*expenseRate;
	}

	public double getTotal() {
		return vauleOfSupply+getVAT();
	}

	private double getVAT() {
		return vauleOfSupply*vatRate;
	}
	
}
public class AccountingClassApp {
	
	public static void main(String[] args) {
		
		Accounting a1 = new Accounting();
		a1.vauleOfSupply = 10000.0;
		a1.vatRate = 0.1;
		a1.expenseRate = 0.3;
		a1.print();	
		
		Accounting a2 = new Accounting();
		a1.vauleOfSupply = 20000.0;
		a1.vatRate = 0.05;
		a1.expenseRate = 0.2;
		a2.print();
		
	}
}
</code></pre>

<h1>boostcorse 쉽게 배우는 자바2<h1>
<h2>1</h2>
<h3>수업소개</h3>

프로그램이란, 컴퓨터에게 우리가 원하는 작업들을 시간 순서대로 진행하도록 명령하는 것. 조건에 따라서 실행할 작업의 순서를 제어하는 조건문이 필요하다. 같은 작업을 여러 번 반복할 경우 사용되는 것이 반복문이다. 즉 조건문과 반복문을 위해서는 조건을 구성해야 한다. 조건을 구성하기 위해서 자바에서는 Boolean 데이터 타입과 비교 연산 기능을 제공한다.

<h2>2</h2>
<h3>Boolean Datatype</h3>

boolean 데이터 타입은 참과 거짓을 표현하는 데이터 타입으로 true와 false 키워드를 이용하여 직접 입력할 수도 있고 메소드의 리턴 값이나 비교 연산으로 도출할 수 있다. boolean 데이터 타입은 콘솔에서 출력해보면 true, false로 출력된다는 것을 알 수 있다. 그리고 문자열 객체의 contains 메소드와 같이 결과값이 boolean 데이터 타입인 경우, 또는 비교 연산자를 이용해서 계산하는 경우에도 boolean 데이터 타입을 다루게 된다.

<pre><code>
ublic class BooleanApp {
	
	public static void main(String[] args) {
		
		System.out.println("One"); //One
		System.out.println(1); //1
		System.out.println(true); //true
		System.out.println(false); //false
		
		String foo = "Hello world";
		// String true = "Hello world" //reserved word 
		
		System.out.println(foo.contains("world")); //true
		System.out.println(foo.contains("egoing")); //false
	}
}
</code></pre>

<h2>3</h2>
<h3>비교연산자</h3>

비교연산자는 값의 대소, 같음을 비교하는 연산자이다. 
* a > b : a가 b보다 큼
* a < b : a가 b보다 작음
* a >= b : a가 b보다 크거나 같음
* a <= b : a가 b보다 작거나 같음
* a == b : a가 b와 같음
* a != b : a가 b와 같지 않음 
설명에 해당하는 진술이 참이라면 true, 아니라면 false를 산출한다.

<pre><code>
public class ComparisonOperatorApp {

	public static void main(String[] args) {
		
		System.out.println(1 > 1); //false
		System.out.println(1 == 1); //true
		System.out.println(1 < 1); //flase
		System.out.println(1 >= 1); //true
	}
}
</code></pre>

<h2>4-1</h2>
<h3>조건문 형식</h3>

if문 구성요소
* if - 필수 구성 요소 
* 조건식 - 필수 구성 요소, 조건식엔 boolean 타입만 들어갈 수 있다
* 코드블럭(실행할 코드)
* else if
* else
조건문은 중첩할 수 있고, if와 else는 하나의 조건문에 한 번만 들어갈 수 있지만, else if는 여러 개가 들어갈 수 있다.

<pre><code>
public class IfApp {

	public static void main(String[] args) {
		
		System.out.println("a");
		if(flase) {
			System.out.println(1);
		} else if(true) { 
			System.out.println(2);
		} else {
			System.out.println(3);
			}
		
		System.out.println("b");
	}
}
</code></pre>

<h2>4-2</h2>
<h3>조건문 응용1</h3>

<pre><code>
public class AuthApp {
	
	public static void main(String[] args) {

		String id = "egoing";
		String inputId = args[0];
		
		System.out.println("Hi.");
		
		//if(inputId == id) {
		if(inputId.equals(id)) {
			System.out.println("Master!");
		} else {
			System.out.println("Who are you?");
		}
		}
	}
}
</code></pre>

<h2>4-3</h2>
<h3>조건문 응용2</h3>

boolean 데이터를 연산하기 위해서는 조건 연산자를 사용한다. 조건 연산자는 &&(and), ||(or)가 있다. && 연산자는 전항과 후항이 모두 참일 경우에만 참을 반환하고, 아니면 거짓을 반환한다. || 연산자는 전항과 후항 중 하나라도 참일 경우에 참을 반환하고, 모두 거짓일 때만 거짓을 반환한다. && 연산자는 || 연산자보다 우선순위가 높다.
<pre><code>
public class AuthApp {
	
	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "1111";
		String inputPass = args[1];
		
		System.out.println("Hi.");
		
		//if(inputId == id) {
//		if(inputId.equals(id)) {
//			if(inputId.equals(pass)) {
//				System.out.println("Master!");
//			} else {
//				System.out.println("Wrong password!");
//			}
//		} else {
//			System.out.println("Who are you?");
//		}
		
		if(inputId.equals(id) && inputPass.equals(pass)) {
			if(inputId.equals(pass)) {
				System.out.println("Master!");
		} else {
			System.out.println("Who are you?");
		}
		
	}
}
}
}
</code></pre>

<h2>5</h2>
<h3>== vs equals</h3>

원시 데이터 타입과 클래스   
원시 데이터 타입 
* boolean
* byte
* char
* short
* int
* long 
* float
* double   
원시 데이터 타입의 변수는 선언되면 메모리(Stack)에 공간이 할당되며, 그 메모리 공간 안에 실제 값이 들어가게 된다. 원시 데이터의 경우 == 연산자는 변수가 가리키는 값을 토대로 비교하게 된다.   
반면 모든 클래스들은 원시 데이터 타입이 아니다. 클래스는 new 키워드를 통한 인스턴스가 만들어지는 시점에 또다른 메모리 구역(Heap)에서 새로운 공간을 할당하여 값을 저장하고 변수는 그 값이 저장된 메로리의 주소를 가리키게 된다. 그래서 인스턴스 간 == 연산자를 이용할 경우 그 메모리의 주소를 비교하게 된다.   
한편 문자열 리터럴과 같은 방식으로 문자열을 생성할 때, 이미 같은 문자열을 생성한 적이 있다면 새로 메모리 공간을 할당하지 않고, 새로운 변수는 기존의 문자열이 저장된 메모리(String Pool(Heap))의 주소를 가리키게 된다. 이러한 경우는 == 연산자를 이용하였을 때 같은 주소를 가리키고 있기 때문에 true가 나오게 된다. 

<h2>6</h2>
<h3>논리연산자</h3>

<pre><code>
public class LogicalOperatorApp {

	public static void main(String[] args) {
		
		System.out.println(1 == 1);
		
		//And
		System.out.println(true && true); //true
		System.out.println(true && false); //false
		System.out.println(false && true); //false
		System.out.println(false && false); //false
		
		//Or
		System.out.println(true || true); //true
		System.out.println(true || false); //true
		System.out.println(false || true); //true
		System.out.println(false || false); //false
		
		//not
		System.out.println(!true); //false
		System.out.println(!false); //true
	}

}
</code></pre>

<pre><code>
public class AuthApp2 {
	
	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "1111";
		String pass2 = "2222";
		String inputPass = args[1];
		
		System.out.println("Hi.");

		boolean isRightpass = inputPass.equals(pass) || inputPass.equals(pass2);
		if(inputId.equals(id) && isRightpass) {
			if(inputId.equals(pass)) {
				System.out.println("Master!");
		} else {
			System.out.println("Who are you?");
		}
		
	}
}
}
</code></pre>

<h2>7-1</h2>
<h3>반복문</h3>

조건에 따라 특정한 작업을 반복하게 하는 제어문을 반복문이라고 한다.   
**while문**   
while문은 조건식이 참일 동안에 코드블럭의 작업을 반복한다. 조건식에 true를 입력할 경우 조건이 항상 참이기 때문에 무한으로 반복하게 된다.
**for문**   
for문은 조건식이 3개의 부분으로 나뉘어져 있다.   
* 1. 변수의 초기화
* 2. 조건식
* 3. 1회 반복을 끝내고 수행할 연산
각각의 부분은 세미콜론으로 구분되어 있다. 변수의 초기화는 for문이 시작될 때 한번만 수행되고, 조건식이 참일 경우에만 반복한다. 1회 반복이 끝나면 (}부분) 지정한 연산을 처리하고 다시 조건식을 확인하여 반복작업을 실행한다. 변수의 초기화 부분에서 변수를 새로 선언했다면, 그 변수는 for문 안에서만 존재하고 for문을 벗어나면 사라진다.

<pre><code>
public class LoopApp {

	public static void main(String[] args) {
		
		System.out.println(1);
		
		System.out.println("===while===");
		int i = 0;
		while(i < 3) {
			System.out.println(2);
			System.out.println(3);
//			i = i + 1;
			i++;
		}
		System.out.println("===for===");
		for(int j =0; j < 3; j++) {
			System.out.println(2);
			System.out.println(3);
		}
		
		System.out.println(4);
	}
}
</code></pre>

<h2>7-2</h2>
<h3>배열</h3>

배열을 선언할 때는 변수 타입명 뒤에 빈 [] 대괄호를 입력하고 변수 이름을 입력한다. 초기화를 할 경우엔 new 키워드를 이용하여 [] 대괄호 안에 요소의 개수를 입력한다. 또는 리터럴로 입력할 수 있는 데이터 타입의 경우, {} 중괄호 안에 요소를 리터럴로 입력할 수 있다. 배열은 인덱스를 통해 접근하고 인덱스는 [] 대괄호 안에 입력한다.
<pre><code>
public class ArrayApp {

	public static void main(String[] args) {
		
		String[] users = new String[3];
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		
		System.out.println(users[1]); //jinhuck
		System.out.println(users.length); //3
		
		int[] scores = {10, 100, 100};
		System.out.println(scores[1]); //100
		System.out.println(users.length); //3
		
	}
}
</code></pre>

<h2>7-3</h2>
<h3>반복문 + 배열</h3>
length 필드는 배열의 요소 개수를 담고 있는 필드이다. 조건식에서 이 필드를 이용하게 되면 직접 배열의 요소 개수를 입력하지 않아도 프로그램을 실행할 때마다 달라질 수 있는 요소의 개수를 반영하여 반복문을 돌릴 수 있다.
<pre><code>
public class LoopArray {

	public static void main(String[] args) {

		String[] users = new String[3];
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		
		for(int i=0; i<users.length; i++) {
			System.out.println("<li>"+users[i]+"</li>");
		}

	}

}
</code></pre>

<h2>8-1</h2>
<h3>종합응용1</h3>
break문은 더 이상 현재 반복문을 진행하지 않고 빠져나오게 하는 구문이다. 배열에 요소들이 더 남아 있다고 할지라도 break문을 만나면 더 이상 추가적인 연산을 수행하지 않고 현재 반복문의 코드블럭 밖으로 빠져나온다.
<pre><code>
public class AuthApp3 {

	public static void main(String[] args) {
		
		String[] users = {"egoing", "jinhuck", "youbin"};
		String inputId = args[0];
		
		boolean isLogined = false;
		for(int i=0; i<users.length; i++) {
			String currentId = users[i];
			if(currentId.equals(inputId)) {
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

<h2>8-2</h2>
<h3>종합응용2</h3>
<pre><code>
public class AuthApp3 {

	public static void main(String[] args) {
		
		String[][] users = {
				{"egoing", "1111"},
				{"jinhuck", "2222"},
				{"youbin", "3333"}
				
		};
		String inputId = args[0];
		String inputPass = args[1];
		
		boolean isLogined = false;
		for(int i=0; i<users.length; i++) {
			String[] current = users[i];
			if(current.equals(inputId) && current.equals(inputPass)) {
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

<h2>JAVA 메소드 2</h2>
<h3>이미 익숙한 메소드</h3>
Math 클래스의 floor 메소드는 double형 자료형을 받아서 올림 연산을 수행하여 double형으로 반환한다. main 메소드는 특수한 메소드로, 클래스를 실행할 때 어떠한 명령을 내리지 않아도 main 메소드를 실행한다.
<pre><code>
public class FirstMethod {

	public static void main(String[] args) {
		
		System.out.println("Hello Method"); //Hello Method
		System.out.println(Math.floor(1.1)); //1
	}
}
</code></pre>

<h2>JAVA 메소드 3</h2>
<h3>메소드의 기본 형식</h3>

메소드의 필요성   
쉽게 같은 코드를 재사용하고, 유지보수를 쉽게 할 수 있다.
<pre><code>
public class WhyMethod {
	public static void printTwoTimesA(){
		System.out.println("-"); 
		System.out.println("a"); 
		System.out.println("a"); 
	}

	public static void main(String[] args) {
		
		printTwoTimesA();
		printTwoTimesA();
		printTwoTimesA();
	}
}
</code></pre>

<h2>JAVA 메소드 4</h2>
<h3>메소드의 입력</h3>
파라미터와 아규먼트   
매개변수(파라미터)는 메소드 안에서 통용되는 변수이다. 메소드를 호출할 때는 실제 데이터를 메소드의 파라미터 안에 넣게 되는데, 이를 인자(아규먼트)라고 한다. main 메소드는 문자열 배열인 args 파라미터를 이용한다. 프로그램을 실행할 때 아규먼트로 주어지는 값을 넣게 되면 args에 아규먼트 값들이 들어가게 되고, 이를 이용해서 작업을 실행하게 된다.
<pre><code>
public class WhyMethod {

	public static void main(String[] args) {
					  //인자, argument
		printTwoTimes("a","-");
		printTwoTimes("a","*");
		printTwoTimes("a","&");
		printTwoTimes("b","!");
	}
									//매개변수, parameter 
	public static void printTwoTimes(String text, String delimiter){
		System.out.println(delimiter); 
		System.out.println(text); 
		System.out.println(text); 
	}
}
</code></pre>

<h2>JAVA 메소드 5</h2>
<h3>메소드의 출력</h3>

**값을 반환하는 메소드**   
두 메소드에서 사용하는 문자열을 구성하는 메소드를 만들어서 그것을 이용하게 한다면 콘솔에 출력하거나 파일에 출력하거나 문자열 구성은 한 번만 실행하지 않을까? 그렇게 하기 위해선 메소드가 문자열 객체를 반환하도록 한다.   
메소드가 데이터를 반환하도록 만들기 위해선 몇 가지 구성 요소가 필요하다.   
* 반환되는 데이터의 타입
* return   
반환되는 데이터의 타입은 메소드의 이름 앞에 넣어서 이 메소드가 그 데이터 타입을 반환한다는 것을 명시한다. 만약 메소드가 아무것도 반환하지 않는다면 void를 넣어 둔다. 그리고 우리가 작업을 처리한 후 반환하고자 하는 데이터를 'return 반환값' 형식으로 입력하여 메소드가 데이터를 반환하도록 한다. 그리고 return이 실행된 후에는 그 뒤에 실행한 코드가 메소드에 남아 있어도 더 처리하지 않고 바로 메소드로 빠져 나온다.

<pre><code>
public class OutputMethod {

	public static String a(){
		return "a";
	}

	public static String one(){
		return 1;
	}

	public static void main(String[] args) {
		System.out.println(a());
		System.out.println(one());
	}
}
</code></pre>
<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class WhyMethod {
	public static void main (String[] args) throws IOException {

		System.out.println(twoTimes("a", "-"));
		FileWriter fw = new FileWriter("out.txt");
		fw.write(twoTimes("a", "*"));
		fw.close();
	}
	public static String twoTimes(String text, String delimiter){
		String out = "";
		out = out + delimiter + "\n";
		out = out + text + "\n";
		out = out + text + "\n";
		return out;
		}
}
</code></pre>

<h2>JAVA 메소드 6</h2>
<h3>메소드의 기본 활용</h3>

<pre><code>
public class AccountingApp {
	public static void main(String[] args){
		double valueOfSupply = 10000.0;
		double vatRate = 0.1;
		double vat = valueOfSupply * vatRate;
		double total = valueOfsupply + vat;

		System.out.println("Value of supply:"+valueOfSupply);
		System.out.println("VAT:"+vat);
		System.out.println("Total:"+total);
	}
}
</code></pre>
공급가와 부가가치세율은 모든 메소드에서 바로 접근할 수 있게 클래스의 static 필드로 빼내었다.    
메소드 안에서 메소드를 호출할 수 있다. main 메소드 안에서 여러 메소드를 호출할 수 있었던 것처럼 우리가 만든 메소드도 다른 메소드를 호출할 수 있다. 이렇게 메소드를 이용해서 만든 코드는 지금의 예시에서는 큰 차이가 존재하진 않지만 재사용성이 훨씬 높아진다.
<pre><code>
public class AccountingApp {
	
		double valueOfSupply = 10000.0;
		double vatRate = 0.1;

		public static double getVAT(){
			return valueOfSupply*vatRate;
		}

		public static double getTotal(){
			return valueOfSupply + getVAT();
		}
		public static void main(String[] args){
		System.out.println("Value of supply:"+valueOfSupply);
		System.out.println("VAT:"+vat);
		System.out.println("Total:"+total);
	}
}
</code></pre>

<h2>JAVA 메소드 7</h2>
<h3>수업을 마치며</h3>
클래스는 비슷한 연관된 일을 하는 메소드와 변수들을 묶어 그룹으로 만든 것이다. 이러한 클래스를 틀로 하여 실제로 프로그램에서 동작하는 객체들을 인스턴스라고 한다. 이러한 객체를 뼈대로 해서 프로그램을 만들어 가는 방식을 객체 지향 프로그래밍(OOP, Object Oriented Programming)이라고 한다. 
<pre><code>
</code></pre>

<h2>JAVA 메소드 8, 9</h2>
<h3>부록</h3>
public은 동작을 제어하기 위해 바깥으로 드러나서 호출할 수 있는 것들을 위해 지정한다.
private은 동작을 위해 꼭 필요하지만, 외부에서 굳이 알 필요도 없거나 알아서는 안 되는 것들을 위해서 지정.
<pre><code>
public class AccessLevelModifiersMethod {

	private static void hi() {
		System.out.println("Hi");
	}
	public static void main(String[] args) {
		hi();
	}

}
</code></pre>

클래스는 일종의 형틀이고, 인스턴스는 그 형틀로 찍어서 만든 실체.   

클래스는 프로그램에서 한번 정의되는 형틀이다. 즉 여러 개 가질 수 없는 유일무이한 메소드.   

반면 static이 아닌 메소드는 인스턴스의 메소드로, 프로그램 안에서 여러 개 있을 수 있고, 그 인스턴스를 통해서 접근하는 메소드이다.

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
//      Print.a("-");
//      Print.b("-");
         
        // instance
        Print t1 = new Print();
        t1.delimiter = "-";
        t1.a();
        t1.b();
        Print.c("$");
         
         
//      Print.a("*");
//      Print.b("*");
         
        Print t2 = new Print();
        t2.delimiter = "*";
        t2.a();
        t2.b();
    }
     
 
}
</code></pre>

<h2>JAVA 객체지향 프로그래밍 1</h2>
<h3>수업소개</h3>
클래스를 이용해서 프로그램의 구조를 만들어 가는 방식을 객체 지향 프로그래밍(Object Oriented Programming)이라 함. 이러한 방식을 언어 차원에서 지원하는 프로그래밍 언어를
객체 지향 언어(Object Oriented Language)라고 부름.

<h2>JAVA 객체지향 프로그래밍 2</h2>
<h3>남의 클래스 남의 인스턴스</h3>

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

<h2>JAVA 객체지향 프로그래밍 3</h2>
<h3>변수와 메소드</h3>

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

<h2>JAVA 객체지향 프로그래밍 4-1</h2>
<h3>클래스(존재 이유와 기본형식)</h3>
클래스는 관련있는 변수들과 메소드를 묶어서 정리정돈을 할 수 있게 함. 구분자로 분리된 A 문자열과 B 문자열을 출력하는 메소드를 Print라는 클래스로 따로 떼어내서 만들 수 있게 됨. 굳이 메소드의 이름을 printA라고 적지 않고 A라고만 적어도 Print 객체의 A 메소드이기 때문에 A를 출력한다는 의미를 쉽게 유추할 수 있게 됨.

<h2>JAVA 객체지향 프로그래밍 4-2</h2>
<h3>클래스(형식)</h3>
클래스는 한 파일에 여러 개를 넣을 수 있지만, 접근제어자 public은 java 파일과 같은 이름의 클래스에 하나만 붙일 수 있다. 한 파일 안에 여러 클래스가 등장할 수도 있지만
여러 클래스를 각각 하나의 java 파일로 만들게 되면, 프로그램의 기능별로 쪼개어서 소스 코드를 별도로 저장할 수 있게 됨.
<pre><code>
</code></pre>

<h2>JAVA 객체지향 프로그래밍 5</h2>
<h3>인스턴스</h3>
클래스는 어떠한 형틀이고, 인스턴스는 그 형틀로 찍어낸 실체와도 같은 것.
그래서 클래스를 바꾸면 그것으로 찍어낸 모든 사물들이 다른 형태를 갖게 되고
형틀로 찍어낸 사물을 바꾸면 그 사물의 자매와도 같은 다른 사물에는 어떠한 영향도 없음.
즉 객체를 인스턴스로 만들면, 그 인스턴스를 바꾼다고 해도 다른 인스턴스에는 영향을 끼치지 않게 됨.
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

<h2>JAVA 객체지향 프로그래밍 6</h2>
<h3>static</h3>
static 변수와 메소드는 클래스에서 생성된 모든 인스턴스가 공유하는 자원이다. 인스턴스를 만들지 않고도 클래스에서 직접 호출할 수 있다.
<pre><code>
class Foo{
    public static String classVar = "I class var";
    public String instanceVar = "I instance var";
    public static void classMethod() {
        System.out.println(classVar);   //Ok
//      System.out.println(instanceVar);   //Error
    }
    public void instanceMethod() {
        System.out.println(classVar);   //Ok
        System.out.println(instanceVar);   //Ok
    }
}
public class StaticApp {
 
    public static void main(String[] args) {
        System.out.println(Foo.classVar);    //OK
//      System.out.println(Foo.instanceVar);    //Error
        Foo.classMethod();
//      Foo.instanceMethod();
         
        Foo f1 = new Foo();
        Foo f2 = new Foo();
//      
        System.out.println(f1.classVar);    //I class var
        System.out.println(f1.instanceVar);    //I instance var
//      
        f1.classVar = "changed by f1";
        System.out.println(Foo.classVar);    //changed by f1
        System.out.println(f2.classVar);     //changed by f1
//      
        f1.instanceVar = "changed by f1";
        System.out.println(f1.instanceVar);    //changed by f1
        System.out.println(f2.instanceVar);    //I instance var
    }
 
}
</code></pre>
static 변수와 메소드는 해당 클래스로 생성된 모든 인스턴스가 공유하는 자원이기 때문에
인스턴스 모두는 같은 static 변수와 메소드를 사용할 수 있음. static이 아닌 변수와 메소드는 인스턴스마다 고유의 값을 가지기 때문에 인스턴스에서 변경한다고 해도 다른 인스턴스에 어떠한 영향도 끼치지 않음.


<h2>JAVA 객체지향 프로그래밍 7</h2>
<h3>생성자와 this</h3>
<pre><code>
class Print {
	public String delimiter = "";
	public Print(String delimiter) {
		this.delimiter = delimiter;
	}
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
        Print p1 = new Print("----");
        p1.A();
        p1.A();
        p1.B();
        p1.B();
 
        Print p2 = new Print("****");
        p2.A();
        p2.A();
        p2.B();
        p2.B();
         
         
        p1.A();
        p2.A();
        p1.A();
        p2.A();
    }
}
</code></pre>
클래스는 인스턴스를 생성할 때 클래스의 이름과 같은 이름인 생성자로 인스턴스를 만든다.
클래스는 따로 만들어 주지 않아도 기본 생성자를 포함하고 있는데, Print()와 같이 아무것도 지정하지 않는 생성자를 기본 생성자라고 한다. 기본적으로 public 권한으로 설정되어 있어서 따로 명시하지 않아도 클래스를 만들게 되면 새로운 인스턴스를 생성할 수 있도록 만든다.   
 
만약 처음에 인스턴스를 생성할 때부터 필드를 초기화하고 싶다면, 필드를 초기화할 수 있게 만드는 생성자를 구성할 수 있다. 생성자는 접근 권한을 설정할 수 있고, 리턴 타입은 명시하지 않으며, 초기화할 필드에 따라 파라미터를 설정한다.   

생성자도 클래스 내부의 메소드이고, 보통 초기화할 필드를 파라미터로 넣기 때문에
생성자 내부에서 필드에 접근할 때 파라미터의 이름과 같게 되어 접근하기 어렵게 된다.
이 때 사용하는 예약어가 this인데, this는 인스턴스를 가리키는 예약어임.
this를 통해 필드를 손쉽게 사용할 수 있다.

<h2>JAVA 객체지향 프로그래밍 8-1</h2>
<h3>활용(클래스화)</h3>
<pre><code>
class Accounting{
    public static double valueOfSupply;
    public static double vatRate = 0.1;
    public static double getVAT() {
        return valueOfSupply * vatRate;
    }
    public static double getTotal() {
        return valueOfSupply + getVAT();
    }
}
public class AccountingApp {
    public static void main(String[] args) {
        Accounting.valueOfSupply = 10000.0;
        System.out.println("Value of supply : " + Accounting.valueOfSupply);
        System.out.println("VAT : " + Accounting.getVAT());
        System.out.println("Total : " + Accounting.getTotal());
  
    }
}
</code></pre>

<h2>JAVA 객체지향 프로그래밍 8-2</h2>
<h3>활용(인스턴스화)</h3>
<pre><code>
class Accounting{
    public double valueOfSupply;
    public static double vatRate = 0.1;
    public Accounting(double valueOfSupply) {
        this.valueOfSupply = valueOfSupply;
    }
    public double getVAT() {
        return valueOfSupply * vatRate;
    }
    public double getTotal() {
        return valueOfSupply + getVAT();
    }
}
public class AccountingApp {
    public static void main(String[] args) {
        Accounting a1 = new Accounting(10000.0);
         
        Accounting a2 = new Accounting(20000.0);
         
        System.out.println("Value of supply : " + a1.valueOfSupply);
        System.out.println("Value of supply : " + a2.valueOfSupply);
         
        System.out.println("VAT : " + a1.getVAT());
        System.out.println("VAT : " + a2.getVAT());
         
        System.out.println("Total : " + a1.getTotal());
        System.out.println("Total : " + a2.getTotal());
         
  
    }
}
</code></pre>
인스턴스를 이용하면, 각각의 인스턴스는 서로에게 영향을 미치지 않기 때문에
독립적으로 작업을 처리하게 만들 수 있다.
여기에 인스턴스의 이름까지 상황에 걸맞은 이름을 붙여 준다면 이해하기 쉬움.

<h2>JAVA 객체지향 프로그래밍 9</h2>
<h3>수업을 마치며</h3>
어떤 클래스와 비슷한 다른 것을 만들고 싶을 때 가능한 2가지 방법이 있음. 어떤 클래스의 변수와 메소드들을 모두 복사해서 만드는 방법과 상속이라는 개념을 이용하는 방법.
어떤 클래스를 상속해서 새로운 클래스를 만들게 되면, 어떤 클래스의 모든 변수와 메소드들이 기본적으로 새로운 클래스에 포함되게 되고, 만약 부족하다면 기존의 변수와 메소드를 덮어쓰거나, 아예 새로운 변수와 메소드를 추가할 수도 있다.
 
그리고 인터페이스는 일종의 규격과도 같은 것이다. 인터페이스도 마찬가지로, 앞으로 어떤 클래스를 만들지는 전혀 모르지만, 그 클래스에 대한 규격을 선언하는 것.


<h2>JAVA 상속 1</h2>
<h3>수업소개</h3>
두 개의 클래스를 만들어야 할 일이 있는데 한 클래스가 다른 클래스의 기능들을 모두 포함하는 형태라면 모두 복사해서 일일이 넣는 것이 아니라 상속의 기능을 활용.
<pre><code>
class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
}
class Cal3 extends Cal{
	
}
...
public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));
	}

}
</code></pre>

<h2>JAVA 상속 2</h2>
<h3>기능의 개선과 발전</h3>
<pre><code>
class Cal3 extends Cal{
	
	public int sum(int v1, int v2) {
		System.out.println("Cal3!!!");
		return v1 + v2;
	}

	public int minus(int v1, int v2) {
		return v1 - v2;
	}
}
</code></pre>

<h2>JAVA 상속 3</h2>
<h3>Overriding, Overloading</h3>
오버로딩은 상속과는 직접적인 관련이 없음. 특정 이름을 지닌 메소드가 있다고 할지라도 우리는 같은 이름을 가진 메소드를 또 만들 수 있다. 다만 파라미터의 형식이 달라야 함.
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
이렇게 같은 이름을 가진 메소드라고 해도, 메소드를 호출할 때는 파라미터의 형식도 모두 보기 때문에 프로그램은 각각의 메소드가 서로 애매하다고 판단하지 않는다.
반면 overriding은 같은 클래스 안에서는 이뤄질 수 없고,
상속 관계를 가진 클래스 사이에서 이뤄질 수 있다.

<h2>JAVA 상속 4</h2>
<h3>This Super</h3>
this는 인스턴스를 가리키는 키워드.
이와 비슷하게 부모 클래스를 가리키는 super라는 키워드도 존재.
자식 클래스에서 super를 이용하여 접근 권한이 부여된 부모 클래스의 변수와 메소드에 접근할 수 있다.
<pre><code>
class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
	// Overloading
	public int sum(int v1, int v2, int v3) {
		return this.sum(v1, v2) + v3;
	}
}
class Cal3 extends Cal{
	// Overriding
	public int sum(int v1, int v2) {
		System.out.println("Cal3!!!");
		return super.sum(v1, v2);
	}

	public int minus(int v1, int v2) {
		return v1 - v2;
	}
}
</code></pre>

<h2>JAVA 상속 5</h2>
<h3>상속과 생성자</h3>
부모 클래스에 생성자가 있는 경우에 자식 클래스의 생성자는 자식 클래스에 이미 해당하는 생성자가 만들어져 있다면 그것을 호출하겠지만, 그렇지 않다면 암묵적으로 부모 클래스의 생성자(super())를 호출하게 된다.
하지만 상속관계에 있는 클래스의 생성자에 기본 생성자(인자가 전혀 없는 생성자)가 아닌 
인자가 포함된 생성자를 사용하는 경우 주의 필요.

<pre><code>
class Cal{
    int v1,v2;
    Cal(int v1, int v2){
        System.out.println("Cal init!!");
        this.v1 = v1; this.v2 = v2;
    }
    public int sum(){return this.v1+v2;}
}

// Compile Error
class Cal3 extends Cal{
    
    public int minus(){return this.v1-v2;}
}
</code></pre>
위와 같이 부모 클래스에 기본 생성자가 아닌 인자를 주는 생성자만 명시된 경우,
자식 클래스에서 생성자를 명시적으로 만들지 않는다면 컴파일이 되지 않는다. 자식 클래스에서 생성자를 호출하는 경우(인스턴스 생성), 정의한 생성자가 없기 때문에 부모 클래스의 생성자(super())를 사용해야 하는데, 명시적으로 인자를 받는 생성자만 부모 클래스에 만들어져 있기 때문에 기본 생성자가 없는 것으로 받아들여지기 때문.

자식 클래스의 경우에도, 기본 생성자는 명시적으로 만들지 않고,
인자를 받는 생성자만 만들었을 경우에는 인수를 주지 않고 인스턴스를 생성할 수 없다.
<pre><code>
class Cal{
    int v1,v2;
    
    public int sum(){return this.v1+v2;}
}
class Cal3 extends Cal{
	Cal3(int v1, int v2) {
		this.v1 = v1;
		this.v2 = v2;
        System.out.println("Cal3 init!!");
    }
    public int minus(){return this.v1-v2;}
}

public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
        Cal3 c3 = new Cal3(); // Compile Error
	}
}
</code></pre>
따라서 부모 클래스에 인자를 받는 생성자만 만들었을 경우에는,
다음과 같이 자식 클래스에도 인자를 받는 생성자를 만들어야 함.
<pre><code>
class Cal{
    int v1,v2;
    Cal(int v1, int v2){
        System.out.println("Cal init!!");
        this.v1 = v1; this.v2 = v2;
    }
    public int sum(){return this.v1+v2;}
}
class Cal3 extends Cal{
    Cal3(int v1, int v2) {
        super(v1, v2);
        System.out.println("Cal3 init!!");
    }
    public int minus(){return this.v1-v2;}
}
public class InheritanceApp {
    public static void main(String[] args) {
        Cal c = new Cal(2,1);
        Cal3 c3 = new Cal3(2, 1);
        System.out.println(c3.sum()); // 3
        System.out.println(c3.minus()); // 1
    }
}
</code></pre>

<h2>JAVA 상속 6</h2>
<h3>수업을 마치며</h3>

* 다형성(polymorphism)   
상속 관계에 있는 클래스간의 호환성을 높여주는 기능. 인스턴스를 생성할 때, 같은 클래스의 자료형을 가진 변수를 선언하여 인스턴스를 생성해왔지만, 부모 클래스의 자료형을 가진 변수를 선언하여 자식 클래스의 인스턴스를 생성할 수 있다. 그렇게 생성한 변수에서 자식 클래스의 변수나 메소드를 호출할 수 있다.

* 접근 제어자(access modifier)   
접근 제어자에는 이 외에도 default, protected라는 두 개의 접근 제어자가 더 있다.
default의 경우 같은 패키지 내의 클래스에서는 접근할 수 있는 권한이 있고, 
protected의 경우 해당 클래스와 자식 클래스를 통해서 접근할 수 있다.

* final 키워드   
상속과 관련하여 제한을 걸어주는 키워드.
만약 현재 클래스에서 더 이상 자식 클래스를 생성하지 못하게 막기 위해서는 
클래스에 final 키워드를 삽입한다. 메소드가 자식 클래스에서 더 이상 오버라이드 되기를 원하지 않는다면 메소드에 final 키워드를 삽입.

* abstract 키워드
해당 클래스, 메소드가 재정의가 필요하다는 것을 강제하는 키워드.
abstract 메소드는 선언만 되어 있는 상태이고, abstract 클래스는 인스턴스로 만들 수 없다. 만약 클래스 안에 abstract 메소드가 있다면 그 클래스는 abstract 클래스여야 한다.


<h2>JAVA 인터페이스 1</h2>
<h3>수업소개</h3>
인터페이스(Interface)를 이용하면 앞으로 만들 클래스의 메소드 규격을 선언할 수 있다.
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

<h2>JAVA 인터페이스 2</h2>
<h3>인터페이스의 형식</h3>
인터페이스의 이름은 클래스와 마찬가지로 보통 첫 글자를 대문자로 만들고, 
"~을 할 수 있는" 것들의 규격이라는 의미에서 형용사의 이름을 붙이기도 함.
클래스를 상속할 때는 하나의 클래스로부터 상속받을 수 있는 것과 대조적으로
인터페이스는 여러 개를 모두 적용할 수 있다.
이 경우 적용한 인터페이스들의 메소드를 모두 구현해야 한다.   
 
인터페이스에는 변수를 정의할 수도 있다.
다만 변수는 반드시 초기화되어야 한다.
인터페이스를 적용한 클래스는 변수를 다시 대입할 수 없다.
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
		RealCal c = new RealCal();
		System.out.println(c.sum(2, 1));
		c.print();
		System.out.println(c.PI);
	}

}
</code></pre>

<h2>JAVA 인터페이스 3</h2>
<h3>다형성</h3>
클래스의 인스턴스를 변수로 선언할 때, 해당 클래스의 데이터 타입으로 선언하지 않고
부모 클래스나 인터페이스를 데이터 타입으로 선언할 수도 있다.
이렇게 객체의 타입이 부모 클래스, 인터페이스, 자식 클래스 등 여러 형태인데도
인스턴스로 만든 객체(자식 클래스의 인스턴스)와 같이 행동하는 것을 다형성이라고 한다.
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

<h2>JAVA 인터페이스 4</h2>
<h3>사용설명서 속의 인터페이스</h3>
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

<h2>JAVA 인터페이스 5</h2>
<h3>수업을 마치며</h3>
클래스의 기능이 너무 많고 구획화를 할 필요가 있다면 
그 때 인터페이스를 이용해서 프로그램을 만든다. 다른 사람과 협업을 할 때, 서로 공통적으로 적용해야 할 규격이 있을 때도 인터페이스를 이용한다면 좋을 것.

<h2>JAVA 예외 1</h2>
<h3>수업소개</h3>

<h2>JAVA 예외 2</h2>
<h3>예외의 발생</h3>
예외가 발생하는 이유는 여러 경우가 있겠지만 프로그램이 실행하는 동안에
프로그램을 만들 사람들이 설계한 모양대로 운영되지 않았기 때문일 것임.
<pre><code>
public class ExceptionApp {
	public static void main(String[] args) throws ArithmeticException {
		System.out.println(1);
		System.out.println(2/0); // Run-Time Exception ArithmeticException
		System.out.println(3); 
	}
}
</code></pre>
자바에서는 숫자를 0으로 나누는 경우에 예외로 처리한다.
실제로 실행을 시켜보면 ArithmeticException이라고 알려주고, 0으로 나누었다는 설명도 나오게 된다.
나누는 숫자를 이 경우에는 직접 입력하여 구현하였지만, 
나누는 숫자를 인자로 받아서 프로그램을 구동하는 경우가 있을 수 있다.
사용자가 입력한 값에 따라서 나누는 숫자가 결정된다면
나누는 숫자가 0이 절대 아니라는 보장이 없다.

<h2>JAVA 예외 3</h2>
<h3>예외의 처리</h3>
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

<h2>JAVA 예외 4</h2>
<h3>예외의 우선순위</h3>
ArithmeticException도 Java API 문서를 참고하면,
RuntimeException으로부터 상속받은 클래스라는 것을 알 수 있다. RuntimeException은 Exception 클래스로부터 상속받은 클래스임.
그래서 여러 예외가 있더라도 Exception 클래스를 이용해서 포괄적으로 처리할 수 있다.
또한, 예외의 처리에 있어서 catch 문의 위치도 중요함.
try 문에서 발생한 예외는 여러 개의 catch 문을 순서대로 거쳐가면서 
해당 catch 문의 예외가 이번에 발생한 예외와 맞는지 확인한 후, 맞다면 그 catch 문을 실행한다.
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

<h2>JAVA 예외 5</h2>
<h3>e의 비밀</h3>
예외들의 인스턴스에는 예외가 발생한 원인, 어디서 발생했는지 등에 대한 정보들이 들어 있다. 이것들을 이용하면 프로그램의 어디서 왜 예외가 발생했는지 손쉽게 알 수 있다.
getMessage 메소드를 이용하면 예외 상황에 대한 디테일한 정보를 얻을 수 있다.
다만, 이러한 정보를 통해, 코드의 내용이나 구조 등을 나쁜 의도를 가진 사람들에게 노출할 수도 있기 때문에 보통 이러한 정보를 사용자가 직접 볼 수 있게 구성하지는 않고, 
서버 측에서 로그 파일 등을 이용해 관리자만 볼 수 있게 처리한다.

<h2>JAVA 예외 6</h2>
<h3>Checked exception vs Unchecked exception</h3>
우리가 만들었던 프로그램은 ArithmeticException, ArrayIndexOutOfBoundsException 같은 경우는 try catch문으로 잡아내지 않아서 프로그램이 뻗는다고 할지라도
컴파일해서 실행할 수 있기는 했다. 이러한 Exception들을 unchecked Exception이라고 부른다. unchecked Exception은 모두 RuntimeException 클래스로부터 상속된 예외들이다.
하지만 try catch문 등으로 잡아내지 않으면 프로그램이 컴파일도 안되는 예외들도 있다.
이러한 예외들을 checked Exception이라고 부른다. Throwable로부터 상속된 모든 클래스에서 RuntimeException을 제외한 모든 에러와 예외들이
checked Exception에 속한다. checked Exception은 반드시 예외 처리를 해 주어야 한다.
만약 IOException을 처리하지 않는다면 제대로 컴파일이 되지 않는다.
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

<h2>JAVA 예외 7</h2>
<h3>Finally와 Resource 다루기</h3>
대표적인 자원으로는 파일, 네트워크, 데이터베이스 등이 있다.
이러한 자원들은 프로그램 외부에 존재하기 때문에 우리의 프로그램이 온전히 제어하지 못한다. 프로그램만을 위해 존재하지 않기 때문에 읽기나 쓰기 작업을 하는 도중에 상황에 따라 연결이 불량하여 작업이 실패할 수 있다. 그래서 이러한 자원을 사용할 때는 자원을 붙들기 위해 파일의 경우 점유상태를 나타내기도 하고, 네트워크나 데이터베이스는 연결 상태를 유지한다. 그리고 우리가 필요한 작업을 끝내고 나서는 자원을 놓아주는 작업을 한다.      
    
그런데, try 문에서 오류가 발생하면 이후에 작업이 있더라도 catch문으로 넘어간다.
자원을 놓아주는 작업을 try 문에 넣게 되면, 예외가 발생했을 때 자원을 놓아주는 작업을 하지 못하게 된다. 그래서 예외가 발생했든, 발생하지 않았든 자원을 일단 잡았으면 놓아주는 작업을 실행하도록 해야 한다. 이런 경우에 사용하는 형식이 finally 문이다.
finally 문은 try 문에서 예외가 발생했거나 발생하지 않았거나 무조건 실행된다.
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

<h2>JAVA 예외 8</h2>
<h3>Try with Resource</h3>
try-with-resource문은 try 문에 괄호를 추가하여 그 안에 사용할 자원을 정의한다.
객체를 여러 개 선언할 수도 있고, 세미콜론(;)으로 구별한다. 객체의 정의 가장 마지막에는 세미콜론(;)을 넣지 않는다. 전체 try문(try, catch, finally 등)이 종료되면 생성된 인스턴스는 자동으로 종료되기 때문에 명시적으로 close를 이용해서 자원을 놓아주지 않는다.

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

<h2>JAVA 예외 9</h2>
<h3>수업을 마치며</h3>
<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class ThrowException {

	public static void main(String[] args) throws IOException {
		FileWriter f = new FileWriter("./data.txt");
		f.write("Hello");
		f.close();
	}

}
</code></pre>

<h1>Do it! HTML+CSS+자바스크립트 웹 표준의 정석</h1>
<h2>HTML 기본 문서 만들기</h2>

* HTML이란 
HT(Hyper Text): 웹에서 자유롭게 오갈 수 있는 링크   
M(Mark up): 텍스트뿐만 아니라 이미지, 영상 등을 표시함. 마크업에 사용하는 꼬리표를 태그라 함   
-> HTML은 웹에서 자유롭게 오갈 수 있는 웹 문서를 만드는 언어

~~~
<!doctype html>   //현재 문서가 html5 언어로 작성한 웹 문서라는 뜻.
	<html lang="ko">    //웹 문서의 시작과 끝을 나타내는 태그. 웹 브라우저가 <html>태그를 만나면 </html>까지 소스를 읽어 화면에 표시.
	<head>    //웹 브라우저가 웹 문서를 해석하는 데 필요한 정보를 입력하는 부분. 웹 브라우저 화면에 나타나지 않는다.
		<meta charset="UTF-8">
		<title>HTML 기본문서</title>
	</head>
	<body>    //실제로 웹 브라우저 화면에 나타나는 내용.
		<h1> 프런트엔드 웹 개발 </h1>
		<hr>
		<p>HTML</p>
		<p>CSS</p>
		<p>자바스크립트</p>
	</body>
</html> 
~~~

* head 태그
	* 문서 관련 정보 입력, 웹 브라우저 화면엔 보이지 않음.
	* 문서에서 사용할 외부 파일 링크

* 문자 세트 등 문서 정보가 들어 있는 meta 태그: 한글로 된 내용을 표시하기 위해 UTF-8문자 세트를 사용한다. 이외에도 다양한 문서 정보를 지정.
~~~
<meta charset="UTF-8">
~~~

* 문서 제목을 나타내는 title 태그
~~~
<title>HTML 기본문서</title>
~~~

* body 태그
	* 실제 브라우저에 표시될 내용 입력
	* 태부분의 태그가 body 태그와 /body 태그 사이에서 사용하는 태그들
	* !을 치고 shift 누르며 enter 누르면 html의 기본 형식 코드가 뜬다.
	* 들여쓰기는 실제 웹 브라우저에 영향을 끼치진 않음. 가독성을 위해 쓰는 것.
~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>첫 번째 문서 연습</title>
</head>
<body>
  <h1>웹 문서 만들기</h1>
</body>
</html>
~~~

<h2>웹 문서에 다양한 내용 입력하기(1)</h2>

* p 태그 ~ /p 태그: 하나의 텍스트 단락. 다음 줄과의 사이에 빈 줄을 생성.
* em 태그 ~ /em 태그: 강조
* strong 태그 ~ /strong: 진하게 표시 - 강조의 의미가 있음
* br 태그: 한 단락 내에서 줄 변환. 닫는 태그가 없다.
* hr 태그: 가로 줄을 넣어줌으로 영역 표시하여 분위기 전환. 닫는 태그가 없다.
* b 태그: 굵게 표시 - 강조의 의미는 없음

~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>상품 소개 페이지</title>
</head>
<body>  
  <h1>레드향</h1>
  <p>껍질에 붉은 빛이 돌아 레드향이라 불린다.</p>
  <p>레드향은 <em>한라봉과 귤을 교배</em>한 것으로<br> 알맹이가 굵고 통통해 식감이 좋으며<br> 비타민 C와 비타민 P가 풍부해<br> <strong>혈액순환, 감기예방</strong> 등에 좋은 것으로 알려져 있다.</p>
  <hr>
  <h2>레드향 샐러드 레시피</h2>
  <p><b>재료 : </b>레드향 1개, 아보카도 1개, 토마토 1개, 샐러드 채소 30g</p>
  <p><b>드레싱 : </b>올리브유 1큰술, 레몬즙 2큰술, 꿀 1큰술, 소금 약간</p>  

  <hr>
  <h2>상품 구성</h2>

</body>
</html>
~~~

* ol 태그 ~ /ol 태그: 순서가 있는 목록.
	* 순서가 아닌 a, b, c 타입으로 하고 싶다면 ol 태그 안에 type="a"를 작성. 
* ul 태그 ~ /ul 태그: 순서가 없는 목록.
* li 태그 ~ /li 태그: 목록 내의 리스트.

~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>상품 소개 페이지</title>
</head>
<body>
  <h2>레드향 샐러드 레시피</h2>
  <p><b>재료 : </b>레드향 1개, 아보카도 1개, 토마토 1개, 샐러드 채소 30g</p>
  <p><b>드레싱 : </b>올리브유 1큰술, 레몬즙 2큰술, 꿀 1큰술, 소금 약간</p>  
  <ol>
    <li>샐러드 채소를 씻고 물기를 제거한 후 준비합니다.</li>
    <li>레드향과 아보카도, 토마토를 먹기 좋은 크기를 썰어둡니다.</li>
    <li>드레싱 재료를 믹서에 갈아줍니다.</li>
    <li>볼에 샐러드 채소와 썰어 둔 레드향, 아보카도, 토마토를 넣고 드레싱을 뿌리면 끝!</li>
  </ol>
</body>
</html>
~~~

* caption 태그 ~ /caption 태그: 표 제목
* table 태그 ~ /table 태그: 표 전체
* tr 태그 ~ /tr 태그: 행
* td 태그 ~ /td 태그: 셀
* th 태그 ~ / th 태그: 제목 셀
* style 태그 ~ /style 태그: 표의 선 테두리

~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>상품 소개 페이지</title>
  <style>
    table, th, td {
      border:1px solid #ccc;
      border-collapse: collapse;
    }
    th, td { padding:10px 20px; }
  </style>
</head>
<body>
  <h2>상품 구성</h2>
  <table>
    <caption>선물용과 가정용 상품 구성</caption>
    <tr>
      <th>용도</th>
      <th>중량</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
    <tr>
      <td>선물용</td>
      <td>3kg</td>
      <td>11~16과</td>
      <td>35,000원</td>
    </tr>
    <tr>
      <td>선물용</td>
      <td>5kg</td>
      <td>18~26과</td>
      <td>52,000원</td>
    </tr>
    <tr>
      <td>가정용</td>
      <td>3kg</td>
      <td>11~16과</td>
      <td>30,000원</td>
    </tr>
    <tr>
      <td>가정용</td>
      <td>5kg</td>
      <td>18~26과</td>
      <td>4,7,000원</td>
    </tr>
  </table>
</body>
</html>
~~~

<h2>웹 문서에 다양한 내용 입력하기(2)</h2>

* img 태그: 이미지 삽입
	* src: 이미지 파일 경로
	* alt: 대체텍스트(이미지 이름)

~~~
<img src="images/tangerines.jpg" alt="레드향">
~~~

* audio 태그 ~ /audio 태그: 오디오 삽입

~~~
<audio src="medias/spring.mp3" controls></audio>
~~~

* video 태그 ~ /video 태그
~~~ 
<video src="medias/salad.mp4" controls width="700"></video> 
~~~

* audio 태그와 video 태그 속성
	* controls: 플레이어 화면에 컨트롤 바를 표시
	* autoplay: 오디오나 비디오를 자동으로 실행
	* loop: 오디오나 비디오를 반복 재생
	* muted: 오디오나 비디오의 소리를 제거
	* preload: 페이지를 불러올 때 오디오나 비디오 파일을 어떻게 로딩할 것인지 지정. 사용할 수 있는 값은 auto, metadata, none이다. 기본적으로 preload="auto"가 사용.
	* width, height: 비디오 플레이어의 너비와 높이를 지정. width나 height의 값 중에서 하나만 지정하면 나머지는 자동으로 계산해서 표시.
	* poster="파일 이름": video 태그에서 사용하는 속성으로, 비디오가 재생되기 전까지 화면에 표시될 포스터 이미지를 지정함.

* a 태그 ~ /a 태그: 멀티미디어 삽입된 링크 생성.
	* href: 연결하고자 하는 파일
	* target='_blank': 현제 페이지가 아닌 새 페이지로 열림
	
~~~
<a href="../05/order.html" target="_blank">주문서 작성하기</a>
//주문서 작성하기란 텍스트에 멀티미디어가 들어있는 문서로 이동
~~~

<h2>입력 양식 작성하기(1)</h2>

* form 태그 ~ /form 태그
* label 태그 ~ /label 태그
* input태그
	* type="text": 텍스트 필드
	* type="password": 비밀번호 필드
	* type="submit" value:"표시될 텍스트": 값을 전송하는 필드
	* type="email": 이메일 필드
	* type="tel": 전화번호 필드  
	
~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>웹 폼 삽입하기</title>
</head>
<body>
  <form action="">
    <label for="user-id">아이디: </label>
    <input type="text" id="user-id">
    
    <label>비밀번호: <input type="password"></label>
    <input type="submit" value="로그인">
  </form>
</body>
</html>
~~~
~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>폼 삽입하기</title>
</head>
<body>
  <form action="">
    <ul id="shipping">
      <li>
        <label for="prod">주문 상품</label>
        <input type="text" id="prod" value="상품용 3kg">
      </li>
      <li>
        <label for="user-name">이름</label>
        <input type="text" id="user-name">
      </li>
      <li>
        <label for="addr">배송 주소</label>
        <input type="text" id="addr">
      </li>
      <li>
        <label for="mail">이메일</label>
        <input type="email" id="mail">
      </li>
      <li>
        <label for="phone">연락처</label>
        <input type="tel" id="phone">
      </li>
    </ul>    
  </form> 
</body>
</html>
~~~
   

* input태그  
	* type="radio": 여러 항목 중 한 개의 항목만을 선택할 수 있는 필드
		* radio의 value 값 적기 전 name=""을 기입 후 두 개 항목 모두 같은 그룹이란 것을 뜻하기 위해 같은 네임 작성
	* type="checkbox": 여러 개 항목 중 두 개 이상의 항목을 선택할 수 있는 필드
		* radio와 checkbox는 서버에 전송되는 value값이 필수 
~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>레드향 주문하기</title>
</head>
<body>
  <h1>레드향 주문하기</h1>
  <form>
    <fieldset>
      <legend>상품 선택</legend>
      <p><b>주문할 상품을 선택해 주세요.</b></p>
      <ul>
        <li>
          <label><input type="checkbox" value="s_3">선물용 3kg</label> //선물용 3kg 항목 선택하면 value값인 s_3이 서버에 전송되는 것
          <input type="number">개
        </li>
        <li>
          <label><input type="checkbox" value="s_5">선물용 5kg</label>
          <input type="number">개
        </li>
        <li>
          <label><input type="checkbox" value="f_3">가정용 3kg</label>
          <input type="number">개
        </li>
        <li>
          <label><input type="checkbox" value="f_5">가정용 5kg</label>
          <input type="number">개
        </li>
      </ul>   
      <p><b>포장 선택</b></p>
      <ul>
        <li><label><input type="radio" name="gift" value="yes" >선물 포장</label></li>
        <li><label><input type="radio" name="gift" value="no">선물 포장 안 함</label></li>
      </ul>     
    </fieldset>
    <fieldset>
      <legend>배송 정보</legend>
      <ul>
        <li>
          <label for="user-name">이름 </label>
          <input type="text" id="user-name">
        </li>
        <li>
          <label for="addr">배송 주소</label>
          <input type="text" id="addr">
        </li>
        <li>
          <label for="mail">메일 주소</label>
          <input type="email" id="mail">
        </li>        
        <li>
          <label for="phone">연락처</label>
          <input type="tel" id="phone">
        </li>
      </ul>  
    </fieldset>      
  </form>
</body>
</html>
~~~
 
<h2>입력 양식 작성하기(2)</h2>
  
* input태그
	* type="number": 화살표를 이용한 숫자 필드
	* type="range": 슬라이드 막대를 이용한 숫자 필드
		* min="", max="" 속성을 이용해 최솟값, 최댓값 설정
		* value="" 속성으로 화면에 나타나는 초기값 설정 가능
~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>레드향 주문하기</title>
</head>
<body>
  <h1>레드향 주문하기</h1>
  <form>
    <fieldset>
      <legend>상품 선택</legend>
      <p><b>주문할 상품을 선택해 주세요.</b></p>
      <ul>
        <li>
          <label><input type="checkbox" value="s_3">선물용 3kg</label>
          <input type="number" min="0" max="5">개 (최대 5개)
        </li>
        <li>
          <label><input type="checkbox" value="s_5">선물용 5kg</label>
          <input type="number" min="0" max="3" value="1">개 (최대 3개)
        </li>
      </ul>
      <ul>
        <li>
          <label><input type="checkbox" value="f_3">가정용 3kg</label>
          <input type="range" min="0" max="5">개 (최대 5개)
        </li>
        <li>
          <label><input type="checkbox" value="f_5">가정용 5kg</label>
          <input type="range" min="0" max="3" value="1">개 (최대 3개)
        </li>
      </ul>      
      <p><b>포장 선택</b></p>
      <ul>
        <li><label><input type="radio" name="gift" value="yes">선물 포장</label></li>
        <li><label><input type="radio" name="gift" value="no">선물 포장 안 함</label></li>
      </ul>    
    </fieldset>
    <fieldset>
      <legend>배송 정보</legend>
      <ul id="shipping">
        <li>
          <label for="user-name">이름 </label>
          <input type="text" id="user-name">
        </li>
        <li>
          <label for="addr">배송 주소</label>
          <input type="text" id="addr">
        </li>
        <li>
          <label for="mail">이메일</label>
          <input type="email" id="mail">
        </li>        
        <li>
          <label for="phone">연락처</label>
          <input type="tel" id="phone">
        </li>
      </ul>  
    </fieldset>
    <div>
      <input type="submit" value="주문하기"> 
      <input type="reset" value="취소하기">
    </div>        
  </form>
</body>
</html>
~~~
   
* input 태그
	* type="date"
	* type="month"
	* type="week"
	* type="time"
	* type="datetime"
		* 시간, 날짜 모두 min, max 속성으로 최소값, 최댓값으로 제한 줄 수 있음

~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>날짜와 시간</title>
</head>
<body>
  <form>
    <h1>날짜 지정하기</h1>
    <input type="date">
    <input type="month">
    <input type="week">
    <hr>
    <h1>시간 지정하기</h1>
    <input type="time">
    <input type="datetime-local">
    <hr>
    <h1>범위 제한하기</h1>
    <input type="date" min="2020-02-01" max="2020-02-15">
    <input type="time">
  </form>
</body>
</html>
~~~
   
* input 태그
	* type="hidden": 화면엔 나타나진 않지만 서버에 전송되는 값 ex)사용자가 굳이 입력하지 않아도 되는 것
~~~
<!DOCTYPE html>
<html lang="ko">
  <head>
		<meta charset="UTF-8">
		<title>로그인</title>
  </head>
  <body>
	<form>
    <fieldset>
      <input type="hidden" name="url" id="url" value="사이트를 통한 직접 로그인">
    	<label>아이디: <input type="text" id="user_id" size="10"></label>
      <label>비밀번호: <input type="password" id="user_pw" size="10"></label>
      <input type="submit" value="로그인">
    </fieldset>
  </form>
  </body>
</html>
~~~

   
<h2>입력 양식 작성하기(3)</h2>

* input 태그
	* required: 필수 필드 마지막에 작성
	* readonly: 사용자가 읽을 수만 있는 필드
	* autofocus: 사용자가 가장 먼저 기입할만한 필드에 커서가 깜빡이게 할 수 있음

~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>레드향 주문하기</title>
  <link rel="stylesheet" href="css/form2.css">
</head>
<body>
  <h1>레드향 주문하기</h1>
  <form>
    <fieldset>
      <legend>배송 정보</legend>
      <ul id="shipping">
        <li>
          <label for="prod">주문 상품</label>
          <input type="text" id="prod" value="상품용 3KG" readonly>
        </li>
        <li>
          <label for="user-name">이름 </label>
          <input type="text" id="user-name" autofocus required>
        </li>
        <li>
          <label for="addr">배송 주소</label> 
          <input type="text" id="addr" required>
        </li>
        <li>
          <label for="mail">이메일</label>
          <input type="email" id="mail">
        </li>        
        <li>
          <label for="phone">연락처</label>
          <input type="tel" id="phone" placeholder="하이픈 빼고 입력해 주세요.(01012345678)" required>
        </li>
        <li>
          <label for="d-day">배송 지정</label>
          <input type="date" id="d-day"> <small>(주문일로부터 최소 3일 이후)</small>
        </li>        
      </ul>  
    </fieldset>
    <div>
      <input type="submit" value="주문하기"> 
      <input type="reset" value="취소하기">
    </div>        
  </form>
</body>
</html>
~~~

* textarea 태그 ~ /textarea 태그: 여러 줄의 텍스트 입력할 수 있는 필드
	* cols, rows 속성으로 행렬 제한 줄 수 있음
~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>레드향 주문하기</title>
  <link rel="stylesheet" href="css/order.css">
</head>
<body>
  <div id="container">
    <h1>레드향 주문하기</h1>
    <form>
      <fieldset>
        <legend>배송 정보</legend>
        <ul id="shipping">
          <li>
            <label for="user-name">이름 </label>
            <input type="text" id="user-name">
          </li>
          <li>
            <label for="addr">배송 주소</label>
            <input type="text" id="addr">
          </li>
          <li>
            <label for="mail">이메일</label>
            <input type="email" id="mail">
          </li>        
          <li>
            <label for="phone">연락처</label>
            <input type="tel" id="phone">
          </li>
          <li>
            <label for="d-day">배송 지정</label>
            <input type="date" id="d-day"> <small>(주문일로부터 최소 3일 이후)</small>
          </li>     
          <li>
            <label for="memo">메모</label>
            <textarea id="memo" cols="40" rows="4"></textarea>
          </li>   
        </ul>  
      </fieldset>
      <div>
        <input type="submit" value="주문하기"> 
        <input type="reset" value="취소하기">
      </div>        
    </form>
  </div>
</body>
</html>
~~~

* select 태그 ~ /select 태그: 화살표를 누르면 여러 항목이 보일 수 있게 함
	* option 태그 ~ /option 태그: 항목 필드
		* 서버로 전송되는 value값 필수이며 초기값의 항목에 selected 기입
~~~
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>레드향 주문하기</title>
</head>
<body>
  <h1>레드향 주문하기</h1>
  <form action="">
    <fieldset>
      <legend>상품 선택</legend>
      <p><b>주문할 상품을 선택해 주세요.</b></p>
      <label>
        <select>
          <option value="special_3" selected>선물용 3kg</option>
          <option value="special_5">선물용 5kg</option>
          <option value="family_3">가정용 3kg</option>
          <option value="family_5">가정용 5kg</option>
        </select>
      </label>
    </fieldset>
    <fieldset>
      <legend>상품 선택</legend>
      <p><b>주문할 상품을 선택해 주세요.</b></p>
      <label><input type="text" list="goods"></label>
      <datalist id="goods">
        <option value="special_3">선물용 3kg</option>
        <option value="special_5">선물용 5kg</option>
        <option value="family_3">가정용 3kg</option>
        <option value="family_5">가정용 5kg</option>
      </datalist>      
    </fieldset>      
  </form>
</body>
</html>
~~~
