1) 在ubuntu16.04里面用'ctrl + ;'会调用fcitx的select to paste快捷健，可以在fcitx的 configureFcitx->Addon -> Clipboard里修改
2) ubuntu18.04 默认使用 'ctrl + shift + alt + up'来移动窗口，与ide冲突
```sh
sudo apt-get install dconf-tools
dconf-editor
来到: /org/gnome/desktop/wm/keybindings/
查找 move-to-workspace-down, 只保留['<Super><Shift>Page_Up']

点保存，离开后生效
```