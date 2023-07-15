# WouoUI
模仿稚晖君MonoUI风格的超丝滑菜单，使用EC11旋转编码器控制。

主要版本：
* 128_128：基本上复刻了UltraLink的界面。
* 128_64：在128_128版本的基础上，重新设计主界面和电压测量界面，适配了列表，关于本机界面改为列表类。
* 128_32：在128_64版本的基础上，重新设计主界面和电压测量界面。
* Lite_General：仅保留列表类和弹窗代码，主菜单改为列表类。

实验版本：
* osu：Lite_General分支，模仿 osu! 这款音乐播放器的选歌界面，增加支持调整抛物线曲率。
* wave：Lite_General分支，灵感来自 macOS 程序坞的波浪效果，增加支持调整抛物线曲率。

注意：
* 列表类代码适配了屏幕高度与行高度不能整除的情况，并且能简单修改行高，字高，分辨率等参数，因此Lite_General版本能适配任意情况。
* 磁贴类和电压测量页面需要根据分辨率特殊设计，因此分出三种常见分辨率版本，但列表还是通用的。
* 实验版本为尚未成熟的列表风格，在普通列表的场景下使用会产生强烈的违和感，但可能有特殊用处。

# 第三方项目
* 基于或参考WouoUI展开的第三方项目，如果想将这套UI用在其它地方，不妨在这里看看有没有好心人分享过。
* 在其他平台发布或者通过云盘分享的项目，也可以使用模板分享相关链接。
* 由于本项目不设置开源协议，如果发布者有需要，请在自己的文件夹下添加相关协议。
* 注意，代码不会被审查，发布者可以自由发挥，也请使用者注意计算机安全。

# 功能 
* 全部使用非线性的平滑缓动动画，包括列表，弹窗，甚至进度条
* 优化平滑动画算法到只有两行，分类别定义平滑权重，并且每个权重值都分别可调
* 可以打断的非线性动画，当前动画未结束但下一次动画已经被触发时，动画可以自然过渡
* 非通用版本分别适配了类似 UltraLink 主菜单的磁贴界面（因为让我想起 WP7 的 Metron 风格，所以称之为磁贴）
* 通用版本仅保留列表类界面，经过简单修改可以适配所有分辨率的屏幕，包括屏幕内行数不是整数的情况
* 列表菜单，列表可以无限延长
* 列表文字选择框，选择框可根据选择的字符串长度自动伸缩，进入菜单时从列表开头从长度 0 展开，转到上一级列表时，长度和纵坐标平滑移动到上一级选择的位置
* 列表单选框，储存数据时也储存该值在列表中所在的位置，展开列表时根据每行开头的字符判断是否绘制外框，再根据位置数据判断是否绘制里面的点
* 列表多选框，储存数据的数组跟多选框列表的行数对应，不要求连续排列，展开列表时根据每行开头的字符判断是否绘制外框，再根据行数对应的储存数据位置的数值是否为1判断是否绘制里面的点
* 列表显示数值，与多选框原理相似，但不涉及修改操作
* 列表展开动画，初始化列表时，可以选择列表从头开始展开，或者从上次选中的位置展开
* 图标展开动画，初始化磁贴类界面时，可以选择图标从头开始展开，或者从上次选中的位置展开
* 弹出窗口，实现了窗口弹出的动画效果，可以自定义最大值，最小值，步进值，需要修改的参数等，窗口独立运行，调用非常简单
* 弹出窗口背景虚化可选项，背景虚化会产生卡顿感，但删掉代码有些可惜，因此做成可选项，默认关闭
* 亮度调节，在弹出窗口中调节亮度值可以实时改变当前亮度值
* 旋钮功能，使用EC11旋钮控制，旋钮方向可以软件调整，内置一个USB控制电脑的示例，在睡眠模式下旋转调整音量或者亮度，短按输入一个键值，长按进入主菜单，旋钮消抖时长等参数可以在弹出窗口中调整
* 循环模式，选择项超过头尾时，选择项跳转到另一侧继续，列表和磁贴类可以分别选择
* 黑暗模式，其实本来就是黑暗模式，是增加了白天模式，默认开启黑暗模式
* 消失动画适配两种模式，一种是渐变成全黑，另一种渐变成全白
* 断电存储，用简单直观的方式将每种功能参数写入EEPROM，只在修改过参数，进入睡眠模式时写入，避免重复擦写，初始化时检查11个标志位，允许一位误码

# 效果
* 128_128版本：
![image](https://github.com/RQNG/WouoUI/assets/115459678/0da977bc-5a8f-42f3-bbcc-3ce90da6027b)
演示视频：https://www.bilibili.com/video/BV1Ao4y147La

* 128_64版本：
![image](https://github.com/RQNG/WouoUI/assets/115459678/65437f96-5c1b-46bd-a198-558a0de811e3)
演示视频：https://www.bilibili.com/video/BV1CL41187da/

* 128_32版本：
![image](https://github.com/RQNG/WouoUI/assets/115459678/77ce9c6b-2dcd-4bb9-8d59-f6beeb959015)
演示视频：https://www.bilibili.com/video/BV1Ss4y1D72s/

* 通用版本：
![image](https://github.com/RQNG/WouoUI/assets/115459678/0fae540a-bc7e-43e0-8936-60f22ae3733f)
演示视频：https://www.bilibili.com/video/BV1wo4y1474K/

* osu版本128_128效果演示：
![osu_128_128](https://github.com/RQNG/WouoUI/assets/115459678/b36274a3-51ac-4410-9c9b-a98ac0f01f6d)
演示视频：https://www.bilibili.com/video/BV1Mh4y1s7mB/

* osu版本128_32效果演示：
![osu_128_32](https://github.com/RQNG/WouoUI/assets/115459678/3a3762a9-4c4c-41e1-9476-58925d9f074e)
演示视频：https://www.bilibili.com/video/BV1r24y1A7YF/

* wave版本128_128效果演示：
![屏幕截图 2023-05-30 175808](https://github.com/RQNG/WouoUI/assets/115459678/f939c7e5-cc02-4256-8a05-d85915d80284)
演示视频：https://www.bilibili.com/video/BV1mu411s7q1/

# 参考
* 旋钮：https://zhuanlan.zhihu.com/p/453130384
* UI：
  1. B站用户，路徍要什么自行车：https://www.bilibili.com/video/BV1HA411S7pv/
  2. Github，createskyblue，OpenT12：https://github.com/createskyblue/OpenT12
  3. Github，peng-zhihui，OpenHeat：https://github.com/peng-zhihui/OpenHeat
  4. 知名音乐播放器：osu!
  5. macOS 程序坞

# 更新
## WouoUI

### v 2.2
* 优化动画函数，动画结束后不会再进行无意义的浮点数计算。

### v 2.1
* 修复EC11旋钮使界面卡死的问题，感谢 GitHub 安红豆 提供的线索。

### v 2.0
* UI 流畅度优化，实现了优雅的平滑动画，动画算法被优化到只有两行。
* UI 架构优化，实现了独立弹窗，白天和黑暗模式，单选和多选框，开关等。
* 删除主界面列表菜单风格，增加主界面图标动画可选项。
* 选择框跳转动画改为宽度和竖直方向位置都从当前位置到上一级选中位置平滑过渡。
* 增加动画速度可调区间。10 ~ 100。
* 修复循环模式选择框在跳转动画未结束前，选择项后退时，列表与屏幕错位的问题。
* 修复选择框在选择滚动过快时，滚出屏幕外的问题。
* 增加独立弹窗动画，背景虚化开关功能。
* 重新设计电压测试页，增加波形显示功能，现在可以同时观察数值和波形。

### v 1.1
* 重构代码，只保存路径和选择框所在位置，分页面类型定义变量。
* 增加图标和列表两种主界面风格。
* 支持128×64，128×32两种主流OLED屏幕分辨率，只需要替换驱动即可。
* 增加列表展开动画效果。
* 增加选择框展开和跳转动画效果。
* 增强动画速度的可调精度。
* 增加循环模式。
* 增加旋钮方向反转选项。

### v 1.0
* UI从Rapid-trigger-minipad项目中独立出来。

## WouoUI - osu

### v 1.3
* 优化动画函数，动画结束后不会再进行无意义的浮点数计算。

### v 1.2
* 修复EC11旋钮使界面卡死的问题，感谢 GitHub 安红豆 提供的线索。

### v 1.1
* 列表弯曲程度可调精度提高十倍，范围不变。

### v 1.0
* WouoUI v 2.0 通用版本分支，简单模仿了osu选歌界面列表动效。
* 继承了通用的特性，即支持任意行高，任意字高，任意屏幕分辨率，增加支持调整抛物线曲率。

## WouoUI - wave

### v 1.3
* 优化动画函数，动画结束后不会再进行无意义的浮点数计算。

### v 1.2
* 修复EC11旋钮使界面卡死的问题，感谢 GitHub 安红豆 提供的线索。

### v 1.1
* 列表弯曲程度可调精度提高十倍，范围不变。

### v 1.0
* WouoUI v 2.0 通用版本分支，灵感来自 macOS 程序坞的波浪效果。
* 继承了通用的特性，即支持任意行高，任意字高，任意屏幕分辨率，增加支持调整抛物线曲率。
