1.重启系统，在引导默认内核前按shift进入grub菜单，这个窗口期较短，一般过了pxe引导装机开始引导硬盘时，就可以尝试疯狂按，如果触发windows的粘滞键功能，可以使用cmd运行osk将虚拟键盘呼出。将预选光条停留在第二项上（ Advanced options for Ubuntu），按e进入编辑页面。

<img src="images\image-20250106110147672.png" alt="image-20250106110147672" style="zoom: 50%;" />

2.找到linux开头的行，结尾是ro recovery nomodeset dis ucode ldr（演示系统是 ubuntu 22.04）

<img src="images\image-20250106104927184.png" alt="image-20250106104927184" style="zoom: 80%;" />

在本行后面补写 rw init=/bin/bash，效果如下，需要注意图片中结尾/bin/\后面有个反斜线\，这个是因为屏幕显示宽度问题，此处的反斜代表换行，自动补充的，并不需要填写。

<img src="images\image-20250106112023663.png" alt="image-20250106112023663" style="zoom: 80%;" />

补写完成后，按下Ctrl + X保存，将预选停留在第二项，按回车键开始引导

<img src="images\image-20250106112516968.png" alt="image-20250106112516968" style="zoom:80%;" />

引导完成会看到root提示符，可以直接使用passwd命令修改密码，因vnc有时可能出现大小写输入混淆的情况，建议先改个简单的数字密码，修改完成后输入quit，然后点击vnc界面的重启，重启完成即可测试刚刚修改过的密码

<img src="images\image-20250106112924066.png" alt="image-20250106112924066" style="zoom:80%;" />
