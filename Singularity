BootStrap: docker
From: centos:centos7
# more details at https://keychest.net/roca and https://github.com/crocs-muni/roca 

%runscript
echo "running roca-detect from the container:"
roca-detect "$@"

%post
yum -y update && yum -y upgrade
yum -y install python-devel python-pip gcc gcc-c++ make automake autoreconf libtool openssl-devel libffi-devel dialog git epel-release
yum -y install python2-pip
pip install roca-detect

touch /centos7-`date +%Y%m%d-%H%M%S`

# specific to my setup, required if you don't have overlay support (CentOS-6)
# CentOS-7 host can ignore that mkdir line
mkdir -p /local-storage /mnt/beegfs /baycells/home /baycells/scratch /c6/shared /c6/eb /local/gensoft2 /c6/shared/rpm /Bis/Scratch2 /mnt/beegfs

