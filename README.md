# Git Bash环境下vim的基础使用方法
# 前言：
vim由[Bram Moolenaar](https://zh.wikipedia.org/wiki/布萊姆·米勒)于1988年开发并于1991年发布的一款编辑器，此编辑器拥有强大的功能和高效的操作，因此也受到了全球程序员的推崇（也因此vim编辑器的使用对新手来说并不是很习惯）。此文是笔者的学习笔记，写作目的是供自己记忆复习并和各位同学们各位一起交流和学习的。望大家看到有错误或不准确的请提出批评及建议，感谢！



### 一，打开和退出vim以及光标的上下左右
前言中说到此编辑器的操作对新手来说并不习惯，从打开就开始了。
##### 1.在git环境中进入vim并用vim打开文件
![1-1](http://upload-images.jianshu.io/upload_images/8084817-7f162ce23de7d4ef.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![1-2](http://upload-images.jianshu.io/upload_images/8084817-508affbe0250727d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在任意行键入  `vim` （图1-1）并回车即可进入，如要打开文件只需要键入`vim 文件名`（图1-2）回车即可进入.
#### 2.退出和保存退出

进入vim后，我们会进入命令模式（模式将在下一节介绍），如果想退出vim，不用管光标在哪里，只需要键入`:q!`即可退出（此时的文本尚未保存），如果想保存退出只要键入`:qw!`即可保存退出。这些键入的内容会出现在在vim编辑器的左下方。
#### 3.光标的上下左右


![图3-1](http://upload-images.jianshu.io/upload_images/8084817-14f4b52cb52d7193.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


vim是一款可以让你脱离鼠标并高效操作的编辑器，所以它并不推崇使用上下左右方向键进行光标的移动（当然了方向键也是被vim所允许的）。它使用的是 h（左）、j（下）、k（上）、l（右）键就可以了，如图3-1。

### 二，vim的模式及转换
在进入vim后我们所在的模式是正常模式，此外主要还有插入模式 替代模式  可使模式 。
#### 1.正常模式：
这个是我们日常键入命令，浏览文本所使用的模式，任何模式按下 **ESC**键，即可进入正常模式。
#### 2.插入模式：
这个是我们插入修改文本的模式，在正常模式下按下**i**、**a**、**A**等键即可进入插入模式（下面会介绍）。
#### 3.替代模式：
这个是我们进行替换文本的模式，在正常模式下按下**R**键即可进入。
#### 4.可视模式：
这个是我们进行选择文本的模式，在正常模式下按下**v**即可进入，被选中的内容会高亮显示。
### 三，文本的操作
#### 1：文本的插入：
①**i**  在正常模式下按下**i**键即可进入插入模式，可以自由的添加和修改内容。
②**A**  在正常模式下按下**A**键光标会转移到所在行的末尾，并进入插入模式。
③**a** 在正常模式下按下**a**键后，可以进入插入模式进行编辑。
③**q** 在正式模式下按下**q**键会在光标下方插入一行空行，并进入插入模式。
④**Q**同④一样，不过是在光标的上一行插入一行空行。
#### 2：文本的删除：
①**dw**  正常模式下把光标移到想要删除的单词起始处，按下**d**键后按下w即可删除此单词。
②**x**  正常模式下按下**x**键可以删除光标所在位的字符。
③**d$**  正常模式在光标移到某处，按下**d**键后按下**$**键后，会删除光标到行尾，所有的单词。
④**dd**  正常模式下按下两次**d**键后，删除光标所在行的文本。
#### 3：文本操作的撤销：
①**u**  正常模式下按下u键后撤销上步操作。
②**U**  正常模式下 按下U键后，使上步操作的行，回到原始状态。
③**CTRL+R**  正常模式按下CTRL+R可以撤销u和U所撤销的结果，恢复本来的操作。
#### 4：文本的复制粘贴：
①**p**    用dd删除的行会被储存在一个寄存器中，只要按下p键，即可粘贴到光标所在行的上一行。
②**v**  在正常模式下按下v键，会进入可视模式。这样我们可以选中一些内容进行操作，只要动动光标就可以选中。被选中的内容会高亮显示。
③**y**  在②的基础上可以按下y键进行复制，同样的只要光标移到内容想要去的地方了。按下p键就可以粘贴到那里了。
#### 5：文本的更改替换：
①**r**  把光标移到想要替换字符的前方，按下r键，然后就可以替换成正确的字符。
②**R**  把光标移到想要替换字符的前方，按下R键，会进入替换模式替换模式可以进行多字符的替换。
②**ce** 把光标移到想要更改的单词前面按下c键后再按下e键即可删除此单词，并进入插入模式，修改需要修改的内容。
③**:s/被替换/替换/g**  在正常模式下键入此格式，填入被替换和替换的文本光标所在行的匹配串就都可以进行替换了。
④**:s/被替换/替换**  此命令于③相同，不过是它只操作光标所在行的第一个匹配串。
⑤**:#,#s/被替换/替换/g**  这里的#号代表了行数，只要填入首行数和末行数和替代和被替代内容，就可以替换多行所有的匹配串。
⑥**:#,#s/被替换/替换/gc** 此命令与⑤相同，不过在替代前会询问是否进行替代。
#### 6：光标的快速移动和查找：
①**gg**  在正常模式下，只要按下gg键，光标即可跳到文件的第一行。
②**G**    同样的按下G键后光标会出现在文件最后一行。
③**#G**  这里的#代表了行数，在正常模式下按下组合键GTRL+G，就可以在vim的左下角看到光标所在行的行数，然后无论在文件的那个位置，只要输入行数，然后按下大写G键，就可以让光标转移到文本的指定行数。
④**/内容**  在正常模式下键入/和需要查询的内容即可查到您想要找到内容，然后你可以按下n键寻找下一个匹配串或者按下N键反向寻找匹配的字符串。
⑤**？内容**     在正常模式下键入/和需要查询的内容即可查到您想要找到当前编辑内容相反方向的匹配串。
⑥**%**  此命令是让你找到配对的括号的，把光标移到想要找配对的(、[ 或 { 处，按下%就可以找到想排队的括号了。
#### 7：截取和提取合并文件
①**：w 文件名**  之前说了按下**v**键进入可视模式后移动光标即可选中内容，这时我们键入```:w 文件名```按下回车即可截取并保存了。
②**：r 文件名** 如果想要引入并合并文本，只要把光标移到想要引入的地方键入```:r 文件名```即可引入我们的之前截取的内容了。
#### 8：在vim内部执行外部命令：
①**:! 命令**vim内部可以执行外部命令，只需要键入```:!  命令```即可执行，比如```:! ls```;即可查看我们当前目录下的内容。
#### 9：vim的设置命令：
①***:set  ic***  可在正常模式下键入```:set ic```，即可设置***/***的搜索结果忽略大小写。（如要关闭键入```:set noic```即可，如果尽在一次搜索中忽略大小写 键入```\c： /ignore\c```并回车即可 ）
②***:set hls is*** 同样的键入```:set hls is```，即可设置搜索结果高亮。（如要关闭键入```:nohlsearch```即可）
## 结语：
这是我第一次写博客，写的很不好，正如vim的官方文档所说的那样要在使用中学习，在之后的日子随着使用的深入还是会更新改正的，也希望在以后的学习中不断的进步。
