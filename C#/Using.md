# Using

Using의 용도는 두 가지로 구분할 수 있습니다. 바로 **Using 지시어**와 **Using구문**이 있습니다. 또 이 안에서 Using 지시어는 두 두가지로 나눌 수 있는데 네임스페이스 안에 있는 타입을 허용할 수 있게하는 방법과 별칭을 만드는데에 사용하는 것입니다. 

정리하자면 , 다음과 같습니다. 

___

> [그림1]																
> Using	---> Using지시어	---> 	네임스페이스 안에있는 타입 허용 <br>
> 						--->	별칭만들기<br>
> 		---> Using구문	--->	구문만들기
>
> ___

그럼 예제를 통해 설명해 보겠습니다. 

~~~C#
using System.Text;   
~~~

네임스페이스 안에있는 타입을 허용할 때 사용합니다.

~~~C#
using Project = PC.MyCompany.Project;  
~~~

별칭을 만듭니다.

```C#
using (Font font3 = new Font("Arial", 10.0f),
            font4 = new Font("Arial", 10.0f))
{
    // Use font3 and font4.
}
```

구문을 만듭니다. 이를 통해서 메모리 관리를 보다 편하게 해줍니다.

### 참조

+ http://hoonihoon.tistory.com/entry/C-using-%EB%AC%B8-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0
+ https://docs.microsoft.com/ko-kr/dotnet/csharp/language-reference/keywords/using-directive