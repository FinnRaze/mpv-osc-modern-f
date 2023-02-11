此分支调整了按键布局，便于查看字幕轨和音轨；添加了ontop按键

this branch adjusted buttons' layout for easier checking sid&aid; added a button for 'ontop'


Fork自modern的mpv osc脚本，修改了外观布局、部分按键功能；加回mpv内置osc的透明度调整选项；加回可用快捷键控制可视性的功能。

mpv osc script forked from [modern](https://github.com/maoiscat/mpv-osc-modern).Changed the layout\some buttons' action；make boxalpha could be customized in osc.conf；make osc-visibility could be adjusted with shortcut in input.conf，just like the builtin OSC

![mpv-shot0001](https://user-images.githubusercontent.com/84557113/217278486-93970905-2685-4a82-9cf6-031ed41e710b.jpg)



# Installation 安装

osc.lua --> "\~\~/scripts/" (!!REMOVE OTHER OSC SCRIPTS!! 移除其他的osc脚本！！)

material-design-iconic-font.ttf --> "\~\~/fonts" ([FONT LINK](https://zavoloklom.github.io/material-design-iconic-font/)) 复制图标字体文件

Then edit "\~\~/mpv.conf", add the following lines to the end. 在mpv.conf中加下列代码关闭内置osc

```
osc=no

```

# thumbnail 略缩图支持
Install [thumbfast](https://github.com/po5/thumbfast)

# Configuration 设置

Config file locates at "\~\~/script-opts/modernf.conf". Supported options are listed below.

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
## playlist_back/forwad
* mbtn_left: play previous/netx file.
* mbtn_right: open [playlistmanager](https://github.com/jonniek/mpv-playlistmanager).
## cycle_audio/subtitle
* mbtn_left: cycle to next track.
* mbtn_right: show track list.
## ontop
* mbtn_left: cycle ontop
## info
* mbtn_left: stats/display-stats-toggle.
* mbtn_right: stats/display-page-4

# 按键行为

一些按键可能具有多种鼠标操作功能，下面列出一些：

## 进度条
* 鼠标左键: 跳转至点击位置
* 鼠标右键: 跳转到所在章节开头
## 上一个/下一个
* 鼠标左键: 打开播放列表上一个/下一个文件.
* 鼠标右键: 打开[playlistmanager](https://github.com/jonniek/mpv-playlistmanager)播放列表脚本.
## 音频/字幕
* 鼠标左键: 切换到下一个轨道.
* 鼠标右键: 显示轨道列表.
## 置顶
* 鼠标左键：切换置顶
## 信息
* 鼠标左键: 统计信息开关
* 鼠标右键: 查看激活的快捷键
