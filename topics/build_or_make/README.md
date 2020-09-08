
## 如何產生 .so 檔，並引用執行
- [Linux 編譯 shared library 的方法和注意事項](https://medium.com/fcamels-notes/_-cb35844ef331)
- [Build .so file from .c file using gcc command line](https://stackoverflow.com/questions/14884126/build-so-file-from-c-file-using-gcc-command-line)

## 如何產生 .a 檔，並引用執行
- [[C/C++] 3-1 建立.a函式庫來使用- 以Orwell Dev C++為例 @ 給你魚竿 :: 痞客邦 ::](https://rx1226.pixnet.net/blog/post/220107256)

## Library 可分成三種：static、shared 與 dynamically loaded
- [Linux 的 .a / .so / .la 函式庫的差異](https://blog.longwin.com.tw/2013/03/linux-a-so-la-library-diff-2013/)
  - .o (obj file) 是目標物件函式庫, 等同於 Windows 的 .obj
  - .a 為靜態函式庫, 可以是 一個 或 多個 .o 合在一起, 用於靜態連結
  - .so 為動態函式庫, 類似 Windows 的 DLL(Dynamic-link library)檔
- [Re: [問題] Linux 上 .a 跟 .so](https://www.ptt.cc/man/C_and_CPP/DBF2/D139/DA10/M.1212250886.A.DF4.html)
  - .a 優點是執行效能通常會比 shared 和 dynamically loaded 快
  - Dynamicaaly loaded libraries 才是像 windows 所用的DLL
- [Linker Script初探 - GNU Linker Ld手冊略讀](http://wen00072.github.io/blog/2014/03/14/study-on-the-linker-script/)
  - object(.o)檔
  - archive(.a)檔
  - shared object(.so)檔
- [What exactly is in a .o / .a / .so file?](https://stackoverflow.com/questions/31179452/what-exactly-is-in-a-o-a-so-file)
  - .a files are simply just archives (an old format that predates tar, but does the same thing). 
