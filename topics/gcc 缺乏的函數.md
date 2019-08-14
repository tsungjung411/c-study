## gcc 缺乏的函數

### atoi
```c
warning: implicit declaration of function ‘atoi’ [-Wimplicit-function-declaration]
  return symbol[0] * 100 + atoi(symbol + 1);
                           ^
```
- Getting warning in C for 'atoi' function
  <br>https://stackoverflow.com/questions/20778903/getting-warning-in-c-for-atoi-function
- 使用 atoi C 標準函式庫，遇到 error: implicit declaration of function 'atoi' is invalid in C99
  <br>https://smartboyqq.pixnet.net/blog/post/345988447

### itoa
- implicit declaration of function itoa is invalid in c99
  <br>https://stackoverflow.com/questions/10162465/implicit-declaration-of-function-itoa-is-invalid-in-c99
  - How do I use itoa() with GCC?
    <br>http://www.strudel.org.uk/itoa/

### strrev
- [Solved] Undefined reference to strrev | Error Code in C
  <br>https://www.csestack.org/undefined-reference-to-strrev/
  - Complete C Program for Palindrome | Check if String is Palindrome
    <br>https://www.csestack.org/c-program-for-palindrome/
