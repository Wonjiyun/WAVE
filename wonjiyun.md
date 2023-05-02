<h1>5월 1일 boostcorse 쉽게 배우는 자바1<h1>
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
