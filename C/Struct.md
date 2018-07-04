 # Structure

### 목차

1. 구조체란?
2. 구조체의 선언과 정의
3. 구조체 배열의 정의
4. 구조체 동적할당
5. 참조

### 1. 구조체란?

구조체는 자신이 필요한 데이터형을 직접 만들어서 사용하는 **사용자 정의 자료형** 입니다. 

구조체는 어쨌든 자료형이기 때문에 반환자료가 될 수도 있고 매개변수가 될 수도 있습니다. 하지만 구조체는 선언하기에 따라 크기가 달라집니다. 따라서 구조체의 크기가 크다면 반환자료나 매개변수로 사용할때 그 만큼 스택을 많이 사용해야하고 메모리 복사 연산도 계속되기 때문에 효율이 떨어집니다. 그러므로  **구조체 변수를 매개변수나 반환 자료형식으로 사용하는 것은 비효율적입니다.**

구조체는 자기 자신을 포함한 모든 구조체를 맴버로 가질 수 있습니다. 

### 2. 구조체의 선언과 정의 

우선 구조체를 선언하는 법은 다음과 같습니다.
→ 필요한 데이터를 구조체로 선언하는 법 : struct (구조체 이름) {필요한 데이터 필드};

구조체 변수를 선언하는 법은 다른 변수들과 다를 것 없이 구조체 이름을 사용하지만 유일한 차이점은 이름 앞에 struct라고 꼭 붙여주는 것입니다. 그리고 선언과 동시에 초기화를 해주는 법은 다음과 같습니다.
→ struct(구조체 이름) (변수이름) = { 필드에 들어갈 데이터1, 필드에 들어갈 데이터2}

하지만 struct를 붙이고 싶지 않을 때는 typedef라는 예약어를 통해서 형 재선언을 포함하는 방법이 있습니다. 

**Sample 1**

```c
#include <stdio.h>
#include <string.h>

struct USERDATA {
	int nAge;
	char szName[32];
	char szPhone[32];
};

int main(void) {
	struct USERDATA user = {0, "", ""};
	user.nAge  = 10;
	strcpy(user.szName, "Hoon");
	strcpy(user.szPhone, "010-1234-1234");
	
	printf("%d살, %s, %s\n",user.nAge, user.szName, user.szPhone);
	return 0;
}
```

result : 10살, Hoon, 010-1234-1234

___

**Q1. **왜 초기화 할때 데이터를 똑바로 입력하지 않으면 정수를 대입하는 것과 달리 strcpy( )를 사용해야할까요?

다음 코드는 strcpy( )를 사용하지 않고 구조체 안의 변수를 대입해보는 코드와 그에 따른 결과입니다. 

```c
#include <stdio.h>
#include <string.h>

struct USERDATA {
	int nAge;
	char szName[32];
	char szPhone[32];
};

int main(void) {
	struct USERDATA user = {0, "", ""};
	user.nAge  = 10;
    user.szName = "Name";
	user.szPhone = "010-1234-1234";
	
	printf("%d살, %s, %s\n",user.nAge, user.szName, user.szPhone);
	return 0;
}
```

result : [Error] incompatible types in assignment of 'const char [14]' to 'char [32]'

**A1. **이미 할당된 배열에는 문자열을 바로 넣을 수 없기 때문에 strcpy를 사용해서 해야합니다.
~~보다 정확한 대답은 나중에 추가할 예정~~

___

### 3. 구조체 배열의 정의

*stuct를 선언했을 때 typedef 예약어를 사용했다고 가정하고 작성했습니다.*

구조체 배열 변수를 선언할 때는	다른 변수를 선언 할 때와 동일하며 초기화 역시도 동일한 방법으로 초기화 할 수 있습니다. 

### 4. 구조체 동적할당

구조체는 사용자가 자신이 필요한 자료형을 만드는 것입니다. 그렇기 때문에 메모리를 동적할당할 떄는 무조건 sizeof( )를 사용해야합니다. 만약 임의로 구조체의 필드들의 크기를 계산하여 사용한다면 선언된 구조체에 수정사항이 있을때 임의로 계산하여 메모리를 할당했던 부분을 모두 수정해주어야합니다. 그렇기 때문에 **구조체 동적할당에서는 반드시 sizeof( )를 사용해야합니다.**

**SAMPLE2**

```c
typedef struct USERDATA
{
    int nAge;
};

int main(Void)
{
    USERDATA *pUser = NULL;
    pUser = (USERDATA*) malloc (sizeof(USERDATA));
    pUser -> nAge = 10;
    
    printf("%d살", pUser -> nAge);
}
```

Sample2의 코드에서 보이듯, **포인터로 구조체에 접근할 때에는 화살표 연산자를 사용합니다.**

___

**Q2. ** 구조체에서 화살표(->) 연산자란? 

포인터로 구조체에 접근할 때는 점(.) 연산자 보다는 화살표(->) 연산자를 사용합니다. 사실 보통 구조체 맴버를 참조할 때는 점 연산자를 사용하지만 포인터로 구조체에 접근할 때에는 일반적인 상황과 다르게 화살표 연산자를 사용해 구조체 맴버를 참조합니다. 

→ **구조체 포인터 이름 +  화살표 연산자 (->)  + 맴버이름 **
SAMPLE2와 같은 형식으로 화살표 연산자를 사용합니다. result : 10살

포인터 맴버 연산자가 없었을 때는 **(*구조체 포인터 이름).맴버이름 **의 형식이 일반적이었습니다. 그렇지만 이러한 형식이 불편하다라는 의견에서 나오게 된 연산자가 화살표 연산자 입니다. 

**A2. ** 포인터로 구조체에 접근할 수 있는 가장 일반적인 방법입니다. 왜냐하면 아래의 식이 성립하기 때문입니다.

* ***구조체 포인터 이름 +  화살표 연산자 (->)  + 맴버이름 == (\*구조체 포인터 이름).맴버이름***

___

### 5. Reference

https://m.blog.naver.com/PostView.nhn?blogId=skout123&logNo=50132236162&proxyReferer=https%3A%2F%2Fwww.google.co.kr%2F

독하게 시작하는 C프로그래밍