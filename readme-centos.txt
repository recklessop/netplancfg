sudo yum update
sudo yum install -y https://centos7.iuscommunity.org/ius-release.rpm
sudo yum update
sudo yum install python3 python34-PyYAML
sudo yum install netplan
sudo yum install git

add_drivers+=" hv_vmbus hv_netvsc hv_storvsc nvme ena xen_blkfront xen_netfront "

----- create a netplan.repo in /etc/yum.repos.d/ with this info ----
[ngompa-Netplan]
name=Copr repo for Netplan owned by ngompa
baseurl=https://copr-be.cloud.fedoraproject.org/results/ngompa/Netplan/epel-7-$basearch/
type=rpm-md
skip_if_unavailable=True
gpgcheck=1
gpgkey=https://copr-be.cloud.fedoraproject.org/results/ngompa/Netplan/pubkey.gpg
repo_gpgcheck=0
enabled=1
enabled_metadata=1
