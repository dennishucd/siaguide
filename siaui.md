# Sia-UI使用指南

**如何修改Sia区块存放的目录？**<br>

**说明：** 本文分享了一种可以修改sia区块存储位置的方法。该方法不是直接修改配置文件，而是采用目录链接的方式。
直接修改配置文件的方式我试了，测试失败，可能修改得不对，后面如果知道怎么改了。再分享给大家。<br>


**第一步：先找到当前存放的位置**<br>
Sia-UI程序界面点击左下方的"About"，然后点击"Show Sia Data"即可进入Sia的配置目录。例如我的目录为：C:\Users\dennis\AppData\Roaming\Sia-UI。该目录下有一个config.JSON的文件，打开后找到datadir这个变量的值，如我的为： "datadir":"C:\Users\dennis\AppData\Roaming\Sia-UI\sia"<br>

**第二步：关闭Sia-UI程序**<br>
注意：一定要完整的退出程序。关闭窗口，默认情况下Sia-UI会最小化到状态栏的托盘上，此时Sia-UI并未退出。如果此步骤未做好，可能导致程序崩溃，注意先备份好钱包。<br>

**第三步：拷贝sia目录**<br>
将datadir指向的sia目录拷贝到你打算移动到的新位置。然后同时将原位置的sia文件夹名字改为sia-backup。<br>
注意：拷贝结束后，最好不要删除原目录，如果失败了可以将名字改回来然后直接恢复。<br>

**第四步：创建新目录的符号连接**<br>
命令格式：'mklink /J "C:\old sia path" "D:\new location"'
比如，我的新位置为：G:\blockchain\Sia-UI-v1.3.2-win32-x64\sia，老位置为：C:\Users\dennis\AppData\Roaming\Sia-UI\sia。那么打开命令行cmd，执行命令：
C:\Users\dennis>mklink /J "C:\Users\dennis\AppData\Roaming\Sia-UI\sia" "G:\blockchain\Sia-UI-v1.3.2-win32-x64\sia"<br>
为 C:\Users\dennis\AppData\Roaming\Sia-UI\sia <<===>> G:\blockchain\Sia-UI-v1.3.2-win32-x64\sia 创建的联接<br>
C:\Users\dennis><br>

**第五步：重新开启Sia-UI**<br>
如果一切如常的话，恭喜你已经成功将sia的区块存储目录修改到了新位置。<br>
确保一切都好之后，可以将原位置的sia-backup目录删除。<br>


**参考资料：** <br>
[1] https://www.reddit.com/r/siacoin/comments/6zsb5k/how_do_i_change_the_location_of_where_sia_ui/<br>

