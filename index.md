# 在flatpak安裝fcitx同rime套件
flatpak install org.fcitx.Fcitx5

flatpak install org.fcitx.Fcitx5.Addon.Rime

# 設Fcitx自動啟動
cp /home/.steamos/offload/var/lib/flatpak/exports/share/applications/org.fcitx.Fcitx5.desktop ~/.config/autostart/

# 設環境變量
nano /etc/environment
```
GTK_IM_MODULE=ibus
QT_IM_MODULE=ibus
XMODIFIERS=@im=ibus
SDL_IM_MODULE=ibus
GLFW_IM_MODULE=ibus
```

# 安裝 plum
curl -fsSL https://raw.githubusercontent.com/rime/plum/master/rime-install | bash -s -- :all


# 選用 速成
nano ~/.var/app/org.fcitx.Fcitx5/data/fcitx5/rime/build/default.yaml
```
schema_list:
  - schema: quick5
```

# 設置 速成
nano ~/.var/app/org.fcitx.Fcitx5/data/fcitx5/rime/build/quick5.schema.yaml
```
key_binder:
  bindings:
    - {accept: Return, send: 1, when: has_menu}  #打Enter(選擇第一個選字)
menu:
  page_size: 9  #顯示9行 選字項
```


# 參考
https://www.bilibili.com/opus/1139601518269300768

https://forum.gamer.com.tw/C.php?bsn=60599&snA=40156

https://wiki.archlinux.org/title/Fcitx5
