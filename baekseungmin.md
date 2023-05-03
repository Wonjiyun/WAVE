2023/05/01 java study

public class HelloWorldApp {
	public static void main(String[] args) {
		System.out.println("Hello World!!");
	}
}
//eclipes 코딩중 에러가 뜨는경우 소스코드 안 파일인지 먼저 확인하기.
//자바를 통해 할 수 있는 가능성을 알아봄.
// 코드를 보면서 해석해보며 어떤 단어가 어떤 의미를 가지는지 알아야됌


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
			pin.high(); //코딩 실행시 GPIO라는 핀에 특정한 전기가 흐르면서 전구가 켜짐.
			Thread.sleep(SHORT_INTERVAL);//0.2초만큼 불이 켜짐.(위 INTERVAL200 참고)
			pin.low(); // 여기서 부터 반복되며 모스부호를 나타냄
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

			//아래 코드 짜름
		}
	}
}

