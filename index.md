flatpak install org.fcitx.Fcitx5
flatpak install org.fcitx.Fcitx5.Addon.Rime
cp /home/.steamos/offload/var/lib/flatpak/exports/share/applications/org.fcitx.Fcitx5.desktop ~/.config/autostart/

# /etc/environment
GTK_IM_MODULE=ibus
QT_IM_MODULE=ibus
XMODIFIERS=@im=ibus
SDL_IM_MODULE=ibus
GLFW_IM_MODULE=ibus

cd ~/.var/app/org.fcitx.Fcitx5/data/
mkdir fcitx5
cd fcitx5/
git clone --depth 1 https://github.com/rime/plum.git
cd plum
bash rime-install :preset
bash rime-install --select :all lotem/rime-forge/lotem-packages.conf

# ~/.var/app/org.fcitx.Fcitx5/data/fcitx5/rime/build/default.yaml
schema_list:
  - schema: quick5

# ~/.var/app/org.fcitx.Fcitx5/data/fcitx5/rime/build/quick5.schema.yaml
key_binder:
  bindings:
    - {accept: Return, send: 1, when: has_menu} # 打Enter(選擇第一個選字)
menu:
  page_size: 9
  half_shape:
    #全清


# 參考

https://www.bilibili.com/opus/1139601518269300768

https://forum.gamer.com.tw/C.php?bsn=60599&snA=40156

https://wiki.archlinux.org/title/Fcitx5
