systemctl disable NetworkManager
cat > /etc/yum.repos.d/epel.repo <<EOF
[epel]
name=Extra Packages for Enterprise Linux 7 - x86_64
baseurl=https://mirrors.aliyun.com/epel/7/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://mirrors.aliyun.com/epel/RPM-GPG-KEY-EPEL-7
priority=2
EOF
yum -y install python-pip
cat > /etc/pip.conf <<EOF
[global]
index-url = http://mirrors.aliyun.com/pypi/simple/
trusted-host = mirrors.aliyun.com
EOF
pip install --upgrade pip

mount /dev/sr0 /media
cat > /etc/yum.repos.d/Redhat-Base.repo <<EOF
[redhat]
name=Redhat-7 - Media
baseurl=file:///media/
gpgcheck=1
enabled=1
gpgkey=file:///media/RPM-GPG-KEY-redhat-release
priority=1
EOF
cat > /etc/yum.repos.d/CentOS-Base.repo <<EOF
[base]
name=CentOS-7 - Base
baseurl=https://mirrors.aliyun.com/centos/7/os/x86_64/
gpgcheck=1
gpgkey=https://mirrors.aliyun.com/centos/7/os/x86_64/RPM-GPG-KEY-CentOS-7
priority=2
[updates]
name=CentOS-7 - Updates
baseurl=https://mirrors.aliyun.com/centos/7/updates/x86_64/
gpgcheck=1
gpgkey=https://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-7
priority=2
[extras]
name=CentOS-7 - Extras
baseurl=https://mirrors.aliyun.com/centos/7/extras/x86_64/
gpgcheck=1
gpgkey=https://mirrors.aliyun.com/centos/RPM-GPG-KEY-CentOS-7
priority=2
EOF
yum -y install git wget yum-plugin-priorities

wget https://github.com/suzhen99/openstack/raw/master/queens.tar.gz
tar -xf queens.tar.gz -C /home

/home/devstack/tools/create-stack-user.sh

sudo chown -R stack:stack /home/devstack
cd /home/devstack
wget https://github.com/suzhen99/openstack/raw/master/local.conf
./stack.sh
