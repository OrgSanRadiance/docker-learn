FROM centos:7
WORKDIR /
RUN mkdir /testdir
RUN yum install -y python3
RUN python3 --version
CMD ["/bin/sh", "-c", "sleep 20 && touch /testdir/file1.txt /testdir/file2.txt && sleep 60"]
