# 实验报告链接

## 1.1-1.5
[![asciicast](https://asciinema.org/a/zZug1KG8gPwisXLe9mUFzfU8C.svg)](https://asciinema.org/a/zZug1KG8gPwisXLe9mUFzfU8C)

## 1.6
[![asciicast](https://asciinema.org/a/lP4DkEVt4jkzCaa3d2kQzKKbi.svg)](https://asciinema.org/a/lP4DkEVt4jkzCaa3d2kQzKKbi)

## 2.1-2.7
[![asciicast](https://asciinema.org/a/K29LkK7S4S2IQI5YKUUGffo2b.svg)](https://asciinema.org/a/K29LkK7S4S2IQI5YKUUGffo2b)

# 3.1-3.4
[![asciicast](https://asciinema.org/a/8WXxubIBcEpesCJgOf3YlTzQD.svg)](https://asciinema.org/a/8WXxubIBcEpesCJgOf3YlTzQD)

## 4.1-4.4
[![asciicast](https://asciinema.org/a/Pq5qzaTZtgbKBFCCl6kZSoaTb.svg)](https://asciinema.org/a/Pq5qzaTZtgbKBFCCl6kZSoaTb)

## 5.1-5.4
[![asciicast](https://asciinema.org/a/NoOv5GGkhJc1DN8LGCLAAk6yu.svg)](https://asciinema.org/a/NoOv5GGkhJc1DN8LGCLAAk6yu)

## 6.1-6.5
[![asciicast](https://asciinema.org/a/ghsekYZN3N016ybcIGrj93qRI.svg)](https://asciinema.org/a/ghsekYZN3N016ybcIGrj93qRI)

## 7.1-7.3
[![asciicast](https://asciinema.org/a/3SBAhXejhS0PpqRzOjxJpOcgj.svg)](https://asciinema.org/a/3SBAhXejhS0PpqRzOjxJpOcgj)

## vimtutor完成后的自查清单


1. 
- insert 插入模式
- visual 可视模式
- normal 普通模式
- cmd-line 命令行模式

2. 
|目标操作|方法|
|--|--|
|从当前行开始，一次向下移动光标10行|10j|
|快速移动到文件开始行|gg|
|快速移动到文件结束行|G|
|快速跳转到文件中的第N行|:N|

3. 
|目标操作|方法|
|--|--|
|删除单个字符|dl或x|
|删除单个单词|dw|
|从当前光标位置一直删除到行尾|d$|
|从当前光标位置删除单行|dd|
|从当前行开始删除下面N行|Ndd|

4. 
  No或者NO能够快速插入N个空行，但是需要按下esc之后才能生效
  普通模式下输入'80i-'然后'ESC' 


5. 
  撤销最近一次编辑操作：在normal模式下按u；

  重做最近一次被撤销的操作：键入: CTRL-R


6. 
  剪切粘贴单个字符: 在想要剪切的字符前使用'x'，在想要粘贴的字符前'p'

  单个单词: 在想要剪切的单词前使用'dw'，在想要粘贴的单词前'p'

  单行: 'dd'然后'p'

  实现相似的复制粘贴操作：按v进入可视模式visual mode，移动光标选择需要复制的内容，按y复制文本，移动光标至指定位置，然后按下p粘贴文本


7. 
  插入文本类命令：
    i: 在光标前
    I: 在当前行首
    a: 光标后
    A: 在当前行尾
    o: 在当前行之下新开一行
    O: 在当前行之上新开一行

  删除文本类命令：
    do: 删至行首
    d$: 删至行尾
    ndd: 删除当前行及其后n-1行
    x或X: 删除一个字符，x删除光标后的，而X删除光标前的

  复制粘贴文本类命令：
    v,y,p的组合操作

  撤销与重做:
    u：撤销最近一次操作
    CTRL-R：重做最后一次被撤销的操作

  保存更改：
    :w ：保存刚才的更改

  退出vim：
    :q! :退出当前文件并放弃一切修改
    :wq!:退出当前文件并保存一切修改


8. 
  用 :f 可以看文件名，用 :!pwd  可以看当前的详细路径。

  显示行号：: set nu  取消显示行号：: set nonu


9. 
  关键词搜索：/想要查找的关键词，然后按下回车

  忽略大小写：set ic

  将匹配结果高亮显示: set hls is

  匹配到的关键词进行批量替换:
    全局替换：'%s/old/new/g'
    对指定行数（m-n）进行替换：:m,ns/old/new/g



10. 
  Normal 模式下执行 CTRL-O 和 CTRL-I


11. 
  先将光标定位到任一的(,[,{ ，键入 % 以找到所匹配的),],}


12. 
   :! 并加上要执行的外部命令。


13. 
  :help[快捷键名] + enter

  在不同的分屏窗口移动光标，通过  :set mouse=a
  开启vim鼠标支持模式，然后就可以移动光标了 