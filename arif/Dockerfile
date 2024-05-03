FROM centos:latest

WORKDIR /appdir


RUN dnf --disablerepo '*' --enablerepo=extras swap centos-linux-repos centos-stream-repos -y \
    && dnf distro-sync -y \
    && yum update -y \
    && yum install -y python3 \
    && pip-3 install flask 

COPY . /appdir

CMD ["/usr/bin/python3", "helloapp.py"]