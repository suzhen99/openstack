# 安装
1. 光盘安装
2. 选择`Install Red Hat Enterprise Linux 7.6`
3. <kbd>Tab</kbd>
4. <kbd>Space</kbd>ks=https://github.com/suzhen99/openstack/raw/master/ks.cfg
# 布署
```bash
chown -R stack:stack /home/devstack
/home/devstack/tools/create-stack-user.sh
su - stack
cd /home/devstack
./stack.sh
```
