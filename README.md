#include <stdio.h>

int main()
{
    int i;
    int *ptr;
    int **dptr;

    i = 1234;

    printf("[checking values before ptr = &i] \n");
    printf("value of i == %d\n", i); //i에 저장된 값 출력
    printf("address of i == %p\n", &i); // 변수 i의 주소 출력
    printf("value of ptr == %p\n", ptr); //포인터 변수의 쓰레기값 출력
    printf("address of ptr == %p\n", &ptr);// 포인터 변수의 주소 출력

    ptr = &i; /* ptr is now holding the address of i */ //포인터 ptr이 변수 i를 가리킴

    printf("\n[checking values before ptr = &i] \n");
    printf("value of i == %d\n", i); // i에 저장된 값 출력
    printf("address of i == %p\n", &i); // 변수 i의 주소 출력
    printf("value of ptr == %p\n", ptr); //포인터 변수에 저장된 i의 주소 출력
    printf("address of ptr == %p\n", &ptr); // 포인터 변수의 주소 출력

    dptr = &ptr; /* dptr is now holding the address of ptr */ //이중포인터 dptr이 변수 ptr를 가리킴

    printf("\n[checking values before ptr = &ptr] \n");
    printf("value of i == %d\n", i); // i에 저장된 값 출력
    printf("address of i == %p\n", &i); // i의 주소 출력
    printf("value of ptr == %p\n", ptr); // 포인터 변수에 저장된 i의 주소 출력
    printf("address of ptr == %p\n", &ptr); // 포인터 변수의 주소 출력
    printf("value of *ptr == %p\n", *ptr); // 포인터가 가리키는 변수에 저장된 값 출력 = i
    printf("value of dptr == %p\n", dptr); // 이중 포인터 변수에 저장된 포인터의 주소 출력 = &ptr
    printf("address of dptr == %p\n", &dptr); // 이중포인터의 주소 출력
    printf("value of *dptr == %p\n", *dptr); //이중포인터가 가리키는 포인터의 저장된 값 출력 = ptr
    printf("value of **dptr == %p\n", **dptr); //이중포인터가 가리키는 포인터가 가리키는 변수에 저장된 값 출력 = i

    *ptr = 7777; /* changing the value of *ptr */ //포인터 ptr이 변수에 7777을 저장, i = 7777

    printf("\n[after *ptr = 7777]\n");
    printf("value of i == %d\n", i); // i에 저장된 값 출력
    printf("value of *ptr == %d\n", *ptr); // 포인터가 가리키는 변수의 값
    printf("value of**dptr == %d\n", **dptr); // 이중포인터가 가리키는 포인터가 가리키는 변수의 저장된 값 출력 = i

    **dptr = 8888; /* changing the value of **dptr */ //이중 포인터가 가리키는 포인터가 가리키는 변수에 8888 저장, i = 8888

    printf("\n[after **dptr = 8888]\n");
    printf("value of i == %d\n", i); // i에 저장된 값 출력
    printf("value of *ptr == %d\n", *ptr); // 포인터가 가리키는 변수의 값
    printf("value of**dptr == %d\n", **dptr); // 이중포인터가 가리키는 포인터가 가리키는 변수의 저장된 값 출력 = i

    return 0;
}
