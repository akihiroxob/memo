### general settings
##### nodejs


##### git
- Enter a command below
```
sudo apt-get install git
```
- And then clone my repository "settings"
```
$ git clone https://github.com/akihiroxob/settings.git
$ cd settings
$ ./setup.sh
```


### atom

### gnome extensions
```
sudo apt-get install chrome-gnome-shell
```

### add shortcut
##### workspaceの移動に関して
- 上下に関してはSettingsから設定可能
- 左右に関しては下記コマンドで設定
```
gsettings set org.gnome.desktop.wm.keybindings switch-to-workspace-right  "[\"<Ctrl>Right\"]"
gsettings set org.gnome.desktop.wm.keybindings move-to-workspace-right  "[\"<Ctrl><Shift>Right\"]"
gsettings set org.gnome.desktop.wm.keybindings switch-to-workspace-left  "[\"<Ctrl>Left\"]"
gsettings set org.gnome.desktop.wm.keybindings move-to-workspace-left  "[\"<Ctrl><Shift>Left\"]"
```

##### multi gesture
- cui
```
sudo apt install touchegg
```
- add startup
    - see https://www.maketecheasier.com/add-multitouch-gestures-ubuntu/
- gui
```
sudo apt-get install build-essential libqt4-dev libx11-6
git clone https://github.com/Raffarti/Touchegg-gce/
cd Touchegg-gce
qmake
make
sudo make install
```

### docker
- https://qiita.com/iganari/items/fe4889943f22fd63692a
    - [docker redis](https://qiita.com/iyuichi/items/3a6f748cf1069205ba46)
        - appendonlyはredisの設定 永続化のAOFを使う設定
    - [docker mysql](https://qiita.com/astrsk_hori/items/e3d6c237d68be1a6f548)
