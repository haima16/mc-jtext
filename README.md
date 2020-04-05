## 前言

现有的Json Text生成器有很多，但总是不那么好用，不论界面设计的多好，但本质交互设计上就不友好。理想的Json Text生成器应该像使用word编辑文稿一样，不过由于个人技术问题，只能折中实处理，尽量的做到便捷、实用。

做此软件的初衷是希望帮助热爱mc的玩家，尤其是制作地图和萌新们，现在MC在国内的形式感觉又慢慢好转起来，但优秀的地图并似乎没有随之增多，究其原因还是mc在变的好玩的同时也越来越复杂，制作地图的大大们真的是要身兼多项技能，更不要说萌新们了。

## 地址
| 源             | 链接                                          | 使用文档                                           | 问题反馈                                                  | 更新日志                                                     |
| -------------- | --------------------------------------------- | -------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------ |
| gitee（国内）  | [链接](http://hans000.gitee.io/jtext-studio/) | [使用文档](https://gitee.com/hans000/JText-Studio) | [问题反馈](https://gitee.com/hans000/JText-Studio/issues) | [更新日志](https://gitee.com/hans000/JText-Studio/blob/master/log.md) |
| github（国际） | [链接](https://haima16.github.io/mc-jtext/)   | [使用文档](https://github.com/haima16/mc-jtext)    | [问题反馈](https://github.com/haima16/mc-jtext/issues)    | [更新日志](https://github.com/haima16/mc-jtext/blob/master/log.md) |



## 功能特色

- 所见即所得
- 模板化、模块化
- 丰富的快捷操键
- 强大的编辑功能
- 实时保存

## 术语说明

  - JText、Json text：[JSON文本](https://minecraft-zh.gamepedia.com/%E5%91%BD%E4%BB%A4#JSON.E6.96.87.E6.9C.AC)是mc中聊天组件的最小组成
  - tile：可操作的最小单元，对应mc中的一个JText 
  - tile group：tile的集合，对应mc中的一个Tellraw、book中一页等
  - raw json text：JText的集合
  - export json：生成器导出的工程数据

> P.S. 只是为方便说明，仅为个人定义

## 交互说明

### 预览

预览可以把用户当前操作呈现出来，实时预览

- 点选操作: 鼠标点击tile即可，点击后会有高亮显示
- 更换背景色: 右下角有个拾色器，可以点击更换颜色

### 操作栏

- 添加: 当你完成一个tile后想要继续添加一个样式不一样的tile时可以点击此按钮
- 拆分：强大的功能，替代了「插入」「克隆」功能，按回车符将其拆分为多个tile
- 删除: 当你不想要某个tile时，选中一个tile可以将其移除，不可恢复
- 清空: 当你不想要当前这个工程时，可以点击此按钮，所有的tile都会被删除，不可恢复
- 取消: 可以取消tile的高亮
- 生成: 生成一段可用的JText
- 暂存: 将当前工程保存，可以在仓库查看
- 导入: 可以把合法的json文本解析
- 导出: 可以把当前的内容保存为json文本，作为模板
- 仓库~~~~: 打开仓库管理

### 样式

样式共6项，对应JText中的6个字体样式nbt标签，即加粗、斜体、下划线、删除线、混淆和字体颜色，并设置快捷键，详细见快捷键

### 事件

点击事件：分5种，open_url | run_command | change_page | suggest_command | copy_to_clipboard

悬浮事件：分3种 text | block | entity。注意: 当类型选择text时，会有两种模式，默认常规模式是以普通文本显示，如果是要以JText格式显示，请选择高级模式

### 可选类型

在一个tile中仅能选择一个可选类型，即text | nbt | selector | score，对应JText中的相应nbt标签，关于显示：选择text显示对应的文本，其他由于无法确定内容，所以对应显示[@ + 类型]

1. text：默认使用当前项，普通的文本模式，使用最普遍

2. nbt：新增解析功能，使用游戏中使用F3 + i复制nbt数据粘贴进行解析，辅助用户填写nbt路径。妈妈再也不用担心我不会nbt路径了~

3. selector

4. score

### 备注

作为当前工程的说明，类似文件名、注释，同时也作为输出面板表格中的一列，用于区分不同的tile，如果不填写取第一个tile中的文字

### 仓库

用于管理暂存的项目，既可以格式化命令（内预制了4种常用的指令），也可以对项目增删改查等

1. 预置命令的使用

   「tellraw」、「sign」、「book」、「title」，勾选列表中的tile然后点击对应的按钮即可获得相应的指令

2. 操作按钮

- 「移动」「整理」对表格中的数据进行调整
- 「编辑」对当前行二次编辑
- 「删除」删除当前行，如果工程使用当前行，工程也会清楚
- 「生成」生成简单的json text字符串
- 「hover」用于hover的高级模式，即以json解析字符串



> 注意，这里输出不会做功能校验，如tile的clickEvent选择的是跳转页码，但是您生成的是告示牌，系统不会产成警告，所以请保证您tile的正确性。

### 快捷键

  - shift + enter 添加一个tile，相当于点击按钮[新增]
  - enter 换行
  - escape 取消选中状态的tile，相当于点击按钮[取消]
  - ctrl + delete 删除选中状态的tile，相当于点击按钮[删除]
  - ctrl + B 加粗，相当于点击按钮[粗体]
  - ctrl + I 斜体，相当于点击按钮[斜体]
  - ctrl + U 下划线，相当于点击按钮[下划线]
  - ctrl + shift + S 删除线，相当于点击按钮[删除线]
  - ctrl + O 模糊，这里暂时用上划线替代，相当于点击按钮[模糊]
  - ctrl + G 生成代码，相当于点击按钮[生成]
  - ctrl + P 打开输出面板，相当于点击按钮[输出]
  - alt + ArrowUp 上一个颜色
  - alt + ArrowDown 下一个颜色
  - alt + ArrowLeft 选中前一个tile
  - alt + ArrowLeft 选中后一个tile
  - ctrl + K 拆分，相当于点击按钮[拆分]
  - ctrl + S 暂存功能，相当与点击按钮「暂存」

## 开发工具与技术

- 技术栈：react + typescript，使用antd UI框架，使用react新特性Hooks
- 编辑器：VS Code

> 如果对你有帮助，不妨支持一下我哦~