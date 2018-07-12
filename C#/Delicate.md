> 최초 작성일 : 2018-07-12
>
> 작성자 : 고수민
>
> 최종 작성일 

# Delegate

### 목차

1. 델리게이트란?
   1.1. 기본적인 예제
2. 사용하는 이유
3. Callback
4. 심화내용
5. 참조

### 1. 델리게이트란?

델리게이트의 뜻은 '대리자'입니다. 하지만 이름으로 델리게이트의 쓰임새를 유추하기는 어려울 수도 있습니다. 하지만 델리게이트를 이해하고 나면 왜 이름이 이렇게 붙었는지 알 수 있습니다.

델리게이트는 메소드를 호출해 주는 역할을 수행하는 것입니다. 이는 '대리자'라는 뜻과 어울리게, 대신 메소드를 호출해줍니다. 이렇게 대신 무언가를 호출해주는 것은 프로그램이 실행될때 동작됩니다. **델리게이트는 콜백을 구현하는데 사용됩니다.** 콜백은 델리게이트의 핵심적인 부분중 하나이기 때문에 뒤에서 자세하게 설명하도록 하겠습니다.

앞으로 나올 델리게이트의 사용 예제를 보면 메소드와 비슷하다고 생각 할 수도 있지만 **델리게이트는 형식(Type)입니다.** 

#### 1.1. 예제

1. 델리게이트 선언

   ~~~c#
   delegate int MyDelegate(int a, int b)
   ~~~

2. 델리게이트가 참조할 메서드 작성

   ~~~C#
   class Calculator 
   {
       public int Plus(int a, int b) {
           return a + b;
       }
       
       public int Minus(int a, int b) {
           return a -b;
       }
   }
   ~~~

3. 델리게이트 사용

   ~~~C#
   Class MainApp
   {
   	static void main(string[], args)
       {
       	Calculator Cal = new Calculator();
       	MyDelegate Callback;
       	
       	Callback = new MyDelegator(Cal.Plus);
       	Callback = new MyDelegator(Cal.Minus);
       }
   }
   ~~~

델리게이트는 기본적으로 이런식으로 사용한다. 여기서 주의해야할 점은 델리게이트가 참조할 메서드의 매개변수와 반환형식은 같아야한다는 것이다.

### 2. 사용하는 이유

+ 값이 아닌 메서드를 매개변수로 넘기고 싶을 때

### 





