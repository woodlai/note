# vim

## Command Mode（命令模式）

用户刚刚启动 vim，便进入了命令模式

- `i`: 切换到输入模式，在光标当前位置开始输入文本。
- `a`: 进入插入模式，在光标下一个位置开始输入文本。
- `o`: 在当前行的下方插入一个新行，并进入插入模式。
- `O`: 在当前行的上方插入一个新行，并进入插入模式。
- `dd`: 剪切当前行。
- `yy`: 复制当前行。
- `p`（小写）: 粘贴剪贴板内容到光标下方。
- `P`（大写）: 粘贴剪贴板内容到光标上方。
- `x`: 删除当前光标所在处的字符。
- `u`: 撤销上一次操作。
- `Ctrl + r`: 重做上一次撤销的操作。
- `:`: 切换到底线命令模式，以在最底一行输入命令。

## Insert Mode（输入模式）

在命令模式下按下 i 就进入了输入模式，使用 Esc 键可以返回到普通模式
在输入模式中，可以使用以下按键

- `字符按键以及 Shift 组合`: 输入字符
- `ENTER`: 回车键，换行
- `BACK SPACE`: 退格键，删除光标前一个字符
- `DEL`: 删除键，删除光标后一个字符
- `方向键`: 在文本中移动光标
- `HOME/END`: 移动光标到行首/行尾
- `Page Up/Page Down`: 上/下翻页
- `Insert`: 切换光标为输入/替换模式，光标将变成竖线/下划线
- `ESC`: 退出输入模式，切换到命令模式

## Command-Line Mode（命令行模式）

在命令模式下按下 :（英文冒号）就进入了底线命令模式

- `:w`：保存文件
- `:q`：退出 Vim 编辑器
- `:wq`：保存文件并退出 Vim 编辑器
- `:q!`：强制退出 Vim 编辑器，不保存修改
