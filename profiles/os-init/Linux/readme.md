
## winget

### demo

ref: https://docs.microsoft.com/zh-cn/windows/package-manager/winget/install

~~~ powershell
winget install --id Git.Git -i
~~~

or

~~~ powershell
winget install -q huorong -i
~~~

### list

#### envk

可作为其它工具的管理底座

~~~
BraveSoftware.BraveBrowser
msys2.msys2
Waterfox.Waterfox
~~~

#### neti

网络

~~~
bitbeans.SimpleDNSCrypt
tailscale.tailscale
~~~

#### data

数据的归档与使用

~~~
7zip.7zip
Bandisoft.Bandizip
Bandisoft.Honeyview
Daum.PotPlayer XP8BSBGQW2DKS0
RARLab.WinRAR
VideoLAN.VLC XPDM1ZW6815MQM
~~~

#### cybr

控制

~~~
CPUID.CPU-Z
Ditto.Ditto 9NBLGGH3ZBJQ
File-New-Project.EarTrumpet 9NBLGGH516XP
"Huorong Internet Security" XPDDXVFRXCXK80
Microsoft.PowerToys
"Microsoft Edge Browser" XPFFTQ037JWMHS
Mozilla.Firefox
qBittorrent.qBittorrent
RustDesk.RustDesk
Starship.Starship
TimKosse.FileZilla.Client
TimKosse.FileZilla.Server
voidtools.Everything 9WZDNCRDKD2B
~~~

#### lang

语言

~~~
Erlang.ErlangOTP
Racket.Racket
Rustlang.Rustup
Scala.Scala.2
~~~

#### code

代码的编辑及其管理

~~~
Git.Git
KDE.Kate 9NWMW7BB59HW
Microsoft.VisualStudioCode
~~~


## Msys2

### latest

#### pkg

list:

~~~~
mingw64/mingw-w64-x86_64-starship
mingw64/mingw-w64-x86_64-aria2
mingw64/mingw-w64-x86_64-dnscrypt-proxy
mingw64/mingw-w64-x86_64-qbittorrent
mingw64/mingw-w64-x86_64-pidgin
mingw64/mingw-w64-x86_64-ffmpeg

mingw64/mingw-w64-x86_64-zstd
mingw64/mingw-w64-x86_64-xz
mingw64/mingw-w64-x86_64-wget
mingw64/mingw-w64-x86_64-emacs
mingw64/mingw-w64-x86_64-tools-git
mingw64/mingw-w64-x86_64-git-repo
mingw64/mingw-w64-x86_64-luabind-git
mingw64/mingw-w64-x86_64-jq

mingw64/mingw-w64-x86_64-postgresql
mingw64/mingw-w64-x86_64-toolchain
mingw64/mingw-w64-x86_64-xpdf
mingw64/mingw-w64-x86_64-wxsvg
mingw64/mingw-w64-x86_64-openssl
mingw64/mingw-w64-x86_64-libressl

mingw64/mingw-w64-x86_64-luajit
mingw64/mingw-w64-x86_64-rust
mingw64/mingw-w64-x86_64-cargo-c
mingw64/mingw-w64-x86_64-nim
mingw64/mingw-w64-x86_64-lld
mingw64/mingw-w64-x86_64-llvm
mingw64/mingw-w64-x86_64-mlir
mingw64/mingw-w64-x86_64-clang
mingw64/mingw-w64-x86_64-flang
mingw64/mingw-w64-x86_64-ghdl-llvm
mingw64/mingw-w64-x86_64-openmp
mingw64/mingw-w64-x86_64-polly
clang64/mingw-w64-clang-x86_64-compiler-rt
mingw64/mingw-w64-x86_64-perl
mingw64/mingw-w64-x86_64-vala
mingw64/mingw-w64-x86_64-julia
mingw64/mingw-w64-x86_64-libgccjit
mingw64/mingw-w64-x86_64-drmingw

msys/findutils
msys/neofetch
msys/screenfetch
msys/sshpass
msys/nano
msys/procps-ng
~~~~

~~~ sh
: use for a good look may be
eval "$(
    
    echo '
        
        pacman -S --needed
        
        --
        
        mingw64/mingw-w64-x86_64-luajit
        msys/neofetch
        mingw64/mingw-w64-x86_64-qbittorrent
        mingw64/mingw-w64-x86_64-nim
        mingw64/mingw-w64-x86_64-zstd
        
    ' | xargs -- echo )"

: or just paste your needs manual
pacman -S --needed -- mingw64/mingw-w64-x86_64-luajit msys/neofetch mingw64/mingw-w64-x86_64-qbittorrent mingw64/mingw-w64-x86_64-nim mingw64/mingw-w64-x86_64-zstd
~~~

#### ops

`starship`

~~~ sh
echo $'\n''eval "$(starship init bash)"'$'\n' | tee -a -- ~/.bashrc && exec bash
~~~

## AlpineLinux

### x

#### pkg

~~~ sh

~~~

#### ops

## Termux

### latest

#### pkg

~~~ sh
pkg install -- starship neovim elixir luajit dropbear git
~~~

#### ops

`starship`

~~~ sh
echo $'\n''eval "$(starship init bash)"'$'\n' | tee -a -- ~/.bashrc && exec bash
~~~

`adi1090x/termux-style`

~~~ sh
git clone -- https://github.com/adi1090x/termux-style ~/.style/adi1090x/termux-style
~/.style/adi1090x/termux-style/install.sh

termux-style
: C=89 F=20
~~~

## openSUSE

### Leap 15.2

#### pkg

##### base

~~~ sh
zypper in -y -- rsync cargo php xrdp tigervnc screen libvirt qemu-kvm firecracker neovim htop screenfetch neofetch suse-module-tools guestfs-tools
zypper in -t pattern -y -- kvm_tools xen_tools
zypper in -y -- snapper-zypp-plugin yast2-snapper
~~~

##### more

~~~ sh
zypper in -y -- nano git emacs git-daemon git-web luajit erlang
~~~

lang

~~~ sh
zypper in -- luajit erlang rust cargo elixir java clang llvm php
zypper in -- gcc go
~~~

code

~~~ sh
zypper in -- nano git
zypper in -- emacs git-daemon git-web
~~~

virt

~~~ sh
zypper in -t pattern -y -- kvm_tools xen_tools
zypper in -- virtualbox vagrant
~~~

container

~~~ sh
zypper in -- containerd podman buildah katacontainers
zypper in -- docker docker-compose
~~~

#### ops

nothing now ...

## openEuler

### 22.03 LTS

#### req

~~~ voml
wpp: https://www.openeuler.org/whitepaper/openEuler-whitepaper-2203.pdf
playground: https://moocstudio.openeuler.sh/
isos:
- https://repo.openeuler.org/openEuler-22.03-LTS/ISO/x86_64/
~~~

#### pkg

~~~ sh
dnf -y up
dnf -y in -- cockpit wget git rsync screen git net-tools nss-tools sshpass bind-utils virt-install
dnf -y in -- postgresql mariadb
dnf -y in -- luajit cargo rebar elixir php
dnf -y in -- npm gem golang
~~~

#### ops

`cockpit`

~~~ sh
systemctl enable --now -- cockpit.socket
firewall-cmd --add-service cockpit --permanent && systemctl reload firewalld
~~~

## Debian

## Deepin



## fedora

### 36

#### pkg

~~~~ sh
sudo dnf -y up

: may be have installed
sudo dnf -y in -- git wget rsync ffsend php podman bind-utils net-tools nss-tools sshpass dnf-plugins-core

: needs for me
sudo dnf -y in -- fish screen git sshpass zstd bind-utils net-tools nss-tools
sudo dnf -y in -- dnf-plugins-core dnf-automatic
sudo dnf -y in -- distrobox starship virt-install
sudo dnf -y in -- podman buildah
sudo dnf -y in -- postgresql mariadb php
sudo dnf -y in -- luajit cargo rebar elixir php
~~~~

### 35

#### req

随便玩儿点儿无关紧要的就行。

- 我发现这玩意儿更新都有 bug ，检测出来更新需要 [`k/kernel-modules-5.18.4-101.fc35.x86_64.rpm`](https://mirrors.tuna.tsinghua.edu.cn/fedora/updates/35/Everything/x86_64/Packages/k/kernel-modules-5.18.4-101.fc35.x86_64.rpm) ，结果人家源直接已经是 [`k/kernel-modules-5.18.5-100.fc35.x86_64.rpm`](https://mirrors.tuna.tsinghua.edu.cn/fedora/updates/35/Everything/x86_64/Packages/k/kernel-modules-5.18.5-100.fc35.x86_64.rpm) 了，也不知道为啥这个以为最新的包和实际最新的包的文件名会不一致。。。（虽然这次至少只是以为的最新的版本号有些落后。。。当然也有可能是它真的需要先更新成这个老一点的但无奈没有了已经。）

#### pkg

~~~ sh
sudo dnf -y in -- ffsend dnf-plugins-core dnf-automatic starship wget git rsync screen git net-tools sshpass bind-utils virt-install zsh jq
sudo dnf -y in -- podman buildah
sudo dnf -y in -- postgresql mariadb
sudo dnf -y in -- luajit cargo rebar elixir
sudo dnf -y in -- vagrant nomad packer waypoint boundary
sudo dnf -y in -- npm gem golang
~~~

#### ops

[`cockpit`]

- 在 Fedora 发行版，这个软件默认在最小安装也是已经被配置好了的，直接用就行了。
- 访问途径是 `https://this-node-ip:9090` 。
- 登录就是用你正常的 Linux 用户登录。

[`dnf-automatic`]

- 访问 `https://this-node-ip:9090/updates` ，并根据 Web 界面的提示启用你需要的配置。

[`starship`](https://starship.rs/guide/#%F0%9F%9A%80-installation)

- `eval "$(starship init bash)"` : Add the following to the end of `~/.bashrc`
- `eval "$(starship init zsh)"` : Add the following to the end of `~/.zshrc`
- `eval (starship init elvish)` : Add the following to the end of `~/.elvish/rc.elv`
- `starship init fish | source` : Add the following to the end of `~/.config/fish/config.fish`
- `Invoke-Expression (&starship init powershell)` : Add the following to the end of your PowerShell configuration (find it by running `$PROFILE` )
- `execx($(starship init xonsh))` : Add the following to the end of `~/.xonshrc`
- `eval \`starship init tcsh\`` : Add the following to the end of `~/.tcshrc`
- `eval $(starship init ion)` : Add the following to the end of `~/.config/ion/initrc`



## Manjaro

### latest

## CentOS

### 7.9.2009

#### req

~~~ voml
isos:
- http://isoredirect.centos.org/centos/7/isos/x86_64/
- https://mirrors.ustc.edu.cn/centos/7.9.2009/isos/x86_64/
- http://mirrors.njupt.edu.cn/centos/7.9.2009/isos/x86_64/
- http://ftp.sjtu.edu.cn/centos/7.9.2009/isos/x86_64/
- http://mirrors.163.com/centos/7.9.2009/isos/x86_64/
- https://mirrors.tuna.tsinghua.edu.cn/centos/7.9.2009/isos/x86_64/
~~~

#### pkg

~~~ sh
yum -y update
yum -y install -- cockpit php wget git rsync telnet net-tools nss-tools screen sshpass bind-utils mariadb
~~~

#### ops

`cockpit`

~~~ sh
systemctl enable --now -- cockpit.socket
firewall-cmd --add-service cockpit --permanent && systemctl reload firewalld
~~~


