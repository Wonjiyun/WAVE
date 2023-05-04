
0501 - 자바 1 : 챕터 1,2,3,4,5 강의내용

설치, 자바관련 이야기


기본 프린트문

public class @@@
    pulic static void main(String[] args){

    System.out.println("@@@@")

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

	   System.out.printl(6); number
	   System.out.printl("six"); string
	   System.out.printl("6"); string 6
	   System.out.printl(6+6); 12
	   System.out.printl("6"+"6"); 66
	   System.out.printl(6*6); 36
	   System.out.printl("1111".length()); 4

다른 연산

	   System.out.printl(Math.PI);//파이 3.14159~
	   System.out.printl(Math.floor(Math.PI));//올림 4
	   System.out.printl(Math.ceil(Math.PI));//내림 5


'Character', "String"

줄바꿈은 \n 로 인식됨
쌍따옴표를 문장안에 사용하려면 /"@@@/" 형태로 사용


	   System.out.printl("Hello World"/length); //11
	   
	   System.out.printl("Hello [[[name]]]".replace("[[[name]]]","@@@"));

replace는 앞 문자열에서 원하는 부분을 바꿀수있음 .replace("앞 문자열의 바꿀부분","대신 넣을 부분") 