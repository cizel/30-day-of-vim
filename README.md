# 15-day-of-vim


在这 15 天里，每天使用一个番茄钟 (25 分钟）的时间阅读《Practical Vim》并实践练习 Vim 的一些技巧。

## Day 1

> 时间：2020.03.19 | 阅读完成《Practical Vim》第一章 VIM 的解决问题的方式

其中一个重要的原则：不要重复自己（Don't Repeat Yourself）

- 用 Dot(.) 来重复上一次执行的命令
- 常用的组合插入方式 (`C`, `s`, `S`, `I`, `A`, `o`, `O`) 分别代表 （`c$`, `cl`, `^C`, `^i`, `$a`, `A<CR>`, `ko`）
- 常用动作已经回退方式 `({edit} . u)`, `(f{char}/t{char} ; ,)`, `(/pattern<CR> n N)`, `(qx{changes}q @x u)`

## Day 2

> 时间：2020.03.20 | 阅读完成 《Practical Vim》第一部分 模式 - 普通模式

其中的一些原则：

- 构造可重复的修改，构建删除一个单词使用 `daw` 更加优秀，可以使用到 `.` 重复删除单词
- 能够重复，就不要用次数。 `dw.` 比 `2dw` 更加方便撤回
- 操作符 + 动作指令 = 操作 （常见操作符：`c`, `d`, `y`, `g~`, `gu`, `gU`, `>`, `<`, `=`, `!`)

## Day 3

> 时间：2020.03.21 | 阅读完成 《Practical Vim》第一部分 模式 - 插入模式

插入模式的技巧：

- 插入模式回到普通模式的方式 (`ESC`, `<C-[>`, `<C-o>`),
- `<C-o>` 是插入 - 普通模式，处于这个模式可以执行一次普通模式命令就会自动切换回插入模式（例如：`<C-o>zz`)
- 使用寄存器方式在插入模式粘贴内容：`<C-r>{register}` （例如：<C-r>0)
- 使用`R`, `r` 进入替换模式，`R` 替换多个，`r` 替换单个

## Day 4

> 时间：2020.03.22 | 阅读完成 《Practical Vim》第一部分 模式 - 可视模式

可视模式的技巧：

- 激活可视模式的快捷键 (`v`, `V`, `<C-v>`, `gv`), (`字符可视模式`, `行的可视模式`, `块的可视模式`, `重选高亮区域`)
- `gv` 命令，重选高亮区域，推荐多尝试
- `o` 用于切换选择范围的活动端
- 块的可视模式下，`r` 可以用来替换快字符，`$` 可以切换当行位插入

## Day 5

> 时间：2020.03.23 | 阅读完成 《Practical Vim》第一部分 模式 - 命令模式

命令模式的技巧：

- 常用的 ex 命令 (`[range] normal {command}`, `[range]substitute/{pattern}/{string}/flag`, `[range]gobal/{pattern}/[cmd]`) 分别代表 (`normal 模式执行命令`, `替换替换`，`匹配内容执行命令`)
- range 范围选择可以是 `1, 2`, `1, +1`, `'<,'>`
- 使用 `shell` 进入 shell 模式
- 使用 `!` 执行 shell 命令
- 使用 `read !{cmd}` 输入到当前 buffer
- 使用 `[range]write !{cmd}` 使用指定行，作为 {cmd} 的参数

## Day 6

> 时间：2020.03.24 | 阅读完成 《Practical Vim》第二部分 文件

文件的一些操作：

- `:edit` 编辑打开 `文件`, `文件夹`
-  工作区分屏的快捷键 `<C-w>s`, `<C-w>v`, `sp[lit] {file}`, `vsp[lit] {file}`
- `:tabe{dit} {filename}`, `tabn[ext]`, `tabp[revious]`

## Day 7

> 时间：2020.03.25 | 阅读完成 《Practical Vim》第三部分 更快的移动及跳转 - 用动作命令在文档中移动 1

移动的一些技巧：

- 使用 `h`, `l` 向前向后移动需不超过 2 次，`h`, `l` 只解决差异的错误
- 屏幕行的移动 `gj`, `gk`, `g0`, `g^`, `g$`
- 基于单词的一些移动方式 (`w`, `b`, `e`, `ge`), (`移动下一个单词开头`，`反向移动到当前单词 / 上一单词的开头`, `正向移动到当前单词 / 下一单词的结尾`, `反向移动到上一单词的结尾`)
- 对字符进行查找 - 正向移动到下一个 {char} 所在之处 `f{char}`, `F{char}`, 继续搜索 `;`, 向前搜索 `,`
- 对字符进行查找 - 正向移动到下一个 {char} 所在之处的前一个字符上 `t{char}`, `T{char}`, 继续搜索 `;`, 向前搜索 `,`


## Day 8

> 时间：2020.03.26 | 阅读完成 《Practical Vim》第三部分 更快的移动及跳转 - 用动作命令在文档中移动 2

移动的一些技巧：

- 查找移动 `/{word}<CR>`, 通过 `n` 查找下一个， `N` 查找上一个
- `a` 匹配带上分隔符，`i` 匹配不带分隔符
- `a`,`i` 可以匹配的内容：`)`, `}`, `]`, `>`, `'`, `"`, `t`, 其中 `t` 匹配 <xml> 标签
- `iw`, `aw`, `iW`, `aW`, `is`, `as`, `ip`, `ap` 其中`a` 开头会带上后面的一个空格
- `%` 匹配 `()`, `{}`, `[]` 来跳转
- `` 跳转到上传编辑的位置

## Day 9

> 时间：2020.03.27 | 阅读完成 《Practical Vim》第三部分 更快的移动及跳转 - 在文件间跳转

跳转的一些技巧：

- `<C-o>`,`<C-i>` 跳转前一次的位置，跳转到下一次的位置
- `gf` 跳转到光标处的文件


## Day 10

> 时间：2020.03.28 | 阅读完成 《Practical Vim》第四部分 寄存器 - 复制和粘贴

复制和粘贴的一些技巧：

- `xp` 可以用来交换二个字符的位置，`xp` 可以用来交换两行的位置
- 默认复制，删除等会复写 无名寄存器 `""`, 如果要保持其他复制内容可以使用 `"` + `a-z` 寄存器
- 如果是是复制的内容可以使用 复制的专用寄存器 `"0` 来避免被无名寄存器 `""` 被覆盖
- 常用的替换已个单词的方法 (`yiw`, `jww`, `ve`, `p`)

## Day 11

> 时间：2020.03.29 | 阅读完成 《Practical Vim》第四部分 寄存器 - 宏

使用宏的一些技巧：

- 使用 `q{register}` 的方式来开启宏，使用 `q` 来结束宏的录制
- 宏的使用 `@{register}`, 比如：使用 `qa` 开启宏，之后可以使用 `@a` 来执行宏的内容
- 串行执行宏 `3@a`, 并行执行宏 (`jVG`, `:'<,'>normal @a`) 核心是使用视图模式选取，兼容性更好
- 给宏追加命令 `qA`, 使用大写字母来追加宏

## Day 12

> 时间：2020.03.30 | 阅读完成 《Practical Vim》第五部分 模式 - 按模式匹配及按原意匹配

匹配模式的一些技巧：

- `/\v` 开启 very magic 模式，搜索正则更加方便
- `/\V` 关闭正则匹配
- `()` 圆括号可以匹配子串，并使用数字 `\{1-9}` 进行重复匹配串
- 正向查找要转义 `/` 字符，反向查找要转义 `?` 字符

## Day 13

> 时间：2020.03.31 | 阅读完成 《Practical Vim》第五部分 模式 - 查找

查找的一些技巧：

- `/<CR>` 正向搜索，`?<CR>` 反向搜索
- `/{word}/e<CR>` 将光标移动到查找内容的结尾
- `//e` 可以移动到下一个匹配的结尾
- `*` 可以搜索光标下的内容
