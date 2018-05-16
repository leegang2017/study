自己用过很多的IDE或者文本编辑器，eclipse, itellij(webstorm, android studio), sublime text,不过现在最喜欢用vscode
先说下优点
1) 启动速度快，运行速度快，比eclipse, intellij快，和sublime text差不多
2) 占用内存小，这个真心重要，我电脑是16G内存，不过要开发后台，也要开发前端，所以会开很多IDE，网页也会打开很多，以前用webstorm的时候，内存经常用完，自从换成vscode以后，好了很多
3) 自带debug，这么小巧，快速的软件，像真正的IDE一样，可以debug, so cool
4) 智能提示，庞大的插件库,很多功能都可以通过插件实现，比如编辑和预览markdown的插件Markdown all in one
缺点就是不像webstorm那个智能（好象要求有点高）

下面说下个人觉得比较好的入门方法，
 打开vscode, help -> Interactive Playground，可以在里面边学，边测试

常用快捷健tips
  - 多行选择编辑可以通过下面方法
        Shift+Alt和鼠标
        Shift+Alt+UpArrow加上上一行
        Shift+Alt+DownArrow加上下一行
        先选择一个单词，然后Ctrl+Shift+L选择所有相同的单词
  - 智能提示
    默认要ctrl+space,可以修改为其它，比如'ctrl+;'
  - 行操作
    Ctrl+Shift+Alt+DownArrow 或 Ctrl+Shift+Alt+UpArrow可以向上或者向下插入一行和当前行一样的数据
    Alt+UpArrow 和 Alt+DownArrow分别是把当前行和上一行或者下一行交换
    Ctrl+Shift+K删除当前行
  - 重命名
    用F2或者Ctrl+Shift+L
  - 重构
    ...
  - 格式化(如果发现不能格式化这种文件类型,可以通过安装插件来获得支持)
    Ctrl+Shift+I格式化整个文档
    Ctrl+K Ctrl+F格式化选择的文档
  - 代码折叠
    Ctrl+Shift+[ 折叠代码,  Ctrl+Shift+] 打开代码
    Ctrl+K Ctrl+0 折叠所有代码, Ctrl+K Ctrl+J打开所有代码
  - 错误和警告
    F8可以跳到文件的错误和警告处
  - 代码块(Snippets) (可以通过插件扩展)
    如输入在js文件中输入trycatch,会提示,选择好对应的snippets,点tab就可以了
  - Emmet
    在Snippets上又加强了,比如输入ul>li.item$*5,然后点击菜单-> EDIT ->  Emmet: Expand Abbreviation
    
  