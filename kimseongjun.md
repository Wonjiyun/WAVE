//변수의 정의, 정 int에서는 정수가 
public class variable {

    public static void main(String[] args) {

      int a=1; // number -> integer ... -2, -1, 0, 1, 2 ... 정수 데이터 integer를 이용해서 정수 표현
      System.out.println(a);
      double b=1.1; // real number -> double = (실수값이 올수있다) ... -2.0, -1.0, 0, 1.0, 2.0 ...
      System.out.println(b);
      String c = "Hello World"; // 문자열 데이터 string 선언
      System.out.println(c);                          
    }
}
// 변수의 효용 //
public class letter{

    public static void main(String[] args){
        String name = "leezche"; // name이라는 변수를 지정해주면, 자주 사용하는 데이터를 여러번 재사용 가능(변수의 재사용)
        System.out.println("Hello, "+name+"..."+name+" ... egoing ... bye");

        double VAT = 10.0; // VAT(부가가치세)라는 이름을 붙이게 되면, 단순히 실수 10이 아닌 '부가가치세'라는 의미, 코드의 의미를 쉽게 파악
        System.out.println(VAT); // 코드의 가독성
    }
}
//데이터 타입의 변환
public class Casting {

    public static void main(String[] args) {
//정수와 실수 간에 변환하기
        double a = 1.1; //명시적으로 데이터 타입 변환을 나타내야됨
        double b = 1;
        double b2 = (double) 1;
        System.out.println(b);

//      int c = 1.1;
        double d = 1.1; //실수 1.1에서 정수로 변환할려면 데이터 타입을 명시적으로 변경해 주어야 함.
        int e = (int) 1.1;
        System.out.println(e);

        //1 to string
        String f = Integer.toString(1); //정수를 문자열로 변환 , integer 객체의 toString를 이용하면 숫자를 문자열로 변환 가능 
        System.out.println(f.getClass());
    }
}
//프로그래밍이란 무엇인가 ?
//프로그램 = 순서를 나타내는 것 , 컴퓨터 프로그래밍으로 사람이 잘 못하는 일을 기계에서 위임하여 자동화할 수 있다.
public class Program{

    public static void main(sting[] args){

        System.out.println(1);
        System.out.println(2);
        System.out.println(3);
    }
}
//프로그램 만들기 - IoT 라이브러리 만들기 , IoT 프로그램 만들기
//import 구문을 이용해서 org.opentutorials.Elevator를 입력해야 되는 구문을 Elevator로 단순하게 할 수 있다!
import  org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OKjavaGoInHome {

    public static void main(String[]args){
        String id = "JAVA APT 507"; // 반복적으로 사용되는 값의 경우는 변수로 지정하여 재사용함(코드의 가독성 높임)

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
//디버거
//본인의 코드를 분석하고 싶을 때 이용하는 것 : 디버거
//브레이크 포인트

//입력과 출력 1,2 - arguments & parameter
import javax.swing.JOptionPane; // JOptionpane 객체의 showInputDialog 메소드를 이용하면 id 값을 입력 가능하다.

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
public class OKjavaGoInHomeInput {

    public static void main(String[]args){
        String id = JOptionPane.showInputDialog("Enter a ID");
        string bright = JOptionPane.showInputDialog("Enter a Bright level"); //밝기 값 입력
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
        moodLamp.setbright(Double.parseDouble(bright)); //setbright 메소트의 밝기는 double 데이터로 타입 변환을 해야됨.
        moodLamp.on();

        DimmingLights moodLamp = new DimmingLights(id+" moodLamp");
        moodLamp.setBright(10);
        moodLamp.on(); // 밝기 10으로 조절한 것
    }
}

input -> program -> output == 입력정보를 받아서 출력을 하는 것!

import javax.swing.JOptionPane; // JOptionpane 객체의 showInputDialog 메소드를 이용하면 id 값을 입력 가능하다.

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
public class OKjavaGoInHomeInput {
//parameter, 매개변수
    public static void main(String[]args){
        String id = args[0];
        String bright = args[1];
        // args parameter는 argument의 값을 받아서 동작, 인덱스를 통해 배열의 데이터를 꺼내 쓸수 있고, 인덱스는 0번부터 시작 ! //
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
        moodLamp.setbright(Double.parseDouble(bright)); 
        moodLamp.on();

        DimmingLights moodLamp = new DimmingLights(id+" moodLamp");
        moodLamp.setBright(10);
        moodLamp.on(); 
    }
}
//argument를 입력받아 프로그램 실행시키기
main 메소드의 args 파라미터를 이용하여 입력값을 받는 방법이 있다.

// 직접 컴파일 - 실행
'이클립스는 자바로 프로그램을 만들기 위해 유용한 도구'
이클립스 없이 자바로 프로그래밍을 하려면 우선 자바 파일을 스스로 컴파일할 수 있어야 한다.
그리고 컴파일한 클래스 파일을 실행하는 과정을 거쳐야 한다.
Compile , Run , Input

// 직접 컴파일 - 실행 - 실행환경 살펴보기
// 터미널 열기 //
window : 윈도우 키 + R로 실행 창을 키고, cmd를 입력하여 명령 프롬프트를 실행한다.
MacOS: 스포트라이트에서 terminal을 입력해서 터미널을 실행한다.

// javac 확인 //
터미널에 javac를 입력하고 실행하면 javac 명령어의 사용 방법이 출력된다.
//Windows 자바 확인
자바의 설치 경로(ex: C:\Program files\java\jdk-14.0.1)\bin\javac.exe
// 환경 변수 경로 //
내 pc 오른쪽 클릭 -> 속성 클릭 => 고급 시스템 설정 클릭 -> 환경 변수 클릭 -> path 더블클릭해서 수정 가능

// 직접 컴파일 - 실행 - 컴파일과 실행하기
cd 명령어를 통해 프로젝트 디렉토리로 이동한다.
// 자바 파일 컴파일하기 // 
터미널에 javac를 입력하면 javac 명령어의 사용 방법을 보여준다.
javac Program.java
입력하면 Program.class가 생성된 것을 확인할 수 있다.
javac -cp "." Program.java
(에러가 난다면 위의 코드로 해보기)
// 실행하기 //
java 명령어 이용해서 입력
java Program
(에러가 난다면 아래의 코드로 해보기)
java -cp "." Program

이렇게 해서 파일을 컴파일해서 실행까지 해보는 시간이였다.

//직접 컴파일 - 실행 - 라이브러리이용
//라이브러리를 이용하는 프로그램을 컴파일하기

// OKjavaGoInHome.java 파일 컴파일
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHome {
 
    public static void main(String[] args) {
         
        ....
    }
 
}
//외부 라이브러리도 포함해서 컴파일하기 위해서는 javac 명령어의 옵션 중 --class-path(-cp) 옵션을 이용해서 외부 라이브러리도 함께 지정해야 한다.//
javac -cp ".;lib" OkJavaGoInHome.java 로 입력
macOS나 Linux의 경우에는 ".;lib" 부분의 세미콜론(;)을 콜론(:)으로 바꿔서 입력한다.
콜론(:)이나 세미콜론(;)은 구분자의 의미를 가진다.
//외부 라이브러리의 클래스들도 함께 사용하는 프로그램을 실행하기 위해서는
컴파일했을 때와 마찬가지로 --class-path 옵션에 외부 라이브러리도 포함해서 실행해야 한다.//
//윈도우
java -cp ".;lib" OkJavaGoInHome 로 입력

// 직접 컴파일-실행 - 입력과 출력
// OKjavaGoInHomeInput.java 파일 컴파일
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
 
    public static void main(String[] args) {
         
        String id = args[0];
        String bright = args[1];
        
        ....
 
    }
 
}
실행할 때 argument 입력
org.opentutorials.iot 패키지는 다시 lib 폴더 밖으로 꺼낸다.
터미널에서 argument 주기
- 실행할 클래스 파일 이름 다음에 연달아서 입력 -
java OkJavaGoInHomeInput "JAVA APT 507" 15.0

자바 문서 보는 법 - API VS UI//
------------------------------------------
API: 사용자가 직접 사용하는 것
UI: 사용자가 자바 프로그램을 이용할 수 있도록 만들어 놓은 것

자바 문서 보는 법 - 패키지, 클래스, 변수, 메소드//
---------------------------------------------------------------
클래스 : 서로 연관된 변수와 메소드로 모아서 이름을 붙히는 것 
패키지 : 연관된 클래스를 묶어서 정리한 것 
자바 문서 보는 법 - 클래스
------------------------------------------
클래스 ? 서로 연관된 변수와 메소드로 모아서 이름을 붙히는 것
public class OKjavaGoInHome {

    public static void main(String[]args){ // Math 클래스 : 수학과 관련된 여러 변수들과 메소드들이 있다.

        System.out.println(Math.PI); // PI: 원주율이 적절한 정밀도로 저장되어 있는 변수
        System.out.println(Math.floor(1.6)); // floor 메소드: 특정 소수점 이하에 대하여 버림한 값 산출
        System.out.println(Math.ceil(1.6)); // ceil 메소드: 특정 소수점 이하에 대하여 올림한 값 산출
    }

}

//자바 문서 보는 법 - 인스턴스
------------------------------------
인스턴스 ? 클래스를 컴퓨터 상에서 실체화한 것
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.PrintWriter;
public class InstanceApp {
 
    public static void main(String[] args) throws IOException{
         
        PrintWriter p1 = new PrintWriter("result1.txt");
        p1.write("Hello 1");
        p1.close();
         
        PrintWriter p2 = new PrintWriter("result2.txt");
        p2.write("Hello 2");
        p2.close();

    }

}
자바 문서 보는 법
--------------------

나의 앱 만들기
=====================
오리엔테이션
---------------------
'우리의 문제 현상은 무엇인가?'
계산기로 하면 너무 손이 많이 감 !
프로그램으로 하면 대기업을 위한 프로그램이라서 너무 복잡함 !
-> 자바로 해결해보자 !
'우선적으로 해야될 일은 현실을 분석하는 것'


//나의 앱 만들기_기본 기능 구현
-------------------------------
public class AccountingApp{

    public static void main(String{ args}){

        System.out.println("Value of supply:" + 10000.0);
        System.out.println("VAT:"(10000.0*0.1));
        System.out.println("Total:"+(10000.0 + 10000.0*0.1));
        System.out.println("Expense:"+(10000.0*0.3));
        System.out.println("Income:"+(10000.0 - 10000.0*0.3));
        System.out.println("Dividend 1:"+(10000.0 - 10000.0*0.3)*0.5);
        System.out.println("Dividend 2:"+(10000.0 - 10000.0*0.3)*0.3);
        System.out.println("Dividend 3:"+(10000.0 - 10000.0*0.3)*0.2);
    }
}
//나의 앱 만들기-
---------------------
public class AccountingApp{

    public static void main(String{ args}){

        double valueOfSupply = 12345.0;
        double vatRate = 0.1;
        double expenseRate = 0.3;
        double vat = valueOfSupply * vatRate;
        double total = valueOfSupply + vat;
        double expense = valueOfSupply * expenseRate;
        double income = valueOfSupply - expense;
        double dividend1 = income * 0.5;
        double dividend2 = income * 0.3;
        double dividend3 = income * 0.2;


        System.out.println("Value of supply:" + valueOfSupply);
        System.out.println("VAT:"+ vat);
        System.out.println("Total:"+ total);
        System.out.println("Expense:"+ expense);
        System.out.println("Income:"+ income);
        System.out.println("Dividend 1:"+ dividend1);
        System.out.println("Dividend 2:"+ dividend2);
        System.out.println("Dividend 3:"+ dividend3);
    }
}

//나의 앱 만들기
----------------
import javax.management.ValueExp;

public class AccountingApp{

    public static void main(String[]args){

        double valueOfSupply = Double.parseDouble(args[0]);
        double vatRate = 0.1;
        double expenseRate = 0.3;
        double vat = valueOfSupply * vatRate;
        double total = valueOfSupply + vat;
        double expense = valueOfSupply * expenseRate;
        double income = valueOfSupply - expense;
        double dividend1 = income * 0.5;
        double dividend2 = income * 0.3;
        double dividend3 = income * 0.2;


        System.out.println("Value of supply:" + valueOfSupply);
        System.out.println("VAT:"+ vat);
        System.out.println("Total:"+ total);
        System.out.println("Expense:"+ expense);
        System.out.println("Income:"+ income);
        System.out.println("Dividend 1:"+ dividend1);
        System.out.println("Dividend 2:"+ dividend2);
        System.out.println("Dividend 3:"+ dividend3);
    }
}

나의 앱 만들기_조건문
------------------------
> 조건문 : 비슷한 프로그램 두가지를 하나로 합칠 때 유용하게 쓰인다.
public class AccountingIFApp {
 
    public static void main(String[] args) {
 
        double valueOfSupply = Double.parseDouble(args[0]);
        double vatRate = 0.1;
        double expenseRate = 0.3;
        double vat = valueOfSupply * vatRate;
        double total = valueOfSupply + vat;
        double expense = valueOfSupply * expenseRate;
        double income = valueOfSupply - expense;
         
        double dividend1;
        double dividend2;
        double dividend3;
         
        if(income > 10000.0) {
            dividend1 = income * 0.5;
            dividend2 = income * 0.3;
            dividend3 = income * 0.2;
        } else {
            dividend1 = income * 1.0;
            dividend2 = income * 0;
            dividend3 = income * 0;
        }
 
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + vat);
        System.out.println("Total : " + total);
        System.out.println("Expense : " + expense);
        System.out.println("Income : " + income);
        System.out.println("Dividend 1 : " + dividend1);
        System.out.println("Dividend 2 : " + dividend2);
        System.out.println("Dividend 3 : " + dividend3);
 
    }
 
}
나의 앱 만들기 - 배열 
----------------------
> 배열 : 비슷한 종류의 정보를 정리하기 위한 것


public class AccountingArrayApp {

  public static void main(String[] args) {

    double valueOfSupply = Double.parseDouble(args[0]);
    double vatRate = 0.1;
    double expenseRate = 0.3;
    double vat = valueOfSupply * vatRate;
    double total = valueOfSupply + vat;
    double expense = valueOfSupply * expenseRate;
    double income = valueOfSupply - expense;

    double[] dividendRates = new double[3];
    dividendRates[0] = 0.5;
    dividendRates[1] = 0.3;
    dividendRates[2] = 0.2;
> 배열은 데이터 타입 옆에 대괄호[]를 붙여서 표현, 인스턴스를 만들 때는 배열의 길이를 지정하여 생성
    double dividend1 = income * dividendRates[0]; 
    double dividend2 = income * dividendRates[1];
    double dividend3 = income * dividendRates[2];

    System.out.println("Value of supply : " + valueOfSupply);
    System.out.println("VAT : " + vat);
    System.out.println("Total : " + total);
    System.out.println("Expense : " + expense);
    System.out.println("Income : " + income);
    System.out.println("Dividend 1 : " + dividend1);
    System.out.println("Dividend 2 : " + dividend2);
    System.out.println("Dividend 3 : " + dividend3);

  }

}
나의 앱 만들기 - 반복문
-----------------------
> while 문 : 괄호 안의 조건이 참인 한 블록 내의 작업을 게속 반복
> 
public class AccountingArrayApp {

  public static void main(String[] args) {

    double valueOfSupply = Double.parseDouble(args[0]);
    double vatRate = 0.1;
    double expenseRate = 0.3;
    double vat = valueOfSupply * vatRate;
    double total = valueOfSupply + vat;
    double expense = valueOfSupply * expenseRate;
    double income = valueOfSupply - expense;

    double[] dividendRates = new double[3];
    dividendRates[0] = 0.5;
    dividendRates[1] = 0.3;
    dividendRates[2] = 0.2;

    double dividend1 = income * dividendRates[0];
    double dividend2 = income * dividendRates[1];
    double dividend3 = income * dividendRates[2];

    System.out.println("Value of supply : " + valueOfSupply);
    System.out.println("VAT : " + vat);
    System.out.println("Total : " + total);
    System.out.println("Expense : " + expense);
    System.out.println("Income : " + income);

    double[] dividendRates = new double[3];
    dividendRates[0] = 0.5;
    dividendRates[1] = 0.3;
    dividendRates[2] = 0.2;

    int i = 0;
    while (i < dividendRates.length) {
      System.out.println("Diviidend:" + (income * dividendRates[i]));
      i = i + 1;
    }

  }

}
> while 문을 이용하여 반복적으로 동작하던 작업을 간결하게 바꿀 수 있다 !!
        ....

        double dividend1 = income * dividendRates[0];
        double dividend2 = income * dividendRates[1];
        double dividend3 = income * dividendRates[2];

        System.out.println("Dividend 1 : " + dividend1);
        System.out.println("Dividend 2 : " + dividend2);
        System.out.println("Dividend 3 : " + dividend3);

        ....

        double[] dividendRates = new double[3];
        dividendRates[0] = 0.5;
        dividendRates[1] = 0.3;
        dividendRates[2] = 0.2;
        
        int i = 0;
        while (i < dividendRates.length) {
            System.out.println("Dividend : " + income * dividendRates[i]);
            i = i + 1;
        }
나의 앱 만들기 - 메소드
------------------------
> 메소드 : 클래스의 동작을 나타내는 함수
> Math의 floor, ceil
> PrintWriter의 write, close 등의 메소드

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
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + getVAT());
        System.out.println("Total : " + getTotal());
        System.out.println("Expense : " + getExpense());
        System.out.println("Income : " + getIncome());
        System.out.println("Dividend 1 : " + getDiviend1());
        System.out.println("Dividend 2 : " + getDiviend2());
        System.out.println("Dividend 3 : " + getDiviend3());
    }
 
    public static double getDiviend1() {
        return getIncome() * 0.5;
    }
    public static double getDiviend2() {
        return getIncome() * 0.3;
    }
    public static double getDiviend3() {
        return getIncome() * 0.2;
    }
 
    public static double getIncome() {
        return valueOfSupply - getExpense();
    }
 
    public static double getExpense() {
        return valueOfSupply * expenseRate;
    }
 
    public static double getTotal() {
        return valueOfSupply + getVAT();
    } 
 
    public static double getVAT() {
        return valueOfSupply * vatRate;
    }
 
}
# result
> Value of supply : 10000.0
VAT : 1000.0
Total : 11000.0
Expense : 3000.0
Income : 7000.0
Dividend 1 : 3500.0
Dividend 2 : 2100.0
Dividend 3 : 1400.0

나의 앱 만들기 - 클래스 
-----------------------
+<<<<<<< HEAD
-----------------------
> 클래스 : 객체지향의 핵심, 서로 연관된 변수와 메소드를 그룹핑해 소속관계를 명확히 해서 이름을 붙여 놓은 것
class Accounting{
    public static double valueOfSupply;
    public static double vatRate;
    public static double expenseRate;
    public static void print() {
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + getVAT());
        System.out.println("Total : " + getTotal());
        System.out.println("Expense : " + getExpense());
        System.out.println("Income : " + getIncome());
        System.out.println("Dividend 1 : " + getDiviend1());
        System.out.println("Dividend 2 : " + getDiviend2());
        System.out.println("Dividend 3 : " + getDiviend3());
    }
 
    public static double getDiviend1() {
        return getIncome() * 0.5;
    }
    public static double getDiviend2() {
        return getIncome() * 0.3;
    }
    public static double getDiviend3() {
        return getIncome() * 0.2;
    }
 
    public static double getIncome() {
        return valueOfSupply - getExpense();
    }
 
    public static double getExpense() {
        return valueOfSupply * expenseRate;
    }
 
    public static double getTotal() {
        return valueOfSupply + getVAT();
    } 
 
    public static double getVAT() {
        return valueOfSupply * vatRate;
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
        // 이전 메소드에서 표현한 것에서 이사시킴, Accounting.를 써서 명확하게 표현함(소속감을 가짐)
    }
 
     
 
}
나의 앱 만들기 - 인스턴스
--------------------------
> 인스턴스 : 클래스를 실제로 실행시킨 실체화된 클래스
class Accounting{
    public double valueOfSupply; //accouunting을 복제했을때, static은 사용되면 안된다.
    public double vatRate;
    public double expenseRate;
    public void print() {
        System.out.println("Value of supply : " + valueOfSupply);
        System.out.println("VAT : " + getVAT());
        System.out.println("Total : " + getTotal());
        System.out.println("Expense : " + getExpense());
        System.out.println("Income : " + getIncome());
        System.out.println("Dividend 1 : " + getDiviend1());
        System.out.println("Dividend 2 : " + getDiviend2());
        System.out.println("Dividend 3 : " + getDiviend3());
    }
 
    public double getDiviend1() {
        return getIncome() * 0.5;
    }
    public double getDiviend2() {
        return getIncome() * 0.3;
    }
    public double getDiviend3() {
        return getIncome() * 0.2;
    }
 
    public double getIncome() {
        return valueOfSupply - getExpense();
    }
 
    public double getExpense() {
        return valueOfSupply * expenseRate;
    }
 
    public double getTotal() {
        return valueOfSupply + getVAT();
    } 
 
    public double getVAT() {
        return valueOfSupply * vatRate;
    }
}
public class AccountingClassApp {
     
    public static void main(String[] args) {
        // instance 
        // 1. 상품
        Accounting a1 = new Accounting(); -> Acounting a1을 복제
        a1.valueOfSupply = 10000.0;
        a1.vatRate = 0.1;
        a1.expenseRate = 0.3;
        a1.print();
        // 2. 상품 
        Accounting a2 = new Accounting(); -> Accounting a2을 복제
        a2.valueOfSupply = 20000.0;
        a2.vatRate = 0.05;
        a2.expenseRate = 0.2;
        a2.print();
         
        a1.print();
    }
}
==============================
## 쉽게 배우는 자바 2
==============================

1. JAVA 제어문
====================

Boolean Datatype
--------------------------
> Boolean : 참과 거짓을 표현하는 데이터 타입
> true와 false 키워드를 이용하여 직접 입력, 메소드의 리턴 값이나 비교 연산으로 도출할 수 있음
public class BooleanApp {

    public static void main(String[] args) {

        System.out.println("one");
        System.out.println(1);

        System.out.println(true);
        System.out.println(false);

        String foo = "Hello world";
        // String true = "Hello world"; reserved word
        // contains 메소드와 같이 결과값이 boolean 데이터 타입인 경우 또는 비교 연산자를 이용하여 계산하는 경우에도 boolean 데이터 타입을 다루게 됨
        System.out.println(foo.contains("world"));  
        System.out.println(foo.contains("egoing"));

    }
}

비교 연산자
----------------------
> 비교 연산자 = 값의 대소, 같음을 비교하는 연산자 (부등호, 등호)
public class ComparisonOperatorApp {
 
    public static void main(String[] args) {
         
        System.out.println(1 > 1); // false
        System.out.println(1 == 1); // true
        System.out.println(1 < 1);
        System.out.println(1 >= 1);
         
    }
 
}

조건문 형식
--------------------
> 조건문은 중첩할 수 있고, if와 else는 하나의 조건문에 한 번만 들어갈 수 있지만, eise if는 여러 개가 들어갈 수 있다.
# if
## 조건식
### 코드블럭 (실행할 코드)
#### else if
##### else
public class IfApp {
 
    public static void main(String[] args) {
 
        System.out.println("a");
        if(false) {
            System.out.println(1);
        } else if(true) {
            System.out.println(2);
        } else {
            System.out.println(3);
        }
        System.out.println("b");
 
    }
 
}
조건문 응용 1,2
------------------------
public class AuthApp {
 
    public static void main(String[] args) {
         
        String id = "egoing";
        String inputId = args[0];
         
        System.out.println("Hi.");
        //==와 같은 비교 연산자는 기본 데이터 형과는 달리 문자열과 같은 객체에는 의도치 않은 결과를 가져옴
        //if(inputId == id) {
        if(inputId.equals(id)) {
            System.out.println("Master!");
        } else {
            System.out.println("Who are you?");
        }
 
    }
 
}
}
> boolean 데이터를 연산하기 위한 조건 연산자 사용
> 조건 연산자에는 &&(AND)와 ||(OR, shift + \)가 있다.
public class AuthApp {
 
    public static void main(String[] args) {
         
        String id = "egoing";
        String inputId = args[0];
         
        String pass = "1111";
        String inputPass = args[1];
         
        System.out.println("Hi.");
         
        if(inputId.equals(id) && inputPass.equals(pass)) {
            System.out.println("Master!");
        } else {
            System.out.println("Who are you?");
        }       
 
    }
 
}
>> && 연산자는 전항과 후항이 모두 참일 경우에만 참을 반환하고, 아니면 거짓을 반환한다.
>> || 연산자는 전항과 후항 중 하나라도 참일 경우에 참을 반환, 모두 거짓일 때에만 거짓을 반환한다.
>> && 연산자는 || 연산자보다 우선순위가 높다 !!

 == vs equals
------------------
# 자바에서는 기본적으로 다루는 데이터 타입이 존재, 이러한 데이터 타입을 <원시 데이터 타입> 이라고 부름
## boolean, byte, char, short, int, long, float, double 8개가 있다.

+>원시 데이터 타입의 변수는 선언되면 메모리(stack)에 공간에 할당, 그 메모리 공간 안에 실제 값이 들어감
int a = 1;
int b = 1;

String s1 = new String("JAVA");
String s2 = new String("JAVA");
> new 키워드를 통한 인스턴스를 만든 시점에 또 다른 메모리 구역(Heap)에서 새로운 공간을 할당
String s3 = "JAVA";
String s4 = "JAVA";
> 문자열 리터럴로 문자열로 생성할 때, 이미 같은 문자열을 생성한 적이 있다면, 새로 메모리 공간을 할당하지 않고 새로운 변수는 기존의 문자열이 저장된 메모리(String pool(Heap))의 주소를 가리키게 된다.

# == 연산자는 변수가 일차적으로 가리키고 있는 메모리 공간의 값을 기준으로 판단
> 반면 equals 메소드는 구현에 따라 다르지만, 변수가 최종적으로 가리키고 있는 값을 기준으로 판단

논리연산자
-----------------
> ! 연산자 : NOT 연산을 수행하고 참, 거짓 값을 반전시킨다.

public class AuthApp2 {
 
    public static void main(String[] args) {
         
        String id = "egoing";
        String inputId = args[0];
         
        String pass = "1111";
        String pass2 = "2222";
        String inputPass = args[1];
        // 둘 중 하나만 충족, || 연산자를 이용하고, 이 조건을 boolean 변수 IsRightPass에 할당하여 간결성있게 표현
        System.out.println("Hi.");
        boolean isRightPass = (inputPass.equals(pass) || inputPass.equals(pass2));
        if(inputId.equals(id) && isRightPass ) {
            System.out.println("Master!");
        } else {
            System.out.println("Who are you?");
        }       
 
    }
 
}

반복문, 배열 
-----------------
> 반복문 : 조건에 따라 특정한 작업을 반복하게 하는 제어문
> 자바에서는 while문, for문 등으로 반복문을 구현
public class LoopApp {
 
    public static void main(String[] args) {
         
        System.out.println(1);
        System.out.println("=== while ===");
        int i = 0;
        //..
        while(i < 3) {
            System.out.println(2);
            System.out.println(3);
//          i = i + 1;
            //..
            i++;
        }
        System.out.println("=== for ===");
        for(int j=0; j < 3; j++) {
            System.out.println(2);
            System.out.println(3);
        }
         
        System.out.println(4);
 
    }
 
}
>> while문 : 조건식이 참일 동안에 코드블럭의 작업을 반복, 조건식에 true을 입력할 경우 조건이 항상 참이기 때문에 무한으로 반복하게 된다
>> For문은 조건식이 3개의 부분을 나누어짐
# 변수의 초기화
## 조건식
### 1회 반복을 끝내고 수행할 연산 
각각의 부분은 세미콜론(;)으로 구분이 되어있음
변수의 초기화는 for문이 시작될 때 한 번만 수행되고, 조건식이 참일 경우에만 반복
1회 반복이 끝나면(}부분) 지정한 연산을 처리하고 다시 조건식을 확인하여 반복작업을 실행

>>변수의 초기화 부분에서 변수를 새로 선언했다면, 그 변수는 for문 안에서만 존재하고, for문을 벗어나면 사라진다 

>>> 배열

public class ArrayApp {
 
    public static void main(String[] args) {
         
        // egoing, jinhuck, youbin 
//      String users = "egoing, jinhuck, youbin";
        String[] users = new String[3];
        users[0] = "egoing";
        users[1] = "jinhuck";
        users[2] = "youbin";
         
        System.out.println(users[1]);
        System.out.println(users.length);
         
        int[] scores = {10, 100, 100}; // 원소, element
        System.out.println(scores[1]);
        System.out.println(scores.length);
 
    }
 
}
 
종합 응용 
---------------------------
>> 이전에 사용했던 java 제어문 배열 + 반복문 + 조건문을 이용해서 로그인 프로그램을 확장시켜 보았다.
public class AuthApp3 {

    public static void main(String[] args) {

        String[] users = { "egoing", "jinhuck", "youbin" };
        String inputId = args[0];

        boolean isLogined = false;
        for (int i = 0; i < users.length; i++) {
            String currentId = users[i];
            if (currentId.equals(inputId)) {
                isLogined = true;
                break; 
            }
        }
        System.out.println("Hi,");
        if (isLogined) {
            System.out.println("Master!!");
        } else {
            System.out.println("Who are you?");
        }

    }

}
>break: 더 이상 현재 반복문을 진행하기 않고 빠져나오게 하는 구문

>>이차원 배열
public class AuthApp4 {

    public static void main(String[] args) {

        // String[] users = {"egoing", "jinhuck", "youbin"};
        String[][] users = {
                { "egoing", "1111" },
                { "jinhuck", "2222" },
                { "youbin", "3333" }
        };
        String inputId = args[0];
        String inputPass = args[1];

        boolean isLogined = false;
        for (int i = 0; i < users.length; i++) {
            String[] current = users[i];
            if (current[0].equals(inputId) &&
                    current[1].equals(inputPass)) {
                isLogined = true;
                break;
            }
        }
        System.out.println("Hi,");
        if (isLogined) {
            System.out.println("Master!!");
        } else {
            System.out.println("Who are you?");
        }

    }
>> 터미널에서 javac AuthApp4.java 입력하고, java AuthApp4 [user] [비밀번호] 올바르게 입력하면 Hi, Master가 나오고, 아니면 who are you가 나오는 구문이다.
}
=========================
java 메소드
=========================
>메소드: 클래스와 관련된 작업을 하는 함수
>메소드에 대한 예제 : floor 메소드
public class FirstMethod {
 
    public static void main(String[] args) {
         
        System.out.println("Hello Method");
        System.out.println(Math.floor(1.1)); 
 >> floor 메소드는 double 형 자료형을 받아서 내림 연산을 수행하여 double 형으로 반환
    }
메소드의 기본 형식
---------------------
>1억줄 이상의 코드가 있는 상황, 메소드를 이용해서 같은 코드 재사용, 유지보수를 쉽게 할 수 있다!!
}
public class WhyMethod {
     
    public static void main(String[] args) {
         
        // 100000000
        printTwoTimesA();
        // 100000000
        printTwoTimesA();
        // 100000000
        printTwoTimesA();
 
    }
 
    public static void printTwoTimesA() {
        System.out.println("-");
        System.out.println("a");
        System.out.println("a");
    }
 
}
> 이클립스에서 Refactor라는 기능 -> 메소스 추출을 빠르게 할 수 있도록 도와줌
> 메소드 추출을 원하는 부분을 블록으로 지정하여 우클릭 후 Refactor -> Extract Method
> 메소드 이름 입력, priview를 누르면 미리 바뀔 모습을 확인 가능
> ok버튼을 눌러서 메소드를 추출할 수 있음
 
메소드의 입력
--------------------
>매개변수는 메소드 안에서 통용되는 변수, 메소드를 호출할 때는 실제 데이터를 메소드의 파라미터 안에 넣게 되는데 이를 인자(아규먼트)라고 함
public class WhyMethod {
     
    public static void main(String[] args) { //main 메소드는 문자열 배열인 args 파라미터 이용
         
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
 
}
# result
*
a
a
&
a
a
!
b
b

메소드의 출력
--------------------
public class OutputMethod {
     
    public static String a() {
        // ... 
        return "a";
    }
     
    public static int one() {
        return 1;
        //...
    }
 
    public static void main(String[] args) {
 
        System.out.println(a());
        System.out.println(one());
         
    }
> 메소드가 데이터를 변환하도록 만들기 위해 구성 요소들이 필요하다.
>> 반환되는 데이터의 타입, return
>메소드가 반환하지 않는다면 void를 넣는다.
'return 반환값' 형식으로 입력하여 메소드가 데이터를 반환하도록 한다.
그리고 return이 실행된 후에는 그 뒤에 실행할 코드가 메소드에 남아 있어도 더 처리하지 않고 바로 메소드를 빠져 나오도록 함
}

import java.io.FileWriter;
import java.io.IOException;

public class WhyMethod {

	public static void main(String[] args) throws IOException {
		String out = twoTimes("a", "-");
		System.out.println(out);
		FileWriter fw = new FileWriter("out.txt");
		fw.write(out);
		fw.close();
		System.out.println(twoTimes("a", "*"));
	}
	public static String twoTimes(String text, String delimiter) {
		String out = "";
		out = out + delimiter + "\n";
		out = out + text + "\n";
		out = out + text + "\n";
		return out;
	}
}
메소드의 활용
------------------
> 이전 쉽게 배우는 자바 14-1 AccountingApp 코드 참조
>> 1
public class AccountingApp { 

	public static void main(String[] args) {
		double valueOfSupply = 10000.0;
		double vatRate = 0.1;
		double vat = valueOfSupply * vatRate;
		double total = valueOfSupply + vat;
		
		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + vat);
		System.out.println("Total : " + total);
	}

}
# result
Value of supply : 10000.0
VAT : 1000.0
Total : 11000.0
>> 여기서 부가가치세와 총 가격을 구하는 부분을 메소드로 추출해서 만들어보자.
>> 2
public class AccountingApp {
	// 공급가액
	public static double valueOfSupply = 10000.0;
	// 부가가치세율
	public static double vatRate = 0.1;

	public static double getVAT(){
		return valueOfSupply*vatRate;
	}

	public static double getTotal(){
		return valueOfSupply + getVAT();
	}

	public static void main(String[] args){
		System.out.println("Value of supply:"+valueOfSupply);
		System.out.println("VAT:"+getVAT());
		System.out.println("Total:"+getTotal());

   }

}
# result
Value of supply:10000.0
VAT:1000.0
Total:11000.0
> 공급가와 부가가치세율은 모든 메소드에서 바로 접근할 수 있게 클래스의 static 필드로 빼내었다. 이렇게 메소드를 이용해서 만든 코드는 재사용성이 휠씬 높아진다 !
>>> (1번 코드랑 2번 코드 결과값은 같음)
부록 (access level modifiers, static)
-----------------------------

접근 제어 
--------------
>> public ? ?
> 동작을 제어하기 위해서 바깥으로 드러나서 호출할 수 있는 것들을 위해 지정함
>> private ? ?
> 외부에서 굳이 알 필요도 없거나 알아서는 안되는 것들을 위해서 지정함
public class AccessLevelModifiersMethod {

	private static void hi() {
		System.out.println("Hi");
	}
	public static void main(String[] args) {
		hi();
	}
# result
Hi
}

(static)
------------
>> 클래스 ? ?
>일종의 형들
>> 인스턴스 ? ?
>그 형들로 찍어서 만든 실체

static 메소드는 클래스의 메소드로, 
프로그램에서 한번만 정의됩니다. 즉 여러 개 가질 수 없는 유일무이한 메소드이다.
반면 static이 아닌 메소드는 인스턴스의 메소드로, 
프로그램 안에서 여러 개 있을 수 있고, 그 인스턴스를 통해서 접근하는 메소드이다.

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
//      Print.a("-");
//      Print.b("-");
         
        // instance
        Print t1 = new Print();
        t1.delimiter = "-";
        t1.a();
        t1.b();
        Print.c("$");
         
         
//      Print.a("*");
//      Print.b("*");
         
        Print t2 = new Print();
        t2.delimiter = "*";
        t2.a();
        t2.b();
    }
     
 
}
>> static 메소드는 클래스의 메소드로 프로그램에서 한번만 정의된다. 즉 여러 개 가잘 수 없는 유일무히한 메소드
>> static이 아닌 메소드는 인스턴스의 메소드로 프로그램 안에서 여러 개 있을 수 있고, 그 인스턴스를 통해서 접근하는 메소드

=============================
JAVA 객체지향 프로그래밍
=============================
> 객체 지향 프로그래밍: 클래스를 이용하여 프로그램의 구조를 만들어 가는 방식
> 객체 지향 언어: 언어 차원에서 지원하는 프로그래밍 언어

남의 클래스 남의 인스턴스
-------------------------------
import java.io.FileWriter;
import java.io.IOException;
public class OthersOOP {
 
    public static void main(String[] args) throws IOException {
        // class : System, Math, FileWriter
        // instance : f1, f2
         
        System.out.println(Math.PI);
        System.out.println(Math.floor(1.8));
        System.out.println(Math.ceil(1.8));
         
        FileWriter f1 = new FileWriter("data.txt"); 
        f1.write("Hello");
        f1.write(" Java");
  
         
        FileWriter f2 = new FileWriter("data2.txt");
        f2.write("Hello");
        f2.write(" Java2");
        f2.close();
         
        f1.write("!!!");
        f1.close();
    }
 
}
# result
3.141592653589793
1.0
2.0
>> Math 클래스에서는 이름에 걸맞게 수학적 계산을 도와주는 여러 메소드를 포함하고 있고, 이전에 사용했던 floor, cell메소드, 클래스의 필드(변수)로 PI 등이 있다.
# 이러한 메소드와 변수는 인스턴스를 생성하지 않더라도 클래스에서 직접적으로 호출할 수 있다.

>> FileWriter 클래스: 파일을 열어서 원하는 내용을 입력할 수 있는 기능들을 제공, 그래서 각각의 파일에 해당하는 인스턴스르 생성하여 write 메소드로 쓰기 작업을 수행하고 close 메소드로 파일을 닫는다.
# 이러한 메소드와 변수는 인스턴스를 생성하여 사용하여야 하고 클래스에서 직접적으로 호출할 수 없음 !

변수와 메소드
-----------------------------

public class MyOOP {

	public static void main(String[] args) {
		
		System.out.println("----");
		System.out.println("A");
		System.out.println("A");
		
		System.out.println("----");
		System.out.println("A");
		System.out.println("A");
	}

}
# result
----
A
A
----
A
A
> 이전에 배웠던 코드 인용
public class MyOOP {

	public static void main(String[] args) {
		
		printA();
		
		printA();
	}

	public static void printA() {
		System.out.println("----");
		System.out.println("A");
		System.out.println("A");
	}

}
# result 
----
A
A
----
A
A
>> 중복되는 작업을 메소드로 추출해서 만들기

public class MyOOP {

	public static void main(String[] args) {
		String delimiter = "----";
		printA(delimiter);
		printA(delimiter);
		printB(delimiter);
		printB(delimiter);
		
		delimiter = "****";
		printA(delimiter);
		printA(delimiter);
		printB(delimiter);
		printB(delimiter);
	}

	public static void printA(String delimiter) {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	public static void printB(String delimiter) {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
}
# result
----
A
A
----
A
A
----
B
B
----
B
B
****
A
A
****
A
A
****
B
B
****
B
B
>> 구분자를 파라미터로 주어 실행할 때마다 원하는 구분자로 출력하기

public class MyOOP {
	public static String delimiter = "";
	
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
# result
====
A
A
====
A
A
====
B
B
====
B
B
****
A
A
****
A
A
****
B
B
****
B
B
>> 구분자를 클래스의 변수로 추출

class Print { /////
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
	public static void printAll() {
		printA();
		printA();
		printB();
		printB();
	}
}
public class MyOOP {
	
	public static void main(String[] args) {
		Print.delimiter = "----";
		Print.printAll();
		
		Print.delimiter = "****";
		Print.printAll();
	}	
}
# result
----
A
A
----
A
A
----
B
B
----
B
B
****
A
A
****
A
A
****
B
B
****
B
B
>> 하나의 클래스로 분리해서 정리정돈 

클래스
------------------------------
> 클래스 : 관련있는 변수들과 메소드를 묶에서 정리정돈을 할 수 있개 하는 것 

class Print{
    public static String delimiter = "";
    public static void A() {
        System.out.println(delimiter);
        System.out.println("A");
        System.out.println("A");
    }
    public static void B(){
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
# 클래스의 장점
> 관련있는 변수들과 메소드를 묶어서 정리정돈을 할 수 있다
> print 객체의 a메소드이기 때문에 a를 출력한다는 의미를 쉽게 유추
> 이클립스와 같은 IDE 프로그램을 이용하게 되면, 접근할 수 있는 클래스의 메소드, 변수를 추천해주는 기능도 존재, 프로그램을 작성하는 데에도 편의성을 증진시킬 수 있다.
# 클래스의 형식
> 클래스는 한 파일에 여러 개를 넣을 수 있지만, 접근제어가 public은 java 파일과 같은 이름의 클래스에 하나만 붙일 수 있다.
> 한 파일 안에 여러 클래스가 등장할 수도 있지만 여러 클래스를 각각 하나의 java 파일로 만들게 되면, 
프로그램의 기능별로 쪼개어서 소스 코드를 별도로 저장할 수 있게 된다.
 
인스턴스
-------------------------
> 객체를 인스턴스로 만들면, 그 인스턴스를 바꾼다고 해도 다른 인스턴스에는 영향을 끼치지 않는다.
> 지난 실습에 사용했던 print 클래스를 인스턴스로 만들어 작업하기
class Print {
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
		Print.delimiter = "****";
		Print.A();
		Print.delimiter = "----";
		Print.B();
		Print.delimiter = "****";
		Print.B();		
	}	
} //구분자를 바꿀때마다 필드에 새로 대입
> 구분자를 바꿀때마다 필드에 새로 대입하여 만들었어야 했지만, 이번에는 구분자마다 인스턴스를 만들어보자
class Print {
	public String delimiter = "";
	public void A() {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	public void B() {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
}
public class MyOOP {
	
	public static void main(String[] args) {
		Print p1 = new Print();
		p1.delimiter = "----";
		Print p2 = new Print();
		p2.delimiter = "****";
		
		p1.A();
		p2.A();
		p1.B();
		p2.B();	
	}	
} //p1, p2 두 개의 인스턴스를 print 클래스를 이용해서 찍어낸 후, 각각 다른 구분자를 넣어줌
>>> 위의 코드랑 결과는 똑같음.
Static
-----------------------------
<pre><code>
> static 변수와 메소드는 클래스에서 생성된 모든 인스턴스가 공유하는 자원
> 인스턴스를 만들지 않고도 클래스에서 직접 호출할 수 있다.
class Foo{
    public static String classVar = "I class var";
    public String instanceVar = "I instance var";
    public static void classMethod() {
        System.out.println(classVar); // Ok
//      System.out.println(instanceVar); // Error
    }
    public void instanceMethod() {
        System.out.println(classVar); // Ok
        System.out.println(instanceVar); // Ok
    }
}
public class StaticApp {
 
    public static void main(String[] args) {
        System.out.println(Foo.classVar); // OK
//      System.out.println(Foo.instanceVar); // Error
        Foo.classMethod();
//      Foo.instanceMethod();
         
        Foo f1 = new Foo();
        Foo f2 = new Foo();
//      
        System.out.println(f1.classVar); // I class var
        System.out.println(f1.instanceVar); // I instance var
//      
        f1.classVar = "changed by f1";
        System.out.println(Foo.classVar); // changed by f1
        System.out.println(f2.classVar);  // changed by f1
//      
        f1.instanceVar = "changed by f1";
        System.out.println(f1.instanceVar); // changed by f1
        System.out.println(f2.instanceVar); // I instance var
    }
 
}
# result
I class var
I class var
I class var
I instance var
changed by f1
changed by f1
changed by f1
I instance var
</code></pre>


생성자와 this
---------------------
<pre><code> 
> print 객체를 생성할 때(인스턴스화) new print()를 사용
>> 구분자를 따로 두기 위해서 구분자마다 print 인스턴스를 사용했던 것
>>> 구분자를 지정하기 위해서는 print 인스턴스의 delimiter 필드를 직접 수정해야 했다.
class Print {
	public String delimiter = "";
	public Print(String delimiter) {
		this.delimiter = delimiter; //
	}
	public void A() {
		System.out.println(delimiter);
		System.out.println("A");
		System.out.println("A");
	}
	public void B() {
		System.out.println(delimiter);
		System.out.println("B");
		System.out.println("B");
	}
}
public class MyOOP {
    public static void main(String[] args) {
        Print p1 = new Print("----");  // 기본 생성자 p1
        p1.A();
        p1.A();
        p1.B();
        p1.B();
 
        Print p2 = new Print("****"); // 기본 생성자 p2
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
> 기본 생성자: Print()와 같이 아무것도 지정하지 않는 생성자
> this 키워드 : 인스턴스를 가리키는 예약어
</code></pre>
활용
-------------
<pre><code>
* 활용(클래스화)
class Accounting{
    public static double valueOfSupply;
    // 공급가액
    public static double vatRate = 0.1;
    // 부가가치세율
    public static double getVAT() {
        return valueOfSupply * vatRate;
    }
    public static double getTotal() {
        return valueOfSupply + getVAT();
    //총 가격
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
>> Accounting 클래스를 새로 정의해서 valueOfSupply, vatRate를 static 필드로 두고, getVAT,getTotal의 static 메소드 구현
--> 이를 통해 회계라는 큰 범주의 이름을 가진 클래스에서 공급가, 부가가치세율, 총 가격 등 의미를 보다 명확하게 파악할 수 있게 문제를 풀 수 있다.
* 활용(인스턴스화)
class Accounting{
    public double valueOfSupply;
    public static double vatRate = 0.1; 
    public Accounting(double valueOfSupply) {  // Accounting의 메소드 표현
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
        //a1.valueOfSupply의 인스턴스를 만들어줌
        System.out.println("Value of supply : " + a2.valueOfSupply);
        //a2.valueOfSupply의 인스턴스를 만들어줌
        //-> 각각의 인스턴스는 서로에게 영향을 미치지 않기 때문에 독립적으로 작업을 처리하게 만들 수 있다.
        System.out.println("VAT : " + a1.getVAT());
        System.out.println("VAT : " + a2.getVAT());
         
        System.out.println("Total : " + a1.getTotal());
        System.out.println("Total : " + a2.getTotal());
    }
}
# result
Value of supply : 10000.0
Value of supply : 20000.0
VAT : 1000.0
VAT : 2000.0
Total : 11000.0
Total : 22000.0
</code></pre>


상속과 인터페이스
------------------------
<pre><code>
클래스와 비슷한 다른 것을 만들고 싶다면 어떻게 해야될까 ?
#1 어떤 클래스의 변수와 메소드들을 모두 복사해서 만드는 방법
#2 상속이라는 개념을 이용하는 방법
* 상속
상속해서 새로운 클래스를 만들게 되면, 어떤 클래스의 모든 변수와 메소드들이 기본적으로 새로운 클래스에 포함, 만약 부족하다면 기존의 변수와 메소드를 덮어쓰거나 아예 새로운 변수와 메소드를 추가할 수도 있다.
* 인터페이스
규격을 선언하는 것
</code></pre> 

==============================
JAVA 상속
==============================

상속을 쓰는 이유 ??
> 어떠한 클래스를 있을때, 클래스가 가지고 있는 변수와 메소드를 확장해서 상속해서 다른 클래스가 같도록 하는 것을 통해 재사용성을 높히고, 유지보수의 편의성을 높히고,
가독성을 높히고, 코드의 양을 줄이는 목적
<code><pre>
class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
}
>> cal이라는 클래스 = 덧셈을 하는 sum 메소드가 있다.
class Cal2 {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
	public int minus(int v1, int v2) {
		return v1 - v2;
	}
}
>> cal에서 뺄셈 기능을 추가한 cal2 클래스
public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
	}

}


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
>> cal3 클래스를 생성할 때 extends 키워드를 이용하여 cal로부터 상속을 받을 수 있다. 
</pre></code>

기능의 개선과 발전
---------------------
>> 자바에서 상속이라는 개념은 부모 클래스(상위 클래스)와 자식 클래스(하위 클래스)의 관계에서 발생함
<code><pre>

class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
}
class Cal3 extends Cal{
	public int minus(int v1, int v2) {
		return v1 - v2;
	}
	public int sum(int v1, int v2){
		System.out.println("Cal3!!");
		return v1 + v2;
	}
}

public class InheritanceApp {

	public static void main(String[] args) {
		Cal c = new Cal();
		System.out.println(c.sum(2, 1));
		Cal3 c3 = new Cal3();
		System.out.println(c3.sum(2, 1));
		System.out.println(c3.minus(2, 1)); 
        // 뺄셈 기능을 자식 클래스에 추가하고자 한다면 새롭게 메소드를 정의해서 넣을 수 있음
	}
}
# result
3
Cal3!!
3
1
>>재정의(override): 상속을 하다보면 자식 클래스에서 부모 클래스에 정의된 메서드를 사용할 때 수정이 필요한 경우 이용함
</pre></code>

override(재정의) vs overload
----------------------------------
오버로딩은 상속과는 직접적인 관련은 없다.
<code><pre>
class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
    // overriding
    	public int sum(int v1, int v2){
		System.out.println("Cal3!!");
		return v1 + v2;
}
	// Overloading
	public int sum(int v1, int v2, int v3) {
		return v1 + v2 + v3;
	}
}
>> overloaing은 특정 이름을 지닌 메소드가 있다고 할지라도 우리는 같은 이름을 가진 메소드를 또 만들 수 있다. 다만 파라미터의 형식이 달라진다.
>> overriding은 같은 클래스 안에서는 이뤄질 수 없고, 상속 관계를 가진 클래스 사이에서 이뤄질 수 있다.
</pre></code>

super
-----------------
<code><pre>
class Cal {
	public int sum(int v1, int v2) {
		return v1 + v2;
	}
	// Overloading
	public int sum(int v1, int v2, int v3) {
		return this.sum(v1, v2) + v3; //this는 자기 자신, sum은 부모
	} // this는 인스턴스를 가리키는 키워드
}
class Cal3 extends Cal{
	// Overriding
	public int sum(int v1, int v2) {
		System.out.println("Cal3!!!");
		return super.sum(v1, v2); //super: 부모 클래스 Cal에 sum을 가리킴
	} // 자식 클래스에서 super를 이용하여 접근 권한이 부여된 부모 클래스의 변수와 메소드에 접근이 가능함.


	public int minus(int v1, int v2) {
		return v1 - v2;
	}
}
>> Cal3에서 Cal의 변수와 메소드에 접근하기 위해서 super를 이용할 수 있다.
</pre></code>

상속과 생성자
----------------------------
<code><pre>
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
>> 부모클래스에 기본 생성자가 아닌 인자를 주는 생성자만 명시된 경우, 자식 클래스에서 생성자를 명시적으로 만들지 않는다면 컴파일이 되지 않는다.
>> 이유는 자식 클래스에서 생성자를 호출하는 경우(인스턴스 생성), 정의한 생성자가 없기 때문에 부모 클래스의 생성자(super())를 사용해야 하는데, 명시적으로 인자를 받는 생성자만 부모 클래스에 만들어져 있기 때문에 기본 생성자가 없는 것으로 받아들여지기 때문이다.

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
	}
}
>> 자식 클래스의 경우에도, 기본 생성자는 명시적으로 만들지 않고, 인자를 받는 생성자만 만들었을 경우에는 인수를 주지 않고 인스턴스를 생성할 수 없다.
>> 부모 클래스에 인자를 받는 생성자만 만들었을 경우, 자식 클래스에도 인자를 받는 생성자를 만들어야 한다.
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
}ㄴ
# result
Cal init!!
Cal3 init!!
3
1
</pre></code>

다음에 배울 만한 주제
------------------------
다형성(polymorphism): 상속 관계에 있는 클래스간의 호환성을 높여주는 기능

접근 제어자(access modifier)

final 키워드: 상속과 관련하여 제한을 걸어주는 키워드 

abstract 키워드:  해당 클래스, 메소드가 재정의가 필요하다는 것을 강제하는 키워드

====================
JAVA 인터페이스
====================
<code><pre>
>> 처음 원했던 덧셈을 수행하는 메소드
 
# 1
class DummyCal {
	public int sum(int v1, int v2) { // v1, v2 인수 2개를 받아서 덧셈을 수행하는 메소드
		// do something
        return result_value;
	}
}
# 2
class RealCal {
	public int sum(int v1, int v2, int v3) {
		return v1 + v2 + v3;
	}
}
// 인수 세 개를 받아서 덧셈을 수행하는 메소드를 지닌 형태
## 두 개를 받아서 덧셈을 수행하는 메소드를 가진 형태 원했는데, 세 개를 받아서 덧셈을 수행하는 메소드를 지닌 형태의 코드를 만들었다면 ??
>> 다시 수정해야된다. 최악의 경우에는 사용자에게 큰 피해를 끼칠 수도 있다.
>> 이러한 경우에 인터페이스를 이용함
interface Calculable {
	int sum(int v1, int v2);
}
class RealCal implements Calculable {

	public int sum(int v1, int v2) {
		return v1 + v2;
	}	
}
</pre></code>


인터페이스의 형식
------------------
> 인터페이스의 이름은 클래스와 마찬가지로 보통 첫 글자를 대문자로 만들고, "~을 할 수 있는" 것들의 규격이라는 의미에서 형용사의 이름을 붙이기도 함
<code><pre>
interface Calculable {
	double PI = 3.14; // 인터페이스에서는 변수를 정의할 수도 있다. 다만 변수는 반드시 초기화 되어야된다.
	int sum(int v1, int v2);
}
interface Printable {
	void print();
}
class RealCal implements Calculable, Printable { //클래스를 상속할 때는 하나의 클래스로부터 상속받을 수 있는 것과 대조적으로 인터페이스는 여러 개를 모두 적용할 수 있다 !!

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
>> 인터페이스를 적용한 클래스는 변수를 다시 대입할 수 없다!!
</pre></code>

다형성
-------------------
>
<code><pre>

# 1
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
		Calculable c = new RealCal(); //Calculable로 받았기 때문에 sum, pi는 실행이 되지만, print는 에러가 난다
		System.out.println(c.sum(2, 1)); //printable로 받으면 반대로 print는 실행이 되지만, sum,pi는 에러가 난다
		c.print(); // Compile Error
		System.out.println(c.PI);
	}
# 2 
}

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
class AdvancedPrint implements Printable{ 
    public void print(){
        System.out.println("This is RealCal!!");
    }
}

public class InterfaceApp {
    public static void main(string[] args){ 
        printable c = new AdvancedPrint(); // AdvancedPrint로 다양한 클래스 표현
        c.print();
    }
}
>> 다형성: 객체의 타입이 부모 클래스, 인터페이스, 자식 클래스 등 여러 형태인데도 인슽턴스로 만든 객체와 같이 행동하는 것
</pre></code>

사용설명서 속의 인터페이스
--------------------------------
<code><pre>
import java.io.FileWriter; 
import java.io.IOException;
import java.io.Writer;

public class FileWriterApp {
	public static void main(String[] args) throws IOException {
		Writer fileWriter = new FileWriter("filewriter.txt");
		fileWriter.write("data 1"); 
		fileWriter.write("data 2");
		fileWriter.write("data 3");
        // close 메소드는 AutoCloseable 인터페이스에 선언되어 있는 메소드
		fileWriter.close(); //close 메소드 사용으로 현재 파일에 대한 점유를 끝낸다.
	}
}
> 조작 하는 방식을 표준화하는데 많이 사용됨.
>> FileWriter와 같이 작업에 있어서 복수의 접근을 막을 필요가 있는 경우에 해당 인터페이스를 적용한다.
</pre></code>

=============================
JAVA 예외
=============================

우리는 프로그램은 어려 오류를 낼 수 있다. 
>> 예외: 예상한 범위를 벗어나는 방식으로 프로그램을 동작시켜서 예상치 못한 결과내는 것

예외의 발생, 처리
-----------------------------
<code><pre>

# 1
public class ExceptionApp {
	public static void main(String[] args) throws ArithmeticException {
		System.out.println(1);
		System.out.println(2/0); // Run-Time Exception ArithmeticException
		System.out.println(3); 예외를 발생 시킴
	}
}

# 2
public class ExceptionApp {
	public static void main(String[] args) throws ArithmeticException {
		System.out.println(1);
		int[] scores = {10, 20, 30};

		try {
			System.out.println(2);
			System.out.println(scores[3]); 
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
# result
1
2
없는 값을 찾고 계시네요 ^^
5
>> try - catch 문: 예외가 발생할 것으로 예상되는 부분을 try로 묶어서 처리하고 코드를 실행 시킬때, 예외가 발생하는 코드가 실행되면 그 다음 코드를 실행하지 않고 해당 예외를 처리하는 catch 문으로 넘어간다.
>> catch 문은 여러 개 사용 가능하다.
</pre></code>

예외의 우선순위
-----------------
<code><pre>
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
# result
1
2
뭔가 이상합니다. 오류가 발생했습니다.
5
>> 여러 예외가 있더라도 Exception 클래스를 이용해서 포괄적으로 처리할 수 있다.
>> catch 문의 위치도 중요함.
>> try 문에서 발생한 예외는 여러 개의 catch 문을 순서대로 거쳐가면서 해당 catch 문의 예외가 이번에 발생한 예외와 맞는지 확인 !
</pre></code>

e의 비밀
------------------

<code><pre>
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
			System.out.println("계산이 잘못된 것 같아요."+e.getMessage());
            e.printStackTrace();
		} catch (Exception e) {
			System.out.println("뭔가 이상합니다. 오류가 발생했습니다. ");
		}	
		System.out.println(5); 
	}
}
>> +e.getMessage, e.printStacktrace를 이용해서 에러가 나는 디테일한 정보를 알 수 있다.
</pre></code>

checked, unchecked Excption
----------------
>>  우리가 만들었던 프로그램은 ArithmeticException, ArrayIndexOutOfBoundsException 같은 경우, try catch 문으로 잡아내지 않아서 프로그램이 뻗는다고 할지라도 컴파일해서 실행할 수 있었다. 이러한 Exception들을 <unchecked Excecption> 이라고 부른다.
>> unchecked Exception은 모두 RuntimeException 클래스로붙터 상속된 에외들이다.

<code><pre>
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
</pre></code>

>> 하지만 try catch 문 등으로 잡아내지 않으면 프로그램이 컴파일도 안되는 예외들도 있다.
>> 이러한 예외들을 checked Exception이라고 함


Finally, Resource
--------------------------------

Resource
>> 우리의 프로그램은 프로그램 외부의 자원에 접근해서 작업을 진행할 수 있다.
>> 대표적인 자원으로는 파일, 네트워크, 데이터베이스 등이 있고, 우리가 필요한 작업을 끝내고 나서는 자원을 놓아주는 작업을 한다.

# finally 문

<code><pre>
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
</pre></code>

>> try 문에서 오류가 발생하면 이후에 작업이 있더라도 catch 문으로 넘어간다.
그래서 자원을 놓아주는 작업을 try 문에 넣게 되면, 예외가 발생했을 때 자원을 놓아주는 작업을 하지 못하게 된다.
>> finally 문: 예외가 발생했든, 발생하지 않았든 자원을 일단 잡았으면 놓아주는 작업을 실행하도록 해야 된다.


Try with Resource
---------------------------

<code><pre>
import java.io.FileWriter;
import java.io.IOException;

public class TryWithResource {

	public static void main(String[] args) {
		try (FileWriter f = new FileWriter("data.txt")) { // 클래스를 인스턴스화 시키는 코드를 나타낸 것 !!
			f.write("Hello");
		} catch (IOException e) {
			e.printStackTrace();
		}
	}
}
>> try-with-resource 문은 try 문에 괄호를 추가하여 그 안에 사용할 자원을 정의,
객체를 여러 개 선언할 수도 있고, 세미콜론(;)으로 구별, 객체의 정의 가장 마지막에는 세미콜론(;)을 넣지 않는다.
>> try-with-resource문은, try catch finally 구문보다 보기 좋고 실수 할 확률이 적어진다.
</pre></code>

앞으로 배울 만한 주제
-------------------------
throw Exception 

import java.io.FileWriter;
import java.io.IOException;

public class ThrowException {

	public static void main(String[] args) throws IOException {
		FileWriter f = new FileWriter("./data.txt");
		f.write("Hello");
		f.close();
	}

}
>> 우리가 우리의 코드에서 예외를 발생 시킬 때, throw 구문을 통해서 예외를 발생 시킬 수 있었다.
>> 이 경우에는 RuntimeException 객체를 이용하였지만, Exception 객체도 직접 생성할 수 있다.
