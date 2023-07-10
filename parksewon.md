**helloworld출력**
0501
public class HelloworldApp{
	public static void main(String[] args) {
		System.out.println("HelloWorld!!");
	}
}
**데스크톱 어플리케이션 만들기**
import javax.swing.*;   
import java.awt.Dimension;
import java.awt.Toolkit;
public class HelloWorldGUI{
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
**Dimension()괄호안의 숫자로 가로 세로의 길이 조정and right를 넣어서 문자를 우측으로 보냄
수장한 코드JLabel label = new JLabel("Hello World!!", SwingConstants.LEFT);**

**java코드를 이용해 라즈베리파이의 특정된 부위에 전기를 통하도록 할수 있음**
0502
public class Datatype{
	public static void main(String[]args) {
		System.out.println(6);//Number
		System.out.println("six");//String
		System.out.println("6");//String 6
		System.out.println(6+6);//12
		System.out.println("6"+"6");//66"문자사이의+는 문자결합자로 사용됨
		
		System.out.println(6*6);//36
		//System.out.println("6"*"6");문자열은 *사용이 되지않음//
		System.out.println("1111".length());//문자열의 길이를 알려줌 length는 숫자의 길이를 알려주지는 않음
		
		
	}
}
public class StringApp {

	public static void main(String[] args) {
	
		System.out.println("Hello World");//String
		//System.out.println('Hello World');Charter 문자와 문자열은 차이가 있음//
		System.out.println("Hello "
				+ "World");
		System.out.println("Hello \nWorld");//\n을 이용하여 줄바꿈을 사용할수 있다.
		System.out.println("Hello \"World\""); //문자열 사이에 ""를 추가하기 위해서 \\사이에 ""문자열을 추가해준다Hello "World"
		
	}

}

public class StringOperation {

	public static void main(String[] args) {
		
		System.out.println("Hello World".length());//11
		System.out.println("Hello, leezche ...bye. ".replace("leezche", "egoing"));//replace는 앞에를 뒤에로 바꿔준다.
		

	}

}
0503
public class Variable {

	public static void main(String[] args) {
		
		int a = 1;//number => integer==정수 -값과 0 +값을 가짐
		System.out.println(a);
		double b = 1.1;//real number =>double 실수 음의값과 0과 양의값과 소수점의 값을 가짐
		System.out.println(b);
		String c = "Hello World";//문자열
		System.out.println(c);
	}

}
public class Letter {

	public static void main(String[] args) {
		String name = "leezche";//변수의 이름을 정해줌으로써 목적을 파악할 수있다.
		System.out.println("Hello. "+name+" ... "+name+" ... "+name+" ... bye");
		double VAT = 10.0;
		System.out.println(VAT);
	}

}
public class program {

	public static void main(String[] args) {
		
		System.out.println(1);
		System.out.println(2);
		System.out.println(3);
		//만약 위 코드의 개수가 10000개가 넘는다면 사람이 할 수 없는 일을 컴퓨터 언어인 자바에 위임이켜서 실해하는것
	}

}
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
public class OKjavaGoinHome {

	public static void main(String[] args) {
		
		String id = "java apt 507";
		
		//Elevator call
		Elevator myElevator = new Elevator(id);//Elevator 는 데이터 타입, myElevator는 변수.
		myElevator.callForUp(1);
		
		//Security off
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		//Light on
		Lighting hallLamp = new Lighting("id+ /  hall lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting("id+ / hall lamp");
		floorLamp.on();
		
		

	}

}
//디버거 코드를 분석 step over 명령어 하나만 실행 디버거를 통해 잘못된 코드를 찾을 수 있다.

0507
import javax.swing.JOptionPane;

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
public class OKjavaGoinHome {

	public static void main(String[] args) {
		
		String id = JOptionPane.showInputDialog("Enter a ID");//showInputDialog는 상자에 값을입력할때까지 대기함		
		//Elevator call
		String bright = JOptionPane.showInputDialog("Enter a Bright Level");
		Elevator myElevator = new Elevator(id);//Elevator 는 데이터 타입, myElevator는 변수.
		myElevator.callForUp(1);
		
		//Security off
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		//Light on
		Lighting hallLamp = new Lighting("id+ /  hall lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting("id+ / hall lamp");
		floorLamp.on();
		
		DimmingLights moodLamp = new DimmingLights(id+"moodLamp");
		moodLamp.setBright(Double.parseDouble(bright));
		moodLamp.on();
	}

}
//디버거 코드를 분석 step over 명령어 하나만 실행
//showInputDialog를 통해 값을 입력해야만 작동한는 장치를 만들어 보았다.
String id = args[0];
String bright = args[1];
// argument는 사용자 입력을 의미하는 문자열배열이다.
//parameter는 함수에서 전달되어 사용되어지는 변수이다. argument는 main()함수의 매개변수로 작용한다.
//배열은 메모리에 순서대로 차곡차곡 저장된 데이터 묶음이다.배열은 미리 데이터의 크기와 각 데이터의 종류가 지정되어야 메모리를얼마나 차지할지 정할수 있다.
javac를 이용해 자바의 각종 명령어를 알 수 있음.
컴파일 : 'javac 파일이름.java' 명령어를 사용하면 해당 파일이 컴퓨터가 이해할 수 있는 확장자가 .class인 파일이 생성된다. 

실행 : 'java 파일이름' 명령어를 사용해 프로그램을 실행시킨다. java가 해당 파일에서 파일이름과 동일한 클래스를 찾고 main 함수를 찾은 뒤 main 안의 코드를 순차적으로 실행하고 종료한다.

다른 사람이 만들어 여러 유용한 기능을 모아둔 클래스 집합, 개발 시 공동으로 사용될 수 있는 특정한 기능들을 모듈화 한 것으로, 완전한 프로그램이 아닌 특정한 부분만을 수행할 수 있도록 만들어 놓은 것. 
패키지는 비슷한 기능을 모아둔 것, 라이브러리는 패키지들이나 파일들이 모아져 있는것이 라이브러리이다 

이클립스나 비주얼 스튜디오가 설치가 안되어있거나 실행이 안될때 간략하게 터미널로 실행해 볼 수 있다


많은 클릭 과정을 생략하고 단 한줄로 컴파일 후 실행할 수 있다. 

0508
프로그램에게 사용되는 것이 API,
사용자가 자바 프로그램을 이용할 수 있도록 만들어 놓은것이 UI

패키지 : 클래스들을 모아둔 것 패키지를 통해 라이브러리와 구별이 가능하다. 


패키지를 사용하는 것은 클래스명을 보장하기 위함이다
서로 다른 용도의 라이브러리를 사용할 때 이름이 충돌하는 클래스가 있을 수 있는데 
이럴 때 패키지 기능을 이용하여 클래스 이름이 충돌하는 것을 방지한다.

클래스 : 객체를 정의할 수 있는 틀 또는 설계도이다. 클래스는 객체의 변수들과 객체 생성을 나타내는 메소드들로 나타낸다. 

변수 : 데이터를 저장하기 위한 메모리 공간

메소드 : 특정 작업을 수행하는 일련의 과정을 묶은 것, 즉 클래스에 필요한 기능을 함수로 묶은 것 이 때, 클래스는 객체의 변수들로 이루어져있다고 되어있는데 이는 필드라고도 한다. 클래스에 포함되어 있는 변수가 필드인 것이다. 

클래스는 메소드와 변수들의 집합이다.
패키지는 그 클래스들을 담아놓은 집합
메소드는 값을 입력해야 하는 함수이고, 변수는 그 함수의 값이다.
클래스안에는 변수와 메소드가 있다.
인스턴스는 클래스에 있는 속성을 사용하는 복제품을 만드는 것이다.
단, 인스턴스를 사용하려면 클래스 안에 컨스트럭쳐가 있어야 된다.
그러나 클래스 중에 constructor가 없는 클래스(예:Math)는  인스턴스로 사용하지 못하는 클래스다. 즉, 인스턴스를 사용하려면 일단 해당 클래스에 constructor 있어야된다 

상속은 말 그대로 상속받는것.
하위클래스가 상위클래스의 변수와 메소드를 어느정도 이어받으면서 새로운 클래스를 만들어 내는 것
모든 메소드나 변수를 만들지 않아도되고, 상위클래스의 메소드/변수를 함께 사용 할 수 있어서 좋다.

public class Accounting {

	public static void main(String[] args) {
		
		System.out.println("Value of supply : "+10000.0);
		System.out.println("VAT : "+(10000.0*0.1));
		System.out.println("Total : "+ (10000.0*0.1));
		System.out.println("Expense : "+ (10000.0*0.1));
		System.out.println("Income : "+ (10000.0 - 10000.0*0.3));
		System.out.println("Dividend1 : "+ (10000.0 - 10000.0*0.3)*0.5);
		System.out.println("Dividend2 : "+ (10000.0 - 10000.0*0.3)*0.3);
		System.out.println("Dividend3ㅍ : "+ (10000.0 - 10000.0*0.3)*0.2);
		
		
		
	}

}
public class Accounting {

	public static void main(String[] args) {
		
		
		double valueOfSupply = 10000.0;
		double exepnseRate = 0.3;
		double vatRate = 0.1;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply*exepnseRate;
		double income = valueOfSupply - expense;
		double dividend1 = income*0.5;
		double dividend2 = income*0.3;
		double dividend3 = income*0.2;
		
		System.out.println("Value of supply : "+valueOfSupply);	
		
		System.out.println("VAT : "+vat);
		
		System.out.println("Total : "+ total);
		
		System.out.println("Expense : "+ expense);
		System.out.println("Income : "+ income);
		
		System.out.println("Dividend1 : "+ dividend1);
		
		System.out.println("Dividend2 : "+ dividend2);
		
		System.out.println("Dividend3 : "+ dividend3);
		
		
		
	}

}
double valueOfSupply = Double.parseDouble(args[0]);
//args라는 문자열을 더블형에 넣어줌
if문을 사용한 조건문
public class Accountingif {

	public static void main(String[] args) {
			
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double exepnseRate = 0.3;
		double vatRate = 0.1;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply*exepnseRate;
		double income = valueOfSupply - expense;
		double dividend1;
		double dividend2;
		double dividend3;
		if(income > 10000.0) {
			dividend1 = income*0.5;
			dividend2 = income*0.3;
			dividend3 = income*0.2;
		} else {
			dividend1 = income*1.0;
			dividend2 = income*0;
			dividend3 = income*0;
		}
		
		
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+vat);
		System.out.println("Total : "+ total);
		System.out.println("Expense : "+ expense);
		System.out.println("Income : "+ income);
		System.out.println("Dividend1 : "+ dividend1);
		System.out.println("Dividend2 : "+ dividend2);
		System.out.println("Dividend3 : "+ dividend3);
		
		
		
	}
	public class AccountingArray {

	public static void main(String[] args) {
			
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double exepnseRate = 0.3;
		double vatRate = 0.1;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply*exepnseRate;
		double income = valueOfSupply - expense;
		
		double[] dividendRates = new double[3];
		dividendRates[0] = 0.5;
		dividendRates[1] = 0.3;
		dividendRates[2] = 0.2;
		
		double dividend1 = income*dividendRates[0];
		double dividend2 = income*dividendRates[1];
		double dividend3 = income*dividendRates[2];
		
		System.out.println("Value of supply : "+valueOfSupply);	
		
		System.out.println("VAT : "+vat);
		
		System.out.println("Total : "+ total);
		
		System.out.println("Expense : "+ expense);
		System.out.println("Income : "+ income);
		
		System.out.println("Dividend1 : "+ dividend1);
		
		System.out.println("Dividend2 : "+ dividend2);
		
		System.out.println("Dividend3 : "+ dividend3);
		
		
		
	}
반복문을 사용함으로써 하나의 문장으로 여러개의 로직을 사용가능하게 한다.
	public class AccountingArrayLoop {

	public static void main(String[] args) {
			
		
		double valueOfSupply = Double.parseDouble(args[0]);
		double exepnseRate = 0.3;
		double vatRate = 0.1;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply*exepnseRate;
		double income = valueOfSupply - expense;
		
		double[] dividendRates = new double[3];
		dividendRates[0] = 0.5;
		dividendRates[1] = 0.3;
		dividendRates[2] = 0.2;
		
		
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+vat);
		System.out.println("Total : "+ total);
		System.out.println("Expense : "+ expense);
		System.out.println("Income : "+ income);
		
		double dividend1 = income*dividendRates[0];
		double dividend2 = income*dividendRates[1];
		double dividend3 = income*dividendRates[2];
		
		
		int i = 0;
		while(i < dividendRates.length) {
		System.out.println("Dividend : "+ (income * dividendRates[i]));
		i = i + 1;
		}
		
	}

}

public class AccountingMethod {
	public static double valueOfSupply;
	public static double vatRate;
	public static double exepnseRate;
	public static void main(String[] args) {
			
		valueOfSupply = 10000.0;
		vatRate = 0.1;
		
		double vat = getVAT();
		double total = getTotal();
		double expense = getExepnse();
		double income = getIncome();
		double dividend1 = getDividend1();
		double dividend2 = getDividend2();
		double dividend3 = getDividend3();
		
		print();
			
	}

	public static void print() {
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : "+ getTotal());
		System.out.println("Expense : "+ getExepnse());
		System.out.println("Income : "+ getIncome());
		System.out.println("Dividend1 : "+ getDividend1());
		System.out.println("Dividend2 : "+ getDividend2());
		System.out.println("Dividend3 : "+ getDividend3());
	}

	public static double getDividend1() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}
	public static double getDividend2() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public static double getDividend3() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public static double getIncome() {
		double income = valueOfSupply - getExepnse();
		return income;
	}

	public static double getExepnse() {
		double expense = valueOfSupply*exepnseRate;
		return expense;
	}

	public static double getTotal() {
		double total = valueOfSupply + getVAT();
		return total;
	}

	private static double getVAT() {
		return valueOfSupply*vatRate;//메소드를 만드는 코드
	}

}
//메소드를 사용해 수많히 많은 개수의 코드를 간략화 해서 만들수 있다.

//클래스
class Accounting{
	 {
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : "+ getTotal());
		System.out.println("Expense : "+ getExepnse());
		System.out.println("Income : "+ getIncome());
		System.out.println("Dividend1 : "+ getDividend1());
		System.out.println("Dividend2 : "+ getDividend2());
		System.out.println("Dividend3 : "+ getDividend3());
	}

	public static double valueOfSupply;
	public static double vatRate;
	public static double exepnseRate;
	public static double getDividend1() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}
	public static double getDividend2() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public static double getDividend3() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public static double getIncome() {
		double income = valueOfSupply - getExepnse();
		return income;
	}

	public static double getExepnse() {
		double expense = valueOfSupply*exepnseRate;
		return expense;
	}

	public static double getTotal() {
		double total = valueOfSupply + getVAT();
		return total;
	}

	private static double getVAT() {
		return valueOfSupply*vatRate;//메소드를 만드는 코드
	}
	public static void print() {
		
		
	}

	
}
public class Accountingclass {
	
	public static void main(String[] args) {
			
		Accounting.valueOfSupply = 10000.0;
		Accounting.vatRate = 0.1;
		Accounting.exepnseRate = 0.3;
		Accounting.print();;
		//anotherVariable = ...;
		//anotherMethod = ...;
	
		
			
	}

	
	
}
//클래스는 객체지향의 핵심으로 서로 연관된 변수와 메소드를 그룹핑해 소속관계를 명확히 해서 이름을 붙여 놓은 것이다. 사용하는 이유는 소속관계를 명확학게 해 재사용성과 유지보수를 용이하게 하기 위해서 이다.//
//인스턴스는 하나의 클래스를 복제해서 서로다른 데이터의 값과 서로 같은 메소드를 가진 복제본을 만드는 것.
//클래스의 상태를 변경하는 행위가 버그를 유발할 가능성이 있음
//클래스 앞에 new를 붙여 복제한 것을 인스턴스(instance)라고 함
//static이 사용되어서는 안됨

class Accounting{
	public double valueOfSupply;
	public double vatRate;
	public double exepnseRate;
	 {
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : "+ getTotal());
		System.out.println("Expense : "+ getExepnse());
		System.out.println("Income : "+ getIncome());
		System.out.println("Dividend1 : "+ getDividend1());
		System.out.println("Dividend2 : "+ getDividend2());
		System.out.println("Dividend3 : "+ getDividend3());
	}

	
	public double getDividend1() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}
	public double getDividend2() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public double getDividend3() {
		double dividend1 = getIncome()*0.5;
		return dividend1;
	}

	public double getIncome() {
		double income = valueOfSupply - getExepnse();
		return income;
	}

	public double getExepnse() {
		double expense = valueOfSupply*exepnseRate;
		return expense;
	}

	public double getTotal() {
		double total = valueOfSupply + getVAT();
		return total;
	}

	private  double getVAT() {
		return valueOfSupply*vatRate;//메소드를 만드는 코드
	}
	public void print() {
		
		
	}

	
}

public class Accountingclass {
	
	public static void main(String[] args) {
			
		
		//instance
		Accounting a1 = new Accounting();
		a1.valueOfSupply = 10000.0;
		a1.vatRate = 0.1;
		a1.exepnseRate = 0.3;
		a1.print();
		
		Accounting a2 = new Accounting();
		a2.valueOfSupply = 20000.0;
		a2.vatRate = 0.05;
		a2.exepnseRate = 0.2;
		a2.print();
			
	}

	
	
}
0510
public class BooleanApp {

	public static void main(String[] args) {
		
		System.out.println(true);
		System.out.println(false);
		String foo = "Hello World";
		System.out.println(foo.contains("world"));
		System.out.println(foo.contains("egoin"));

	}

}
//boolean은 값의 일치 불일치 여부를 확인할 수 있다.

public class ComparisonOperatorApp {

	public static void main(String[] args) {
		
		System.out.println(1 > 1);//false
		System.out.println(1 == 1);//true
		System.out.println(1 < 1);//false
		System.out.println(1 >= 1);//true
		
	}

}
//비교연산자는 두 값을 비교하여 비교에 대한 결과값을 출력함.

if문의 작성
public class ifApp {

	public static void main(String[] args) {
		
		
		//System.out.println("a");
		//if(false) {
			//System.out.println(1);
		//} else {
		//	if(true) {
		//		System.out.println(2);
		//	} else {
		//		System.out.println(3);
		//	}
		//}
		if(false) {
			System.out.println(1);
		} else if(true){
			System.out.println(2);
		} else {
			System.out.println(3);
		}
		
		System.out.println("b");
		}
}


//비밀번호도 인식하게 바꾸고 논리연사자를 사용해 코드 간략화 실시
public class AutApp {

	public static void main(String[] args) {
		
		System.out.println(args[0]);

		String id = "egoing";
		String inputId = args[0];
		
		String pass = "1111";
		String inputPass = args[1];
		
		System.out.println("hi");
		
		//if(inputId == id) {
//		if(inputId.equals(id)) {//코드가 반환하는 값은 boolean이다.
//			if(inputPass.equals(pass)) {
//				System.out.println("Master!");
//			}else {
//				System.out.println("wrong password");
//			}
//			
//		}else {
//			System.out.println(":Who are you?");
//		}
		if(inputId.equals(id)  && (inputPass.equals(pass)) ) {//논리연산자인 && 사용.
			{
				System.out.println("Master!");
			}
		}else {
			System.out.println(":Who are you?");//코드 간략화 실시
		}
		
	}

}

논리연산자를 이용해 2개의 비밀번호의 if를 간략화 시킬수 있다.
public class AutApp2 {

	public static void main(String[] args) {
		
		System.out.println(args[0]);

		String id = "egoing";
		String inputId = args[0];
		
		String pass = "1111";
		String pass2 = "2222";
		String inputPass = args[1];
		
		System.out.println("hi");
		boolean isRightPass = (inputPass.equals(pass) || inputPass.equals(pass2));
		

		if(inputId.equals(id)  &&  isRightPass  ) {
			{
				System.out.println("Master!");
			}
		}else {
			System.out.println(":Who are you?");
		}
		
	}

}

배열
public class ArrayApp {

	public static void main(String[] args) {
		
		String[] users = new String[3];
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		System.out.println(users[1]);
		System.out.println(users.length);
		
		int[] scores = {10,100,100};
		System.out.println(scores[1]);
		System.out.println(scores.length);
	}

}
데이터타입[] 배열이름= new 데이터타입[크기]; 

데이터타임[] 배열이름 = {데이터, 데이터, ...} 2가지 형식으로 배열 생성이 가능하다.

반복문과 배열의 결합
public class LoopArray {

	public static void main(String[] args) {
		
		String[] users = new String[3];
		users[0] = "egoing";
		users[1] = "jinjuck";
		users[2] = "youbin";
		
		for(int i = 0; i<3; i++) {
			System.out.println(users[i]+",");
		}
	}

}

아이디 저장하는 프로그램
public class AutApp3 {

	public static void main(String[] args) {
		
		String[] users = {"egoing", "jinhuck", "youbin"};
		String inputId = args[0];
		
		boolean isLogined = false;
		for(int i = 0; i<users.length; i++) {
			String currentId = users[i];
			if(currentId.equals(inputId)) {
				isLogined = true;
				break;
			}
		}
		System.out.println("hi,");
		if(isLogined) {
			System.out.println("master");
		}else {
			System.out.println("hwo are you");
		}
		
	}

}

아이디와 비밀번호를 가지는 프로그램
public class AutApp3 {

	public static void main(String[] args) {
		
		//String[] users = {"egoing", "jinhuck", "youbin"};
		String[][] users = {
				{"egoing", "1111"},
				{"jinhuck", "22222"},
				{"youbin", "3333"}
		};
		String inputId = args[0];
		String inputPass = args[1];
		
		boolean isLogined = false;
		for(int i = 0; i<users.length; i++) {
			String[] current = users[i];
			if(
					current[0].equals(inputId) && 
					current[1].equals(inputPass)
					) {
				isLogined = true;
				break;
			}
		}
		System.out.println("hi,");
		if(isLogined) {
			System.out.println("master");
		}else {
			System.out.println("hwo are you");
		}
		
	}

}

0511
public class Firstmethod {

	public static void main(String[] args) {
		
		System.out.println("Hello Method");
		System.out.println(Math.floor(1.1));

	}

}
//프로그램을 실행하기 위해서는 main이라는 특수한 메소드를 사용해야한다

public class whymethod {
	public static void printTwoTimesA() {//메소드의 이름이printTwoTimesA
		System.out.println("-");
		System.out.println("a");
		System.out.println("A");
	}
	public static void main(String[] args) {
		
		printTwoTimesA();
		printTwoTimesA();
		printTwoTimesA();//리팩터의 기능을 이용해서 편하게 메소드화 시킬수 있음.
		
		
	}

}

//메소드로 값을 주입하는 방법
public class whymethod {
	public static void printTwoTimes(String text, String delimiter) {//text, delimiter를 매개변수랑 함parameter
		System.out.println(delimiter);
		System.out.println(text);
		System.out.println(text);
	}
	public static void main(String[] args) {
						//인자 argument
		printTwoTimes("a", "-");
		printTwoTimes("a", "*");
		printTwoTimes("a", "&");
		printTwoTimes("b", "!");
	}

}

//메소드의 장점은 코드가 짧아지고 코드의 사용의 용이, 수정이 쉽다는 장점이 있지만 함수안에 어떤 코드가 있는지 보기 전에는 알아채기 어렵다는 단점이 있다.
import java.io.FileWriter;
import java.io.IOException;

public class whymethod {
	
	public static void main(String[]args)throws IOException{
		String out = twoTimes("a","-");
		System.out.println(out);
		FileWriter fw = new FileWriter("out.txt");
		fw.write(out);
		fw.close();
		System.out.println(twoTimes("a","*"));
	}
	public static String twoTimes(String text, String delimiter) {
		String out = "";
		out = out + delimiter + "\n";
		out = out + text + "\n";
		out = out + text + "\n";
		return out;
	
	}
	
}


//메소드를 이용해 코드를 간략하고 가독성이 좋게 만들수 있다.
public class AccountingApp {
	//공급가액	
	public static double valueOfSupply = 10000.0;
			
			//부가가치세율
	public static double vatRate = 0.1;
	
	public static double getVAT() {//메소드의 리턴값이 더블형임.
		return valueOfSupply*vatRate;
	}
	public static double getTotal(){
		return valueOfSupply + getVAT();
	}
	
	public static void main(String[] args) {
		
		//부가세
		//double vat = valueOfSupply*vatRate;
		double vat = getVAT();
		//합계
		//double total = valueOfSupply + vat;
		double total = getTotal();
		
		System.out.println("Value of supply : "+valueOfSupply);	
		System.out.println("VAT : "+getVAT());
		System.out.println("Total : "+ getTotal());
		
		
	}

}	


class Greeting{
	public static void hi() {
		System.out.println("HI");
	}
}
//public,protected, default, private
public class AccesLevelModifierMethod {
	
	public static void main(String[] args) {
		
		Greeting.hi();

	}

}
//private는 클래스 내부에서만 사용가능하다.
//public은 클래스 외부에서도 사용이 가능하다.1

0514
//static이 있는 메소드는 class method다
//sttic이 없는 메소드는 instance method이다
class Print{
	public String delimiter;
	public void a() {
		System.out.println(this.delimiter);//메소드가 인스턴스 소속일 경우 static을 사용하지 않는다
		System.out.println("a");
		System.out.println("a");
	}
	public void b () {
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
public class staticmethod {
	
	public static void main(String[] args) {
		
//		Print.a("-");
//		Print.b("-");
		
		Print t1 = new Print();//앞에 new가 붙으면 복제가 된다,instance
		t1.delimiter = "-";
		t1.a();
		t1.b();
		Print.c("$");//class소속이기 때문에 static을 사용해서 불러옴
		
		Print t2 = new Print();
		t2.delimiter = "*";
		t2.a();
		t2.b();
		

	}
	

}


import java.io.FileWriter;
import java.io.IOException;
public class OthersAppOOP {

	public static void main(String[] args) throws IOException {
		//class: System, Math, FileWriter
		//instance : f1, f2
		
		System.out.println(Math.PI);
		System.out.println(Math.ceil(1.8));
		
		FileWriter f1 = new FileWriter("data.txt");
		f1.write("Hello");
		f1.write("java");
		f1.close();
		
		FileWriter f2 = new FileWriter("data2.txt");
		f2.write("Hello");
		f2.write("java2");
		f2.close();
	}

}



public class MyOOP {
	
	public static void main(String[] args) {
		delimiter = "----";
		printA();
		printA();
		printB();
		printB();
		
		delimiter = "****";
		printA();
		printA();
		printB();
		printB();
		
	}
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


}


클래스의 장점 내부의 코드가 수정이 필요할 때 수많은 코드를 모두 수정할 필요 없이 클래스 내부를 수정해 주면 된다.
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
public class MyOOP{
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

//public 접근제어자
여러 개의 클래스를 하나의 파일에 쓸 경우 한눈에 코드를 파악하기 좋지만 너무 길어질 경우 가독성이 떨어질 것 이다. 
각각 하나의 파일에 쓰는 경우 기능에 따라 분리해 관리할 수 있어 좋지만 한눈에 코드 파악하기에 어려울 것이다.



0515

class Foo{
	public static String classVar = "I class var";
	public String instanceVar = "I instance var";
	public static void classMethod() {
		System.out.println(classVar);
		//System.out.println(instanceVar);
	}
	public void instanceMethod() {
		System.out.println(classVar);
		System.out.println(instanceVar);
	}
}
public class StaticApp {

	public static void main(String[] args) {
		
		System.out.println(Foo.classVar);
		//System.out.println(Foo.instanceVar);
		Foo.classMethod();
		//Foo.intanceMethod();
		Foo f1 = new Foo();
		Foo f2 = new Foo();
		System.out.println(f1.classVar);
		System.out.println(f1.instanceVar);
		f1.classVar = "changed by f1";
		System.out.println(Foo.classVar);
		System.out.println(f2.classVar);
		
		f1.instanceVar = "changed by f1";
		System.out.println(f1.instanceVar);
		System.out.println(f2.instanceVar);
		
	}

}


0516
class accounting{
	public static double valueOfsupply;
	public static double vatRate = 0.1;
	public static double getVat() {
		return valueOfsupply * vatRate;
	}
	public static double getTotal() {
		return valueOfsupply + getVat();
			
		}	

	}

public class acountingapp {
	public static void main(String[] args) {
		accounting.valueOfsupply = 10000.0;
		System.out.println("Value of supply:" + accounting.valueOfsupply);
		System.out.println("VAT : " + accounting.getVat());
		System.out.println("Total : " + accounting.getTotal());
	}


	}




static을 삭제처리해서 인스턴스화 하고

생성할때 초기화해야하기 때문에 생성자 세팅을 해줘야한다. 
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


0518
class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
}
class Cal3 extends Cal{
	
}

public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));
		
	}


	

}
//상속을 통해 코드의 양을 줄일 수 있다.

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
//상속을 통해 부모가 가지지 않는 메소드를 추가하고, 부모가 가지는 메소드를 재정의 할 수 있다.<Overriding>

overriding : 기존의 클래스를 새로 상속한 클래스에서 기존 클래스의 메서드와 같은 이름의 메서드로 재정의 한 경우(같은 클래스 안에서 는 이뤄질 수 없다.)

overloading : 같은 클래스 내에서 형식이 다른 같은 이름의 메소드들이 여러개 있는 경우 기존에 없던 새로운 메서드를 정의.

super : 부모 클래스 인자

this : 본인 클래스 인자
부모클래스의 메서드를 오버라이딩 했을 때 자식클래스에서 부모 클래스를 사용하고 싶은 경우에 super 키워드 하나만으로 부모 클래스의 메서드에 접근 할 수 있다는 점이 편리하다.



0521
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

다형성(polymorphism)은 상속 관계에 있는 클래스간의 호환성을 높여주는 기능

접근 제어자(access modifier)default의 경우 같은 패키지 내의 클래스에서는 접근할 수 있는 권한이 있고,protected의 경우 해당 클래스와 자식 클래스를 통해서 접근할 수 있다.

final 키워드는 상속과 관련하여 제한을 걸어주는 키워드이다.만약 현재 클래스에서 더 이상 자식 클래스를 생성하지 못하게 막기 위해서는 클래스에 final 키워드를 삽입한다. 그리고, 메소드가 자식 클래스에서 더 이상 오버라이드 되기를 원하지 않는다면 메소드에 final 키워드를 삽입합니다.

abstract 키워드는 해당 클래스, 메소드가 재정의가 필요하다는 것을 강제하는 키워드 이다. abstract 메소드는 선언만 되어 있는 상태이고, abstract 클래스는 인스턴스로 만들 수 없다. 만약 클래스 안에 abstract 메소드가 있다면 그 클래스는 abstract 클래스여야 한다.

인터페이스
class DummyCal {
	public int sum(int v1, int v2) {
		// do something
        return result_value;
	}
}

class RealCal {
	public int sum(int v1, int v2, int v3) {
		return v1 + v2 + v3;
	}
}

interface Calculable {
	int sum(int v1, int v2);
}
class RealCal implements Calculable {

	public int sum(int v1, int v2) {
		return v1 + v2;
	}	
}

interface : 규격 지정

메소드에서 implements 인터페이스

시에 해당 메소드에서는 interface의 규격 메소드가 생성됨.

인스턴스로 해당 메소드 생성.

(A a = new A();)

a.해당 메소드로 기능 정립 및 호출


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

인터페이스는 껍데기만 만드는 구조(메소드 껍데기 만들기) 실제 구현은 implements받은 클래스 내 메소드에서 실 구현.



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
A a = new B()
A 메소드 기준으로 a가 생성된다.
뒤 B의 메소드 내 함수들은 무존재, 무기능으로 감쳐짐(=다형성)


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

예외
개발자는 '어떤 기능을 하는 코드'를 '의도'를 가지고 만들게 되는데, 모든 사람이 그 의도에 맞춰서 행동하는 것은 불가능하기 때문에 그 "예외" 케이스에 대해 처리하는 코드를 작성해주어야 한다.

public class ExceptionApp {
	public static void main(String[] args) throws ArithmeticException {
		System.out.println(1);
		System.out.println(2/0); // Run-Time Exception ArithmeticException
		System.out.println(3); 
	}
}


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
예외를 포괄적으로 처리하는것은 좋지 않다.


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
try문의 괄호 안에 들어가는 인스턴스 자원의 클래스가 "AutoCloseable"을 인터페이스로 가지고 있어야 한다.


public class MyException {

	public static void main(String[] args) {
		throw new RuntimeException("무언가 문제가 있습니다.");

	}

}

import java.io.FileWriter;
import java.io.IOException;

public class ThrowException {

	public static void main(String[] args) throws IOException {
		FileWriter f = new FileWriter("./data.txt");
		f.write("Hello");
		f.close();
	}

}