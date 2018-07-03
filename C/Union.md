# Union

The way of using Union is just the same with they way we use struct. The difference between Union and Struct is that Sturcut contains many form of data, and can init each one of that but in the case of Union, it has only one data and convert it to many forms that are written in Union scope.

Here is the example of using union :

```c
#include<stdio.h>

typedef union _IP_ADDR
{
    int nAddress;
    short awData[2];
    unsigned char addr[4];
}

int main(void)
{
    IP_ADDR Data = { 0 };
    Data.nAddress = 0x14124344;
    
    printf("%c%c%c%c\n", Data.addr[0], Data.addr[1], Data.addr[2], Data.addr[3]);
    printf("%x, %d\n", Data.awData[0], Data.awData[0]);
    printf("%x, %d\n", Data.awData[1], Data.awData[1]);
    return 0;
}
```

result : 	DCBA
		4344, 17220
		4142, 16706

Those are the three ways of translating one data.

#### Refernece

독하게 배우는 C프로그래밍