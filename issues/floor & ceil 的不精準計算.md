## Q: pow(sqrt(2), 2) 預期等於 2
也就是 pow(sqrt(x), 2) = x

且預期
- ceil(x) = x
- floor(x) = x
- (ceil(x) - x) = 0
- (x - floor(x)) = 0
- (ceil(x) - x) || (x - floor(x)) 必定是 true

使用 double 會造成 (ceil(x) - x) || (x - floor(x)) 是 false

底下是程式碼：
```c
#include <stdio.h>
#include <math.h>

void main() {
	// r: result
	double r1 = pow(sqrt(2), 2); // should be 2
	printf("r = %.15lf\n", r1);
	printf("r > 2  ? %d\n",  r1 > 2);
	printf("r == 2 ? %d\n", r1 == 2);
	printf("r < 2  ? %d\n",  r1 < 2);
	printf("ceil(r) = %.15lf\n", ceil(r1));
	printf("floor(r) = %.15lf\n", floor(r1));
	printf("ceil(r) - r = %.15lf, is zero = %d\n",
		(ceil(r1) - r1),  (ceil(r1) - r1) == 0);
	printf("r - floor(r) = %.15lf, is zero = %d\n",
		(r1 - floor(r1)), (r1 - floor(r1)) == 0);
	printf("(r - floor(r)) * 1e15 = %.15lf\n",
		(r1 - floor(r1)) * 1e15);
	
	printf("------------------------------\n");
	
	float r2 = pow(sqrt(2), 2); // should be 2
	printf("r = %.15lf\n", r2);
	printf("r > 2  ? %d\n",  r2 > 2);
	printf("r == 2 ? %d\n", r2 == 2);
	printf("r < 2  ? %d\n",  r2 < 2);
	printf("ceil(r) = %.15lf\n", ceil(r2));
	printf("floor(r) = %.15lf\n", floor(r2));
	printf("ceil(r) - r = %.15lf, is zero = %d\n",
		(ceil(r2) - r2),  (ceil(r2) - r2) == 0);
	printf("r - floor(r) = %.15lf, is zero = %d\n",
		(r2 - floor(r2)), (r2 - floor(r2)) == 0);
	printf("(r - floor(r)) * 1e15 = %.15lf\n",
		(r2 - floor(r2)) * 1e15);
}
```


執行結果：
```
r = 2.000000000000000
r > 2  ? 1
r == 2 ? 0
r < 2  ? 0
ceil(r) = 3.000000000000000
floor(r) = 2.000000000000000
ceil(r) - r = 1.000000000000000, is zero = 0
r - floor(r) = 0.000000000000000, is zero = 0
(r - floor(r)) * 1e15 = 0.444089209850063
------------------------------
r = 2.000000000000000
r > 2  ? 0
r == 2 ? 1
r < 2  ? 0
ceil(r) = 2.000000000000000
floor(r) = 2.000000000000000
ceil(r) - r = 0.000000000000000, is zero = 1
r - floor(r) = 0.000000000000000, is zero = 1
(r - floor(r)) * 1e15 = 0.000000000000000
```

## 相關問題
- [Checking if float is an integer](https://stackoverflow.com/questions/5796983/checking-if-float-is-an-integer)
