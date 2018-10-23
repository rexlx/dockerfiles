FROM centos

RUN yum -y update
RUN yum -y install libpcap-devel libpcap gcc-c++ openssl-devel \
openssl-libs openssl ncurses-devel lksctp-tools lksctp-tools-devel
RUN yum clean all


ADD https://github.com/SIPp/sipp/releases/download/v3.5.1/sipp-3.5.1.tar.gz /
RUN tar -xzf /sipp-3.5.1.tar.gz

WORKDIR /sipp-3.5.1
RUN ./configure --with-pcap --with-sctp --with-openssl --with-rtpstream
RUN make install

WORKDIR /
RUN rm -rf sipp-3.5.1*

WORKDIR /sipp
EXPOSE 5060-5070
EXPOSE 5060-5070/udp

ENTRYPOINT ["sipp"]
