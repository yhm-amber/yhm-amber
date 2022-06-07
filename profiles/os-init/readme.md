


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
zypper in -- containerd podman buildah katacontainers cilium
zypper in -- docker docker-compose
~~~

#### ops

nothing now ...

## openEuler

### 22.03 LTS

#### pkg

~~~ sh
dnf in -y -- cockpit wget git rsync
~~~

#### ops

`cockpit`

~~~ sh
systemctl enable --now -- cockpit.socket
firewall-cmd --add--service cockpit --permanent
~~~

## Debian

## Deepin

## AlpineLinux

## CentOS

### 7.9.2009

#### pkg

~~~ sh
yum -y install -- cockpit wget git rsync telnet net-tools
~~~

#### ops

`cockpit`

~~~ sh
systemctl enable --now -- cockpit.socket
firewall-cmd --add--service cockpit --permanent
~~~


