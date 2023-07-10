
0501 - 자바 1 : 챕터 1,2,3,4,5 강의내용

설치, 자바관련 이야기


기본 프린트문

public class @@@
    pulic static void main(String[] args){

    System.out.println("aaaa")

    }


1. 데스크톱 에플리케이션 만들기

import javax.swing.*;   
import java.awt.Dimension;
import java.awt.Toolkit;
public class HelloWorldGUIApp{
    public static void main(String[] args){
        javax.swing.SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                JFrame frame = new JFrame("HelloWorld GUI");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setPreferredSize(new Dimension(800, 300));
                JLabel label = new JLabel("Hello World!!", SwingConstants.RIGHT);
                frame.getContentPane().add(label);
                Dimension dim = Toolkit.getDefaultToolkit().getScreenSize();
                frame.setLocation(dim.width/2-400/2, dim.height/2-300/2);

                frame.pack();
                frame.setVisible(true);
            }
        });
    }
}

직접 수치를 변경하여 애플리케이션 GUI 수정가능

2. 사물을 자바로 제어하기

사물에 프로그래밍을 접목시키면 사물인터넷(IoT)이 된다

ex) 라즈베리파이라는 작은 컴퓨터에 프로그래밍을 하여 LED를 점멸 시킨다

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

위 프로그래밍으로 라즈베리파이에 연결된 LED전구를 점멸시킬수있음


3. 안드로이드 애플리케이션 만들기

안드로이드 스튜디오를 이용해 안드로이드 앱 개발가능



=========================================================



0502 - 자바 1 : 챕터 6,7 강의내용 정리

자바의 데이터를 어떤식으로 연산하여 정리할지 알아본다


데이터 종류: 숫자, 문자열, 영상/소리/기타 등등

숫자 : +,-,*,/ 또는 미적분 등
문자열 : 길이를 호출, 특정구간 제거, 특정 문자열이 있는지 검사

System.out.println() 을 sout -> Ctrl+Space 을 하면 자동입력

//  주석

숫자 : 자바는 숫자를 다른 기호없이 그대로 입력
       + 연산자는 덧셈
	   
문자 : 문자는"" 안에 적음
       + 연산자는 결합의 연산
	   문자열 간에는 * 불가능
	   length 연산은 문자열 길이 반환

문자열과 숫자 연산의 차이

	   System.out.println(6); number
	   System.out.println("six"); string
	   System.out.println("6"); string 6
	   System.out.println(6+6); 12
	   System.out.println("6"+"6"); 66
	   System.out.println(6*6); 36
	   System.out.println("1111".length()); 4

다른 연산

	   System.out.println(Math.PI);//파이 3.14159~
	   System.out.println(Math.floor(Math.PI));//올림 4
	   System.out.println(Math.ceil(Math.PI));//내림 5


'Character', "String"

줄바꿈은 \n 로 인식됨
쌍따옴표를 문장안에 사용하려면 /"@@@/" 형태로 사용


	   System.out.println("Hello World"/length); //11
	   
	   System.out.println("Hello [[[name]]]".replace("[[[name]]]","@@@"));

replace는 앞 문자열에서 원하는 부분을 바꿀수있음 .replace("앞 문자열의 바꿀부분","대신 넣을 부분") 


===============================================================

0503 - 자바 1 : 챕터 8,9,10 강의내용 정리

변수 (variable)

정수형 변수 -> int(eger)
실수형 변수 -> double
문자열 -> String

int a = 1;
System.out.println(a);

실행값 -> 1




변수 지정의 효용

String name = "ccc";  // ccc를 name 에 저장
System.out.println("aaa "+name+" bbb");

실행값 -> aaa ccc bbb

double aaa = 10; //숫자에도 적용가능
System.out.println(aaa);

실행값 -> 10 



데이터 타입 변환

double a = 1.1;
double b = 1;            
double c = (double) 1;   // 위 코드를 자세히 풀어쓴것

~~int d = 1.1;~~     // 소수점 아래부터 인식을 못해 사라짐
double e = 1.1;      // 올바른 형태
int f = (int)1.1;    // 실수를 정수로 변환시킴


String g = Integer.toString(1);   // 1 이라는 숫자를 문자로 인식시킴
System.out.println(g);



프로그래밍은 업무의 자동화된 처리를 위해서라고 할 수 있음



String HOME = "Rian APT 503"; // HOME에 내 주소를 할당

Elevator myElevator = new Elevator(HOME);
myElevator.callForUp(1); // 엘리베이터를 부름


Security mySecurity = new Security(HOME);
mySecurity.off(); // 내 집(HOME)의 보안을 끔


Lighting hallLamp = new Lighting(HOME + " / Hall Lamp");
hallLamp.on(); 

Lighting floorLamp = new Lighting(HOME + " / floorLamp");
floorLamp.on();

Lighting roomLamp = new Lighting(HOME + " / RoomLamp");
roomLamp.on();



디버거

프로그램을 한줄한줄 단위로 실행시켜 좀더 자세한 실행 과정을 볼 수 있다


============================================================


0504 - 자바 1 : 챕터 11,12 강의내용 정리


프로그램의 입력과 출력

다이어로그를 이용해  id 값을 사용자가 설정하게 해주는 코드

JOptionPane 객체의 showInputDialog 메소드를 이용하여 id값을 사용자가 입력하게 할 수 있다
JOptionPane 객체를 이용하기 위해서 import 구문을 사용함

<pre><code>
import javax.swing.JOptionPane;

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OKjavaGoInHomeInput {

    public static void main(String[]args){
        String id = JOptionPane.showInputDialog("Enter a ID");  // JOptionPane의 showInputDialog를 이용하여 정보를 String 데이터로 받음 (id)
        String bright = JOptionPane.showInputDialog("Enter a Bright level");  // 밝기 값 또한 받음

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

        DimmingLights moodLamp = new DimmingLights(id+"moodLamp"); 
        moodLamp.setbright(Double.parseDouble(bright)); // setbright 메소드를 통해 밝기값을 double 데이터로 받는다
        moodLamp.on(); 
    }
}
</code></pre>

아규먼트를 이용해 프로그램 실행시키기

main 메소드의 args 파라미터를 이용하여 코드내의 값을 더욱 편하게 설정가능

ex)
public static void main(String[]args){
        String id = args[0];
        String bright = args[1];
}

아규먼트 값을 다양하게 사용하여 결과값을 알아볼 수 있다
args는 문자열 배열로 여러개의 String 데이터가 들어있을 수 있다
인덱스는 0부터 시작함

아규먼트(argument)
파라미터(parameter)
배열(array)




자바로 직접 프로그래밍 하기
컴파일

명령어 프롬포트에서 진행가능

cd 명령어를 통해 프로젝트 파일로 이동
cd C:@@@@  //프로젝트 파일 경로

javac 명령어로 다른 명령어 사용법을 확인가능하다

javac Program.java // 컴파일시 Program.class 생성 
java Program // Program.class를 실행함 (실행시에는 .class 생략)


다른 라이브러리의 사용하는 프로그램의 컴파일

jacac -cp ".;@@" aa.java

aa 자바파일이 존재하는 현재 폴더와 외부 라이브러리 @@ 폴더에서 필요한 자바 파일을 컴파일 한다

-cp = --class-path
".;@@" 의 . 은 현재폴더
윈도우는 ;
맥이나 리눅스는 :

실행시에는
java -cp ".;@@" aa
꼴로 실행가능


직접 컴파일/실행 시 아규먼트 값 설정방법

javac @@.jave // 컴파일시킴
java @@ "aa" 11  // 아규먼트 값은 클래스 파일 실행 명령어 이후 바로 적어서 값을 설정 가능하다


___
0508

# 자바문서 보는법 (자바1 - 13과)

- API 와 UI 의 차이점

	작업들의 시간적 순서에 주목 -> 프로그램

	도구의 응용에 주목 -> 애플리케이션

	- 자바의 도구들을 응용해서 사용하기 위해서 일정한 조작 장치를 구성한 것을  __자바 API__ 라고 한다.

	- 사용자가 자바 프로그램을 사용할 수 있도록 만들어둔 장치들을 __UI__ 라고 한다.

- Java API documentation 사용법

	패키지와 클래스를 찾아볼 수 있고 자신이 찾은 클래스가 어떤 패키지에 속해있는지 알 수 있다.

	 패키지 > 클래스 > 변수, 메소드

- 클래스에 대하여

<pre><code>
public class ClassApp {
	public static void main(String[] args) {
		
		System.out.println(Math.PI);  // PI 변수를 이용해 파이값을 나타냄
		System.out.println(Math.floor(1.6));  // 1.6 이라는 실수를 floor 를 사용해 소수점 이하에 대해서 날린 값을 출력함 
		System.out.println(Math.ceil(1.6));   // 1.6 이라는 실수를 ceil 을 사용해 소수점 이하에 대해서 올림한 값을 출력함
	}
}
</code></pre>
	 
Math 클래스에는 수학과 관련된 여러 변수들과 메소드들이 있다.

PI 변수는 원주율이 적절한 정밀도로 저장되어 있는 변수다.

floor 메소드는 특정 소수점 이하에 대해서 버림한 값을 산출한다.

ceil 메소드는 특정 소수점 이하에 대해서 올림한 값을 산출한다.

	
- 인스턴스

<pre><code>
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.PrintWriter;  //  java.io 패키지에서 불러옴
public class InstanceApp {

	public static void main(String[] args) throws IOException {
		
		PrintWriter p1 = new PrintWriter("result1.txt");  
		// PrintWriter 객체는 math 클래스와 다르게 new 키워드를 통한 인스턴스를 생성한다.
		// PrintWriter 클래스의 이름을 p1으로 설정함.
		
		p1.write("Hello 1");
		p1.close();	
		
		PrintWriter p2 = new PrintWriter("result2.txt");
		p2.write("Hello 2");
		p2.close();
		p2.toString();

		// 간단하게 끝나는 작업이면 평범하게 하면 되지만 작업량이 많아지고 긴 맥락일시 인스턴스를 사용하는것이 더욱 효율적이다.
		// 생성자(Constructors)가 없으면 1회용 이다. (math)
		// 생성자가 있으면 생성자를 이용해 인스턴스를 만드는 것이 허용 되어있다.

		// Add throws declaration을 이용해서 에러 핸들링을 할 수 있다.
	}

}

</code></pre>

- 상속

<pre><code>
java.lang.Object			 // 베이스
	java.io.Writer  		 // Object 에게 상속받음
		jave.io.PrintWriter  // Writer 에게 상속받음

// 자식은 부모의 메소드를 사용가능 (상위 개체의 정보를 물려받음)
// Writer 에도 write 기능이 있고 PrintWriter 에도 write 기능이 있을때 PrintWriter 의 write 기능을 사용하는 것을 override 라고 함
	</code></pre>

# 나의 앱 만들기 (자바1 - 14과)

- 공급가, 부가가치세, 비용, 이익, 배당을 자동으로 계산해주는 나만의 앱 만들기

<pre><code>
public class AccountingApp {
    public static void main(String[]args){

        System.out.println("공급가 : "+ 10000.0);
        System.out.println("부가가치세 :"+ (10000.0*0.1));
        System.out.println("총합 : "+ (10000.0 + 10000.0*0.1));
        System.out.println("비용 : "+ (10000.0*0.3));
        System.out.println("이익 : "+ (10000.0 - 10000.0*0.3));
        System.out.println("배분 1 : "+ (10000.0 - 10000.0*0.3) * 0.5);
        System.out.println("배분 2 : "+ (10000.0 - 10000.0*0.3) * 0.3);
        System.out.println("배분 3 : "+ (10000.0 - 10000.0*0.3) * 0.2);
    }
}
</code></pre>

- 변수도입

<pre><code>
public class AccountingApp {
    public static void main(String[]args){
        double ValueofSupply = 10000.0;
		// double ValueofSupply = Double.parseDouble(args[0]);
		// ValueofSupply가 아규먼트를 받게함
        double VATrate = 0.1;
        double ExpenseRate = 0.3;
        double VAT = ValueofSupply * VATrate;
        double Expense = ValueofSupply * ExpenseRate;
        double Income = ValueofSupply - Expense;
        double Dividend 1 = Income * 0.5;
        double Dividend 2 = Income * 0.3;
        double Dividend 3 = Income * 0.2;

        // 계산식과 값들을 변수로 바꾸어줌

		// Alt + Ctrl + V  변수지정 단축키 
		// Ctrl + R 	   찾아서 바꾸기

        System.out.println("Value of supply : "+ ValueofSupply);
        System.out.println("VAT :"+ VAT);
        System.out.println("Total : "+ (ValueofSupply + VAT));
        System.out.println("Expense : "+ Expense);
        System.out.println("Income : "+ Income);
        System.out.println("Dividend 1 : "+ Dividend 1);
        System.out.println("Dividend 2 : "+ Dividend 2);
        System.out.println("Dividend 3 : "+ Dividend 3);

		
    }
}
</code></pre>

___

0509

# 나의 앱 만들기 (자바1 - 14과 뒷부분)

## 제어문

- 조건문

<pre><code>

        if(Income >= 30000.0) {
            Dividend1 = Income * 0.5;
            Dividend2 = Income * 0.3;
            Dividend3 = Income * 0.2;
        }
        else {
            Dividend1 = Income * 0.7;
            Dividend2 = Income * 0.2;
            Dividend3 = Income * 0.1;
        }

		//if 문을 사용하여 Income이 30000.0 보다 크거나 같을 경우와 그렇지 않을 경우에 사용할 식을 다르게 함
    

</code></pre>

- 배열

<pre><code>

        double[] DividendRates = new double[3]; 
		// DividendRates 라는 변수에 double 값을 3개 저장 할 수 있게 한다.

        DividendRates[0] = 0.5;
        DividendRates[1] = 0.3;
        DividendRates[2] = 0.2;

        double Dividend1 = Income * DividendRates[0];
        double Dividend2 = Income * DividendRates[1];
        double Dividend3 = Income * DividendRates[2];

</code></pre>

- 반복문

<pre><code>
        int i = 0;  // i 값 할당
        while (i < DividendRates.length) {  // i 가 DividendRates의 갯수보다 작을동안 ( [0],[1],[2] 로 총 3개) while문 안의 코드를 실행한다
            System.out.println("Dividend : " + (Income *DividendRates[i]) );  
            i = i + 1;
		}
</code></pre>

- 메소드

메소드는 서로 연관된 코드를 그룹핑 해서 이름을 붙인 정리정돈의 상자이다.

<pre><code>
public class AccountingApp {
    public static double ValueSupply = 10000.0;  
    public static double VATrate = 0.1;
    public static double ExpenseRate = 0.3;
	// void main 밖으로 꺼내 전역변수로 설정한다.

    public static void main(String[]args){

        ValueSupply = 10000.0;
        VATrate = 0.1;
        ExpenseRate = 0.3;

        print();

		// 모두 메소드화 시켜 main 안쪽을 깔끔하게 만들었다.
    }

    private static double getDividend3() {
        return getIncome() * 0.2;
    }

    private static double getDividend2() {
        return getIncome() * 0.3;
    }

    private static double getDividend1() {
        return getIncome() * 0.5;
    }

    private static void print() {
        System.out.println("Value of supply : "+ ValueSupply);
        System.out.println("VAT :"+ getVat());
        System.out.println("Total : "+ (ValueSupply + getVat()));
        System.out.println("Expense : "+ getExpense());
        System.out.println("Income : "+ getIncome());
        System.out.println("Dividend 1 : "+ getDividend1());
        System.out.println("Dividend 2 : "+ getDividend2());
        System.out.println("Dividend 3 : "+ getDividend3());
    }

    private static double getIncome() {
        return ValueSupply - getExpense();
    }

    private static double getExpense() {
        return ValueSupply * ExpenseRate;
    }

    private static double getVat() {
        return ValueSupply * VATrate;
    }
}

</code></pre>

- 클래스

<pre><code>

class Accounting{ 

	// Accounting 클래스를 생성한다

    public static double ValueSupply = 10000.0;
    public static double VATrate = 0.1;
    public static double ExpenseRate = 0.3;

    private static double getDividend3() {
        return getIncome() * 0.2;
    }

    private static double getDividend2() {
        return getIncome() * 0.3;
    }

    private static double getDividend1() {
        return getIncome() * 0.5;
    }

    public static void print() {
        System.out.println("Value of supply : "+ Accounting.ValueSupply);
        System.out.println("VAT :"+ getVat());
        System.out.println("Total : "+ (ValueSupply + getVat()));
        System.out.println("Expense : "+ getExpense());
        System.out.println("Income : "+ getIncome());
        System.out.println("Dividend 1 : "+ getDividend1());
        System.out.println("Dividend 2 : "+ getDividend2());
        System.out.println("Dividend 3 : "+ getDividend3());
    }

    private static double getIncome() {
        return ValueSupply - getExpense();
    }

    private static double getExpense() {
        return ValueSupply * ExpenseRate;
    }

    private static double getVat() {
        return ValueSupply * VATrate;
    }
}
public class AccountingIFApp {

    public static void main(String[]args){

        Accounting.ValueSupply = 10000.0;
        Accounting.VATrate = 0.1;
        Accounting.ExpenseRate = 0.3;
        Accounting.print();

		// class Accounting 에 소속된 정보들을 가져온다
    }


}
</code></pre>

- 인스턴스

<pre><code>


		class Accounting1 ~~
		class Accounting2 ~~

        Accounting1.ValueSupply = 10000.0;
        Accounting1.VATrate = 0.1;
        Accounting1.ExpenseRate = 0.3;
        Accounting1.print();

		Accounting2.ValueSupply = 10000.0;
        Accounting2.VATrate = 0.1;
        Accounting2.ExpenseRate = 0.3;
        Accounting2.print();

		Accounting1.print();

		// 이 상황에서 클래스를 깔끔하게 정리하는방법

</code></pre>

<pre><code>

        Accounting a1 = new Accounting();

        a1.ValueSupply = 10000.0;
        a1.VATrate = 0.1;
        a1.ExpenseRate = 0.3;
        a1.print();

        Accounting a2 = new Accounting();

        a2.ValueSupply = 20000.0;
        a2.VATrate = 0.05;
        a2.ExpenseRate = 0.3;
        a2.print();

        a1.print();

		// 이렇게 정리 가능
</code></pre>

___
0510

# 자바 2 - 제어문 1 ~ 7.3

- Boolean Datatype

<pre><code>
public class BooleanApp {
    public static void main(String[] args){

        System.out.println("One");
        System.out.println(1);

        System.out.println(true);
        System.out.println(false);

        String foo = "aaaa";
        // String ture = "aaa";  << 오류발생
        // true, false 같이 프로그램 내에서 사용이 되고있거나 될 가능성이 있는 단어들은 reserved word로 분류된다. (String 값으로 사용 불가)

        System.out.println(foo.contains("a"));
        System.out.println(foo.contains("b"));
    }
}
</code></pre>

- 비교 연산자
<pre><code>
        System.out.println(1 > 1); // f
        System.out.println(1 == 1); // t
        System.out.println(1 < 1); // f
        System.out.println(1 <= 1); //t
</code></pre>

-조건문
<pre><code>
public class IfApp {
    public static void main(String[] args){

        if(false){  // 만약 괄호 안에 있는 값이 거짓이라면 1을 출력한다.
            System.out.println(1);
        }   else if (true) {  // 위에 있던 괄호안의 값이 거짓이 아닐경우에 괄호안의 값이 진실이면 2를 출력한다.
            System.out.println(2);
        }   else {  // 모두 아니였을시 3을 출력한다.
            System.out.println(3);
        }
    }
}
</code></pre>

응용 1

<pre><code>
public class AuthApp {
    public static void main(String[] args){

        //아규먼트 = aaaa

        String id = "aaaa";
        String inputid = args[0];

        System.out.println("Hi.");

        if (inputid.equals(id)){  // == 연산자를 사용시 문자열에서 오류가 일어날 가능성이 있기에 equals 를 사용
            System.out.println("T");
        }   else {
            System.out.println("F");
        }
        
    }
}
</code></pre>

응용 2

<pre><code>
public class AuthApp {
    public static void main(String[] args){

        String id = "aaaa";
        String inputid = args[0];

        String PW = "1111";
        String inputPW = args[1];

        System.out.println("Hi.");

        <!-- if (inputid.equals(id)){
            if (inputPW.equals(PW)){
                System.out.println("T");
            }   else {
                System.out.println("Wrong PassWord");
            }
        }   else {
            System.out.println("F");
        } -->
    }
}
        // 위 코드를 조건 연산자를 이용해 간략화 할수있다

public class AuthApp {
    public static void main(String[] args){

        String id = "aaaa";
        String inputid = args[0];

        String PW = "1111";
        String inputPW = args[1];

        System.out.println("Hi.");

        // && 연산자는 전항과 후항 모두가 참일때만 참을 반환한다.
        // || 연산자는 전항과 후항 중 하나라도 참일 경우 참을 반환하고 모두 거짓일 때에만 거짓을 반환한다.

        if (inputid.equals(id) && inputPW.equals(PW)){
                System.out.println("T");
        }   else {
            System.out.println("F");
        }

    }
}
</code></pre>

- == VS equals
<pre><code>
원시 데이터 타입 : boolean, byte, char, short, int, long, float, double

클래스들은 원시 테이터가 아니다.

int p1 = 1
int p2 = 1

p1 == p2 => true

String o1 = new String("java")
String o2 = new String("java")

o1 == o2 => false

String o3 = "jave2"
String o4 = "jave2"

o3 == o4 => true

int 같은 원시 데이터는 1을 같은 값으로 받지만
new String 으로 값을 만들면 같은 값이여도 따로 받아서 오류가 발생할 수 있음
</code></pre>
- 논리 연산자

<pre><code>
public class WS {
    public static void main(String[] args){

        System.out.println(1 == 1);

        // AND
        System.out.println(true && true); //t
        System.out.println(true && false); //f
        System.out.println(false && true); //f
        System.out.println(false && false); //f

        // OR
        System.out.println(true || true); //t
        System.out.println(true || false); //t
        System.out.println(false || true); //t
        System.out.println(false || false); //f

        // NOT
        System.out.println(!true);
    }
}
</code></pre>

<pre><code>
public class WS {
    public static void main(String[] args){

        String id = "aaaa";
        String inputid = args[0];

        String PW = "1111";
        String PW2 = "2222";
        String inputPW = args[1];

        System.out.println("Hi.");

        boolean RightPW = (inputPW.equals(PW) || inputPW.equals(PW2));
        // PW 둘중 하나만 맞으면 패스워드가 맞은걸로 함
        if (inputid.equals(id) && RightPW){
            System.out.println("T");
        }   else {
            System.out.println("F");
        }
    }
}

</code></pre>

- 반복문

<pre><code>
public class WS {
    public static void main(String[] args){

        System.out.println(1);

        int i = 0;
        System.out.println("=== while ===");
        while (i < 3){
            System.out.println(2);
            System.out.println(3);
            i++;
        }
        System.out.println("=== for ===");
        int j;
        for (j = 0; j < 3; j++){
            System.out.println(2);
            System.out.println(3);
        }
        System.out.println(4);

    }
}
</code></pre>

- 배열

<pre><code>
public class WS {
    public static void main(String[] args){

        String []users = new String[3];
        users[0] = "a";
        users[1] = "b";
        users[2] = "c";

        System.out.println(users[1]);
        System.out.println(users.length);

        int[] scores = {10, 100, 100};
        System.out.println(scores[1]);
        System.out.println(scores.length)
    }
}
</code></pre>

- 반복문 + 배열
<pre><code>

    String []users = new String[3];
    users[0] = "a";
    users[1] = "b";
    users[2] = "c";

    for (int i = 0; i < users.length ; i++){
        System.out.println(users[i]+",");
    }
        
</code></pre>

___
0511

# 자바 2 - 제어문 8.1 ~ 메소드 9

- 응용

<pre><code>
public class WS {
    public static void main(String[] args){

        String []users = {"a", "b", "c"};
        String inputID = args[0];

        boolean Logined = false;
        for (int i=0; i < users.length; i++){
            String currentID = users[i];
            if (currentID.equals(inputID));{
                Logined = true;
                break; // 반복문을 깨고 나옴
            }
        }
        
        System.out.println("Hi,");
        if (Logined){
            System.out.println("Master");
        }   else {
            System.out.println("Who are you");
        }
        
    }
}
</code></pre>

- 응용 2

<pre><code>
public class WS {
    public static void main(String[] args){

        String [][] users = 
        {"a","1111"},
        {"b","2222"},
        {"c","3333"};

        // 행,열 의  순서로 접근

        String inputID = args[0];
        String inputPW = args[1];

        boolean Logined = false;
        for (int i=0; i < users.length; i++){
            String[] current = users[i];
            if (current.equals(inputID) && current.equals(inputPW));
                Logined = true;
                break;
            }

        System.out.println("Hi,");
        if (Logined){
            System.out.println("Master");
        }   else {
            System.out.println("Who are you");
        }

    }
}
</code></pre>

## 메소드

- 이미 익숙한 메소드

equals, contains, floor 등

- 메소드의 기본 형식

<pre><code>
public class WS {
    public static void PrintTwoTimesA(){
        System.out.println(1);
        System.out.println(2);
        System.out.println(3);
    }
    public static void main(String[] args){

        PrintTwoTimesA();  
        // 메소드를 만들어 프린트문을 생략가능하다
        // 100000000
        PrintTwoTimesA();
    }
}

</code></pre>

- 메소드의 입력

<pre><code>
public class WS {

    public static void main(String[] args){

        PrintTwoTimesA("a", "-");
        PrintTwoTimesA("a", "=");
        PrintTwoTimesA("b", "~");
    }
    public static void PrintTwoTimesA(String aa, String bb){
        System.out.println(bb);
        System.out.println(aa);
        System.out.println(aa);
    }
}

</code></pre>

- 메소드의 출력

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class WS {

    public static void main(String[] args) throws IOException {

        System.out.println(twoTimes("a", "-"));
        FileWriter fw = new FileWriter("out.txt");
        fw.write(twoTimes("a", "*"));
        fw.close();


    }
    public static String twoTimes(String aa, String bb){
        String out = "";
        out = out + bb + "\n";
        out = out + aa + "\n";
        out = out + aa + "\n";
        return out;
    }
}

</code></pre>

- 메소드의 활용

<pre><code>
public class WS {
    public static double ValueOfSupply = 10000.0;
    public static double VATrate = 0.1;
    public static double getVAT() {
        return ValueOfSupply * VATrate;
    }
    public static double getTotal() {
        return ValueOfSupply + getVAT();
    }
    
    public static void main(String[] args){
    
            System.out.println("Vaule of supply :" +ValueOfSupply);
            System.out.println("VAT : "+getVAT());
            System.out.println("Total : " +getTotal());

    }
}

</code></pre>

- 부록

pubilc 을 대신할수있는 메소드들 : protected, default,  private

static 이 있으면 class method, 없으면 instance method

___
0512

# 자바 2 - 객체지향 1 ~ 5 

- 남의 클래스 남의 인스턴스

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class WS {
   public static void main(String[] args) throws IOException {

       System.out.println(Math.PI);
       System.out.println(Math.floor(1.8));
       System.out.println(Math.ceil(1.8));

       FileWriter f1 = new FileWriter("data.txt");
       f1.write("aa");

       FileWriter f2 = new FileWriter("data2.txt");
       f2.write("aa");
       f2.close();
       
       f1.write("bb");
       f1.close();
       
       // class : System, Math, FileWriter
       // instance : f1, f2
    }
}

</code></pre>

- 변수와 메소드

<pre><code>
public class WS {
   public static void main(String[] args) {

       qq = "-----";
       printA();
       printA();
       printB();
       printB();
   }
    public static String qq = "";
    public static void printA() {
        System.out.println(qq);
        System.out.println("A");
        System.out.println("A");
    }

    public static void printB() {
        System.out.println(qq);
        System.out.println("B");
        System.out.println("B");
    }
}

</code></pre>

- 클래스

<pre><code>
class Print{
    public static String qq = "";
    public static void A() {
        System.out.println(qq);
        System.out.println("A");
        System.out.println("A");
    }

    public static void B() {
        System.out.println(qq);
        System.out.println("B");
        System.out.println("B");
    }
}
public class WS {
   public static void main(String[] args) {

       Print.qq = "-----";
       Print.A();
       Print.A();
       Print.B();
       Print.B();

       // 클래스를 이용해 더욱 단정한 코드를 만들 수 있다
   }
}
</code></pre>

여러 클래스를 각각의 java 파일로 만들어 기능별로 쪼개는것도 가능하다.

- 인스턴스

<pre><code>
class Print{
    public  String qq = "";
    public  void A() {
        System.out.println(qq);
        System.out.println("A");
        System.out.println("A");
    }

    public  void B() {
        System.out.println(qq);
        System.out.println("B");
        System.out.println("B");
    }
}
public class WS {
   public static void main(String[] args) {

       Print p1 = new Print();
       p1.qq = "-----";
       p1.A();
       p1.A();
       p1.B();
       p1.B();

       Print p2 = new Print();
       p2.qq = "*****";
       p2.A();
       p2.A();
       p2.B();
       p2.B();
   }
}
</code></pre>

___
0515

# 자바 2 - 객체지향 6 ~ 9

- static

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

- 생성자와 this

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

- 활용

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

___
0516 

# 자바 2 - 상속

- 상속 개념

<pre><code>
class Cal{
    public int sum(int v1, int v2){
        return v1+v2;
    }
}

class Cal3 extends Cal{
}

public  class WS {
    public static void main(String[] args){

        Cal c = new Cal();  
        System.out.println(c.sum(2,1));

        // Cal 클래스를 이용한 계산

        Cal3 c3 = new Cal3();  
        System.out.println(c3.sum(2,1));
        
        // Cal3는 Cal 을 상속하였기에 같은 값이 나옴
    }
}
</code></pre>

- 기능의 개선과 발전 / Overriding, Overloading

<pre><code>
class Cal{
    public int sum(int v1, int v2){
        return v1+v2;
    }
    public int sum(int v1, int v2, int v3){
        return v1+v2+v3;

        // 원래 있던 메소드와 이름이 같지만 형태가 다를때 -> overloading
    }
}
class Cal3 extends Cal{
    public int minus(int v1, int v2){
        return  v1-v2;
    }
    public int sum(int v1, int v2){
        System.out.println("Cal3");
        return v1+v2;

        // 부모가 가진 메소드를 재정의 했다 -> overriding

    }
}

public  class WS {
    public static void main(String[] args){

        Cal c = new Cal();
        System.out.println(c.sum(2,1));

        Cal3 c3 = new Cal3();
        System.out.println(c3.sum(2,1));
        System.out.println(c3.minus(2,1));
        System.out.println(c3.sum(2,1));
    }
}

</code></pre>

- This Super

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

- 상속과 생성자

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

___
0517

# 자바 2 - 인터페이스

- 인터페이스 개념

<pre><code>
interface Calculable{  // 만들 클래스의 메소드 형식을 정한다
    int sum(int v1, int v2);
}
class RealCal implements Calculable{  // 정의된 형식대로 만들어야한다

    public int sum(int v1, int v2) {
        return v1+v2;
    }
}

public class WS {
    public static void main(String[] args){

        RealCal c = new RealCal();
        System.out.println(c.sum(1,2));

    }
}
</code></pre>

- 인터페이스의 형식

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

- 다형성 (Polymorphism)

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
class AdvancedPrint implements Printable{
    public void print() {
        System.out.println("This is RealCal");
    }
}

public class WS {
    public static void main(String[] args){

        Printable c = new AdvancedPrint();  
        // Printable을 가진 클래스를 할당시켜준다면 뭐가 들어오든 ok
        System.out.println(c.sum(1,2));  // X
        c.print();
        System.out.println(c.PI); // X
    }
}
</code></pre>

___