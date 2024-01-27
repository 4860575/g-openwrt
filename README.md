## 编译命令

1. 首先装好 Linux 系统，推荐 Debian 11 或 Ubuntu LTS

2.1 x86安装编译依赖

   ```bash
   sudo apt update -y
   sudo apt full-upgrade -y
   sudo apt install -y ack antlr3 aria2 asciidoc autoconf automake autopoint binutils bison build-essential \
   bzip2 ccache cmake cpio curl device-tree-compiler fastjar flex gawk gettext gcc-multilib g++-multilib \
   git gperf haveged help2man intltool libc6-dev-i386 libelf-dev libglib2.0-dev libgmp3-dev libltdl-dev \
   libmpc-dev libmpfr-dev libncurses5-dev libncursesw5-dev libreadline-dev libssl-dev libtool lrzsz \
   mkisofs msmtp nano ninja-build p7zip p7zip-full patch pkgconf python2.7 python3 python3-pip libpython3-dev qemu-utils \
   rsync scons squashfs-tools subversion swig texinfo uglifyjs upx-ucl unzip vim wget xmlto xxd zlib1g-dev
   ```

2.2 arm64安装编译依赖

   ```bash
   sudo apt update -y
   sudo apt full-upgrade -y
   sudo apt install ack antlr3 aria2 asciidoc autoconf automake autopoint binutils bison build-essential bzip2 ccache \
   cmake cpio curl device-tree-compiler fastjar flex gawk gettext git gperf haveged help2man intltool libelf-dev libglib2.0-dev \
   libgmp3-dev libltdl-dev libmpc-dev libmpfr-dev libncurses5-dev libncursesw5-dev libreadline-dev libssl-dev libtool lrzsz msmtp \
   nano ninja-build p7zip p7zip-full patch pkgconf python2.7 python3 python3-pip libpython3-dev qemu-utils rsync scons squashfs-tools \
   subversion swig texinfo uglifyjs upx-ucl unzip vim wget xmlto xxd zlib1g-dev gcc-multilib-i686-linux-gnu gcc-multilib-s390x-linux-gnu \
   gcc-multilib-x86-64-linux-gnu gcc-multilib-x86-64-linux-gnux32 libc6-dev-i386-amd64-cross libc6-dev-i386-cross libc6-dev-i386-x32-cross
   ```

3. 下载 dl 库，编译固件

```bash
git clone --depth=1 -b 21.02-mtk7981 https://github.com/4860575/g-openwrt.git
cd g-openwrt
git pull
./scripts/feeds update -a
./scripts/feeds install -a
make defconfig
make download -j$(nproc) && make V=s -j$(nproc)
```