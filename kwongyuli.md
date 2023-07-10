JAVA Boostcourse
=============
2023-05-01 1일차 스터디
-------------

<pre><code>
public class HelloWorldApp {
	public static void main(String[] args) {
		System.out.println("Hello World!!");
	}
}
</code></pre>

- 데스크톱 애플리케이션 만들기

	- 기본 코드

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
                frame.setPreferredSize(new Dimension(400, 300));
                JLabel label = new JLabel("Hello World!!", SwingConstants.CENTER);
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

- 수정해본 코드

<pre><code>
JLabel label = new JLabel("Hello World!!", SwingConstants.CENTER);
</code></pre>

***

2023-05-02 2일차 스터디
-------------

- Datatype.java

<pre><code>
public class Datatype{
	public static void main(String[] args) {
		System.out.println(6); // number
		System.out.println("six"); // String

		System.out.println("6"); // String

		System.out.println(6+6);
		System.out.println("6+6");
		System.out.println("6"+"6");
		// 양 옆에 문자열이 있을 경우는 더하기가 아닌 결합연산자라는 문자열을 위한 연산이 사용된다
		// 문자열은 곱하기 연산자를 사용할 수 없다

		System.out.println(6*6);

		System.out.println("111".length()); // 문자열의 길이를 알려준다
		System.out.println();
	}
}
</code></pre>

- Number.java

<pre><code>
public class Number {

	public static void main(String[] args) {
		// Operator
		System.out.println(6 + 2);
		System.out.println(6 - 2);
		System.out.println(6 * 2);
		System.out.println(6 / 2);

		// method
		// 메소드는 수학과 관련된 자주 사용되는 것들을 그룹핑해 놓은 캐비냇 같은 것
		System.out.println(Math.PI); // 적당한 정밀도로 보여준다
		System.out.println(Math.floor(Math.PI)); // floor는 수학적으로 내림, 뒤에있는 소수점을 자른다
		System.out.println(Math.ceil(Math.PI)); // ceil은 올림, 3.14에서 그 뒤에 값 1을 올림
		System.out.println(Math.ceil(6.77)); // 7.0

	}

}
</code></pre>

- StringApp.java

<pre><code>
public class StringApp {

	public static void main(String[] args) {

		// Character VS String
		System.out.println("Hello World"); // String, 문자열 = character들이 모여있는 것
		System.out.println('A'); // Character, 문자 = 한 글자만 표현할 때
		System.out.println("A"); // String

		// new line
		System.out.println("Hello "
				+ "World"); // 문자열과 문자열을 더한 것
		System.out.println("Hello \nWorld"); // 줄바꿈

		// escape
		// 역슬래쉬를 통해서 그 뒤에 따라오는 어떤 임무가 있는 문자의 임무를 일시적으로 해방시키는 것
		System.out.println("Hello \"World\""); // \"  \"은 Hello "World"

	}

}
</code></pre>

- Variable.java

<pre><code>
public class Variable {

	public static void main(String[] args) {

		/* 변할 수 있는 문자가 변수
		   변수는 데이터 타입을 지정해줘야 한다
		   변수를 만들 때는 그 변수가 어떤 데이터 타입을 담을 수 있는지 명확하게 표현해줘야 한다 */

		// Number -> interger
		int a = 1; // 정수 1
		System.out.println(a);

		// real number -> double
		double b = 1.1; // 실수 1.1
		System.out.println(b);

		// String
		String c = "Hello World!"; // 문자열
		System.out.println(c);

	}

}
</code></pre>

- Letter.java

<pre><code>
public class Letter {

	public static void main(String[] args) {
		String name = "gyuli";
		System.out.println("Hello, "+name+"... "+name+ "... egoing ... bye..");

		double VAT = 10.0; // 부가가치세
		System.out.println(VAT); // 부가가치세율

		/* 코딩을 하는데 있어서 코드는 나도 보지만 내가 아닌 다른 사람도 보는 것이기 때문에
		   코드를 딱 봤을 때 그 의미를 빨리 파악할 수 있도록 작성하는 것이 중요하다
		   이때 사용하는 가장 중요한 수단 중 하나가 수단이고 변수는 값의 이름을 부여하는 것이다
		   그러므로 좋은 이름을 사용해야 한다 */

	}

}
</code></pre>

- Casting.java

<pre><code>
public class Casting {

	public static void main(String[] args) {

		// casting
		// 데이터 타입을 다른 데이터 타입으로 컨버팅하는 것
		double a = 1.1;
		// 자동으로 1이 double형으로 컨버팅 된 것
		// 손실이 일어나지 않기 때문에 가능하기 때문에 가능한 것
		double b = 1; 
		// 수동으로 한 것 (명시적으로 한 것)
		double b2 = (double) 1;
		System.out.println(b);

		// int c = 1.1; 이렇게 하면 0.1을 잃어버리게 된다

		// Change type of 'd' to 'double'
		double d = 1.1;
		// Add cast to 'int'
		// int 형태로 강제로 바꾸겠다
		// 소수점 밑에 있는 것들이 사라져 손실이 일어난다
		// 그래서 자바에서 자동으로 해주지 않는 것
		int e = (int) 1.1;
		System.out.println(e);

		// 1 to String
		String f = Integer.toString(1);
		System.out.println(f);

		// 변수가 갖고있는 값이 어떤 데이터 타입인지 알려준다
		System.out.println(f.getClass());

	}

}
</code></pre>

- StringOperation.java

<pre><code>
public class StringOperation {

	public static void main(String[] args) {

		// 텍스트가 몇 글자인지 세야되는 경우
		System.out.println("Hello World".length()); // 11 글자

		// name을 gyuli로 바꾸어준다
		System.out.println("Hello, name~ bye!".replace("name","gyuli"));
		System.out.println("Hello, [[[name]]]... bye..".replace("[[[name]]]", "gyuli"));

	}

}
</code></pre>

***

2023-05-03 스터디
-------------

- Program.java

<pre><code>
public class Program {

	public static void main(String[] args) {

		System.out.println(1);
		System.out.println(2);
		System.out.println(3);

		// 하나하나의 기능들을 우리가 하고자 하는 일의 취지에 맞게 배치하면 컴퓨터가 이 작업을
		// 순차적으로 진행해주는 것을 통해서 자동화를 할 수 있다
		// 우리는 프로그래밍이 순차적으로 실행되는 것을 이용해
		// 사람이 잘 못 하는 것들을 기계에게 위임해서 자동화 할 수 있다는 효과를 얻을 수 있다
	}

}
</code></pre>

- OkJavaGoInHome.java

<pre><code>
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHome {

	public static void main(String[] args) {

		String id = "JAVA APT 507";

		// Elevator call
		Elevator myElevator = new Elevator(id);
		myElevator.callForUp(1);
		// id는 나의 주소
		// 엘리베이터가 어디에 있는지를 알아야 거기 있는 엘리베이터를 제어할 수 있다
		// 자바 아파트에 있는 엘리베이터가 12번째 문장이다

		// Security off
		Security mySecurity = new Security(id);
		mySecurity.off();

		// Light on
		Lighting hallLamp = new Lighting(id+ " / Hall Lamp");
		hallLamp.on();

		Lighting floorLamp = new Lighting(id+ " / floor Lamp");
		floorLamp.on();

	}

} // 자동화의 열쇠가 프로그래밍이다

</code></pre>

- 디버거

  버그는 우리가 짠 코드의 의도하지 않은 문제를 말한다.

  그 버그를 잡는 행위를 디버깅이라 하고 디버깅을 할 때 사용하는 도구를 디버거라 부른다.

  현대적인 개발 도구들은 내부적으로 디버거를 가지고 있다.

- 프로그램이 실행되는 것을 멈추고 싶을 때:

  멈추고 싶은 곳에서 더블 클릭을 한다 그러면 점이 생기는데 이 점을 breakpoint라 한다.

  그리고 벌레버튼을 누른다.

  그럼 화면 구성이 바뀌고 중지된 상태로 화면이 멈춘다.

  디버거를 이용하면 프로그램을 한줄한줄 실행시킬 수 있고(Step Over) 실행되는 그 순간에 애플리케이션 내의 변수의 상태를 하나하나 체크할 수 있다.

  디버거를 끝내고 싶을 땐 빨간색 버튼의 터미네이터를 클릭하고 우측 상단에 J(java) 버튼을 클릭한다.

***

2023-05-04 4일차 스터디
-------------

- 프로그램은 들어오는 정보인 입력을 처리해서 출력을 만들어내는 기계이다.

- input(입력값):

  Argument(프로그램을 실행할 때 텍스트 정보를 주는 것), File, Network, Audio, Program

- output(결과): Monitor, File, Audio, Program

- OkJavaGoInHomeInput.java

<pre><code>
import javax.swing.JOptionPane;

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHomeInput {
	
	// parameter, 매개변수 = args에 사용자가 입력한 값이 들어올 것이다
	// 문자열 뒤에 대괄호를 붙이면 문자열로만 이루어져 있는 배열이라는 데이터
	public static void main(String[] args) {
		
		// String id = JOptionPane.showInputDialog("Enter a ID");
		String id = args[0];
		//String bright = JOptionPane.showInputDialog("Enter a Bright level");
		String bright = args[1];
		// 창을 만들어낸다

		// Elevator call
		Elevator myElevator = new Elevator(id);
		myElevator.callForUp(1);
		
		// Security off
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		// Light on
		Lighting hallLamp = new Lighting(id+ " / Hall Lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting(id+ " / floor Lamp");
		floorLamp.on();
		
		DimmingLights moodLamp = new DimmingLights(id+ " moodLamp");
		moodLamp.setBright(Double.parseDouble(bright));
		// bright는 String이지만 입력값으로 들어온 문자가 double 형으로 바뀐다
		moodLamp.on();
	}

} 
</code></pre>

- Runconfiguration

  입력값을 줄 때 Arguments에 값을 입력하면 된다.

  여러개의 값을 줄 땐 “입력값1” “입력값2” ...

  Arguments를 입력하게 되면 main 메소드의 args parameter는 argument 값을 받아서 동작한다.

- args

  문자열 배열(array)로 여러 개의 String 데이터가 들어올 수 있다.

  인덱스 0번부터 시작한다. ( args[0] )

- cmd
	- 외부 라이브러리도 포함해서 컴파일하기

	<pre><code>
	javac -cp ";lib" OkJavaGoInHome.java
	</code></pre>

	- 외부 라이브러리도 포함해서 실행하기

	<pre><code>
	java -cp ";lib" OkJavaGoInHome
	</code></pre>

	- 직접 컴파일 실행

	<pre><code>
	javac OkJavaGoInHomeInput.java
	java OkJavaGoInHomeInput "JAVA APT 707" 15.0
	// 띄어쓰기로 파라미터를 구분한다
	</code></pre>
	
***

2023-05-08 5일차 스터디
-------------

- Application Programming Interface

  자바가 기본적으로 제공하는 부품들의 조작방법을 API라 한다.

  Program은 시간의 순서에 따라서 실행된다는 시간이 강조된 표현 (시간의 순서)을 말한다.

  Application은 자바가 제공하는 부품들을 응용해서 Application 해서 만든다는 응용이 강조된 표현을 말한다.

  즉 우리가 자바를 응용해서 프로그래밍적으로 실행되는 프로그램을 만들기 위해서 사용해야 되는 조작 방법을 말한다.

- User Interface

  사용자가 우리가 만든 프로그램을 조작하기 위해 사용하는 조작 장치라는 뜻에서 UI라고 부른다.

  우리가 만든 프로그램을 사용자가 사용하지 않고 또 다른 부품으로 사용될 수도 있다.

- 상속

  java.lang.Object

   java.io.Writer

    java.io.PrintWriter

  PrintWriter(자식)은 Writer(부모)라는 클래스를 상속받았다.

  Wirter(자식)은 Object(부모)를 상속받았다.

  PrintWriter class를 우클릭해서 Open Type Hierarchy 클릭하면 상속관계를 볼 수 있다.

  Object 자바의 가장 기본적인 class이며 모든 class는 Object를 상속 받는다.

- Override

  Writer class에도 write method가 있고, PrintWriter class에도 write method가 있다면 이는 PrintWriter의 write가 Writer의 write를 덮어쓰기 했다고 한다.

  = 오버라이드 했다

- classApp

<pre><code>
public class ClassApp {

	public static void main(String[] args) {
		
		System.out.println(Math.PI);
		System.out.println(Math.floor(1.6)); // 소수점 없애기
		System.out.println(Math.ceil(1.6)); // 소수점 무조건 올리기
		// class는 서로 연관된 변수와 메소드를 모아서 이름을 붙인 것
		// 얘네들은 다 일회용

	}

}
</code></pre>

- InstanceApp

<pre><code>
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.PrintWriter;
public class InstanceApp {

	public static void main(String[] args) throws IOException {
		
		PrintWriter p1 = new PrintWriter("result1.txt");
		// 괄호 안에 내가 저장하고 싶은 파일의 이름을 적는다
		// 저 변수에 담겨있는 무언가를 PrintWriter라는 class의 instance라 한다
		// p1에 아무거나 들어가면 안 되기 때문에
		// PrintWriter라는 class의 instance만 들어간다는 뜻에서 데이터타입을 저것으로 지정
		p1.write("Hello 1");
		p1.close();
		
		PrintWriter p2 = new PrintWriter("result2.txt");
		p2.write("Hello 2");
		p2.close();
		p2.toString();
		
		// 동시에 여러개의 파일을 작업해야 할 땐 하나의 클래스를 사용하는 것보다 하나의 클래스 앞에 new를 붙여
		// 복제하여 각각의 다른 상태를 가지고 있는 인스턴스를 만들어 사용하는 것이 더 효율적이다
		
		// Constructor가 없으면 일회용
		// 이를 이용해 인스턴스를 만드는 것이 허용되어 있다는 것
		// new 뒤에 붙인 것
		// 인스턴스는 p1

	}

}
</code></pre>

- AccountingApp

<pre><code>
public class AccountingApp {

	public static void main(String[] args) {
		
		double vauleOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = vauleOfSupply*vatRate;
		double total = vauleOfSupply+vat;
		double expense = vauleOfSupply*expenseRate;
		double income = vauleOfSupply-expense;
		double dividend1 = income * 0.5;
		double dividend2 = income * 0.3;
		double dividend3 = income * 0.2;
		
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ vat );
		System.out.println("Total : "+ total );
		System.out.println("Expense : "+ expense );
		System.out.println("Income : "+ income );
		System.out.println("Dividend : "+ dividend1 );
		System.out.println("Dividend : "+ dividend2 );
		System.out.println("Dividend : "+ dividend3 );
		
		// Edit -> Find/Replace... 10000.0의 값 전체를 바꿔준다
		// 값 우클릭 -> Refactor -> Extract Local Variable...

	}

}
</code></pre>

- Package

  정리정돈의 도구

  서로 연관된 비슷한 성격의 class를 모아서 이름을 붙인 것

- class

  Package에 속해있는 것들 

  서로 연관된 변수(Variable)와 메소드(method)를 모아서 이름을 붙인 것

***

2023-05-09 6일차 스터디
-------------

- Method와 Class

  메소드는 서로 연관된 코드를 그룹핑해서 이름을 붙인 정리정돈의 상자다

	클래스는 서로 연관된 변수와 메소드를 그룹핑한 것이다 그리고 거기에 이름을 붙인 것이다 역시나 정리정돈의 상자이다

	메소드와 클래스가 중요한 이유는 우리가 소프트웨어를 만들어가는 데 있어서 구조를 결정하기 때문이다

	마치 우리 신체에서 뼈대와 같은 역할을 하는 것이다 = 상당히 중요함!

- AccountingIFApp

<pre><code>
public class AccountingIFApp {

	public static void main(String[] args) {
		
		double vauleOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = vauleOfSupply*vatRate;
		double total = vauleOfSupply+vat;
		double expense = vauleOfSupply*expenseRate;
		double income = vauleOfSupply-expense;
		
		double dividend1;
		double dividend2;
		double dividend3;
		
		if(income>10000.0) {
		 dividend1 = income * 0.5;
		 dividend2 = income * 0.3;
		 dividend3 = income * 0.2;
		} else {
			dividend1 = income * 1;
			dividend2 = income * 0;
			dividend3 = income * 0;
		}
		
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ vat );
		System.out.println("Total : "+ total );
		System.out.println("Expense : "+ expense );
		System.out.println("Income : "+ income );
		System.out.println("Dividend : "+ dividend1 );
		System.out.println("Dividend : "+ dividend2 );
		System.out.println("Dividend : "+ dividend3 );
		

	}

}
</code></pre>

- AccountingArrayApp

<pre><code>
public class AccountingArrayApp {

	public static void main(String[] args) {
		// String[] -> 문자열로 이루어져 있는 배열이라는 뜻
		// 그 배열의 값을 가져올 때 args[0] 이렇게 해서 입력값을 가져왔다
		// = 배열의 값을 꺼내오는 것을 보여주는 것이다
		
		double vauleOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = vauleOfSupply*vatRate;
		double total = vauleOfSupply+vat;
		double expense = vauleOfSupply*expenseRate;
		double income = vauleOfSupply-expense;
		
		//double rate1 = 0.5;
		//double rate2 = 0.3;
		//double rate3 = 0.2;
		
		double[] dividendRates = new double[3];
		dividendRates[0] = 0.5;
		dividendRates[1] = 0.3;
		dividendRates[2] = 0.2;
		// 서로 연관된 데이터를 정리정돈 하는 수단이 배열이다
		// 배열과 반복문은 서로 같이 쓸 때 엄청난 시너지 효과를 가져온다
		
		double dividend1 = income * dividendRates[0];
		double dividend2 = income * dividendRates[1];
		double dividend3 = income * dividendRates[2];
		
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ vat );
		System.out.println("Total : "+ total );
		System.out.println("Expense : "+ expense );
		System.out.println("Income : "+ income );
		System.out.println("Dividend : "+ dividend1 );
		System.out.println("Dividend : "+ dividend2 );
		System.out.println("Dividend : "+ dividend3 );
		

	}

}
</code></pre>

- AccountingArrayLoopApp

<pre><code>
public class AccountingArrayLoopApp {

	public static void main(String[] args) {
		
		double vauleOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = vauleOfSupply*vatRate;
		double total = vauleOfSupply+vat;
		double expense = vauleOfSupply*expenseRate;
		double income = vauleOfSupply-expense;
		
		System.out.println("Value of supply : "+vauleOfSupply);
		System.out.println("VAT : "+ vat );
		System.out.println("Total : "+ total );
		System.out.println("Expense : "+ expense );
		System.out.println("Income : "+ income );
		
		double[] dividendRates = new double[3];
		dividendRates[0] = 0.5;
		dividendRates[1] = 0.3;
		dividendRates[2] = 0.2;
		
		int i = 0; // 몇 번 반복됐는지
		while(i < dividendRates.length) {
			System.out.println("Dividend : "+ (income*dividendRates[i]) );
			i = i + 1; // 반복할 때마다 i의 값을 1씩 증가시킬 것이다
		}
		
		// while은 반복문의 키워드이고 중괄호 안에 있는 코드가 계속해서 반복되게 하는 것이다
		// dividendRates.length의 값은 3
		// 배열과 단짝이다

	}

}
</code></pre>

- AccountingMethodApp

<pre><code>
public class AccountingMethodApp {
	
	public static double vauleOfSupply;
	public static double vatRate;
	public static double expenseRate;
	// 메인 메소드 밖에서 선언되었기 때문에 전역변수이다
	// 메인 안에서도 접근할 수 있고 getVAT도 접근할 수 있다
	// 즉 모든 메소드에서 접근할 수 있다
	// 우클릭 -> refactor -> Convert Local Variable to Field...

	public static void main(String[] args) {
		
		vauleOfSupply = 10000;
		vatRate = 0.1;
		expenseRate = 0.3;
		
		print();
		
		// vauleOfSupply는 main 메소드 중괄호 안에서 선언되었기 때문에 메인 메소드 안에서만 사용할 수 있는
		// 지역변수 (local variable) 이다

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
	} // 메소드를 만드는 코드

}

// 메소드는 서로 연관된 코드를 정리정돈 하는 상자다
</code></pre>

- AccountingClassApp

<pre><code>
class Accounting { // class 는 파일로 치면 디렉토리 역할과 비슷하다
	
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
		
		//Accounting.vauleOfSupply = 10000;
		//Accounting.vatRate = 0.1;
		//Accounting.expenseRate = 0.3;
		//Accounting.print();
		// 상태 = 변수의 값을 말한다
		// 이 과정이 빈번하게 발생한다면 클래스의 내부적인 상태를 바꾸는 행위가 버그를 유발할 가능성이 굉장히 높아진다
		
		// instance
		Accounting a1 = new Accounting();
		// new를 붙이면 Accounting class를 복제하는 명령이다
		// a1의 변수의 값으로는 Accounting의 복제본만 들어올 수 있다
		a1.vauleOfSupply = 10000.0;
		a1.vatRate = 0.1;
		a1.expenseRate = 0.3;
		a1.print();
		// class 이름 앞에 new를 붙여서 만들어진 그 무엇을 instance라 부른다
		// 이 코드가 동작하기 위해선 static 키워드를 사용하면 안 된다
		System.out.println("------------------------");
		
		Accounting a2 = new Accounting();
		a2.vauleOfSupply = 20000.0;
		a2.vatRate = 0.05;
		a2.expenseRate = 0.2;
		a2.print();

	}
	
	// 소속관계를 명확하게 해야 다른 취지의 코드들과 뒤섞여도 상관없고, 흔한 이름의 메소드를 사용해도 같은 이름의 메소드들이
	// 공존할 수 있게 된다 ( class가 달라야 한다 )

}
</code></pre>

- instance

  인스턴스는 하나의 클래스를 복제해서 서로 다른 데이터의 값과 서로 같은 메소드를 가진 복제본을 만드는 것이다
	
- Outline

  class 안에 소속되어 있는 여러 가지 멤버들(변수, 메소드)의 리스트를 보여준다

  (Window -> showview)

***

2023-05-10 7일차 스터디
-------------

- BooleanApp

<pre><code>
package java_flow_control;

public class BooleanApp {

	public static void main(String[] args) {
		
		System.out.println("One");
		System.out.println(1);
		
		System.out.println(true);
		System.out.println(false);
		
		String foo = "Hello World";
		// String true = "Good";
		// true, false는 변수의 이름으로 사용할 수 없다
		// 이미 쓰이고 있는 컴퓨터 언어
		// = reserved word
		
		System.out.println(foo.contains("World")); // true
		// .contains는 그 문자열에 입력값으로 전달할 어떠한 값이 들어있다면 true를 return하고,
		// 없다면 false를 return 한다
		System.out.println(foo.contains("egoing")); // false

	}

}
</code></pre>

- ComparisonOperatorApp

<pre><code>
package java_flow_control;

public class ComparisonOperatorApp {

	public static void main(String[] args) {
		
		System.out.println(1 > 1); // false
		System.out.println(1 == 1); // true
		System.out.println(1 < 1);
		System.out.println(1 >= 1);
		System.out.println(1 <= 1);
		
		// 비교연산자는 왼쪽에 있는 값과 오른쪽에 있는 값을 비교해서 그 결과가 무엇이냐에 따라서
		// true or false 둘중 하나의 값을 만들어내는 연산자이다
	}

}
</code></pre>

- IfApp

<pre><code>
package java_flow_control;

public class IfApp {

	public static void main(String[] args) {
		
		System.out.println("a");
//		if(false) {
//			System.out.println(1);
//		} else {
//			if(true) {
//			System.out.println(0);
//			} else {
//				System.out.println(00);
//			}
//		}
		
		if(false) {
			System.out.println(1);
		} else if (true) {
			System.out.println(2);
		} else {
			System.out.println(3);
		}
		
		System.out.println("b");
		
		// if문 () 안에는 boolean만이 저 값이 될 수 있다
		// () 안의 값이 true일 때만 실행된다
		// 변화 가능하도록 바꾸어야 한다
	}

}
</code></pre>

- AuthApp

<pre><code>
package java_flow_control;

public class AuthApp {

	public static void main(String[] args) {
		
		System.out.println(args[0]);
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "lk3374";
		String inputPass = args[1];
		
		
		System.out.println("Hi !");
		
		// if(inputId == id) {
//		if(inputId.equals(id)) {
//			if(inputPass.equals(pass)) {
//				System.out.println("Master !!");
//			} else {
//				System.out.println("Wrong pass..");
//			}
//		} else {
//			System.out.println("Who are you?");
//		}
		
		if(inputId.equals(id) && inputPass.equals(pass)) {
			System.out.println("Master !!");
		} else {
			System.out.println("Who are you??");
		}
		
	}

}
</code></pre>

- 산술 연산자

  1 + 1 = 2 여기서 +은 산술연산자

- 결합 연산자

  “1” + “1” = “11” 여기서 +은 결합연산자 (문자열을 만들어내는 연산자)

- primitive (데이터 타입)

  원시라는 뜻으로, 더 이상 쪼갤 수 없는 데이터를 말한다

	primitive = boolean, int, double, short, long, float, char

	non primitive = String, Array, Date, File, Class ...

- LogicalOperatorApp

<pre><code>
package java_flow_control;

public class LogicalOperatorApp {

	public static void main(String[] args) {
		
		// AND
		System.out.println(1 == 1);
		System.out.println(true && true); // true
		// logical 연산자는 좌항과 우항 모두 boolean이 와야한다
		System.out.println(true && false); // false
		System.out.println(false && true); // false
		System.out.println(false && false); // false
		
		// OR
		System.out.println(true || true); // true
		System.out.println(true || false); // true
		System.out.println(false || true); // true
		System.out.println(false || false); // false
		
		// NOT
		System.out.println(!true); // false
		System.out.println(!false); // true

	}

}
</code></pre>

- AuthApp2

<pre><code>
package java_flow_control;

public class AuthApp2 {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "lk3374";
		String pass2 = "lk5332";
		String inputPass = args[1];
		
		
		
		System.out.println("Hi !");
		
		boolean isRight = (inputPass.equals(pass) || inputPass.equals(pass2));
		
		
		if(inputId.equals(id) && isRight) {
			System.out.println("Master !!");
		} else {
			System.out.println("Who are you??");
		}
		
	}

}
</code></pre>

- LoopApp

<pre><code>
package java_flow_control;

public class LoopApp {

	public static void main(String[] args) {
		
		System.out.println(1);
		
		int i = 0; // 어떤 변수 이름을 써도 되지만, 반복문에서 카운팅하기 위해 i를 쓴다
		while(i < 3) {
			System.out.println(2);
			System.out.println(3);
			// i = i + 1;
			i++;
		}
		
		System.out.println("----------------------------------");
		
		// 괄호 안에는 boolean
		// 디버거 F6번 사용 (다음줄 실행)
		
		// 몇번 반복해 ~ 라고 시킬 땐 for문이 더 좋다
		// 괄호 안에 초깃값 설정, boolean, 반복이 실행될 때마다 +
		for(int j = 0; j < 3; j++) {
			System.out.println(2);
			System.out.println(3);
		}
		// 무조건 한번은 실행된다
		
		System.out.println(4);

	}

}
</code></pre>

- ArrayApp

<pre><code>
package java_flow_control;

public class ArrayApp {

	public static void main(String[] args) {
		
		// egoing, jinhuck, youbin
		// String users = "egoing, jinhuck, youbin";
		String[] users = new String[3]; // 배열의 크기 3 (3칸짜리 캐비닛)
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		// 문자열로 이루어져 있는 배열이라고 하는 데이터 타입을 값으로 하는 users라고 하는 변수를 만드는 것
		
		System.out.println(users[1]);
		System.out.println(users.length); // 배열에 담겨있는 값이 3개다
		// = 3칸짜리 배열이다
		
		// 배열을 생성할 때 값을 담아서 생성하는 방법
		int[] score = {10, 100, 100};
		System.out.println(score[0]);
		System.out.println(score.length);
		
		// 0,1,2 -> index
		// "egoing"... -> element, 원소

	}

}
</code></pre>

- LoopArray

<pre><code>
package java_flow_control;

public class LoopArray {

	public static void main(String[] args) {
		
		/*
		 * <li>egoing</li>
		 * <li>jinhuck</li>
		 * <li>younin</li>
		 */
		
		String[] users = new String[3]; 
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		
		for(int i = 0; i < 3; i++) {
			System.out.println("<li> " + users[i] +" </li>");
		}
		
		for(int i = 0; i < users.length; i++) {
			System.out.println(users[i] +",");
			if(i==2) {
				System.out.println(users[i]);
			}
		}
	}
}
</code></pre>

***

2023-05-11 8일차 스터디
-------------

- AuthApp3

<pre><code>
package java_flow_control;

public class AuthApp3 {

	public static void main(String[] args) {
		
		// String[] users = {"egoing", "jinhuck", "youbin"};
		String[][] users = {
				{"egoing", "1111"},
				{"jinhuck", "2222"},
				{"youbin", "3333"}
		}; // 각각의 원소가 배열이고, 그 배열의 값이 String인 데이터를 만든 것이다
		
		String inputId = args[0];
		String inputpass = args[1];
		
		boolean isLogined = false;
		for(int i=0; i<; i++) {
			String[] current = users[i];
			if(current[0].equals(inputId) && current[1].equals(inputpass)) {
				isLogined = true;
				break;
			}
		}
		
		System.out.println("Hi !!");
		if(isLogined) {
			System.out.println("Master ~~");
		} else {
			System.out.println("Who are you?");
		}

	}

}
</code></pre>

- FirstMethod

<pre><code>
public class FirstMethod {

	public static void main(String[] args) {
		
		System.out.println("Hello Method"); // println도 method
		System.out.println(Math.floor(1.1)); // 1.0

	} 
	// main이라는 method
	// 자바 애플리케이션을 만들 때는 class를 만들어야 하고
	// class를 실행시킬 때는 반드시 약속된 이름인 main이라고 하는 특수한 이름의 method를 정의해 놓으면
	// first method를 실행해주라는 명령을 받으면 main이라는 method를 실행하도록 약속되어 있다

}
</code></pre>

- WhyMethod

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class WhyMethod {
	
	public static void main(String[] args) throws IOException {
		// main은 method이고 얘는 약속이고, 얘가 있어야 자바는 main을 호출해 프로그램을 실행시킨다
		// String[]은 서로 연관된 문자열을 그룹핑하는 문자열 배열이다
		// args는 main이라고 하는 method를 자바가 실행할 때 입력해주는 입력값이 args를 통해 들어온다
		
		printTwoTimes("a", "-");
		printTwoTimes("b", "*");
		// 한줄짜리더라도 메소드를 만드는 것은 좋은 습관이다
		// a, b
		// 함수 안으로 주입한 구체적인 값
		// = 인자 = argument
		System.out.println(twoTimes("a", "-"));
		FileWriter fw = new FileWriter("out.txt");
		fw.write(twoTimes("a", "*"));
		fw.close();
		// Email.send("egoing@a.com", "two times a", "twoTimes("a", "$"));

	}

	public static void printTwoTimes(String text, String delimiter) {
		
		System.out.println(delimiter);
		System.out.println(text);
		System.out.println(text);
		
	}
	// 코드 우클릭 Refactor -> Extract Method...
	// 메소드의 괄호 안에 들어오는 첫번째 값은 반드시 String
	// 그리고 그렇게 들어온 값은 이 중괄호 안에서 text라는 이름의 변수의 값이 된다 
	
	// text, delimiter
	// 이러한 변수들은 메소드 밖에서 메소드를 사용하는 쪽에서 주입한 값을 메소드 안으로 흘려보내주는 매개자다
	// = 매개변수 = parameter
	
	public static String twoTimes(String text, String delimiter) {
		String out = "";
		out = out + delimiter + "\n";
		out = out + text + "\n";
		return out;
	} // 화면에 출력하는 기능을 빼버리고 return 값을 가지고 있기 때문에 활용도가 높다

}
</code></pre>

- OutputMethod

<pre><code>
public class OutputMethod {
	
	public static String a() {
		// ...
		return "a";
		// return을 쓰게되면 a라는 method는 return 뒤의 값이 된다
		// 그때 return할 값의 데이터 타입이 문자열이면 void가 아니라 String을 써야한다
		// a라는 method는 output이 String이다
	}
	
	public static int one() {
		// ...
		return 1;
	}
	// method의 output!
	// 그 method의 return 값 뒤에 있는 값이 method의 실행 결과가 된다
	// 그리고 return 값은 그 method를 종료시키는 역할도 한다
	// method는 그 method return 값이 어떤 데이터 타입인지 정의해줘야 한다
	// void는 return 값이 없는 method이다

	public static void main(String[] args) {
		
		System.out.println(a());
		System.out.println(one());

	}

}
</code></pre>

- 객체 지향 프로그래밍 (Object Oriented Programming)

  서로 연관된 메소드와 변수를 그룹핑 해서 이름을 붙인 것 = class

	class를 복제해서 서로 다른 내부적인 상태를 갖고있는 복제본들 = instance

	class와 instance를 포괄적으로 객체라고 생각하기

	이 객체를 뼈대로 하는 프로그램을 만들어가는 프로그래밍 방법론을 OOP

- static

  static이라는 키워드가 붙은 method는 class의 method이다

	static이 없는 method는 instance의 method다

- AccountingApp

<pre><code>
public class AccountingApp {
	
	// 공급가액
	public static double valueOfSupply = 10000.0; // 전역변수
			
	// 부가가치세율
	public static double vatRate = 0.1; // 전역변수
	
	public static double getVAT() {
		return valueOfSupply * vatRate;
	}
	
	public static double getTotal() {
		return valueOfSupply + getVAT();
	}
	

	public static void main(String[] args) {
		
		// 부가세
		//double vat = valueOfSupply * vatRate;
		// double vat = getVAT();
		// 합계
		// double total = valueOfSupply + vat;
		// double total = getTotal();
		
		System.out.println("Vaule of supply :" +valueOfSupply);
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : " +getTotal());

	}

}
</code></pre>

- AccessLevelModifiersMethod

<pre><code>
class Greeting{
	public static void hi() {
		System.out.println("Hi");
	}
} // 다른 class 안에 소속된 method

public class AccessLevelModifiersMethod {
	// public에는 다른 값이 올수도 있다
	// public protected, default(생략), private
	
	// private = 같은 class 안에서만 사용할 수 있다

	public static void main(String[] args) {
		
		Greeting.hi();

	}

}
</code></pre>

- staticMethod

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
	// this.delimiter은 t1 인스턴스의 변수의 값으로 지정한 "-"
	
	public static void c(String delimiter) {
		System.out.println(delimiter);
		System.out.println("c");
		System.out.println("c");
	}
}

public class staticMethod {

	public static void main(String[] args) {
//		Print.a("-");
//		Print.b("-");
		// 여기 a,b는 class은 Print 소속으로 실행되는 것
		// 하지만 method가 class의 소속일 때는 static이 있어야 한다
		
		// 분신이 아니라 instance
		Print t1 = new Print(); // 데이터타입이 Print인 변수에 담았다, t1은 Print class의 분신
		t1.delimiter = "-"; // t1이라고 하는 Print의 분신은 내부적으로 구분자의 값이 -가 된다
		t1.a(); // 구분자를 추가하지 않아도 똑같은 동작이 된다
		t1.b();
		// a와 b는 t1이라는 instance 소속으로 실행되는 것
		// method가 instance 소속일 때는 static을 빼줘야 한다
		// t1 instance는 내부적으로 delimiter라고 하는 변수의 값을 공유하고 있다
		Print.c("$");
		
//		Print.a("*");
//		Print.b("*");
		// 이 두가지는 성격이 비슷하기 때문에 이 method들을 그룹핑하는 정리정돈의 도구 class를 이용
	}

}
</code></pre>

***

2023-05-12 9일차 스터디
-------------

- procedural programming

  method = function = subroutine = procedural = procedural programming

	-> 절차지향 프로그래밍

- oriented programming

  class(method, variable)를 중심으로 프로그램의 구조를 만들어가는 컴퓨터 프로그래밍 방법론

	-> 객체지향 프로그래밍

- instance

  복제된 것의 원형을 class라 하고, 저 원형인 class를 복제한 복제본 하나하나를 instance라 할 수 있다

- new

  class를 복제할 때 사용하는 키워드

- OthersAppOPP

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class OthersAppOOP {

	public static void main(String[] args) throws IOException {
		// class : System, Math, FileWriter
		// instance : f1, f2
		
		System.out.println(Math.PI); // Math는 class, PI는 variable
		System.out.println(Math.floor(3.14)); // floor, ceil은 method
		System.out.println(Math.ceil(3.14)); // 일회용 같은 애들
		
		FileWriter f1 = new FileWriter("data.txt"); // 어떤 정보를 파일에 기록할 때 사용하는 class
		// new를 적음으로써 뒤에 따라오는 class는 data.txt에 파일을 저장하겠다는 상태를 가지고
		// FileWriter의 복제본이 생성된다
		f1.write("Hello"); // FileWriter의 instance가 생성됨
		f1.write(" JAVA"); // instance의 메소드를 호출하는 것을 통해서 그 인스턴스를 조작할 수 있게됐다
		f1.close(); // 파일 작업을 끝냈다는 뜻
		
		FileWriter f2 = new FileWriter("data2.txt");
		f2.write("Hello !");
		f2.close();

	}

}
</code></pre>

- MyOpp

<pre><code>
//public class MyOOP {
//
//	public static void main(String[] args) {
//		delimiter = "------";  // method 안에서 정의된 변수는 그 method 안에서만 사용할 수 있다
//		printA();
//		printA();
//		
//		printB();
//		printB();
//		
//		delimiter = "******";
//		printA();
//		printA();
//		
//		printB();
//		printB();
//	}
//	
//	public static String delimiter = "";
//
//	public static void printA() {
//		System.out.println(delimiter);
//		System.out.println("A");
//		System.out.println("A");
//	}
//	
//	public static void printB() {
//		System.out.println(delimiter);
//		System.out.println("B");
//		System.out.println("B");
//	}
//
//}
</code></pre>

- MyOPP2

<pre><code>
public class MyOOP2 {

	public static void main(String[] args) {
		Print p1 = new Print();
		p1.delimiter = "@@@@@@@@@";
		p1.A();
		p1.A();
		p1.B();
		p1.B();
		// 인스턴스화한 p1은 독립된 존재이기 때문에 중복된 코드를 작성할 필요가 없다
		// 돌려막기할 필요가 없다 = 중복을 없앰
		// 각각의 복제본은 서로 내부적으로 다른 데이터를 유지하게 한다
		// (delimiter가 다르다)
		
		Print p2 = new Print();
		p2.delimiter = "&&&&&&&&&";
		p2.A();
		p2.A();
		p2.B();
		p2.B();
		
	}
	// 이렇게 하고 컴파일(저장)했을 때 .class 파일이 생성된다
	// 하나의 파일 안에서 class를 여러개를 만들면 그 각각의 클래스가 파일로써 존재하게 된다
	
}
</code></pre>

- Print

<pre><code>
class Print{
	public String delimiter = "";
	// static은 static 뒤에 따라오는 String이 class의 소속이라는 것

	public void A() {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	} // class 키워드를 사용해서 class의 이름을 정하고, 중괄호 안에 class 소속인 변수,메소드(멤버)를 담아주면 된다
	
	public void B() {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
	// 소스코드를 만들면 소스코드 이름과 똑같은 class를 하나 만드는 것
	// 그러면 소스코드를 컴파일 해서 실행시키게 되면 자바는 저 파일의 이름과 똑같은 class를 찾아서
	// 그 class의 main method를 실행하도록 약속되어 있다
	// 이렇게 만든 class는 앞에 public(접근 제어자)을 붙여야 한다
	// public은 한 번만 등장한다
	
	// Refactor -> Move Type to New File... -> 
	// Type = 데이터 타입, class = 데이터 타입과 같은 표현이라 생각하기
}
</code></pre>

***

2023-05-15 10일차 스터디
-------------

- StaticApp

<pre><code>
class Foo{
	public static String classVar = "I class var"; // 변수
	public String instanceVar = "I instance var"; // 변수
	public static void classMethod() {
		System.out.println(classVar);
		// class method 안에서는 class variable에 접근이 가능하다
		// System.out.println(instanceVar);
		// instance variable에는 접근할 수 없다
	}
	public void instanceMethod() {
		System.out.println(classVar);
		System.out.println(instanceVar); 
		// 모두 접근 가능하다
	}
}

public class StaticApp {

	public static void main(String[] args) {
		System.out.println(Foo.classVar); // ok
		// System.out.println(Foo.instanceVar); // error
		// class를 통해서는 당연히 class variable에 접근이 가능하지만
		// instance는 instance를 통해서 사용할 수 있도록 고안된 variable이다
		Foo.classMethod();
		// Foo.instanceMethod();
		// instanceMethod는 instance 소속이기 때문에 class를 통해서 접근하는 것은 금지되어 있다
		
		Foo f1 = new Foo();
		Foo f2 = new Foo();
		// f1은 class를 원형으로 하기 때문에 class에 있는 여러가지 멤버들을 복제해온다
		// 실제값이 존재하지 않고 Foo라고 하는 class를 가리키고 있을 뿐이다
		// instanceVar라고 하는 변수가 생성되면서 class의 값도 세팅되어 있다면 이 값까지 복제된다
		// 이 둘은 링크되어 있지 않기 때문에 instance f1의 값을 바꾼다고 해서 class Foo instanceVar의 값이 바뀌진 않는다 
		
		// 하지만 instance f1의 classVar 값을 바꾸면 class Foo의 classVar 값이 바뀐다 (반대로 해도 바뀜)
		// 메소드는 서로 독립된 존재이다
		// class의 변수를 바꾸면 모든 instance의 변수의 값이 바뀐다
		// instance에서 class 변수를 바꿀수도 있는데 그렇게 되면 class의 변수가 바뀌고
		// 걔를 사용하고 있는 모든 instance의 값도 바뀐다
		
		System.out.println(f1.classVar);
		System.out.println(f1.instanceVar);
		
		f1.classVar = "changed by f1";
		System.out.println(Foo.classVar); // changed by f1
		System.out.println(f2.classVar); // changed by f1
		
		f1.instanceVar = "changed by f1";
		System.out.println(f1.instanceVar); // changed by f1
		System.out.println(f2.instanceVar); // I instance var
	}

}
</code></pre>

- MyOOp2

<pre><code>
public class MyOOP2 {

	public static void main(String[] args) {
		Print p1 = new Print("----");
		p1.A();
//		p1.A();
//		p1.B();
//		p1.B();
//		
//		Print p2 = new Print();
//		p2.delimiter = "&&&&&&&&&";
//		p2.A();
//		p2.A();
//		p2.B();
//		p2.B();
		
	}
	
}
</code></pre>

- Print

<pre><code>
class Print{
	public String delimiter = "";
	public Print(String delimiter) {
		this.delimiter = delimiter;
	}
	
	public void A() {
		System.out.println(this.delimiter);
		System.out.println("A");
		System.out.println("A");
	} 
	
	public void B() {
		System.out.println(this.delimiter);
		System.out.println("B");
		System.out.println("B");
	}
	
}
</code></pre>

- 자바에서의 class는 생성자라고 하는 아주 특수한 method를 구현할 수 있는 기능을 우리에게 제공하고 이의 주요한 작업은 초기화이다

- class와 똑같은 이름의 method를 정의하면 이것이 생성자(+매개변수)이다

  우리가 instance를 생성할 때 자바는 이 class와 동일한 이름의 method가 있다면 그 method를 호출하도록 약속되어 있기 때문에
	
	우리는 그 class가 instance화 될 때 실행돼야 될 코드를 construct method 안에 정의하는 것을 통해서 초기화의 목적을 달성할 수 있다

- 생성자는 static이나 return 데이터 타입을 지정하지 않는다

- 만약 instance delimiter 변수와 생성자의 delimiter 매개변수를 똑같이 하면 instance 변수가 실행된다

  = 이런 경우엔 this를 붙여주면 된다

  this는 그 class가 instance화 되었을 때 우리가 생성한 instance를 가리키는 이름이다

- class의 상태가 계속해서 바뀌어야 하는 상황에선 instance

  instance마다 고유한 상태를 주게되면 독립된 instance를 제어할 수 있게된다

- AccountingApp

<pre><code>
class Accounting{
	public double valueOfSupply; // this.valueOfSupply	
	public static double vatRate = 0.1;
	// 부가가치세율은 어떤 instance건 간에 동일하기 때문에 class 소속인 static으로 내버려두는 것이 더 좋을 수 있다
	// 컴퓨터 자원 절약(메모리), 유지보수 편이성(한번에 값이 다 바뀐다)
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
		
		System.out.println("Vaule of supply :" +a1.valueOfSupply);
		System.out.println("Vaule of supply :" +a2.valueOfSupply);
		
		System.out.println("VAT : "+a1.getVAT());
		System.out.println("VAT : "+a2.getVAT());
		
		System.out.println("Total : " +a1.getTotal());
		System.out.println("Total : " +a2.getTotal());
		
//		Accounting.valueOfSupply = 10000.0;
//		System.out.println("Vaule of supply :" +Accounting.valueOfSupply);
//		System.out.println("VAT : "+Accounting.getVAT());
//		System.out.println("Total : " +Accounting.getTotal());

	}
}
</code></pre>

- Parent

<pre><code>
class Parent {
	
	public void method1() {
		//..
	}

}
</code></pre>

- Childe

<pre><code>
class Child extends Parent{
	// Child class는 Parent class를 상속(inheritance)받게 된다
	
	public void method2() {
		//..
		// Parent method1을 수정하면 얘를 상속받는 모든 자식들의 method1이 수정된다
	}

}
</code></pre>

- Contract

<pre><code>
interface Contract {
	
	public String method1(String param);
	public int method2(int param);
	
}
</code></pre>

- Contract1

<pre><code>
class Concreate1 implements Contract {
	
	public String method1(String param) {
		return "foo";
	}
	
	public int method2(int param) {
		return 1;
	}

}
</code></pre>

- 규격

  어떻게 구현했는지는 상관 없고 얘가 어떤 값을 뱉어주는지, 어떤 값을 입력하는 지만 신경쓴다

- interface

  method의 이름, parameter return 값의 형식은 적지만 실제 내용은 적지 않는다

  implement에서 interface에 적혀있는 method들의 형식을 구현해야 된다

  interfac에 적혀있는 형태의 method를 구체적으로 구현해야 하는 책임을 implement가 맡게 된다

- package

  같은 이름의 class가 존재하기 위해서는 서로 다른 package에 담는다.

	com.company1.Foo
	
  com.company2.Foo

***

2023-05-16 11일차 스터디
-------------

- inheritanceApp

<pre><code>
class Cal{
	public int sum(int v1, int v2) {
		return v1+v2;
	}
	// Overloading, 자식이 가질수도 있다, 딱히 상속과는 상관이 없다
	public int sum(int v1, int v2, int v3) {
		return this.sum(v1,v2)+v3;
		// sum은 이미 자기자신이 가지고 있는 sum의 기능을 그대로 내부적으로 가지고 있는 것이다
		// this는 자기자신을 나타내고,특히나 인스턴스를 말한다
	}
}

class Cal3 extends Cal{
	public int minus(int v1, int v2) {
		return v1-v2;
	}
	public int sum(int v1, int v2) {
		System.out.println("Cal3 !!");
		return super.sum(v1,v2);
		// super은 부모 class의 sum을 가리킨다
	} 
	// 부모가 갖고있지 않은 method를 추가했고, 
	// 부모가 가지고 있는 method를 재정의(덮어쓰기)했다 = Overriding 
}

public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 5));
		System.out.println(c.sum(2, 1, 1));
		
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));
		System.out.println(c3.minus(2, 1));
		System.out.println(c3.sum(70, 99, 2));
	}

}
</code></pre>

- inheritanceApp

<pre><code>
class Cal{
	int v1,v2;
	Cal(int v1, int v2){
		System.out.println("Cal init !!");
		this.v1 = v1; 
		this.v2 = v2;
	}
	public int sum() {
		return this.v1+v2;
	}
}

class Cal3 extends Cal{
	Cal3(int v1, int v2) {
		super(v1, v2);
		System.out.println("Cal3 init !!");
		// super는 부모 class(의 생성자)
	}
	// 상속받은 class의 부모가 생성자가 있다면 자식은 반드시 부모 생성자를 실행시키도록 강제하고 있다
	public int minus() {
		return this.v1-v2;
	}
}

public class InheritanceApp {
	public static void main(String[] args) {
		Cal c = new Cal(2,1);
		Cal3 c3 = new Cal3(2,5);
		System.out.println(c.sum()); // 3
		System.out.println(c3.minus()); // -3
		System.out.println(c3.sum()); // 7
	}
}
</code></pre>

- 상속

  상속은 어떤 class가 있을 때 그 class가 가지고 있는 변수와 메소드를 확장해서 상속해서 다른 class가 갖도록 하는 것을 통해서 재사용성을 높이고,

	유지보수 편이성을 높이고, 가독성을 높이고, 코드의 양을 줄일 수 있다.

- Polymorphism

  상속을 하면 기능이 급격히 늘어나고 class들 간에 호환성이 굉장히 떨어지며 class를 다른 class로 교체하는 것이 어려워진다 

  이런 맥락에서 자식 class를 부모 class로써 동작하도록 규제하는 테크닉이 다형성이다

- Access Modifiers

  public

  default

  protected

  private

  = 접근제어자

  class, method, variable을 사용자들이 아무나 건드리지 못하게 제한하는 기능이다

  사용자에게 제공하려고 하는 조작장치만 손댈 수 있게하고 그 외에는 하지 못하도록 규제하는 것이다

- Final

  우리가 만든 class 다른 사람이 더 이상 상속하지 못하도록 하고 싶을 때, 

  또 메소드를 오버라이딩 하지 못하게 하고 싶을 때,

  변수를 마음대로 수정하지 못하게 규제하고 싶을 때

- Abstract

  class를 상속해서 사용하려는 사용자에게 어떤 특정한 메소드는 꼭 구현하라고 강제하고 싶을 때
	
  이 기능을 이용하면 상속자가 직접 구현해야 하는 기능을 구현토록 강제할 수 있다.

***

2023-05-18 13일차 스터디
-------------

- error => 숙명

  자바 애플리케이션이 동작하는 환경에서 문제가 생긴 것
	
  ex 메모리 부족, 운영체제 문제 발생으로 인한 프로그램 정지, 컴퓨터 전원이 꺼짐

- exception(예외)

  파일이 있는 줄 알았는데 없을 때, 사용자가 예상하지 못했던 값을 입력해서 예외적인 상황이 발생했을 때

- 예외 발생시

  에러만 출력해주고 나머지 실행을 계속한다면 심각한 문제가 발생할수도 있다

  에러가 발생했을 때 어떤 코드를 실행하도록 해서 그 코드가 예외적 상황에 대응할 수 있는 코드가 동작하게 해주는 것이 예외를 처리하는 방법이다

- ExceptionApp

<pre><code>
public class ExceptionApp {
	public static void main(String[] args) {
		int[] scores = {10,20,30};
		System.out.println(scores[0]);
		try {
			System.out.println(scores[3]);
		} catch(ArrayIndexOutOfBoundsException e) {
			System.out.println("ArrayIndexOutOfBoundsException.");
		}
		// 배열의 울타리 밖에 있는 값을 가져오려고 한다
		System.out.println(1);
		try {
			System.out.println(2/0);
			// java에선 0으로 나눈 것을 허용하지 않는다
		} catch(ArithmeticException e) {
			System.out.println("ArithmeticException.");
		} 
		// ArithmeticException 발생시 실행되는 코드
		// try catch를 하지 않으면 여기서 프로그램이 멈춘다
		
		
		try {
			System.out.println(1);
			System.out.println(2/0);
			System.out.println(2);
			System.out.println(scores[3]);
			System.out.println(3);
		} catch(ArithmeticException e) {
			System.out.println("ArithmeticException.");
		} catch(ArrayIndexOutOfBoundsException e) {
			System.out.println("ArrayIndexOutOfBoundsException.");
		}
		System.out.println(4);
		// 이런 경우엔 1, ArithmeticException, 4만 출력되고 그 아래는 출력이 되지 않는다
	}
}
</code></pre>

- ExceptionApp 수정

<pre><code>
public class ExceptionApp {
	public static void main(String[] args) {
		int[] scores = {10,20,30};
		System.out.println(scores[0]);

		try {
			System.out.println(1);
			System.out.println(2/0);
			System.out.println(2);
			System.out.println(scores[3]);
			System.out.println(3);
		} catch(Exception e) {
			System.out.println("error.");
		}
		System.out.println(4);
		
		try {
			System.out.println(1);
			System.out.println(2/0);
			System.out.println(2);
			System.out.println(scores[3]);
			System.out.println(3);
		} catch(ArithmeticException e) {
			System.out.println("ArithmeticException.");
		} catch(Exception e) {
			System.out.println("Exception.");
		}
		System.out.println(4);
		// ArithmeticException이 출력된다

	}
}
</code></pre>

<pre><code>
public class ExceptionApp {
	public static void main(String[] args) {
		int[] scores = {10,20,30};
		System.out.println(scores[0]);

		try {
			System.out.println(1);
			System.out.println(2/0);
			System.out.println(2);
			System.out.println(scores[3]);
			System.out.println(3);
		} catch(ArithmeticException e) {
			System.out.println("ArithmeticException."+e.getMessage());
			// detailMessage를 출력해준다 ( 왜 에러가 발생했는 지)
			e.printStackTrace(); 
			// 빨간색 메세지도 출력해준다
			// 운영체제 차원에서는 이 프로그램을 실행했을 때 정상적으로 동작하지 않았다는 것도 알려줄 수 있다
			// 사용자한테 보여주는게 좋은 것은 아니다
			// 보안적인 사고를 초래할 수 있는 단서들이 존재할수도 있기 때문에
			// 에러 메세지는 내부적으로 파일 형태 (관리자들만 볼 수 있는 시스템, 로딩 시스템)으로 관리해야 한다
		} catch(Exception e) {
			System.out.println("Exception.");
		}
		System.out.println(4);
	}
}
</code></pre>

- CheckedException

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class CheckedException {

	public static void main(String[] args) {
		try {
			FileWriter f = new FrileWriter("data.txt");
			f.write("Hello");
			f.close();
		} catch(IOException e) {
			e.printStackTrace();
		}
	}
}
</code></pre>

- 상속

  예외는 상속이라는 걸 통해서 부모자식 관계가 있다

  부모 예외를 갖다놓게 되면 부모의 자식에 해당되는 어떠한 예외가 발생하건 부모가 처리한다

  부모 예외는 자식 예외를 다 포괄한다

  캐치문을 어디에 넣느냐에 따라서 우선순위가 달라진다는 것을 주의해야 한다

	ArithmeticException -> RuntimeException -> Exception -> Throwable -> Object

- e

  e는 변수이다

  앞에 있는 Exception은 변수의 타입이 Exception이란 것이다

  e는 아무거나 해도 된다

- CheckedException

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class CheckedException {
	// try catch finally
	public static void main(String[] args) {
		FileWriter f = null;
		// null은 값이 없다고 지정하는 것이다
		// f라고 하는 변수가 FileWriter이라고 하는 데이터 타입이다
		try {
			f = new FileWriter("data.txt");
			f.write("Hello");
		} catch(IOException e) {
			e.printStackTrace();
		} finally {
			if(f != null) {
				try{
					f.close();
				} catch(IOException e) {
					e.printStackTrace();
				}
			}
			// try 안에서 exception이 발생했건 하지 않았건 무조건 close가 실행된다
			// f의 유효범위가 중괄호 안이다 그래서 밖에서 선언해야 함
			// f가 세팅되어 있을 때만 closed가 가능하다
		}
	}
}
</code></pre>

- TryWithResource

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class TryWithResource {

	public static void main(String[] args) {
		// try with resource statements
		try(FileWriter f = new FileWriter("data.txt")){
			f.write("Hello");
			// f.close();
			// 자동으로 해주기 때문에 적을 필요가 없다
			// try 괄호 안에 close가 필요한 class를 instance화 시키는 코드를 작성한다
			// 그럼 자바는 이 모든 작업이 끝나고 나서 자동으로 f.close를 내부적으로 수행해준다
		} catch(IOException e) {
			e.printStackTrace();
		}
		// class가 AutoCloseable라고 하는 interface를 가지고 있으면
		// TryWithResource를 사용할 수 있다		
	}
}
</code></pre>

- MyException

<pre><code>
import java.io.FileWriter;
import java.io.IOException;

public class MyException {

	public static void main(String[] args) throws IOException{
//		throw new RuntimeException("error.");
//		// 직접 예외를 발생시킬수도 있다
		FileWriter f = new FileWriter("./data.txt");
		// try catch or 기능을 사용하는 쪽으로 예외를 던지기
	}

}
</code></pre>

- Exception

  Checked Exception vs Unchecked Exception

  checked는 컴파일러가 체크한다라는 뜻일 것이다

- Unchecked Exception

  Unchecked Exception은 RuntimeException을 포함한 그 자식들이다

  ArithmeticException...

  tryc catch문을 작성하지 않아도 컴파일이 되고, Exception이 발생했을 때 그 때 에러가 발생하는 것이다

- Checked Exception

  Exception에서 RuntimeException을 제외한 나머지 애들이고, Exception의 직계 자손이다

  컴파일러가 체크를 한다 (Exception 처리를 했는지 안 했는지)

  try catch, throws를 통해 예외에 대해서 어떠한 조치를 취해야 하고, 무심코 조치를 안 하고 넘어가는 것을 용인하지 않는다

  IOException, SQLException...

  IO는 input, output이고 컴퓨터의 데이터를 파일과 같은 곳에 저장한다 (output) 파일에서 데이터를 읽어온다 (input)

  ex FileNotFoundException 어떤 파일을 읽으려고 했는데 파일이 존재하지 않는 것 (예외적 상황)

- resource

  java가 프로그램 외부에 있는 데이터에 엑세스하려고 할 때 생기는 문제들

  대표적인 외부에 있는 데이터 = File(이미지, 사운드 파일), Network, DB 이러한 것들을 통틀어서 resource라고 한다

  자바 내부에 존재하는 데이터가 아니기 때문에 변수 등과 비교했을 때 엄청나게 불안정한 애들이다 = 오만가지 예외적 상황이 발생할수도 있다

  이러한 리소스들은 자바로 사용할 때 그 리소스를 붙잡는 모종의 행위가 있다

  (파일 – 독점권, 네트워크 – 커넥션, 데이터베이스도)

  작업이 끝나면 붙잡고 있던 것을 놔줘야 하는데 이때 공통적으로 사용되는 메소드가 close이다

  예외는 폭탄던지기와 비슷해서 어떤 기능에서 예외가 발생하면 그것을 직접 처리할수도 있지만 그 기능을 사용하는 곳으로 예외를 던질수도 있다

  = throw

  throw를 하다가 어느 지점에서 예외를 처리하려고 할 때 사용하는 것이 try catch이다

  아무도 try catch를 하지 않는다면 프로그램은 종료되면서 예외 메시지가 출력되는 것이다


