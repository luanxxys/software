# i3wm

- ### REFERENCE

    + [i3 User’s Guide](https://i3wm.org/docs/userguide.html#_opening_terminals_and_moving_around)

    + [i3 wiki（简体中文）](https://wiki.archlinux.org/index.php/I3_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))

    + [Getting started with the i3 tiling window manager](https://fedoramagazine.org/getting-started-i3-window-manager/)

    + [dotshare.it](http://dotshare.it/category/wms/i3/)

    + [i3conf + i3status : 前辈定制](https://github.com/levinit/i3wm-config)

- ### 安装软件

    sudo dnf install mate-power-manager
    > 主要用于笔记本调节亮度和方便电源管理

    sudo dnf install xcompmgr
    > 使终端透明（可选）

    sudo dnf install feh
    > 设置背景壁纸（可选）

    sudo dnf install alsa-utils
    > 音量管理

    sudo dnf install conky
    > 设置状态栏

    sudo pacman -S dmenu
    > 启动栏
    >
    > 用 archlinux 命令，意为 fedora 下不必要安装，而 arch 下需要安装

- ### 将配置文件移到如下位置

        ~/.config/i3/config

- ### 配置 status bar - 两种方式

    1. ### i3status

        用 i3wm 本身的 i3status 定义 toolbar

            cp /etc/i3status.conf ~/.config/i3status/config

        效果如图：

        ![i3status_bar](images/i3status.png)

    1. ### conky

            vim ~/.conkyrc

        效果如图：

        ![conky_bar](images/conky.png)

    > 选择某种方式后，在 ~/.config/i3/conf 中作出相应修改

- ### i3lock

    将锁屏界面调成黑色 ---> '#000000'

    更多选项参见

		man i3lock

- ### 高分辨率显示器

    通过 ~/.Xresources 调整 DPI

        下载 .Xresources 文件，并移到 home 下

- ### i3-gaps

    [项目主页： https://github.com/Airblader/i3](https://github.com/Airblader/i3)

    为了方便，将安装过程列出来：

    ``` bash
    cd /path/where/you/want/the/repository

    # clone the repository
    git clone https://www.github.com/Airblader/i3 i3-gaps
    cd i3-gaps

    # compile & install
    autoreconf --force --install
    rm -rf build/
    mkdir -p build && cd build/

    # Disabling sanitizers is important for release versions!
    # The prefix and sysconfdir are, obviously, dependent on the distribution.
    ../configure --prefix=/usr --sysconfdir=/etc --disable-sanitizers
    make
    sudo make install
    ```

    安装好以后，将相关配置写入主配置文件

- ### 尚存问题

    1. lantern 在 chrome 中不可用，但在 tor 中可用。可能是 chrome 代理需要设置
    1. 透明效果未奏效
    1. xmind 运行出问题
    1. 总结此配置下的 feature、 shortcut keys
    1. i3wm 禁用触控板
    1. 色温调节（f.lux ?）
