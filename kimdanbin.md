public class HelloWorldApp {
    public static void main(String[] args) {
        System.out.println("Hello World!!");
    }
}


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

6-2
public class Datatype{
	public static void main(String[]args) {
		System.out.println(6);//Number 숫자
		System.out.println("six");//String 문자열
		
		System.out.println("6");//String 6 문자열 6
		
		System.out.println(6+6);// 12 --> 숫자와 숫자를 결합해 더해주는 더하기 연산자
		System.out.println("6"+"6");// 66 --> 문자열일땐 더하기가 아니라 결합 연산자(문자열을 위한 연산)
		
		System.out.println(6*6);// 36
		//System.out.println("6"*"6");// --> 에러 / 문자열이란 데이터 타입은 곱하기를 할 수 없다
		
		System.out.println("1111".length());// 4  --> 문자열의 길이
		//System.out.println(1111.length());// --> 에러 / 숫자 천백십일 : 숫자는 숫자의 길이를 알려주는 연산은 없다
		
		//프로그래밍에서는 데이터 타입이 있다 , 데이터 타입별로 구분하는 이유는 타입별로 그 타입에 어울리는 연산 방법이 있기 때문에 엄격하게 구분
		
		
	}
}


6-3
public class Number {

	public static void main(String[] args) {
		
		//Operator 연산자 : +,-,*,/
		System.out.println(6 + 2); // 8
		System.out.println(6 - 2); // 4
		System.out.println(6 * 2); // 12
		System.out.println(6 / 2); // 3
		
		System.out.println(Math.PI); //3.141592653589793
		System.out.println(Math.floor(Math.PI)); // 3.0 / floor : 내림(바닥)
		System.out.println(Math.ceil(Math.PI)); // 4.0 / ceil : 올림(천장)

	}

}



6-4
public class StringApp {

	public static void main(String[] args) {
		
		System.out.println("Hello World"); //String 문자열 --> character들이 모여 있는 것
		//System.out.println('Hello World'); // 에러 / 자바에서는 작은 따옴표는 특수한 데이터 타입을 가리킨다 
		System.out.println('H'); // character 문자 / 한 글자를 표현하는 데이터 타입
		System.out.println("H"); // String 문자열
		
		System.out.println("Hello "
				+ "World"); // 줄바꿈이 아니다
		
		// new line 줄바꿈
		System.out.println("Hello \nWorld");
		
		// escape
	    System.out.println("Hello "World""); // Hello "World"를 출력하고싶은데 에러 / 큰 따옴표는 문자의 시작과 끝을 알리는 특수한 문자
		System.out.println("Hello \"World\""); // Hello "World" / 역슬래시를 앞에 붙이면 뒤에 따라오는 따옴표는 일반 문자열이 된다
	}

}


6-5
public class StringOperation {

	public static void main(String[] args) {
		
		System.out.println("Hello World".length()); // 11 / 글자가 11글자
		System.out.println("Hello, leezche ... bye.".replace("leezche","egoing")); // Hello, egoing ... bye.
		System.out.println("Hello, [[[name]]] ... bye.".replace("[[[name]]]","egoing")); // Hello, egoing ... bye.
	
	}

}



8-1
public class Variable {

	public static void main(String[] args) {
		
		int a=1; // Number -> integer(정수) ... -2, -1, 0, 1, 2 ...
		System.out.println(a);
		
	   double b=1.1; // real number(실수) -> double ... -2.0, -1.0, 0, 1.0, 2.0 ...
	   System.out.println(b);
	   
	   String c="Hello World";
	   System.out.println(c);
	   
	   // 변수의 타입을 지정하는 이유 : 변수의 데이터 타입을 바로바로 판단할 수 있기 떄문

	}

}


8-2
public class Letter {

	public static void main(String[] args) {
		
		String name = "leezch";
		System.out.println("Hello, "+name+" ... "+name+" ... egoing ... bye");
		// name이라는 변수를 지정하면, 자주 사용하는 데이터를 여러번 재사용 가능
		//이름을 수정할 경우, 변수의 값만 수정하면 되므로 효율적으로 처리할 수 있다.
		
		double VAT = 10.0;
		System.out.println(VAT);
		
		//변수는 값에 이름을 부여하는 것
		// 변수의 이름을 잘 지으면 코드의 의미를 파악할 떄 도움이 된다.
		// 변수를 사용하면 코드의 의미를 쉽게 파악할 수 있다.

	}

}



8-3
public class Casting {

	public static void main(String[] args) {
		
		double a = 1.1;
		double b = 1; // 자동으로
		double b2 = (double)1; // 수동으로(명시적으로)
		
		System.out.println(b); // 1.0 -> 정수지만 b라고 하는 double이라는 변수에 담길때 1이 실수형인 1.0으로 컴버팅이 될때 잃어버리는 값이 없다.
		
		//int c = 1.1; // 에러 -> 1.1이라는 실수를 정수로 바꿔줄 떄 0.1을 잃어버리는 현상(손실)이 생기기 때문
		double d = 1.1;
		int e = (int) 1.1; // 1 ->  정수 1이 된다
		System.out.println(e);
		
		// 1 to String
		String f = Integer.toString(1);
		System.out.println(f); // 1 -> 1의 데이터 타입이 숫자가 아니라 문자열이다
		System.out.println(f.getClass()); // .getClass()-> 변수가 갖고 있는 값이 어떤 데이터 타입인지 알려주는 코드
		
		
	}

}


9-1
.프로그램은 음악회와 같은 곳에서 연주할 곡들의 순서를 나타내는 것
.컴퓨터 각각의 작업들 하나하나로는 별로 의미가 없지만 내가 하고자 하는 일이 무엇이냐에 따라 그 일을 하기 위해서 필요한 각각의 작업들을 시간의 순서에 따라 실행되게 할 수 있다면 그것을 자동화를 할 수 있게 되는 것이다.
.컴퓨터 언어를 이용해서 프로그램을 만드는 것은 업무의 자동화된 처리를 위해서라고 할 수 있습니다

public class Program {

	public static void main(String[] args) {
		
		System.out.println(1);
		System.out.println(2);
		System.out.println(3);
		
		//이 작업은 그저 화면에 1, 2, 3을 순서대로 출력하는 작업을 수행합니다.
		//만약 3줄이 아니라 1억줄에 이르는 작업을 수행한다면 어떨까요?
		//굉장히 오래 걸리는 작업이라서 끝내기 위해서 하염없이 붙잡고 있어야 하는 작업이라면 어떨까요?
		//이런 경우에 컴퓨터 프로그래밍을 이용하여 사람이 잘 못하는 일을 기계에게 위임해서 자동화할 수 있습니다.
	}

}


9-2,3
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
 

10
이클립스에서 디버거 이용하기
디버거를 실행 : 이클립스 상단의 메뉴 도구 중 벌레 모양으로 생긴 버튼을 클릭
브레이크 포인트가 지정 : 코드 편집 창에서 줄 번호 왼편에서 더블클릭
Step Over : 다음 줄에 브레이크 포인트가 생성되어 그 지점까지만 코드가 실행
Resume : 다음 브레이크 포인트까지 실행되고, 만약 더 이상 브레이크 포인트가 없다면 끝까지 실행
Variable 탭에서 변수들을 확인
Step Into : 코드의 자세한 실행 과정을 들여다볼 수 있다
Step Return : 다시 원래의 코드로 돌아가고자 할 경우

11-1
프로그램은 입력정보를 받아서 출력을 하는 것

import javax.swing.JOptionPane;
//JOptionPane 객체를 이용하기 위해서는 import 구문을 이용하여 불러온다
 
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
 
    public static void main(String[] args) {
         
        String id = JOptionPane.showInputDialog("Enter a ID");
        String bright = JOptionPane.showInputDialog("Enter a Bright level");
         
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
//무드 램프(DimmingLight 객체)는 setBright 메소드에 double 데이터를 입력받아서 밝기를 조절한다.
//etBright 메소드의 밝기는 double 데이터로 입력해야 하기 때문에 데이터 타입 변환을 해야 하므로 문자열을 double로 데이터 타입을 변환하기 위해서 Double.parseDouble(bright)과 같이 수정합니다
 
    }
 
}


11-2
 main 메소드의 args 파라미터를 이용해서 입력값을 받는 방법
입력값을 주기위해서 아규먼트탭 클릭 -> 따옴표로 묶어주면 하나의 덩어리로써 들어감 / 여러개의 값을 주고 싶으면 띄우고 따옴표 -> apply -> run

//paramter, 매개변수
	// String[] : 문자열로만 이루어져있는 배열이라고 하는 데이터
	// args라는 변수에 사용자가 입력한 값이 들어올것이다 그렇게 되면 중괄호([]) 안에서는 args가 사용자가 입력한 값이다.
    public static void main(String[] args) {

String id = args[0];
Strign bright = args[1];

}

아규먼트를 입력하게 되면 main 메소드의 args 파라미터는 아규먼트 값을 받아서 동작하게 된다.
args는 문자열 배열(array)로 여러 개의 String 데이터가 들어있을 수 있다.
인덱스를 통해 배열의 데이터를 꺼내 쓸 수 있고, 인덱스는 0번부터 시작.


12-1
이클립스 없이 혼자 컴파일하기
이클립스 없이 자바로 프로그래밍을 하려면 우선 자바 파일을 스스로 컴파일할 수 있어야 한다.
그리고 컴파일한 클래스 파일을 실행하는 과정을 거쳐야 한다.


12-2
javac의 경로를 운영체제에서 환경변수에 이 경로가 이미 입력되어 있다는걸 알고 javac만 입력해도 실행할 수 있는 것이다.
이렇게 환경 변수의 Path에 javac의 경로(자바 설치 경로\bin)가 입력되어 있기 때문에 명령 프롬프트에서 javac 명령어를 바로 이용할 수 있다.
운영체제는 javac 명령어를 입력받으면 Path에 지정되어 있는 경로들 안에 javac 명령어가 있는지 확인하여 실행한다.


12-3
*명령 프롬프트에서 cd 명령어를 통해 프로젝트 디렉토리로 이동
*dir 명령어로 프로젝트 디렉토리 내부의 구조를 확인

*자바 파일 컴파일하기
Program.java를 컴파일 -> Program.class가 생성 -> 컴파일된 클래스 파일을 실행하기 위해서는 java 명령어를 이용
javac Program.java
javac -cp "." Program.java(에러가 난다면)

실행할 때는 .class를 붙이지 않는다.
java Program
java -cp "." Program(에러가 난다면)


12-4
*라이브러리를 이용하는 프로그램을 컴파일하기
import 구문을 통해 OkJavaGoInHome 클래스가 있는 폴더의 org.opentutorials.iot의 클래스들을 불러들이고 있기 때문에
컴파일을 실행할 때 자동적으로 org.opentutorials.iot의 Elevator, Lighting, Security 클래스들도 컴파일을 한다.

*외부 라이브러리도 포함해서 컴파일하기
외부 라이브러리를 포함해서 컴파일하기 위해서는 javac 명령어의 옵션 중 --class-path(-cp) 옵션을 이용해서 외부 라이브러리도 함께 지정해야 한다.
콜론(:)이나 세미콜론(;)은 구분자의 의미
-cp ".:lib"은 자바 파일이 있는 현재 폴더(.)와 lib 폴더에서 필요한 자바 파일들을 컴파일하라는 의미

*외부 라이브러리도 포함해서 실행하기
컴파일했을 때와 마찬가지로 --class-path 옵션에 외부 라이브러리도 포함해서 실행
java -cp ".;lib" OkJavaGoInHome(윈도우)
java -cp ".:lib" OkJavaGoInHome(macOS, Linux)


12-5
*실행할 때 아규먼트 입력하기
org.opentutorials.iot 패키지는 다시 lib 폴더 밖으로 꺼낸다 -> OkJavaGoInHomeInput.java를 컴파일 -> 
터미널에서 아규먼트를 주기 위해서는 실행할 클래스 파일 이름 다음에 연달아서 입력 java OkJavaGoInHomeInput "JAVA APT 507" 15.0

13-1
프로그램(Program) : 작업들의 시간적 순서에 주목
애플리케이션(Application) : 도구의 응용에 주목
자바 API(Application Programming Interface) :  자바는 자바의 도구들을 응용해서 사용하기 위해서 일정한 조작 장치를 구성, 다른 프로그램에서 사용할 수 있도록 만들어둔 장치 (프로그램이 사용)
UI(User Interface) : 사용자가 자바 프로그램을 사용할 수 있도록 만들어둔 장치들(사용자가 사용)
 ex 커맨드 라인 시스템의 아규먼트, 데스크톱 앱의 버튼, 웹 페이지의 링크 등

13-2
패키지 : 서로 비슷한 성격의 클래스를 모아서 이름을 붙인 것 (클래스들을 그루핑해서 이름 붙인 것,클래스(들)을 하나의 묶음으로 정리)
클래스 : 서로 연관된 변수와 메소드를 모아 이름을 붙인 것 (변수와 메소드를 그루핑)

13-3
public class ClassApp {

	public static void main(String[] args) {
		
		System.out.println(Math.PI);
		System.out.println(Math.floor(1.6)); //1.0
		System.out.println(Math.ceil(1.6)); //2.0
		//Math 클래스, PI 변수, floor ceil 메소드
		
	}

}


13-4
import java.io.FileNotFoundException;
import java.io.PrintWriter;

public class InstanceApp {

	public static void main(String[] args) throws FileNotFoundException {
		
		PrintWriter p1 = new PrintWriter("result1.txt"); 
		//클래스가 하는 작업이 일회용이 아니라긴 맥락의 작업을 해야한다면 그떄는 클래스를 복제한 인스턴스를 만들어서 그것을 사용할 수 있도록 사용자에게 제공하는 것이 효율적
		//new뒤에 붙인게 컨스트럭터 , 컨스트럭터 앞에 new를 붙이면 복제되서 인스턴스가 되고,  그 인스턴스에 어떤 값이 올 수 있느냐를 규제하기 위해서 앞에다가 PrintWriter라고 하는 클래스의 이름을 적는다. 
	    p1.write("Hello 1");
		p1.close();//파일을 더 이상 붙잡고 있지 않는다
		
		PrintWriter p2 = new PrintWriter("result2.txt");
		p2.write("Hello 2");
		p2.close();
		p1.write("Hello 1");
		
		PrintWriter.write("result1.txt","Hello 1");
		PrintWriter.write("result2.txt","Hello 2");
		PrintWriter.write("result1.txt","Hello 1");
		PrintWriter.write("result2.txt","Hello 2");
		PrintWriter.write("result1.txt","Hello 1");
		PrintWriter.write("result2.txt","Hello 2");
		PrintWriter.write("result1.txt","Hello 1");
		PrintWriter.write("result2.txt","Hello 2");
		PrintWriter.write("result1.txt","Hello 1");
		PrintWriter.write("result2.txt","Hello 2");
		PrintWriter.write("result1.txt","Hello 1");
		PrintWriter.write("result2.txt","Hello 2");
		//한번 파일에 쓰기 작업을 수행할 때마다 일일이 파일의 이름을 입력해 줘야 한다는 단점이 있다.

	}

}

13-5
들여쓰기되어 표현된 각각의 클래스 간의 관계는 상속 관계를 나타낸다.
자식에 해당하는 클래스는 부모에 해당하는 클래스의 모든 변수와 메소드를 사용할 수 있다.
이클립스 안에서 Open Type hierarchy를 이용하여 클래스의 상속관계를 확인할 수 있다. 

PrintWriter p2 = new PrintWriter("result2.txt");
		p2.write("Hello 2");
		p2.close();
		System.out.println(p1.toString());
		p2.toString();
		//printWriter는 writer를 writer는 object를 상속 받고 있기 떄문에 p2.toString();라는 메소드를 사용할 수 있다.



14-2
public class AccountingApp {

	public static void main(String[] args) {
		
		System.out.println("Value of supply : "+10000.0);
		System.out.println("VAT : "+(10000.0*0.1));
		System.out.println("Total : "+(10000.0 + 10000.0*0.1));
		System.out.println("Expense : "+(10000.0*0.3));
		System.out.println("Income : "+(10000.0 - 10000.0*0.3));
		System.out.println("Dividend 1 : "+(10000.0 - 10000.0*0.3)*0.5);
		System.out.println("Dividend 2 : "+(10000.0 - 10000.0*0.3)*0.3);
		System.out.println("Dividend 3 : "+(10000.0 - 10000.0*0.3)*0.2);
		
		
	}

}
Edit -> Find/Replace -> 숫자 10000.0을 12345.0으로 바꿀 수 있다

14-3
public class AccountingApp {

	public static void main(String[] args) {
		
		double valueOfSupply = 12345.0;
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double VAT = valueOfSupply*vatRate;
		double total = valueOfSupply + VAT;
		double expense = valueOfSupply*expenseRate;
		double Income = valueOfSupply - expense;
		double dividend1 = Income*0.5;
		double dividend2 = Income*0.3;
		double dividend3 = Income*0.2;
		
		System.out.println("Value of supply : "+valueOfSupply);
		System.out.println("VAT : "+VAT);
		System.out.println("Total : "+total);
		System.out.println("Expense : "+expense);
		System.out.println("Income : "+Income);
		System.out.println("Dividend 1 : "+dividend1);
		System.out.println("Dividend 2 : "+dividend2);
		System.out.println("Dividend 3 : "+dividend3);
		//Refactor -> Extract Local Variable
		
	}

}

14-4
public class AccountingApp {

	public static void main(String[] args) {
		
		double valueOfSupply = Double.parseDouble(args[0]);
	}
}

This is an H1
=============
This is an H2
-------------
# This is a H1
14-6
조건문

public class AccountingAppIf {

	public static void main(String[] args) {
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double VAT = valueOfSupply*vatRate;
		double total = valueOfSupply + VAT;
		double expense = valueOfSupply*expenseRate;
		double Income = valueOfSupply - expense;
		
		double dividend1;
		double dividend2;
		double dividend3;
		
		
		if(Income>10000.0) {
			dividend1 = Income*0.5;
		    dividend2 = Income*0.3;
		    dividend3 = Income*0.2;
		}
		else {
			dividend1 = Income*1;
		    dividend2 = Income*0;
		    dividend3 = Income*0;
		}
	}
}
## This is a H2
14-7
배열

double rate1 = 0.5;
double rate2 = 0.3;
double rate3 = 0.2;

double dividend1 = Income*rate1;
double dividend2 = Income*rate2;
double dividend3 = Income*rate3;
//변수가 많으면 변수가 더럽혀질 가능성이 커진다는 문제점이 있다, 세개의 변수가 서로 같은 성격의 데이터라는게 분명하지 않다.

double[] dividendRates = new double[3];//double형 데이터로 이루어진 배열 이다 / double형의 데이터를 3개를 담을 수 있는 수납상자
dividendRates[0] = 0.5;
dividendRates[1] = 0.3;
dividendRates[2] = 0.2;
		
double dividend1 = Income*dividendRates[0];
double dividend2 = Income*dividendRates[1];
double dividend3 = Income*dividendRates[2];
//각각의 값들이 연관된 값들이라는걸 분명히 할 수 있다, 변수가 줄어들어 변수가 더럽혀질 가능성이 현저히 줄어들었다는 장점이 있다.

### This is a H3
14-8
반복문

double[] dividendRates = new double[3];//double형 데이터로 이루어진 배열 이다 / double형의 데이터를 3개를 담을 수 있는 수납상자
dividendRates[0] = 0.5;
dividendRates[1] = 0.3;
dividendRates[2] = 0.2;
		
		
int i=0; //몇번반복됐는지를 i라는 변수에 기록
while(i<dividendRates.length) {  
	// i의 값이 (dividendRates의 길이)3보다 작은동안 실행
      System.out.println("Dividend : "+(Income*dividendRates[i]));
	i=i+1;//i의 값이 1씩 증가
}

#### This is a H4
14-9
메소드 : 서로 연관된 코드를 그루핑해서 이름을 붙인 정리정돈의 상자

double VAT = getVAT(valueOfSupply, vatRate); //Refactor -> Extract Method...//만들어진 메소드를 호출하는 실행하는 코드//괄호안의 값은 입력값

	private static double getVAT(double valueOfSupply, double vatRate) {
		return valueOfSupply*vatRate; 
	}//Method를 만드는 코드

//private static double getVAT()이렇게 되면 에러 =>  valueOfSupply가 현재 main메소드 중괄호 안에서 선언되었으므로 main메소드 안에서만 사용 가능한 지역 변수
// valueOfSupply를 AccountingMethodApp클래스의 전역 변수로 지정해서 모든 메소드에서 접근할 수 있도록 해야한다 -> main메소드 밖에서 선언(public static double valueOfSupply;)
// Refactor -> Convert Local Variable to Field... -> public 선택


double total = getTotal(vat);

public static double getTotal(double vat) {
		return valueOfSupply + vat;


double total = getTotal();

public static double getTotal() {
		return valueOfSupply + getVAT(); 
// vat가 지역변수인데 얘를 전역변수로 만들 수도있지만 그렇게 하지 않고 그냥  getVAT()를 호출하는 걸로 똑같은 목적을 달성할 수 있다.


public class AccountingMethodApp {
	public static double valueOfSupply;
	public static double vatRate;
	public static double expenseRate;
	public static void main(String[] args) {
		
		valueOfSupply = 10000.0;
		vatRate = 0.1;
		expenseRate = 0.3;		
		print();
		
		
	}

	public static void print() {
		System.out.println("Value of supply : "+valueOfSupply);
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : "+getTotal());
		System.out.println("Expense : "+getExpense());
		System.out.println("Income : "+getIncome());
		System.out.println("Dividend 1 : "+getDiviend1());
		System.out.println("Dividend 2 : "+getDiviend2());
		System.out.println("Dividend 3 : "+getDiviend3());
	}

	public static double getDiviend1() {
		return getIncome()*0.5;
	}

	public static double getDiviend2() {
		return getIncome()*0.3;
	}
	
	public static double getDiviend3() {
		return getIncome()*0.2;
	}
	
	public static double getIncome() {
		return valueOfSupply - getExpense();
	}

	public static double getExpense() {
		return valueOfSupply*expenseRate;
	}

	public static double getTotal() {
		return valueOfSupply + getVAT();
	}

	private static double getVAT() {
		return valueOfSupply*vatRate; 
	}//Method를 만드는 코드
//private static double getVAT()이렇게 되면 에러 =>  valueOfSupply가 현재 main메소드 중괄호 안에서 선언되었으므로 main메소드 안에서만 사용 가능한 지역 변수
	// valueOfSupply를 AccountingMethodApp클래스의 전역 변수로 지정해서 모든 메소드에서 접근할 수 있도록 해야한다 -> main메소드 밖에서 선언(public static double valueOfSupply;)
	// Refactor -> Convert Local Variable to Field... -> public 선택
}
}
}

##### This is a H5
14-10
클래스
class Accounting{
	public static double valueOfSupply;
	public static double vatRate;
	public static double expenseRate;
	
	public static void print() {
		System.out.println("Value of supply : "+valueOfSupply);
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : "+getTotal());
		System.out.println("Expense : "+getExpense());
		System.out.println("Income : "+getIncome());
		System.out.println("Dividend 1 : "+getDiviend1());
		System.out.println("Dividend 2 : "+getDiviend2());
		System.out.println("Dividend 3 : "+getDiviend3());
	}

	public static double getDiviend1() {
		return getIncome()*0.5;
	}

	public static double getDiviend2() {
		return getIncome()*0.3;
	}
	
	public static double getDiviend3() {
		return getIncome()*0.2;
	}
	
	public static double getIncome() {
		return valueOfSupply - getExpense();
	}

	public static double getExpense() {
		return valueOfSupply*expenseRate;
	}

	public static double getTotal() {
		return valueOfSupply + getVAT();
	}

	private static double getVAT() {
		return valueOfSupply*vatRate; 
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

###### This is a H6
14-11
인스턴스 : 하나의 클래스를 복제해서 서로 다른 데이터의 값과 서로 같은 메소드를 가진 복제본을 만드는 것이다.

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

 instance : 클래스 앞에 new를 붙여서 만들어진 것
		// 이 코드가 사용되기 위해선 static이라는 키워드가 사용되면 안된다.
		Accounting a1 = new Accounting();//new를 붙이면 Accounting클래스를 복제 // a1이라는 변수의 값에 반드시 Accounting의 복제본만 들어올 수 있다
		a1.valueOfSupply = 10000.0;
		a1.vatRate = 0.1;
		a1.expenseRate = 0.3;
		a1.print();
		
		Accounting a2 = new Accounting();
		a2.valueOfSupply = 20000.0;
		a2.vatRate = 0.05;
		a2.expenseRate = 0.2;
		a2.print();
		
		a1.print();


This is an java2
=============
This is an 1
-------------
1
조건을 구성하기 위해서 자바에서는 Boolean 데이터 타입과, 비교 연산 기능을 제공

This is an 2
-------------
Boolean Datatype
package javaflowcontrol;

public class BooleanApp {

	public static void main(String[] args) {
		
		System.out.println("One"); 
		System.out.println(1);
		
		System.out.println(true);
		System.out.println(false);
		//Boolean에 속하는 데이터 타입은 두 개 
		
		String foo = "Hello world";
		//String true = "Hello World"; // true, false는 변수의 이름으로 사용할 수 없다.
		//reserved word : 쓰임이 있는,앞으로 그런 기능이 채택될 가능성이 있는 키워드들을 컴퓨터 언어가 이것을 사용하기로 예약되어있다.  
		
		System.out.println(foo.contains("world")); //true  foo에 world가 들어 있으므로 트루
		System.out.println(foo.contains("egoing")); //false
	}

}

This is an 3
-------------
3 비교연산자
package javaflowcontrol;

public class ComparisonOperatorApp {

	public static void main(String[] args) {
		
		System.out.println(1 > 1); //false
		System.out.println(1 == 1); //true
		System.out.println(1 < 1); //false
		System.out.println(1 >= 1); // true

	}

}

This is an 4
-------------
# This is a 4-1
조건문 형식
package javaflowcontrol;

public class IfApp {

	public static void main(String[] args) {
		
		
		System.out.println("a"); //a
		if(true) {
			System.out.println(1); //1
		}//괄호 안이 true면 실행 , false면 실핼되지 않아
		else {
			System.out.println(2);
		}//if(false)를 else라고 해도 똑같음
		System.out.println("b"); //b
		
		
		
		
		if(false) {
			System.out.println(1); //1
		}else {
			if(true) {
				System.out.println(2);
			}else {
				System.out.println(3); //조건문안에 또다른 조건문을 넣을 수 있다.
			}	
		}
		
		
		if(false) {
			System.out.println(1); 
		}else if(true) {
			System.out.println(2);
	    }else {
	    	System.out.println(3); 
			}
		//true면 1실행, false면 else if(true)의 값이 실행 else if(false)면 3실행
	}
}

## This is a 4-2
조건문 응용 1
package javaflowcontrol;

public class AuthApp {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "1111";
		String inputPass = args[1];
		
		System.out.println("Hi.");
		
		//if(inputId == id){ //실행시켰을때 Master!가 안나오고 Who are you?가 나옴.
//		if(inputId.equals(id)) {
//			if(inputPass.equals(pass)) {
//				System.out.println("Master!");
//			} else {
//				System.out.println("Wrong password!");
//			}
//		}else {
//				System.out.println("Who are you?");
//			}
		
		if(inputId.equals(id)) {//id가 같고 pass가 같다면 Master!가 출력되게 하는 논리 연산자
			if(inputPass.equals(pass)) {
				System.out.println("Master!");
			} else {
				System.out.println("Wrong password!");
 		    }
		}else {
				System.out.println("Who are you?");
			}//조건문이 두 개
		
		
		if(inputId.equals(id) && inputPass.equals(pass)) {//논리 연산자 : && : 앞에꺼가 참이고 뒤에꺼가 참이면 전체가 참이되게 하는 연산자
			                                                 //둘 중 하나라도 틀리면 Who are you?가 출력됨
				System.out.println("Master!");
		}else {
				System.out.println("Who are you?");
		}
		
	 }
  }
}

This is an 5
-------------
primitive : 원시 : 더 이상 쪼갤 수 없는
- boolean, int, duoble, short, long, float, char

non primitive : 
- String, Array, Data, File


int p1 = 1 
int p2 = 1 
-> p1 == p2 -> true(같은 곳에 위치)

String o1 = new string("java")
String o2 = new string("java")
-> o1 == o2 -> false(다른 곳에 위치)

원시 데이터 타입이 아닌 객체들은 equals라고 하는 메소드를 다들 가지고 있다.
o1.equals(o2) -> true(내용이 같다면)

== (동등 바교 연산자) : 같은 곳에 있는지
equals : 내용이 같은지 따져보는 취지로 만들어진 메소드

원시 데이터 타입을 할 때는 ==(동등 비교 연산자)를 쓰면 됨. equals를 가지고 있지 않으므로 쓰지x
원시 데이터 타입이 아닌것은 equals를 쓰면 됨.

String o3 = "java2"
String o3 = "java2"
(같은 위치)
-> o3 == o4 -> true

This is an 6
-------------
논리 연산자

package javaflowcontrol;

public class LogicalOperatorApp {

	public static void main(String[] args) {
		
		System.out.println(1 == 1);
		
		// AND
		System.out.println(true && true); // true
		System.out.println(true && false); // false
		System.out.println(false && true); // false
		System.out.println(false && false); // false
		
		// OR (둘 중 하나라도 트루면 트루다)
		System.out.println(true || true); // true
		System.out.println(true || false); // true
		System.out.println(false || true); // true
		System.out.println(false || false); // false
		
		// not
		System.out.println(!true); // false
		System.out.println(!false); // true

	}

}


package javaflowcontrol;

public class AuthApp2 {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "1111";
		String pass2 = "2222";
		String inputPass = args[1];
		
		
		System.out.println("Hi.");
		
		boolean isRightPass = (inputPass.equals(pass) || inputPass.equals(pass2));
		if(inputId.equals(id) && isRightPass ) {
				System.out.println("Master!");
		}else {
				System.out.println("Who are you?");
		}
		
	}
}

This is an 7
-------------
# This is a 7-1
반복문

package javaflowcontrol;

public class LoopApp {

	public static void main(String[] args) {


		System.out.println(1);
		System.out.println("=== while ===");
		int i=0;
		while(i < 3) {
			System.out.println(2);
		    System.out.println(3);
		    // i = i+1;
		    i++;
		}//while(true)하면 무한반복
		
		System.out.println("=== for ===");
		for(int j=0; j<3; j++) {
			System.out.println(2);
		    System.out.println(3);
		}
		
		System.out.println(4);
		

	}

}

## This is a 7-2
배열

package javaflowcontrol;

public class ArrayApp {

	public static void main(String[] args) {


		//egoing, jinhuck, youbin
		//String users = "egoing, jinhuck, youbin";
		String[] users = new String[3];
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		
		System.out.println(users[1]);
		System.out.println(users.length);//3칸짜리 배열이다
		
		
		int[] scores = {10,100,100};
		System.out.println(scores[1]);
		System.out.println(scores.length);
	}

}

### This is a 7-3
반복문 + 배열

package javaflowcontrol;

public class LoopArray {

	public static void main(String[] args) {
		/*
		 * <li>egoing</li>
		 * <li>jinhuck</li>
		 * <li>youbin</li>
		 */
		
		String[] users = new String[3];
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		
		 for(int i=0; i<users.length; i++) {
			 System.out.println(users[i]+",");
		 }
		
	}

}

#### This is a 8-1
종합응용1
package javaflowcontrol;

public class AuthApp3 {

	public static void main(String[] args) {
		
		String[] users = {"egoing", "jinhuck", "youbin"};
		String inputId = args[0];
		
		boolean isLogined = false;
		for(int i=0; i<users.length; i++) {
			String currentId = users[i];
			if(currentId.equals(inputId)) {
				isLogined = true;
				break;//break가 있으면 break가 속해있는 반복문은 종료
			}
		}
		System.out.println("Hi,");
		if(isLogined) {
			System.out.println("Master!!");
		} else {
			System.out.println("Who are you?");
		}
	}

}//아규먼트에 egoing을 넣고 실행하면 Hi, Master!! 실행됨
// 아규먼트에 leezche를 넣으면 Hi, Who are you?가 실행됨

##### This is a 8-2
종합응용2
package javaflowcontrol;

public class AuthApp3 {

	public static void main(String[] args) {
		
		//String[] users = {"egoing","jinhuck", "youbin"};//users의 배열의 값이 string이었는데
		String[][] users = {
				{"egoing", "1111"},
				{"jinhuck", "2222"},
				{"youbin", "3333"}
				//배열안에 또 다른 배열이 들어간다 / users는 users의 원소가 배열이고 그 각가의 배열의 원소의 값은 string인 값
		};
		String inputId = args[0];
		String inputPass = args[1];//두번째 값을 비밀번호로 받는다.
		
		boolean isLogined = false;
		for(int i=0; i<users.length; i++) {
			String[] current = users[i];
			if(
					current[0].equals(inputId)&&
					current[0].equals(inputPass)
			   ) {//입력된 아이디의 값과 각각의 원소의 첫번째 자리인 아이디의 값을 비교하는 코드
				isLogined = true;
				break;//break가 있으면 break가 속해있는 반복문은 종료
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

This is an 메소드
-------------
*메소드
메소드 : 클래스와 관련된 작업을 하는 함수
메소드를 이용하여 코드를 정리정돈하고 재사용성을 높일 수 있는 방법

# This is a 2
익숙한 메소드
public class FirstMethod {

	public static void main(String[] args) {
		
		System.out.println("Hello Method");
		System.out.println(Math.floor(1.1));
	}
}//main이라는 메소드

## This is a 3
메소드의 기본 형식
public class WhyMethod {
	public static void printTwoTimesA() {
		System.out.println("-");
		System.out.println("a");
		System.out.println("a");
	}

	public static void main(String[] args) {
		
	  // 100000000
	  printTwoTimesA();
        // 100000000
        printTwoTimesA();
        // 100000000
        printTwoTimesA();
	}
}
//Refactor -> Etract Method로 만들어도 됨.

### This is a 4
메소드의 입력
public class WhyMethod {
	
	public static void main(String[] args) {
		
		             // 인자, argument : 함수 안으로 주입한 구체적인 값(a라는 문자열)
	  printTwoTimes("a","-");//첫번쨰 입력값이 a구나 그러면 text값은 중괄호 안에서 a구나 라고 생각
	  // 100000000
        printTwoTimes("a","*");
        // 100000000
        printTwoTimes("a","&");
        printTwoTimes("b","!");
        
	}
                                     // 매개변수, parameter : 메소드 바깥쪽에서 메소드를 사용하는 쪽에서 주입한 값을 메소드 안으로 흘려보내주는 매개자 (text,delimiter같은 변수)
	public static void printTwoTimes(String text, String delimiter) {//printTwoTimes이라는 메소드를 정의하고 있구나 그리고 미 메소드의 괄호안에 들어오는 첫번째 값은 반드시 String이구나 그리고 그렇게 들어온 값은 이 중괄호안에서 text라는 이름의 변수의 값이 되겠구나
		System.out.println(delimiter);//delimiter는 구분자
		System.out.println(text);
		System.out.println(text);
	}
}

#### This is a 5
메소드의 출력
public class OutMethod {
	
	public static String a() {//a라는 메소드는 return값이 String이다 아웃풋이 String이다.
		//...
		return "a";//a라는 메소드는 return뒤에 있는 값이 됩니다. 
	}
	
	public static int one() {
		return 1;
	}//그 메소드의 return값 뒤에 있는 값이 그 메소드의 실행결과가 된다. return은 그 메소드를 종료시키는 역할도 한다.

	public static void main(String[] args) {


		System.out.println(a());
		System.out.println(one());
	}
}



import java.io.FileWriter;
import java.io.IOException;

public class WhyMethod {
	
	public static void main(String[] args) throws IOException {
		
		System.out.println(twoTimes("a","-"));
		FileWriter fw = new FileWriter("out.txt");
		fw.write(twoTimes("a","*"));
		fw.close();
 //     Email.send("egoing@a.com", "two times a", twoTimes("a","&")); 
	}
	public static String twoTimes(String text, String delimiter) {
		String out = "";
		out = out + delimiter + "\n";
		out = out + text + "\n";
		out = out + text + "\n";
		return out;
	}
}

##### This is a 6
메소드의 활용
public class AccountingApp {
	//공급가액
	double valueOfSupply = 10000.0;
			
	//부가가치세율
	double vatRate = 0.1;
			
	public static void getVAT() {
		return valueOfSupply * vatRate;
	}
	
	public static double getTotal() {
		return valueOgSupply + getVAT;
	}

	public static void main(String[] args) {
		
		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + getVAT());
		System.out.println("Total : " + getTotal());
	}
}

###### This is a 8
부록 (access level modifiers)
class Greeting{
	//public(다른 클래스에서도 사용 가능), protected, default, private(같은 클래스 안에서만 사용 가능)
		public static void hi() {
			System.out.println("Hi");
		}
}
public class AccessLevelModifierMethod {
	private static void hi() {
		System.out.println("Hi");
	}

	public static void main(String[] args) {
		hi();

	}
}

###### This is a 9
부록 (static)
static - class method (static을 쓰면 클래스의 소속)
non static - instance method (static을 쓰지 않으면 인스턴스의 소속)

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
//		Print.a("-");
//		Print.b("-");
		
		//instance
		Print t1 = new Print();
		t1.delimiter = "-";
		t1.a();//a라는 메소드는 클래스가 아니라 인스턴스의 소속이다
		t1.b();
		Print.c("$");// 프린트의 소속인 c를 호출할 수 있다 (static이기 때문에)
		
//		Print.a("*");
//		Print.b("*");		
		
		Print t2 = new Print();
		t2.delimiter = "*";
		t2.a();
		t2.b();

	}

}//메소드가 인스턴스의 소속일땐 static을 빼줘야 함 하지만 메소드가 클래스의 소속일땐 있어야 함.


This is an 객체지향 프로그래밍
-------------

# This is a H1
메소드는 언어마다 메소드(method), 함수(function), 서브루틴(subroutin), 프로시져(procedure)라는 여러 이름으로 불립니다.
객체 지향 프로그래밍(Object Oriented Programming) :  클래스를 이용해서 프로그램의 구조를 만들어 가는 방식
객체 지향 언어(Object Oriented Language) :  이러한 방식을 언어 차원에서 지원하는 프로그래밍 언어

## This is a H2
2 남의 클래스 남의 인스턴스
import java.io.FileWriter;
import java.io.IOException;

public class OthersOOP {

	public static void main(String[] args) throws IOException {
		//class : System, Math, FileWriter
		// instance : f1, f2
		
		System.out.println(Math.PI);
		System.out.println(Math.floor(1.8));
		System.out.println(Math.ceil(1.8));
		
		FileWriter f1 = new FileWriter("data.txt"); // data.txt에다가 파일을 저장하겠다. FileWriter라는 클래스의 복제본이 생김.
		f1.write("Hello");
		f1.write("Java");
		f1.close();
		
		FileWriter f2 = new FileWriter("data2.txt");
		f2.write("Hello");
		f2.write("Java2");
		f2.close();
		
		f1.write("!!!");
		f1.close();
		// 긴 맥락을 가지고 작업해야하는 작업인 경우에는 클래스를 직접 사용하는게 아니라 클래스를 복제해서 복제본을 만들어 사용한다.

	}

}

### This is a H3
3 변수와 메소드
public class MyOOP {
	public static String delimiter = "";

	public static void main(String[] args) {
		String delimiter = "----";
		printA();
		printA();
		printB();
		printB();
		
		delimiter = "****";
		printA();
		printA();
		printB();
		printB();
//메소드 안에서 정의된 변수는 그 메소드 안에서만 쓸 수 있다.
	}

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

}

#### This is a H4
4-1 클래스(존재 이유와 기본형식)
클래스는 관련있는 변수들과 메소드를 묶어서 정리정돈을 할 수 있게 합니다.
구분자로 분리된 A 문자열과 B 문자열을 출력하는 메소드를
Print라는 클래스로 따로 떼어내서 만들 수 있게 되었습니다.
그래서 굳이 메소드의 이름을 printA라고 적지 않고 A라고만 적어도

Print 객체의 A메소드이기 때문에 A를 출력한다는 의미를 쉽게 유추할 수 있게 됩니다.
class Print{
	public static String delimiter = "";
	public static void A() {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	
	public static void B() {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
}
public class MyOOP {
	public static void main(String[] args) {
		Print.delimiter = "----";
		Print.A();
		Print.A();
		Print.B();
		Print.B();
		
		Print.delimiter = "****";
		Print.A();
		Print.A();
		Print.B();
		Print.B();
	}

}

4-2 클래스 (형식)
클래스는 한 파일에 여러 개를 넣을 수 있지만, 접근제어자 public은 java 파일과 같은 이름의 클래스에 하나만 붙일 수 있습니다.
우리가 public 클래스를 실행하고자 할 때, 자바의 소스코드를 실행하고자 할 때, 소스코드 파일명과 동일한 public 클래스를 컴파일해서 그 클래스의 main 메소드를 실행하도록 약속되어 있습니다. 소스 코드를 컴파일을 할 때 그 안에 들어 있는 클래스는 아래와 같이 따로따로 하나씩 class 파일로 만들어집니다.
그러므로, 한 파일 안에 여러 클래스가 등장할 수도 있지만 여러 클래스를 각각 하나의 java 파일로 만들게 되면, 프로그램의 기능별로 쪼개어서 소스 코드를 별도로 저장할 수 있게 됩니다. 실행을 담당하는 main 메소em가 들어 있는 MyOOP.java 파일,프로그램의 실질적인 액션을 담당하는 Print.java 파일로 분리해서  코드를 정리정돈 할 수 있게 됩니다.

Refactor -> Move type to new File

##### This is a H5
5 인스턴스
클래스는 어떠한 형틀이고, 인스턴스는 그 형틀로 찍어낸 실체와도 같은 것입니다.
그래서 클래스를 바꾸면 그것으로 찍어낸 모든 사물들이 다른 형태를 갖게 되고.
형틀로 찍어낸 사물을 바꾸면 그 사물의 자매와도 같은 다른 사물에는 어떠한 영향도 없습니다.
즉 객체를 인스턴스로 만들면, 그 인스턴스를 바꾼다고 해도 다른 인스턴스에는 영향을 끼치지 않게 됩니다.


public class MyOOP {
	public static void main(String[] args) {
		Print p1 = new Print();
		p1.delimiter = "----";
		p1.A();
		p1.A();
		p1.B();
		p1.B();
		
		Print p2 = new Print();
		p2.delimiter = "****";
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

###### This is a H6
static
인스턴스를 생성하지 않고 클래스에서 바로 인스턴스의 변수와 메소드에 접근할 수 없습니다.
즉 static이 아닌 변수와 메소드는 인스턴스를 생성해야 비로소 접근할 수 있게 됩니다.

클래스의 변수를 바꾸면 모든 인스턴스의 변수의 값이 바뀐다. 인스턴스에서 그 클래스의 변수를 바꿀 수 있는데 그러면 클래스의 변수가 바뀌고 걔를 사용하고 있는 모든 인스턴스의 값도 바뀐다.

class Foo{
	public static String classVar = "I class var";
	public String instanceVar = "I instance var";
	
	public static void classMethod() {
		System.out.println(classVar);//OK // 클래스 메소드 안에서 클래스 변수에는 접근 가능
//		System.out.println(instanceVar);//Error // 인스턴스 변수에는 접근 불가
	}
	public void instanceMethod() {
		System.out.println(classVar);//OK
		System.out.println(instanceVar);//OK
	}//인스턴스 메소드에서는 클래스 변수, 인스턴스 변수 모두 가능
}
public class StaticApp {

	public static void main(String[] args) {
		System.out.println(Foo.classVar);//OK // 클래스를 통해서 클래스 변수에 접근 가능
//		System.out.println(Foo.instanceVar);//Error // 인스턴스는 인스턴스를 통해서 접근해야함
		Foo.classMethod();
//		Foo.instanceMethod();//인스턴스 메소드는 인스턴스 소속이기 떄문에 클래스를 통해 접근하는건 금지
		
		Foo f1 = new Foo(); //f1 인스턴스
		Foo f2 = new Foo(); //f2 인스턴스
		
		System.out.println(f1.classVar); // I class var
		System.out.println(f1.instanceVar); // I instance var
		
		f1.classVar = "changed by f1"; // f1은 인스턴스인데 인스턴스의 클래스바는 static이기 때문에 Foo클래스에 있는 클래스바라고 하는 변수의 값이 changed by f1바뀌게 된다.
		System.out.println(Foo.classVar); // changed by f1
		System.out.println(f2.classVar); // changed by f1
		
		f1.instanceVar = "cganged by f1";
		System.out.println(f1.instanceVar); // changed by f1
		System.out.println(f2.instanceVar); // I instance var // f2는 f1과 독립적인 변수를 운영하고 있기 떄문에 값이 바뀌지 않게 된다.

	}

}

###### This is a H7
7 생성자와 this
클래스는 인스턴스를 생성할 때 클래스의 이름과 같은 이름인 생성자로 인스턴스를 만듭니다.
클래스는 따로 만들어 주지 않아도 기본 생성자를 포함하고 있습니다.
Print()와 같이 아무것도 지정하지 않는 생성자를 기본 생성자라고 합니다.
기본적으로 public 권한으로 설정되어 있어서 따로 명시하지 않아도 클래스를 만들게 되면
새로운 인스턴스를 생성할 수 있도록 만듭니다.

this는 인스턴스를 가리키는 예약어
class Print{
	public  String delimiter = "";
	public Print(String delimiter) {
		this.delimiter = delimiter;// this라고 하는 특수한 키워드는 내가 생성한 인스턴스를 가리키는 이름
	}
	public static void A() {
		System.out.println(this.delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	
	public static void B() {
		System.out.println(this.delimiter);
		System.out.println("B");
		System.out.println("B");
	}
}

###### This is a H8-1
8-1 활용 (클래스화)
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

###### This is a H8-2
8-2 활용 (인스턴스화)
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

###### This is a H9
어떤 클래스를 상속해서 새로운 클래스를 만들게 되면, 
어떤 클래스의 모든 변수와 메소드들이 기본적으로 새로운 클래스에 포함되게 되고,
만약 부족하다면 기존의 변수와 메소드를 덮어쓰거나(overiding),
아예 새로운 변수와 메소드를 추가할 수도 있습니다.
그리고 인터페이스는 일종의 규격과도 같은 것입니다.


This is an 상속
-------------
# This is a H1
수업소개
class Cal{
	public int sum(int v1,int v2) {
		return v1+v2;
		
	}
}
class Cal3 extends Cal{//Cal3가 Cal을 상속 받는다
	
}
public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
		
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));
//c3라는 인스턴스에 sum메소드를 호출해줘 하게되면 c3가 가리키는 클래스에서 sum이라고 하는 메소드를 찾는데 c3는 Cal을 확장하고 있기 때문에 Cal클래스에서 sum이라고 하는 메소드를 찾고 실핼시킨다.
	}

}
class Cal2{
	public int sum(int v1,int v2) {
		return v1+v2;
	}
	public int minus(int v1,int v2) {
		return v1-v2;
	}
}


## This is a H2
기능의 개선과 발전
class Cal{
	public int sum(int v1,int v2) {
		return v1+v2;
		
	}
}
class Cal3 extends Cal{//Cal3가 Cal을 상속 받는다
	public int minus(int v1,int v2) {
		return v1-v2;
	}
	//Overriding : 부모가 가지고 있는 기능을 올라탔다, 덮어썼다. 
	public int sum(int v1,int v2) {
		System.out.println("Cal3");
		return v1+v2;
	}

}
public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
		
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));//3
		System.out.println(c3.minus(2, 1));//1
		System.out.println(c3.sum(2, 1));//Cal3 3

	}

}

### This is a H3
Overriding, Overloading
class Cal{
	public int sum(int v1,int v2) {
		return v1+v2;
	}
	// Overloading
	public int sum(int v1,int v2,int v3) {
		return v1+v2+v3;
	}
	//자바는 같은 이름의 메소드를 여러개를 과적할 수 있다. 형태만 다르면
}
class Cal3 extends Cal{//Cal3가 Cal을 상속 받는다
	public int minus(int v1,int v2) {
		return v1-v2;
	}
	// Overriding : 부모가 가지고 있는 기능을 올라탔다, 덮어썼다. 
	public int sum(int v1,int v2) {
		System.out.println("Cal3");
		return v1+v2;
	}

}
public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
		System.out.println(c.sum(2, 1,1));
		
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));//3
		System.out.println(c3.minus(2, 1));//1
		System.out.println(c3.sum(2, 1));//Cal3 3

	}

}

#### This is a H4
This Super
class Cal{
	public int sum(int v1,int v2) {
		return v1+v2;
	}
	// Overloading
	public int sum(int v1,int v2,int v3) {
		return this.sum(v1,v2)+v3;// this는 자기자신을 가리키므로 자기자신의 sum이므로 위에껄 실행시킨 결과에다가 v3를 더한 연산결과를 만들어 낸다
	}
}
class Cal3 extends Cal{//Cal3가 Cal을 상속 받는다
	public int minus(int v1,int v2) {
		return v1-v2;
	}
	// Overriding
	public int sum(int v1,int v2) {
		System.out.println("Cal3");
		return super.sum(v1, v2);//이 클래스의 부모 클래스 Cal의 sum을 가리키게 된다.
	}

}
public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
		System.out.println(c.sum(2, 1,1));
		
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));//3
		System.out.println(c3.minus(2, 1));//1
		System.out.println(c3.sum(2, 1));//Cal3 3

	}

}

##### This is a H5
상속과 생성자
lass Cal{
	int v1,v2;
	Cal(int v1, int v2){
		System.out.println("Cal init!!");
		this.v1 = v1; this.v2 = v2;
	}
	public int sum() {
		return this.v1+v2;
	}
}
class Cal3 extends Cal{
	
	Cal3(int v1, int v2){
		super(v1,v2);//부모 클래스의 생성자를 실행
		System.out.println("Cal3 init!!");
	}
	public int minus() {
		return this.v1-v2;
	}
}
public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal(2,1);
		Cal3 c3 = new Cal3(2,1);
		System.out.println(c3.sum()); // 3
		System.out.println(c3.minus()); // 1
		
	}

}

###### This is a H6
다형성(polymorphism) : 상속 관계에 있는 클래스간의 호환성을 높여주는 기능
접근 제어자(access modifier) : default의 경우 같은 패키지 내의 클래스에서는 접근할 수 있는 권한이 있고, 
protected의 경우 해당 클래스와 자식 클래스를 통해서 접근할 수 있습니다.
final 키워드 : 상속과 관련하여 제한을 걸어주는 키워드
abstract 키워드 : 해당 클래스, 메소드가 재정의가 필요하다는 것을 강제하는 키워드

This is an 인터페이스
-------------
# This is a H1
소개
interface Calculable{
	int sum(int v1,int v2);
}
class RealCal implements Calculable{
	public int sum(int v1, int v2) {
		return v1+v2;
	}
	
}
class DummyCal implements Calculable{
	public int sum(int v1, int v2) {
		return 3;
	}
}
public class InterfaceApp {
	public static void main(String[] args) {
		RealCal c = new RealCal();
	    System.out.println(c.sum(2,1));
	}
}//인터페이스는 약솟이다 클래스의 형태를 규정한다.

## This is a H2
인터페이스의 형식
interface Calculable{
	double PI = 3.14;// 인터페이스에는 메소드와 변수가 정의 될 수 있는데 변수에는 값이 들어오고 메소드에는 실제 구현이 들어가지 않아서 저 메소드를 구현하는 클래스가 저 형태를 만족하는 메소드의 내용을 직접 구현해야한다.
	int sum(int v1,int v2);
}
interface Printable{
	void print();//메소드를 인터페이스에 정의할 땐 내용이 들어가지 않는다. 변수를 정의할 떈 내용이 들어간다.
	
}

class RealCal implements Calculable, Printable{
	public int sum(int v1, int v2) {
		return v1+v2;
	}// 하나의 클래스는 여러개의 인터페이스를 구현할 수 있다.

	public void print() {
		System.out.println("This is RealCall!!");
	}
}

class DummyCal implements Calculable{
	public int sum(int v1, int v2) {
		return 3;
	}
}
public class InterfaceApp {
	public static void main(String[] args) {
		RealCal c = new RealCal();
	    System.out.println(c.sum(2,1));
	    c.print();
	    System.out.println(c.PI);
	}
}//인터페이스는 약솟이다 클래스의 형태를 규정한다.

### This is a H3
다형성 : 객체의 타입이 부모 클래스, 인터페이스, 자식 클래스 등 여러 형태인데도 인스턴스로 만든 객체(자식 클래스의 인스턴스)와 같이 행동하는 것
interface Calculable{
	double PI = 3.14;
	int sum(int v1,int v2);
}
interface Printable{
	void print();
	
}

class RealCal implements Calculable, Printable{
	public int sum(int v1, int v2) {
		return v1+v2;
	}

	public void print() {
		System.out.println("This is RealCall!!");
	}
}

class AdvancePrint implements Printable{
	public void print() {
		System.out.println("This is RealCal!!");
	}
}
public class InterfaceApp {
	public static void main(String[] args) {
		Printable c = new AdvancePrint();
	    c.print();
	}
}//어떠한 클래스가 데이터 타입을 뭘로 하느냐에따라 다양한 얼굴을 갖게 되는게 다형성 

#### This is a H4
사용설명서 속의 인터페이스
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


This is an H1
================

This is an 섹션1
----------------
# This is a H1
package hello.hellospring;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class HelloSpringApplication {

	public static void main(String[] args) {

		SpringApplication.run(HelloSpringApplication.class, args);
	}

}


## This is a H2
스프링 부트 라이브러리
spring-boot-starter-web에 
 spring-boot-starter-tomcat: 톰캣 (웹서버)
 spring-webmvc: 스프링 웹 MVC
이 2가지가 들어있다.

spring-boot-starter-thymeleaf: 타임리프 템플릿 엔진(View)
spring-boot-starter(공통): 스프링 부트 + 스프링 코어 + 로깅
 spring-boot
  spring-core
 spring-boot-starter-logging 을 logback, slf4j 이 두 가지 조합으로 운영


테스트 라이브러리
spring-boot-starter-test
 junit: 테스트 프레임워크
 mockito: 목 라이브러리
 assertj: 테스트 코드를 좀 더 편하게 작성하게 도와주는 라이브러리
 spring-test: 스프링 통합 테스트 지원


### This is a H3
resources/static/-> New File만들기 : index.html

<!DOCTYPE HTML>
<html>
<head>
 <title>Hello</title>
 <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
Hello
<a href="/hello">hello</a>
</body>
</html>

#### This is a H4
(mian/java/hello.hellospring/controller/HelloController)
package hello.hellospring.controller;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HelloController {
    @GetMapping("hello")
    public String hello(Model model){
        model.addAttribute("data","hello!!"); // 값은 hello!!
        return "hello";
    }
}

-->  return "hello"; 에서 hello는 resources/templates/hello.html의 이름과 같다. 따라서 'resources/templates/hello.html를 찯아서 가서 랜더링 해라.' 라는 뜻.


(resources/templates/hello.html)
<!DOCTYPE HTML>
<html xmlns:th="http://www.thymeleaf.org">
<head>
 <title>Hello</title>
 <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
<p th:text="'안녕하세요. ' + ${data}" >안녕하세요. 손님</p>
</body>
</html>

--> ${data}는 model에서의 hello!!
==> 실행 : localhost:8080/hello -> 안녕하세요. hello!!
( localhost:8080/hello라고 치면 스트링 부트가 톰켓을 내장하고 있기떄문에 HelloController에 @GetMapping("hello")에 매칭이 되서 이 메소드가 실행된다. )

컨트롤러에서 리턴 값으로 문자를 반환하면 뷰 리졸버( viewResolver )가 화면을 찾아서 처리한다.
 스프링 부트 템플릿엔진 기본 viewName 매핑
 resources:templates/ +{ViewName}+ .html   -> 여기서 {ViewName}은 즉, hello

> 참고: spring-boot-devtools 라이브러리를 추가하면, html 파일을 컴파일만 해주면 서버 재시작 없이
View 파일 변경이 가능하다.
> 인텔리J 컴파일 방법: 메뉴 build Recompile


##### This is a H5
빌드하고 실행하기
윈도우 사용자를 위한 팁
콘솔로 이동 명령 프롬프트(cmd)로 이동
./gradlew gradlew.bat 를 실행하면 됩니다.
명령 프롬프트에서 gradlew.bat 를 실행하려면 gradlew 하고 엔터를 치면 됩니다.
gradlew build