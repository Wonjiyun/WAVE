**hello world 출력**
 
 public class HelloworldApp {
	 public static void main(String[] args) {
		 System.out.println("Hello World!!");
	 }
 }

**데스크톱 어플리케이션 만들기기s**

import javax.swing.*;   
 import java.awt.Dimension;
 import java.awt.Toolkit;
 public class HelloworldApp{
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

 **데이터 타입**

 public class Datatype{
	public static void main(String[] args) {
		System.out.prinln(6);//Number
		System.out.println("six");//String
		
		System.out.println("6");//String6
		
		System.out.println(6+6);//12
		System.out.println("6+6")//66
		
		System.out.println(6*6);//36
		//System.out.println("6*6");//
		
		System.out.println("1111".length());//4
		System.out.println(1111.length());
	}
}

**연산산**

public class Number {

	public static void main(String[] args) {
		
		System.out.println(6 + 2); //8
		System.out.println(6 - 2); //4
		System.out.println(6*2); //12
		System.out.println(6/2); //3
	}

}

**문자열**

public class StringApp {

	public static void main(String[] args) {
		
		System.out.println("Hello world"); //String
		System.out.println('H'); //Character
		System.out.println("H");
		
		System.out.println("Hello"
				+ " World");
		//new line
		System.out.println("Hello\nWorld"); 
		//escape
		System.out.println("Hello \"World\""); //Hello"World"
		
	}

}

**문자열2**

public class StringOperation {

	public static void main(String[] args) {
		
		System.out.println("Hello World".length()); //11
		System.out.println("Hello,[[[name]]]...bye.".replace("[[[name]]]", "duru"));

	}

}

**변수의 정의**

public class Variable {

	public static void main(String[] args) {
		
	int	a = 1; //Number -> integer(정수)...-2, -1, 0, 1, 2...
	System.out.println(a);

	double b = 1.1; //real number -> double ... -2.0, -1.0, 0, 0.1, 0,2....
	System.out.println(b);
	
	String c = "Helllo World"; //문자열 c
	System.out.println(c);
	}

}

**변수의 효용**

public class Letter {

	public static void main(String[] args) {
		String name = "egoing";
		System.out.println("Hello, "+name+"  ... "+name+" ... egoing ... bye");
		
		double VAT = 10.0; 
		System.out.println(VAT);
	}

}

**Casting**

public class Casting {

	public static void main(String[] args) {
		
		double a = 1.1;
		double b = 1; // 손실이 없음 그대로 표기 
	    double b2 = (double) 1; 
	    
		System.out.println(b);
		
//		int c = 1.1; 
		double d = 1.1;
		int e = (int) 1.1; //double1.1 -> int 1.0 손실발생  
		System.out.println(e);
		
		// 1 to String
		String f = Integer.toString(1);
		System.out.println(f.getClass()); 
		
	}

}

**
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHome {
	
    public static void main(String[] args) {
		
		Strin id = "JAVA APT 507";
		
		// Elevator call
		Elevator  myElevator = new Elevator(id);
		myElevator.callForUp(1);
		
		// Security off
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		// Light on
		Lighting hallamp = new Lighting(id+" / Hall Lamp");
		halLamp.on();
		
		Lighting flooLamp = new lighting(id+" / floorLamp");
		floorLamp.on();
		
	}

}

**입력과출력**
import javax.swing.JOptionPane;

import org.opentutorials.iot.Elevatoor;
import org.opentutorials.iot.Security;

public class OkJavaGoInHomeinput {
	
	public static void main(String[] args) {

		// parameter, 매개변수
		String id =  JOptionPane.showInputDialog("Enter a ID"); 
		String bright = JOptionPane.showInputDialog("Enter a Bright level");
		
		//Elevator call
		Elevator myElevator = new Elevator("JAVA APT 507");
		myElevator.callForup(1);
		
		//Security off
		Security mySecurity = new Security("JAVA APT 507");
		mySecurity.off();
		
		//Light on
		Lighting hallLamp = new Lighting("JAVA APT 507 / Hall Lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting("JAVA APT 507 / floorLamp");
		floorLamp.on();
		
		DimmingLights moodLamp = new Dimminglights(id+"moodLAmp");
		moodLamp.setBright(Double.parseDouble(bright));

		moodLamp.on();
	}

}

클래스를 모두 포함 하고 있는것 -> 패키지
메소드 혹은 변수 포인터들을 포함 하고 있는것 -> 클래스

**class**

public class classApp {

	public static void main(String[] args) {
		
		System.out.println(Math.PI);
		System.out.println(Math.floor(1.6)); //내림
		System.out.println(Math.ceil(1.6)); //올림  
		//Math.  클래스 메소드와 변수들을 모두 포함  
	}

}

**인스턴스**
인스턴스를 만들어 내기 위해 클래스라는 큰 틀 안에 커스트럭쳐를 포함 해야함   

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

**기본기능**


public class Accounting {

	public static void main(String[] args) {
		
		System.out.println("Value of supply : "+10000.0);
		System.out.println("VAT : "+(10000.0*0.1) );
		System.out.println("Total : " + (10000.0 + 10000.0*0.1) );
		System.out.println("Expense : "+(10000.0*0.3));
		System.out.println("Income : "+ (10000.0-10000.0*0.3));
		System.out.println("Dividen : "+(10000.0 - 10000.0*0.3) * 0.5); 
		System.out.println("Dividen : "+(10000.0 - 10000.0*0.3) * 0.3); 
		System.out.println("Dividen : "+(10000.0 - 10000.0*0.3) * 0.2); 
	}

}

결과 >> Value of supply : 10000.0
       VAT : 1000.0
       Total : 11000.0
       Expense : 3000.0
       Income : 7000.0
       Dividen : 3500.0
       Dividen : 2100.0
       Dividen : 1400.0

**변수도입**

refactor > Extract Local Variable
         > vatRate  부가가치세 윤리


public class Accounting {

	public static void main(String[] args) {
		
		double valueOfSupply = 12345.0;
		double vatRate = 0.1;
		double expenseRate =0.3;
		double vat = valueOfSupply*vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply*expenseRate;
		double income = valueOfSupply-expense;
		
		System.out.println("Value of supply : "+valueOfSupply);
		System.out.println("VAT : "+vat );
		System.out.println("Total : " + total );
		System.out.println("Expense : "+expense);
		System.out.println("Income : "+ income);
		System.out.println("Dividen : "+(valueOfSupply - valueOfSupply*0.3)*0.5 ); 
		System.out.println("Dividen : "+(valueOfSupply - valueOfSupply*0.3) * 0.3 ); 
		System.out.println("Dividen : "+(valueOfSupply - valueOfSupply*0.3) * 0.2) ; 
	}

}

**boolean datatype**

public class BooleanApp {

	public static void main(String[] args) {
		
		System.out.println("One");
		System.out.println(1);
		
		System.out.println(true);
		System.out.println(false);
		
		String foo = "Hello world";
		//String true = "Hello world"; resrved world
		
		System.out.println(foo.contains("world"));
		System.out.println(foo.contains("egoing"));

	}

}

>One
1
true
false
true
false

**비교연산자**


public class ComparisonOperatorApp {

	public static void main(String[] args) {
		
		System.out.println(1>1); //false
		System.out.println(1==1); //true
		System.out.println(1<1);
		System.out.println(1>=1);

	}

}

>false
true
false
true

**조건문**


public class IfApp {

	public static void main(String[] args) {
		
		System.out.println("a");
//		if(false ) {
//			System.out.println(1);
//		} else {
//			if(true) {
//				System.out.println(2);
//			} else {
//				System.out.println(3);
//			}
//		}
		if(false ) {
			System.out.println(1);
		} else if(true) {
			System.out.println(2);
		}else {
			System.out.println(3);
		}
		
		System.out.println("b");

	}

}

**조건문응용1**


public class AuthApp {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args [0];
		
		System.out.println("Hi.");
		
//		if(inputId == id) {
		if(inputId.equals(id)) {
			System.out.println("Master!");
		} else {
			System.out.println("Who are you?");
		}

	}

}
 
duru  변경 > Hi.
Who are you?

**조건문응용2**

public class AuthApp {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args [0];
		
		String pass = "1111";
		String inputPass = args[1];
		
		System.out.println("Hi.");
		
//		if(inputId == id) {
//		if(inputId.equals(id)) {
//			if(inputPass.equals(pass)) {
//				System.out.println("Master!");
//			} else {
//				System.out.println("Wrong password!");
//			}
//		} else {
//			System.out.println("Who are you?");
//		}
		
		if(inputId.equals(id) && inputPass.equals(pass)) {
				System.out.println("Master!");
			} else {
			System.out.println("Who are you?");
		}

	}

}

**논리연산자**


public class AuthApp {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args [0];
		
		String pass = "1111";
		String pass2 = "2222";
		String inputPass = args[1];
		
		System.out.println("Hi.");
		
//		if(inputId == id) {
//		if(inputId.equals(id)) {
//			if(inputPass.equals(pass)) {
//				System.out.println("Master!");
//			} else {
//				System.out.println("Wrong password!");
//			}
//		} else {
//			System.out.println("Who are you?");
//		}
		
		if(inputId.equals(id) && (inputPass.equals(pass) || inputPass.equals(pass2)) )) {
				System.out.println("Master!");
			} else {
			System.out.println("Who are you?");
		}

	}

}

**반복문**


public class LoopApp {

	public static void main(String[] args) {
		System.out.println(1);
		System.out.println("== while ==");
		
		int i = 0; // i >> 반문에서 카운팅하는 용
		//..
		while(i < 3) {
		   System.out.println(2);
		   System.out.println(3);
//		   i = i + 1;
		   //..
		   i++;
		}
		
		for(int j=0; j < 3; j++) {
			System.out.println(2);
		    System.out.println(3);
		}
		
		System.out.println(4);

	}

}

**배열**


public class ArrayApp {

	public static void main(String[] args) {
		
		//egoing, jinhuck, youbin
		//String users = "egoing, jinhuck, youbin";
		String[] users = new String[3]; 
		users[0] = "egoing";
		users[1] = "jinhyuck";
		users[2] = "youbin";
		
		System.out.println(users[1]);
		System.out.println(users.length);
		
		int[] scores = {10, 100, 100};
		System.out.println(scores[1]);
		System.out.println(scores.length);
		}

}

jinhyuck
3
100
3

**반복문 + 배열**

public class LoopArray {
 
    public static void main(String[] args) {
        /*
         *  <li>egoing</li>
         *  <li>jinhuck</li>
         *  <li>youbin</li>
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
> egoing,
jinhuck,
youbin,

**종합**


public class AuthApp3 {

	public static void main(String[] args) {
		
		String[] users = {"egoing", "jinhyuck", "youbin"};
		String inputId = args[0];
		
		boolean isLogined = false;
		for(int i=0; i<users.length; i++) {
			String currentId = users[1];
			if(currentId.equals(inputId)) {
		
				break;
		}
		}
		System.out.println("Hi,");
	if(isLogined) {
		System.out.println("Master!!");
	}else {
		System.out.println("Who are you?");
	}
	}

}

**2**


public class AuthApp3 {

	public static void main(String[] args) {
		
	//	String[] users = {"egoing", "jinhyuck", "youbin"};
		String [][] users = {
				{"egoing", "1111"},
				{"jinhyuck", "2222"},
				{"youbin", "3333"}
				
		};
		String inputId = args[0];
		String inputPass = args[1];
		
		boolean isLogined = false;
		for(int i=0; i<users.length; i++) {
			String[] current = users[1];
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
	}else {
		System.out.println("Who are you?");
	}
	}

}

//메소드

**Methood**

public class FirstMethood {

	public static void main(String[] args) {
		
		System.out.println("Hello Methood");
		System.out.println(Math.floor(1.1));
	}

}

**2**

public class WhyMethood {
	public static void printTwoTimesA() {
		System.out.println("-");
		System.out.println("a");
		System.out.println("a");
	}

	public static void main(String[] args) {
		
	    //100000000
		printTwoTimesA();
		//100000000
		printTwoTimesA();
		//100000000
		printTwoTimesA();
 
		

	}

**메소드입력**

public class WhyMethod {
     
    public static void main(String[] args) {
         
                         //인자, argument
            printTwoTimes("a", "-");
            // 100000000
            printTwoTimes("a", "*");
            // 100000000
            printTwoTimes("a", "&");
            printTwoTimes("b", "!");
 
    }
                          //매개변수,parameter 
    public static void printTwoTimes(String text, String delimiter) {
        System.out.println(delimiter);
        System.out.println(text);
        System.out.println(text);
    }
