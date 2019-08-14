## 計算「各種型態的變數」所佔用的記憶體大小

```c
#include  <stdio.h>

int main(void)
{
	printf("char = %lu\n",          sizeof(char));

	printf("short = %lu\n",         sizeof(short));
	printf("short int = %lu\n",     sizeof(short int));
	printf("int = %lu\n",           sizeof(int));
	printf("long = %lu\n",          sizeof(long));
	printf("long int = %lu\n",      sizeof(long int));
	printf("long long = %lu\n",     sizeof(long long));
	printf("long long int = %lu\n", sizeof(long long int));
	
	printf("float = %lu\n",	        sizeof(float));
	printf("double = %lu\n",        sizeof(double));
	printf("long double = %lu\n",   sizeof(long double));


	printf("\n\n===== unsigned =====\n");
	printf("unsigned char = %lu\n",          sizeof(unsigned char));

	printf("unsigned short = %lu\n",         sizeof(unsigned short));
	printf("unsigned short int = %lu\n",     sizeof(unsigned short int));
	printf("unsigned int = %lu\n",           sizeof(unsigned int));
	printf("unsigned long = %lu\n",          sizeof(unsigned long));
	printf("unsigned long int = %lu\n",      sizeof(unsigned long int));
	printf("unsigned long long = %lu\n",     sizeof(unsigned long long));
	printf("unsigned long long int = %lu\n", sizeof(unsigned long long int));
	return 0;
}
```

## 執行結果：
### Ubuntu 16.04.6 LTS (width: 64 bits)
```
char = 1
short = 2
short int = 2
int = 4
long = 8
long int = 8
long long = 8
long long int = 8
float = 4
double = 8
long double = 16


===== unsigned =====
unsigned char = 1
unsigned short = 2
unsigned short int = 2
unsigned int = 4
unsigned long = 8
unsigned long int = 8
unsigned long long = 8
unsigned long long int = 8
```
