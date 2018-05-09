# SublimeTextSync
Sublime Text的所有插件和配置备份


# Sublime Text配置

## 直接同步插件和配置信息

 - `Windows`: `%APPDATA%Sublime Text 3`
 - `Linux`: `~/.config/sublime-text-3`
 - `OS X`: `~/Library/Application Support/Sublime Text 3`

如果没有找到这些目录, 那么可以打开以下`Sublime Text 3`, 或者手动创建

进入到这些目录下的`Packages`, 使用`Git`工具, 

 - `Windows`上使用[Git](https://git-scm.com/)客户端(打开链接, 下载对应系统`32`或者`64`的安装包, 安装后在`Packages`目录下右键打开`Git Bash`, `Git`的安装网上有很多教程, 这里就不一一赘述了.)
 - `Debian/Ubuntu`: `sudo apt update && sudo apt install git -y`
 - `Fedora/CentOS`: `sudo yum install git -y`

克隆插件和配置信息到`Packages/User`, `git clone https://github.com/zZhaoLei/SublimeTextSync.git User`.

`https://github.com/zZhaoLei/SublimeTextSync.git`是我自己的配置.

克隆之后, 还要在`Sublime`中安装`Package Control`, 这样相关的插件才会自动安装.

 - 安装Package Control

使用` Ctrl + ~ `快捷键或者通过`View-->Show Console`菜单打开命令行, 按`Esc`取消显示窗口, 

 - `Sublime Text 3`粘贴如下代码:

```
import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```

 - `Sublime Text 2`粘贴如下代码:

```
import urllib2,os; pf='Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler( ))); open( os.path.join( ipp, pf), 'wb' ).write( urllib2.urlopen( 'http://sublime.wbond.net/' +pf.replace( ' ','%20' )).read()); print( 'Please restart Sublime Text to finish installation')
```

### 同步自己的插件和配置

在[GitHub](https://github.com/)注册自己的账号(如果已有, 登陆账号), 新建一个仓库.

在`Packages/User`下执行`git init`, 创建`.gitignore`文件, 向其中添加:
```
Package Control.last-run
Package Control.ca-list
Package Control.ca-bundle
Package Control.system-ca-bundle
Package Control.cache/
Package Control.ca-certs/
```

千万不要把`Packages Control.sublime-settings`给添加进去, 这个文件中存放的是需要安装的插件.

然后执行
```
git add -A
git commit -m "备份Sublime插件和配置"
git remote add origin [your git repo]
git push origin master
```

这样, 在别的电脑上时, 只需要进入`Packages`目录, 然后执行`git clone https://github.com/zZhaoLei/SublimeTextSync.git User`, 并且在`Sublime`中安装`Package Control`就可以了.


可能需要修改`Preferences-->Settings`中的`font_face`字段的值为自己的字体, 这个可能不一致.

## Windows安装Sublime Text

在[Sublime Text](https://www.sublimetext.com/)官网下载软件包, 默认是下载的`Sublime Text 3`.

下载完成后双击安装, 在安装时记得勾选`Add to explorer context menu`(加入资源管理器上下文菜单), 这样对一个文件右键的时候, 会显示`Open To Sublime Text 3`, 通过`Sublime Text 3`打开.


## Sublime Text 配置

 - 修改Sublime Text字体和大小

在`Windows`上`Sublime`的中文和英文是上下错乱的, 这是因为对中文字体的支持不太好. 

可以使用`Microsoft YaHei Mono`, 这个字体, 是由`Microsoft YaHei`和`Consolas`组合设计的.

在网上寻找`Microsoft YaHei Mono`的字体包, 一般是`.ttf`结尾的, 将其拷贝到`c:\Windows\Fonts`目录下就是安装.

点击工具栏的`Preferences-->Settings`, 在新窗口的右侧`{}`里追加(记得在每行结尾处加逗号`,`, 应为状态下的字符):

 - Windows

  ```
     "font_face": "Microsoft YaHei Mono",
  ```

 - Linux

  ```
    "font_face": "Dejavu Sans Mono",
  ```

```
    # 字体大小
    "font_size": 16,

    # 将tab键转为4个空格
    "tab_size": 4,
    "translate_tabs_to_spaces": true,

    # 高亮当前行
    "highlight_line": true,

    # 启用vim
    "ignored_packages":
    [
    
    ],
    # 启用`Ctrl`功能键及自定义功能键
    "vintage_ctrl_keys": true,
    # 启动sublime就进入命令模式
    # "vintage_start_in_command_mode": true,

    # 配置主题
    "color_scheme": "Packages/Color Scheme - Default/Mariana.sublime-color-scheme",
    # 配置窗口主题
    "theme": "Adaptive.sublime-theme",

    # 保存文件时自动在末尾添加空行
    "ensure_newline_at_eof_on_save": true,

    # 默认使用Unix换行符
    "default_line_ending": "unix",

```

# 安装Package Control

使用` Ctrl + ~ `快捷键或者通过`View-->Show Console`菜单打开命令行, 按`Esc`取消显示窗口, 

 - `Sublime Text 3`粘贴如下代码:

```
import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```

 - `Sublime Text 2`粘贴如下代码:

```
import urllib2,os; pf='Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler( ))); open( os.path.join( ipp, pf), 'wb' ).write( urllib2.urlopen( 'http://sublime.wbond.net/' +pf.replace( ' ','%20' )).read()); print( 'Please restart Sublime Text to finish installation')
```

## 安装插件

点击`Preferences-->Package Control-->Package Control: Install Package`, 在弹出窗口里搜索想要安装的插件, 选择想要安装的具体插件, 就会自动的在后台安装. 如果已经安装过了就找不到了, 可以下`Package Control: list Package`中查看. 使用`Esc`关闭搜索窗口.

 - `markdown`
   
    编辑`MarkDown`, 编辑和预览. 

    需要插件: `MarkDownEditing`, `Markdown Preview`(`手动在浏览器刷新预览`)或者`OmniMarkupPreviewer`(实时在浏览器预览), `OmniMarkupPreviewer`可能会安装失败, 多试几次就行了, 网络原因.

    如果安装`MarkDownEditing`后, 打开`.md`文件报错如`error: Error loading syntax file "Packages/MarkdownEditing/Markdown.tmLanguage": Unable to open Packages/MarkdownEditing/Markdown.tmLanguage`, 以及类似的错误信息, 可以尝试使用`ctrl+shift+p`, 在命令界面输入`Set Syntax: Markdown`, 选择并确定. 或者输入`Set Syntax: MultiMarkdown`, 选择并确定.

     - `Markdown Preview`配置快捷键

        通过浏览器预览, 在浏览器端需要手动刷新
        ```
          { "keys": ["alt+m"], "command": "markdown_preview", "args": { "target": "browser"} }, 
        ```

     - `OmniMarkupPreviewer`实时在浏览器预览

        快捷键:
        ```
        Ctrl+Alt+O: 在浏览器中预览标记.
        Ctrl+Alt+X: 将标记导出为HTML.
        Ctrl+Alt+C: 将标记复制为HTML.
        ```

     - `MarkDownEditing`配置

        将`Perferences-->Package Settings-->MarkDown Editing-->MarkDown GFM Settings - Default`中的全部内容, 复制粘贴到`Perferences-->Package Settings-->MarkDown Editing-->MarkDown GFM Settings - User`中,

        修改`Perferences-->Package Settings-->MarkDown Editing-->MarkDown GFM Settings - User`中的`"color_scheme": `字段的值为`"Packages/Color Scheme - Default/Mariana.sublime-color-scheme"`

        修改`"line_numbers"`为`true`, 显示行号.
        
        修改`"highlight_line"`为`true`, 高亮当前行.

        修改`"draw_centered"`值, 设置为`flase`, 两边不留白.

        `wrap_width`是每行的长度, 默认是`80`, 可以根据自己的屏幕宽度适当调整.

        `extensions`是配置生效的文件后缀.

        如果没有立即生效, 重启`Sublime`.

 - `Terminal`

    需要插件: `Terminal`.

     - 配置:

        在`Perferences-->Package Settings-->Terminal-->Settings - User`

        如果需要自定义路径那么配置以下内容, 如果使用默认的配置, 那么不进行修改.

         - Cmd on Windows

            ```
            {
              // window下终端路径
              "terminal": "C:\\Windows\\System32\\cmd.exe",
              //  window下终端参数
              "parameters": ["/START", "%CWD%"]
            }
            ```

         - xterm on GNU/Linux

            ```
            {
              "terminal": "xterm"
            }
            ```

         - iTerm on OS X

            ```
            {
              "terminal": "iTerm.sh"
            }
            ```

     - 配置快捷键:

         - `ctrl+shift+t`打开文件所在文件夹
         - `ctrl+shift+alt+t`打开文件所在项目的根目录文件夹

         - 默认的配置
            ```
            [
                { "keys": ["ctrl+shift+t"], "command": "open_terminal" },
                { "keys": ["ctrl+shift+alt+t"], "run_existing_window_commandd": "open_terminal_project_folder" }
            ]
            ```

         - 自定义配置

            ```
            { "keys": ["ctrl+shift+t"], "command": "open_terminal_project_folder", "args": { "parameters": ["-T", "Working in directory %CWD%"] } }, { "keys": ["ctrl+alt+t"], "command": "open_terminal", "args": { "parameters": ["-T", "Working in directory %CWD%"] } }
            ```

 - `SublimeREPL`

    需要插件: `SublimeREPL`.

     - 键位绑定

        可以通过`Tools-->SublimeREPL-->Python`这样的方式进入`Python shell`, 但是这样比较麻烦.

        打开`Preferences->Key Bindings-User`, 复制一下代码:
        ```
          { "keys": ["f1"], "caption": "SublimeREPL: Python", "command": "run_existing_window_command", "args": { "id": "repl_python", "file": "config/Python/Main.sublime-menu"} },
        ```

        如果还想编译下py代码, 可以复制以下代码:
        ```
          { "keys": ["f5"], "caption": "SublimeREPL: Python - RUN current file", "command": "run_existing_window_command", "args": { "id": "repl_python_run", "file": "config/Python/Main.sublime-menu"} },
        ```

 - `SideBarEnhancements`

    `SideBarEnhancements`扩展了侧边栏中菜单选项的数量, 例如`Sublime Text 3`的右键有`Delete file`, 这个是彻底删除文件. 但是这个插件实现的`Delete`是把文件移动到回收站.

 - `A File Icon`

    `A File Icon`是侧边栏的文件和文件夹的图标主题.

 - `Anaconda`

    `Anaconda`是一个终极`Python`插件. 它为`Sublime Text 3`增添了多项`IDE`类似的功能, 例如:

     - `Autocompletion`自动完成, 该选项默认开启, 同时提供多种配置选项.

     - `Code linting`使用支持`pep8`标准的`PyLint`或者`PyFlakes`.

     - `McCabe code complexity checker`让你可以在特定的文件中使用[McCabe complexity checker](https://en.wikipedia.org/wiki/Cyclomatic_complexity). 如果你对软件复杂度检查工具不太熟悉的话, 请点击`McCabe complexity checker`链接.

     - `Goto Definitions`能够在你的整个工程中查找并且显示任意一个变量, 函数, 或者类的定义.
    
     - `Find Usage`能够快速的查找某个变量, 函数或者类在某个特定文件中的什么地方被使用了.
    
     - `Show Documentation`能够显示一个函数或者类的说明性字符串(当然, 是在定义了字符串的情况下).
  
 - `requirementstxt`

    `requirementstxt`可以为`requirements.txt`文件提供自动补全, 语法高亮以及版本管理功能.

 - `SublimeLinter`

    `SublimeLinter`是`Sublime Text 3`的一个代码静态检查工具框架(`linter`). 这个插件本身来说并不包含任何的一个`linter`, 但是你可以通过在`Package Control`中输入`SublimeLinter-[linter_name]`的方式来安装一个`linter`. 

    对于`Python`的代码静态检查器, 建议使用`SublimeLinter-pyflakes`和`SublimeLinter-pep8`.

     - `linter`个性化

    `Preferences-->Package Settings-->SublimeLinter-->Settings`. 例如忽略`pep8`中的错误和警告:
    ```
      "pep8": {
          "@disable": false,
          "args": [],
          "excludes": [],
          "ignore": "E501,C0301,W0142,W0402,R0201,E1101,E1102,C0103,R0901,R0903,R0904,C1001,W0223,W0232,W0201,E1103,R0801,C0111",
          "max-line-length": 100,
          "select": ""
      },
    ```

 - Git

    `Git`, 快捷键`Ctrl+Shift+P`, 输入`Git`命令, 在下拉框中选择即可.

    特别的, 输入`git diff`, 还可以比较文件差异.

 - GitGutter

    `GitGutter`让`Sublime Text 3`能在左边栏的位置显示一个小图标, 用以表示在最后一次提交以后, 代码是否有追加, 修改或者删除.

 - Modific

    `Modific`, 标记代码的改变, 支持`git`和`svn`. 会在`Sublime Text`的左边栏显示各种颜色的状态.

    除了高亮变化, 还可以通过按`Ctrl+Alt+D`来查看或比较当前的代码与最近提交的代码之间的区别.

    还原修改`Ctrl+Alt+R`, 如果光标停留在修改的行上(或在一组线上, 则整个组将被还原), 此命令将还原修改.

    切换突出显示开/关`Ctl+Shift+h`, `Ctrl+Shift+l`.

    含义:

     - `绿色`: `添加的代码`
     - `红色`: `删除的代码`
     - `橙色`: `修改的代码`

 - FTPSync

   `FTPSync`能够将你的项目和远程文件进行同步.

   只需要打开文件便可以下载更新(如果你的远端文件比本地更加新的话), 而且如果对本地文件做出了修改可以立即同步到远程服务器, 这是非常棒的同步本地文件和远程文件的方法.

   添加远程服务器:
   `Preferences-->Package Settings-->FTPSync`. `Settings - User`是全局的配置. `Setup FTPSync in this folder`是对当前目录, 会在当前目录下生成一个`ftpsync.settings`文件, 里面是连接配置.

   ```
   {
       "default": {
            "host": "ftp.example.com",
            "username": "your_login",  // or null for anonymous login
            "password": "your_password",
            "path": "/",
            "upload_on_save": true, // set *false* if you do not want to upload on save!
            "port": 21,
            "timeout": 30, // [seconds]
        }
    }
   ```

 - Block Cursor Everywhere

    `Block Cursor Everywhere`, 将`Vim`模式下的光标, 由下划线改为方块.

