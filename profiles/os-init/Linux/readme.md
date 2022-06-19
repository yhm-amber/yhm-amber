


## openSUSE

### Leap 15.2

#### pkg

##### base

~~~ sh
zypper in -y -- rsync cargo xrdp tigervnc screen libvirt qemu-kvm firecracker neovim htop screenfetch neofetch suse-module-tools guestfs-tools
zypper in -t pattern -y -- kvm_tools xen_tools
zypper in -y -- snapper-zypp-plugin yast2-snapper
~~~

##### more

~~~ sh
zypper in -y -- nano git emacs git-daemon git-web luajit erlang
~~~

lang

~~~ sh
zypper in -- luajit erlang rust cargo elixir java clang llvm
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
dnf -y in -- cockpit wget git rsync screen git net-tools sshpass bind-utils virt-install
dnf -y in -- postgresql mariadb
dnf -y in -- luajit cargo rebar elixir
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

## AlpineLinux

## fedora

### 35

#### req

#### pkg

~~~ sh
sudo dnf -y in -- dnf-plugins-core dnf-automatic starship wget git rsync screen git net-tools sshpass bind-utils virt-install zsh jq
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
yum -y install -- cockpit wget git rsync telnet net-tools screen sshpass bind-utils mariadb
~~~

#### ops

`cockpit`

~~~ sh
systemctl enable --now -- cockpit.socket
firewall-cmd --add-service cockpit --permanent && systemctl reload firewalld
~~~


