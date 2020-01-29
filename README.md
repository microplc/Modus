# Modus

用于模式控制的很小 Arduino 库。

**仅在 Arduino Due 测试过**

## 介绍

引入头文件到你的代码

    #include <Modus.h>

### 结构

仅仅需要创建带有模式个数参数的 Modus 对象即可。

下面代码创建 4 个 Modes，但是 Mode 0 是启动默认模式。

    Modus modes(4);

### 函数共4个


#### mode()

返回当前模式。可以比较数字也可以像例子中一样比较预定义#defines。

    modes.mode() == 4 // true if the current mode is Mode number 4, false otherwise.

#### set(mode)

设置当前模式，不正确的模式将被忽略。

    modes.set(10); // is ignored since there's only Modes 0 to 4.
    modes.set(2); // Changes to Mode 2.
    modes.set(10) == 10; // Returns false since the change wasn't accepted.
    modes.set(4) == 4; // Changes to Mode 4 and returns true.

#### status(mode)

同当前激活模式作比较，返回 true 或 false 。

    modes.status(1); // Returns true if 1 is the current active Mode.

#### state(mode)

与 status(mode) 相似，但返回 HIGH/LOW 。

    modes.status(1); // Returns HIGH if 1 is the current active Mode.
