FROM centos:latest

WORKDIR /appdir


RUN dnf --disablerepo '*' --enablerepo=extras swap centos-linux-repos centos-stream-repos -y \
    && dnf distro-sync -y \
    && yum update -y \
    && yum install -y python3 gcc gcc-c++ kernel-devel python3-devel mysql-devel pkgconfig \
    && pip3 install flask flask_mysqldb

COPY . /appdir

CMD ["/usr/bin/python3", "helloapp.py"]