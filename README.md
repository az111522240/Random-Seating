> Updated on 2021-09-09

### 这是最新一版本的随机排座位程序

#### 新加功能

- 优化文件输入输出，从输出到 `.txt` 文件改为 `.csv` 文件，方便打印与编辑，优化维护数据与交互。
- 保留文件输入输出的同时支持终端输出座位表，方便即时查看。
- 防止部分爱讲话的同学坐一起（tbd）
- 加入更加友好的终端用户界面。

#### 使用方法

##### 概述

`start.cpp` 为换座位源码；`start` 为 Unix 可执行文件，适用于 macOS / Linux 用户；`start.exe` 是可执行文件，适用于 Windows 用户；`LenDepConfigure.txt`、`StudentNameList.txt`  与 `StudentNotTogetherList.txt` 都是配置文件，支持手动修改；`seating.csv` 是输出的座位表。

##### 操作

- 对于 macOS / Linux 用户：直接点开 `start` 文件，后按屏幕指示执行。
- 对于 Windows 用户：直接点开 `start.exe` 文件，后按屏幕指示执行。

当程序运行结束后，打开 `seating.csv` 文件，就得到生成的座位表；支持修改与打印。

##### 高级
- `LenDepConfigure.txt` 是配置教室长宽数与空格子位置的文件。打开后第一行的数字 <img src="https://latex.codecogs.com/svg.image?Len" title="Len" /> 是行数，第二行的数字 <img src="https://latex.codecogs.com/svg.image?Dep" title="Dep" /> 是列数，第三行的数字 <img src="https://latex.codecogs.com/svg.image?n" title="n" /> 代表有 <img src="https://latex.codecogs.com/svg.image?n" title="n" /> 个空格子，后面 <img src="https://latex.codecogs.com/svg.image?n" title="n" /> 行每一行两个数 <img src="https://latex.codecogs.com/svg.image?a,b" title="a,b" /> 代表第 <img src="https://latex.codecogs.com/svg.image?a" title="a" /> 行第 <img src="https://latex.codecogs.com/svg.image?b" title="b" /> 列是空格子。这些空格子不会有人坐。注意：<img src="https://latex.codecogs.com/svg.image?1\leq&space;a\leq&space;Len,&space;1\leq&space;b\leq&space;Dep" title="1\leq a\leq Len, 1\leq b\leq Dep" />。
- `StudentNameList.txt` 是配置学生姓名列表的文件。打开后第一行的数字 <img src="https://latex.codecogs.com/svg.image?num" title="num" /> 是学生人数，后面 <img src="https://latex.codecogs.com/svg.image?n" title="n" /> 行每一行有个字符串，对应每位学生的姓名。注意：学生数量 <img src="https://latex.codecogs.com/svg.image?num" title="num" /> 应该等于有效格子数，即 <img src="https://latex.codecogs.com/svg.image?Len*Dep-n" title="Len*Dep-n" />；如果不相等，可能出现未知错误，敬请注意。
- `StudentNotTogetherList.txt` 是配置被禁止坐邻座的学生姓名列表文件。打开后第一行的数字 <img src="https://latex.codecogs.com/svg.image?numNotTgt" title="numNotTgt" /> 是被禁止坐邻座的学生人数，后面 <img src="https://latex.codecogs.com/svg.image?numNotTgt" title="numNotTgt" /> 行每一行有个字符串，对应这些学生的姓名。当前版本设置所有被禁止坐邻座的学生两两不能邻座（前后左右坐一起）。





-----

#### Changelog

**[2.0.0] -- 2021-09-09**

- 优化文件输入输出，从输出到 `.txt` 文件改为 `.csv` 文件，方便打印与编辑，优化维护数据与交互
- 保留文件输入输出的同时支持终端输出座位表，方便即时查看
- 防止部分爱讲话的同学坐一起（tbd）
- 加入更加友好的终端用户界面
- 移除前后组功能。此功能预计未来将做为可选功能加入程序中

**[1.2.0] -- 2021-04-19**

- 新增前组后组互换功能：前三排和后三排分位两组，只在组内随机换位，避免有些同学连续坐前排或后排很久
- 因为教室只有31个人，无法被2整除，因此设计上添加一个『占位学生』，导致前排后排换位时有一位同学会随机『换组』

**[1.1.0] -- 2020-11-03**

- 采用文件输入输出
- 从 `data.txt` 中读取学生列表，并存储排序后列表于 `data.txt` 中
- 输出座位表到 `seating.txt` 中，可修改可打印

**[1.0.3] -- 2020-08-24**

- 因教室布局变动，修改输出排版

**[1.0.2] -- 2019-??-??**

- 采用 [梅森旋转算法](https://zh.wikipedia.org/wiki/%E6%A2%85%E6%A3%AE%E6%97%8B%E8%BD%AC%E7%AE%97%E6%B3%95)，循环节更大且运行速度更快，也更接近真正意义上的『随机』

- 优化输出界面，手动对齐与排版

**[1.0.1] -- 2019-09-??**

- 修复输出部分空白名字的 bug

- 优化输出界面，手动对齐与排版

**[1.0.0] -- 2019-09-??**

- 第一稿做出
- 需手动设置教室布局，并在终端输出，很粗糙的作品



