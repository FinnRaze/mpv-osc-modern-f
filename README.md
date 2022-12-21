Fork自modern的mpv osc脚本，修改了外观布局、部分按键功能，并带回了mpv内置osc的透明度和可视性调整选项

mpv osc script forked from [modern](https://github.com/maoiscat/mpv-osc-modern).Changed the layout\some buttons' action,and make boxalpha&visibility could be customized just like the builtin OSC

![mpv-shot0019](https://user-images.githubusercontent.com/84557113/208023797-44ea3794-d2e6-4394-8a83-005d6125131d.jpg)



# Installation 安装

osc.lua --> "\~\~/scripts/" (!!REMOVE OTHER OSC SCRIPTS!! 移除其他的osc脚本！！)

material-design-iconic-font.ttf --> "\~\~/fonts" ([FONT LINK](https://zavoloklom.github.io/material-design-iconic-font/)) 复制图标字体文件

Then edit "\~\~/mpv.conf", add the following lines to the end. 在mpv.conf中加下列代码关闭内置osc

```
osc=no

[Idle]
profile-cond=p["idle-active"]
profile-restore=copy-equal
title=' '
keepaspect=no
background=1
```

# thumbnail 略缩图支持
Install [thumbfast](https://github.com/po5/thumbfast)

# Configuration 设置

Config file locates at "\~\~/script-opts/osc.conf". Supported options are listed below.

```
    showwindowed=yes/no             -- show OSC when windowed?
    showfullscreen=yes/no           -- show OSC when fullscreen?
    scalewindowed=1                 -- scaling of the controller when windowed
    scalefullscreen=1               -- scaling of the controller when fullscreen
    scaleforcedwindow=2             -- scaling when rendered on a forced window
    vidscale=yes/no                 -- scale the controller with the video?
    hidetimeout=500                -- duration in ms until the OSC hides if no mouse movement. enforced non-negative for the user but internally negative is 'always-on'.
    fadeduration=200                -- duration of fade out in ms 0=no fade
    minmousemove=3                  -- minimum amount of pixels the mouse has to move between ticks to make the OSC show up
    iamaprogrammer=yes/no           -- use native mpv values and disable OSC internal track list management (and some functions that depend on it)
    font='mpv-osd-symbols'          -- default osc font
    seekrange=yes/no                -- show seekrange overlay
    seekrangealpha=128              -- transparency of seekranges
    seekbarkeyframes=yes/no         -- use keyframes when dragging the seekbar
    title='${media-title}'          -- string compatible with property-expansion to be shown as OSC title
    showtitle=yes/no                -- show title and no hide timeout on pause
    timetotal=yes/no                -- display total time instead of remaining time?
    visibility=auto/yes/no          -- only used at init to set visibility_mode(...)
    windowcontrols=auto/yes/no      -- whether to show window controls
    volumecontrol=yes/no            -- whether to show mute button and volumne slider
    processvolume=yes/no            -- volume bar show processd volume
    language=eng/chs                -- eng=English chs=Chinese
    boxalpha=80                     -- alpha of the background box,0 (opaque) to 255 (fully transparent)
```

# Button Actions

Some buttons may accept multiple mouse actions, here is a list:

(NOTE: mbtn = mouse button)

## seekbar
* mbtn_left: seek to chosen position.
* mbtn_right: seek to the head of chosen chapter
## skip_back/forward
* mbtn_left: skip 90 seconds.
* mbtn_right: add chapter -1/1.
* shift+mbtn_left: frame-step/frame-back-step
## playlist_back/forwad
* mbtn_left: play previous/netx file.
* mbtn_right: show playlist.
## cycle_audio/subtitle
* mbtn_left: cycle to next track.
* mbtn_right: show track list.
## info
* mbtn_left: stats/display-stats-toggle.
* mbtn_right: stats/display-page-4

# 按键行为

一些按键可能具有多种鼠标操作功能，下面列出一些：

## 进度条
* 鼠标左键: 跳转至点击位置
* 鼠标右键: 跳转到所在章节开头
## 快退/快进
* 鼠标左键: 跳90秒
* 鼠标右键: 章节数 -1/1.
* shift+鼠标左键: 帧回退/帧步进
## 上一个/下一个
* 鼠标左键: 打开播放列表上一个/下一个文件.
* 鼠标右键: 打开playlistmanager播放列表脚本.
## 音频/字幕
* 鼠标左键: 切换到下一个轨道.
* 鼠标右键: 显示轨道列表.
## 信息
* 鼠标左键: 统计信息开关
* 鼠标右键: 查看激活的快捷键
