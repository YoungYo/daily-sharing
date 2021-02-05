# 6th
在 Linux 命令行中， 可以用 Ctrl-r 快捷键查询历史命令。按下 Ctrl-r，命令行提示符显示：

(reverse-i-search)`':

这时可以输入文本进行搜索，比如输入 ps aux，则会显示出最近一个包含“ps aux”的历史命令：

(reverse-i-search)`ps aux': ps aux | head

如果这个命令不符合你的预期，可以再按 Ctrl-r 向上查找。可以直接按 Enter 键执行命令，或者按 Ctrl-j 将该命令复制到命令行。按 Ctrl-c 或者 Ctrl-g 可以退出查找。

