## 在Flatpak安裝Fcitx同Rime套件
flatpak install org.fcitx.Fcitx5

flatpak install org.fcitx.Fcitx5.Addon.Rime

## 選用 Rime
<img width="973" height="759" alt="image" src="https://github.com/user-attachments/assets/c724d183-bc30-4698-a070-c1a6874f59c8" />

## 設Fcitx自動啟動
mkdir -p ~/.config/autostart/

cp /home/.steamos/offload/var/lib/flatpak/exports/share/applications/org.fcitx.Fcitx5.desktop ~/.config/autostart/

## 設環境變量
nano /etc/environment
```
GTK_IM_MODULE=ibus
QT_IM_MODULE=ibus
XMODIFIERS=@im=ibus
SDL_IM_MODULE=ibus
GLFW_IM_MODULE=ibus
```

## 安裝 Plum
curl -fsSL https://raw.githubusercontent.com/rime/plum/master/rime-install | bash -s -- :all


## 選用 速成
nano ~/.var/app/org.fcitx.Fcitx5/data/fcitx5/rime/build/default.yaml
```
schema_list:
  - schema: quick5
```
<img width="623" height="435" alt="image" src="https://github.com/user-attachments/assets/cf65badf-1034-40a4-b0e9-bca54141c1ee" />


## 設置 速成
nano ~/.var/app/org.fcitx.Fcitx5/data/fcitx5/rime/build/quick5.schema.yaml
```
key_binder:
  bindings:
    - {accept: Return, send: 1, when: has_menu}  #打Enter(選擇第一個選字)
menu:
  page_size: 9  #顯示9行 選字項
```
nano ~/.var/app/org.fcitx.Fcitx5/config/fcitx5/conf/classicui.conf
```
# vertical candidate 垂直候選字列表
Vertical Candidate List=True
```
<img width="770" height="639" alt="image" src="https://github.com/user-attachments/assets/b635ed97-d33e-467b-811e-613460a5d142" />

nano ~/.var/app/org.fcitx.Fcitx5/config/fcitx5/conf/rime.conf
```
# 可用時在應用程序中顯示預編輯文本
PreeditInApplication=False
```
<img width="770" height="639" alt="image" src="https://github.com/user-attachments/assets/4a0314b6-b74d-47f2-9ab2-01450b609321" />


## 參考
[https://www.bilibili.com/opus/1139601518269300768](https://www.bilibili.com/opus/1139601518269300768)

[https://forum.gamer.com.tw/C.php?bsn=60599&snA=40156](https://forum.gamer.com.tw/C.php?bsn=60599&snA=40156)

[https://wiki.archlinux.org/title/Fcitx5](https://wiki.archlinux.org/title/Fcitx5)
