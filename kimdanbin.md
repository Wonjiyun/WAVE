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
