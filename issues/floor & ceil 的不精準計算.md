## Q: pow(sqrt(2), 2) 預期等於 2
也就是 pow(sqrt(x), 2) = x

且預期
- ceil(x) = x
- floor(x) = x
- (ceil(x) - x) = 0
- (x - floor(x)) = 0
- 如果一個數 x 有小數點(精準度與誤差所造成)，記憶體的值可能大於或小於 x，比如：
  <br>假設 x = 2 在記憶體中的表達是 1.999999 或是 2.000001 這種概念
  <br>若 x = 1.999999，那麼 ceil(x) = 2, floor(x) = 1
  <br>若 x = 2.000001，那麼 ceil(x) = 3, floor(x) = 2
  <br>
  <br>又，如果一個數 x 沒有小數點(剛好是整數)，比如：
  <br>假設 x = 2 在記憶體中的表達是 2.000000 這種概念
  <br>那麼 ceil(x) = floor(x) = x
  <br>且 ceil(x) - x = floor(x) - x = 0


底下是程式碼：
```c
#include <stdio.h>
#include <math.h>

void main() {
	// r: result
	double r1 = pow(sqrt(2), 2); // should be 2
	printf("use double:\n");
	printf("r = %.16lf\n", r1);
	printf("r > 2  ? %d\n",  r1 > 2);
	printf("r == 2 ? %d\n", r1 == 2);
	printf("r < 2  ? %d\n",  r1 < 2);
	printf("ceil(r) = %.16lf\n", ceil(r1));
	printf("floor(r) = %.16lf\n", floor(r1));
	printf("(r - floor(r)) * 1e15 = %.16lf\n",
		(r1 - floor(r1)) * 1e15);

	printf("------------------------------\n");

	float r2 = pow(sqrt(2), 2); // should be 2
	printf("use float:\n");
	printf("r = %.16f\n", r2);
	printf("r > 2  ? %d\n",  r2 > 2);
	printf("r == 2 ? %d\n", r2 == 2);
	printf("r < 2  ? %d\n",  r2 < 2);
	printf("ceil(r) = %.16f\n", ceil(r2));
	printf("floor(r) = %.16f\n", floor(r2));
	printf("(r - floor(r)) * 1e15 = %.16f\n",
		(r2 - floor(r2)) * 1e15);
}
```


執行結果：
```
use double:
r = 2.0000000000000004
r > 2  ? 1
r == 2 ? 0
r < 2  ? 0
ceil(r) = 3.0000000000000000
floor(r) = 2.0000000000000000
(r - floor(r)) * 1e15 = 0.4440892098500626
------------------------------
use float:
r = 2.0000000000000000
r > 2  ? 0
r == 2 ? 1
r < 2  ? 0
ceil(r) = 2.0000000000000000
floor(r) = 2.0000000000000000
(r - floor(r)) * 1e15 = 0.0000000000000000
```

## 相關問題
- [Checking if float is an integer](https://stackoverflow.com/questions/5796983/checking-if-float-is-an-integer)
- [Determining if a float has a fractional part?](https://stackoverflow.com/questions/8549365/determining-if-a-float-has-a-fractional-part)
