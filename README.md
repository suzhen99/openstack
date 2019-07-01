# `VMware`虚拟机配置
- 内存：`8GB`
- 处理器：`2`
- 硬盘(SCSI)：`500GB`
- 新硬盘(SCSI)：`500GB`
- CD/DVD（SATA）：`rhel-server-7.6-x86_64-dvd.iso`
- 网络适配器：`NAT`
- 网络甜配器 2：`仅主机模式`
- USB控制器：`存在`
- 声卡：`自动检测`
- 显示器：`自动检测`

# 安装
1. 光盘安装
2. 选择`Install Red Hat Enterprise Linux 7.6`
3. <kbd>Tab</kbd>
4. <kbd>Space</kbd>ks=https://github.com/suzhen99/openstack/raw/master/ks.cfg
# 布署
```bash
pip install --upgrade pip
yum -y install \
ftp://ftp.pbone.net/mirror/ftp5.gwdg.de/pub/opensuse/repositories/home:/lenovo-lico:/lico-dep:/Factory:/el7/el7/x86_64/{python2-cryptography-2.2.1-2.7.el7.x86_64.rpm,python2-cffi-1.11.5-2.6.el7.x86_64.rpm,python2-pycparser-2.18-7.14.el7.x86_64.rpm} \
ftp://ftp.pbone.net/mirror/ftp5.gwdg.de/pub/opensuse/repositories/home:/lenovo-lico:/lico-dep:/Factory:/el7/el7/noarch/{python2-ipaddress-1.0.22-2.5.el7.noarch.rpm,python2-ply-3.11-1.5.el7.noarch.rpm}

/home/devstack/tools/create-stack-user.sh
chown -R stack:stack /home/devstack
su - stack
cd /home/devstack
./stack.sh

```
# 完成
```bash
=========================
DevStack Component Timing
 (times are in seconds)  
=========================
run_process           51
test_with_retry        4
pip_install          499
osc                  163
wait_for_service      21
yum_install          208
git_timed            704
dbsync                19
-------------------------
Unaccounted time     606
=========================
Total runtime        2275



This is your host IP address: 192.168.60.129
This is your host IPv6 address: ::1
Horizon is now available at http://192.168.60.129/dashboard
Keystone is serving at http://192.168.60.129/identity/
The default users are: admin and demo
The password: redhat

WARNING: 
Using lib/neutron-legacy is deprecated, and it will be removed in the future


Services are running under systemd unit files.
For more information see: 
https://docs.openstack.org/devstack/latest/systemd.html

DevStack Version: queens
Change: e3100794d1615fc6b4216f54e2f7859a33d60b05 Fix installing tempest plugins 2019-06-17 22:30:22 +0000
OS Version: RedHatEnterpriseServer 7.6 Maipo

2019-06-29 01:18:57.383 | stack.sh completed in 2275 seconds.
```
