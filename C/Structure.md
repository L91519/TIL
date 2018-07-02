 # Structure

### 개요

1. 구조체란?
2. 구조체의 선언과 정의
3. 구조체 배열의 정의

### 1. 구조체란?

### 2. 구조체의 선언과 정의 

우선 구조체를 선언하는 법은 다음과 같습니다.
→ 필요한 데이터를 구조체로 선언하는 법 : struct (구조체 이름) {필요한 데이터 필드};

구조체 변수를 선언하는 법은 다른 변수들과 다를 것 없이 구조체 이름을 사용하지만 유일한 차이점은 이름 앞에 struct라고 꼭 붙여주는 것입니다. 그리고 선언과 동시에 초기화를 해주는 법은 다음과 같습니다.
→ struct(구조체 이름) (변수이름) = { 필드에 들어갈 데이터1, 필드에 들어갈 데이터2}

하지만 struct를 붙이고 싶지 않을 때는 typedef라는 예약어를 통해서 형 재선언을 포함하는 방법이 있습니다. 

**Sample one (RIGHT)**

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

### 구조체 배열의 정의

