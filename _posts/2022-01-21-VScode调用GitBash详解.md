# VScode调用GitBash教程~[2022.1.21]~
最近学习了如何使用Git管理个人代码和笔记，也试着使用了几天Git，感觉使用Git来管理代码和笔记真的很是方便，

好处也显而易见，不用太过担心代码丢失，也不用随时随地带个U盘，只要有网就能对自己的代码和笔记进行访问和管

理。但这几天对Git的使用，也是有一点点的小问题，因为个人习惯使用VScode来进行代码编写和写笔记，而在使用

Git进行管理时，我更喜欢使用指令来进行操作，虽然VScode本身自带一个源代码管理工具可以很方便的使用Git进行

管理，但使用指令来进行管理，我更能清晰的知道我做过什么，做了之后是个什么情况也会在指令输入之后有信息提

示，因此每次在写好代码或笔记时就要在VScode和Git Bash之间进行窗口切换，这让我的效率低了一个档次，我就

在想，VScode自带一个终端管理工具，那我能不能在VScode的终端管理工具中调用Git的终端Git Bash呢。说做就做，

通过在网上搜索查阅，成功的实现了在VScode上使用Git Bash。

## 配置过程
> 此次配置过程学习于[CSDN](https://www.csdn.net/)的博主“向宇it”的一篇文章[vscode添加gitbash终端（最新）](https://blog.csdn.net/qq_36303853/article/details/104067540)
1. 打开VScode，点击左下角齿轮选择设置

    ![选项管理](024.png)

2. 在打开的设置界面上面的搜索设置中输入`shell windows`,选择下图中的`在settings.json中编辑`

    ![设置界面](025.png)

3. 将默认生成的`"terminal.integrated.automationShell.windows": "",`删掉

    ![默认生成的语句](026.png)

4. 在`settings.json`空白处加入下列内容
```json
// 添加Git Bash到vscode终端选项里
"terminal.integrated.profiles.windows": 
{
    "GitBash":  // GitBash为自定义的终端名，不能有空格
    {
        "path": "E:\\Git\\bin\\bash.exe", // 这里是的的bash路径
    }
},
```
> 如果想要将Git Bash设置为默认终端，也可以在`settings.json`加入下列内容
```json
"terminal.integrated.defaultProfile.windows": "GitBash"
```
- 内容效果如下

    ![settings.json](027.png)

5. 加入内容之后保存并重启VScode就可以在VScode的终端选项卡中看到Git Bash了

    ![终端选项卡](028.png)

6. 选择GitBash之后的界面如下

    ![GitBash](029.png)

> 如果还不知道Git的用法可以到我的另一篇笔记[git学习笔记](../study/git学习笔记.md)中试着学习一下

