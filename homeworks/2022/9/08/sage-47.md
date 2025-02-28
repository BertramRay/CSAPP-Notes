## p1-5

#### 信息的解释
- 位 + 上下文
- 位：由0 1组成的位， 8个位(bit)为一个字节
- 系统中的所有信息，包括磁盘文件、内存中的程序、数据以及网络上传送的数据，都是一串bit表示。
- 区分不同数据的方式就是上下文。

#### 程序翻译 
为了在系统上运行程序，每条c语句都必须被转化为一系列机器语言指令，然后这些指令按照一种称为可执行目标程序的格式打好包，并已二进制磁盘文件的形式存放。
```
#include <stdio.h>

int main()
{
    printf("hello, world\n");
    return 0;
}
```
- 执行：gcc -o hello hello.c
- 翻译过程：hello.c → 预处理(cpp) → 编译器(ccl) → 汇编器(as) → 链接器(ld) → 可执行目标程序
    - 预处理：读取stdio.h加入程序，生成**hello.i文件**
    - 编译：将.i文件翻译成**hello.s文件** 包含汇编语言程序。
    - 汇编：将.s翻译成机器语言指令，打包成可重定位目标程序格式，保存在**hello.o**二进制文件中
    - 链接：链接程序中使用的函数，某种方式将函数合并到程序中保证其能正常执行，得到**hello文件**。
- 了解编译系统如何工作的益处：
  - 优化性能
  - 更快速定位问题
  - 避免安全漏洞

#### 处理器如何读与解释指令
1. 系统硬件组成
   1. 总线
   2. I/O设备
   3. 主存
   4. 处理器
