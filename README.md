## 前言

现有的Json Text生成器有很多，但总是不那么好用，不论界面设计的多好，但本质交互设计上就不友好。理想的Json Text生成器应该像使用word编辑文稿一样，不过由于技术问题，只能折中实处理，尽量的做到便捷、实用。希望能帮助到热爱MC的你。

当然了，此软件开发还在开发阶段，如果遇到问题，请您第一时间通知我，还有就是也大家能积极参与测试，您提供宝贵的建议和意见我都会仔细看。软件还没有定名字，暂定为[jtext studio](https://haima16.github.io/mc-jtext/)，目标就是打造最好用的mc JSON Text生成器

## 地址
- gitee: http://hans000.gitee.io/jtext-studio/
- github: https://haima16.github.io/mc-jtext/

## 功能特色

- 可视化、实时预览
- 模板化，模块化（工程一键分享，快速导入）
- 丰富的快捷操键操作
- 强大的二次编辑功能，灵活增删改，支持拖拽

> 适用版本: 已mc最新的格式，暂不兼容低版本

## 术语说明

  - JText: Json text, [JSON文本](https://minecraft-zh.gamepedia.com/%E5%91%BD%E4%BB%A4#JSON.E6.96.87.E6.9C.AC)是mc中聊天组件的最小组成
  - tile: 可操作的最小单元，对应mc中的一个JText 
  - tile group: tile的集合，对应mc中的一个Tellraw、book中一页等
  - 文本样式：样式栏内容，包括是否粗体、是否斜体、是否下划线、是否模糊、及字体颜色
  - 工程：当前操作的tile group

> P.S. 只是为方便说明，仅为个人定义

## 交互说明

### 预览

预览可以把用户当前操作呈现出来，实时预览

- 点选操作: 鼠标点击tile即可，点击后会有高亮显示
- 更换背景色: 右下角有个拾色器，可以点击更换颜色

### 操作栏

- 添加: 当你完成一个tile后想要继续添加一个样式不一样的tile时可以点击此按钮
- ~~插入: 选中一个非空tile，在此tile前插入一个新的tile~~
- ~~克隆：当你选中一个非空tile时，可以复制该tile并插入改tile后面，如果没有选中且处于最后时，可以复制所有的tile~~
- 拆分：强大的功能，替代了「插入」「克隆」功能，按回车符将其拆分为多个tile
- 删除: 当你不想要某个tile时，选中一个tile可以将其移除，不可恢复
- 清空: 当你不想要当前这个工程时，可以点击此按钮，所有的tile都会被删除，不可恢复
- 取消: 可以取消tile的高亮
- 生成: 生成一段可用的JText
- 保存: 将当前工程保存，可以在输出面板查看
- 导入: 可以把合法的json文本解析
- 导出: 可以把当前的内容保存为json文本，作为模板
- 输出: 打开输出面板

### 样式

样式共6项，对应JText中的6个字体样式nbt标签

### 点击事件

点击事件分5种，open_url | run_command | change_page | suggest_command | copy_to_clipboard

### 悬浮事件

点击事件分3种 text | block | entity

注意: 当类型选择text时，会有两种模式，默认常规模式是以普通文本显示，如果是要以JText格式显示，请选择高级模式

### 可选类型

在一个tile中仅能选择一个可选类型，即text | nbt | selector | score，对应JText中的相应nbt标签，

关于显示：选择text显示对应的文本，其他由于无法确定内容，所以对应显示[@ + 类型]

### 备注

作为当前工程的说明，类似文件名、注释，同时也作为输出面板表格中的一列，用于区分

### 输出面板

预制了4种常用的指令，tellraw、sign(告示牌)、book(成书)、title，勾选列表中的tile然后点击对应的按钮

> 注意，这里输出不会做功能校验，如tile的clickEvent选择的是跳转页码，但是您生成的是告示牌，系统不会产成警告，所以请保证您tile的正确性。

### 快捷键

  - shift + enter 添加一个tile，相当于点击按钮[新增]
  - enter 换行
  - escape 取消选中状态的tile，相当于点击按钮[取消]
  - ctrl + delete 删除选中状态的tile，相当于点击按钮[删除]
  - ctrl + B 加粗，相当于点击按钮[粗体]
  - ctrl + I 斜体，相当于点击按钮[斜体]
  - ctrl + U 下划线，相当于点击按钮[下划线]
  - ctrl + S 删除线，相当于点击按钮[删除线]
  - ctrl + O 模糊，这里暂时用上划线替代，相当于点击按钮[模糊]
  - ctrl + G 生成代码，相当于点击按钮[生成]
  - ctrl + P 打开输出面板，相当于点击按钮[输出]
  - alt + ArrowUp 上一个颜色
  - alt + ArrowDown 下一个颜色
  - alt + ArrowLeft 选中前一个tile
  - alt + ArrowLeft 选中后一个tile
  - ctrl + K 拆分，相当于点击按钮[拆分]

## 开发工具与技术

- 技术栈：react + typescript，使用antd UI框架，使用react新特性Hooks
- 编辑器：VS Code

> 如果对你有帮助，不妨支持一下我哦~