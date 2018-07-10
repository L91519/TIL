# 문자배열과 String

char[] = new char[] {}의 형식과 String은 모두 문자열을 다루기 위해 사용됩니다. 그렇다면 둘의 차이점은 무엇일까요? 

아래의 예제를 보면  아주 쉽게 이해할 수 있습니다. 

~~~C#
String str = new String(new char[]{'가','나','다'}); 
~~~

String은 그저 Char[]을 추상화한 클래스라고 생각하면 됩니다. 문자 배열을 전달하고 String인스턴스를 생성하여 사용하는 것이 우리 눈에 보이지 않고 몰래 일어나던 일이었습니다. 

~~~C#
string str = "홍길동";
Console.WriteLine(str[0].ToString() + str[1].ToString() + str[2].ToString());
~~~

위와 같은 예제를 실행시키면 어떤 실행결과가 나올까요? 

아까 설명했듯이, String은 Char[]을 추상화한 것이기 때문에 결과값 역시도 "홍길동"이라고 나옵니다. 

#### 참조

http://www.mkexdev.net/Article/Content.aspx?parentCategoryID=1&categoryID=5&ID=683