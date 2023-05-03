0501
**helloworld출력**

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

