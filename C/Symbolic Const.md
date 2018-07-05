# Symbolc Const
### 목차

1. 상수란?
   1.1. 상수의 뜻
   1.2. 상수가 사용되는 이유
2. Const
3. Define
4. 상수형 포인터
5. 참조

### 1. 상수란? 

#### 1.1. 상수의 뜻

**심볼릭 상수란 의미가 명확할 수 있도록 숫자와 변수이름을 조합하여 표현하는 것입니다.** 변수 네이밍은 프로그램이 돌아가는데는 아무런 영향이 없지만 변수의 의미가 명확한 것은 굉장히 중요합니다. 그렇기 때문에 늘 프로그램을 보다 좋은 방향으로 발전시키려는 노력이 필요합니다.

상수란 일종의 변수에 포함되지만 값이 변하지 않는 변수를 뜻합니다. 변수의 본질이 메모리임을 생각한다면 더 쉽게 설명이 가능합니다. 상수는, 특정한 메모리가 '읽기 전용'메모리가 된 것입니다.

상수는 프로그래밍 도중에 상수가 되어 '읽기전용'으로 변하는 것이 아니라 처음에 선언과 정의를 동시에 내릴때 상수화가 되어 프로그래밍이 실행되어지는 것입니다.

#### 1.2. 상수가 사용되는 이유

- 기억하기 힘든 값이 존재할 때

  → 원주율처럼 기억하기 힘든 값이 존재할 때 상수를 씀으로써 쉬운 이름을 줄 수 있습니다.

- 값이 변하면 위험한 경우에

+ 유지보수를 쉽게하기 위해

  → 	특정한 값을 쉽게 바꾸고 싶을 때 한 번에 상수의 값을 바꿈으로써 유지보수가 쉬워집니다.

  Sample1의 코드처럼 기준 점수를 바꾸러면 70이 들어간 모든 부분을 바꾸기 보다는 nCUTOFF를 정한 부분의 코드만 수정하면 됩니다.
+ 유지보수를 쉽게하기 위해

  → 	특정한 값을 쉽게 바꾸고 싶을 때 한 번에 상수의 값을 바꿈으로써 유지보수가 쉬워진다. 

  Sample1의 코드처럼 기준 점수를 바꾸러면 70이 들어간 모든 부분을 바꾸기 보다는 nCUTOFF를 정한 부분의 코드만 수정하면 된다.
  **Sample 1**

  ```c
  #include<stdio.h>
  
  int main(Void) {
      const int nCUTOFF = 70;
      int nInput = 0;
      
      printf("점수입력 : ");
      scanf("%d", &nInput);
      
      if(nInput >= nCUTOFF)
      	printf("합격");
      else
      	printf("불합격");
  }
  ```

+ 성능향상을 위해

  → 컴파일러 입장에서는 상수를 사용함으로써 줄어든 변수의 수만큼 번역에도 유리해집니다.

------

**Q1.** 상수를 사용하는 것이 왜 컴파일러에게 도움이 될까?

**A1.** 우선 C언의 가장 큰 특징중에 하나는 포인터입니다. 이는 굉장히 강력한 기능으로써 잘 쓰면 굉장히 유용한 기능이지만 그렇지 않는다면 역효과를 줄 수 있습니다. 나쁜 예로는 컴파일러가 C언어를 기계어로 변환할 떄 효율적이지 못한 코드로 변환된다던가 동시성을 심각하게 떨어뜨릴 수 있습니다. 

이러한 문제는 매우 심각한 문제가 될 수도 있지만 완벽하게 해결하기란 굉장히 어렵습니다. 하지만 포인터를 상수로 변환해줌으로써 포인터 변수가 적어지고 읽기전용 데이터가 많아집니다. 이러한 것이 컴파일러를 도와줍니다.

___

+ 값이 변하면 위험한 경우에

+ 기억하기 힘든 값이 존재할 때
  → 원주율처럼 기억하기 힘든 값이 존재할 때 상수를 씀으로써 쉬운 이름을 줄 수 있다. 
### 2. Const

const라는 예약어는 변수를 상수화 해주는 예약어입니다. 그리고 이 예약어는 변수를 선언할 때 적용해야합니다. 변수선언에서 변수 형 앞에 예약어를 입력하고 사용합니다. 그러므로 처음에는 쓰기 가능 변수였다가 나중에 읽기 전용 변수가 되는 것이 아니라 처음부터 읽기 전용 변수라는 것입니다. 

~~사실 위에서 설명했듯이 define처럼 다른 상수화하는 예약어도 처음부터 읽기 전용입니다. const만의 특징이 아닙니다.~~

### 3. Define

변수를 상수화해주는 방법에는 const뿐만이 아니라 "#define 전처리기"도 있습니다.  이는 예제를 통해 설명하도록 하겠습니다.

```c
#include<stdio.h>
#define CUTOFF 70

int main(void) {
	int nInput = 0;
	
	prinf("점수 입력 : ");
	scanf("%d", &nInput);
	
	if(nInput >= CUTOFF)
    	prinf("합격");
	else
		prinf("불합격");
}
```

위와 같은 코드에서 컴파일을 하게될 때의 과정은 컴파일을 하기 전에 CUTOFF라고 쓰여져 있는 모든 것을 70으로 변경합니다. const를 사용하는 것과 전처리기를 사용하는 것에는 큰 차이가 없지만 전처리기는 문법적으로 완전한 상수라는 것이 차이점입니다.

### 4. 상수형 포인터

~~사실 이부분은 저도 완벽히 이해가 안 가서 자신감이 매우 떨어진 채로 쓸 것 같고 책(독하게 시작하는 C프로그래밍)의 내용을 많이 참고 할 것 같습니다.~~

위의 QnA에 상수형 포인터가 왜 필요하고 어떻게 효율적인지는 미리 설명을 했습니다. 하지만 다시 짧게 설명하자면 포인터의 기능을 매우 강력하여 컴파일러에도 영향을 많이 끼치는데 이의 부작용을 어느정도 해결해보고자 사용하는 것입니다.

___

**Q1.** 포인터가 상수로 되면 메모리의 구조가 달라집니까? 또한 왜 포인터의 남용이 동시성에 악영향으로 주고 기계어로 번역하는데에 문제가 생기는 것 입니까?

___

그렇다면 이렇게 간단히 상수형 포인터를 쓰는 이유에 대해 이해하고 어떻게 쓰는지 무엇을 의미하는지 등등을 알아보도록하겠습니다.



### 5. 참조

+ http://mwultong.blogspot.com/2007/03/c-define-constant.html
+ 독하게 배우는 C프로그래밍