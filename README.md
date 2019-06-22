# 安装
1. 光盘安装
2. 选择`Install Red Hat Enterprise Linux 7.6`
3. <kbd>Tab</kbd>
4. <kbd>Space</kbd>ks=https://github.com/suzhen99/openstack/raw/master/ks.cfg
# 布署
```bash
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
pip_install          497
osc                  160
wait_for_service      22
yum_install          545
git_timed            380
dbsync                19
-------------------------
Unaccounted time     2992
=========================
Total runtime        4670



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
Change: 
OS Version: RedHatEnterpriseServer 7.6 Maipo

2019-06-22 16:55:30.083 | stack.sh completed in 4670 seconds.
```
