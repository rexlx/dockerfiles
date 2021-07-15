FROM fedora

RUN dnf upgrade -y
RUN dnf install libpcap-devel libpcap gcc-c++ openssl-devel \
openssl-libs openssl ncurses-devel lksctp-tools lksctp-tools-devel \
make cmake automake gcc kernel-devel rpm-devel -y --skip-broken
RUN dnf groupinstall 'Development Tools' -y
RUN dnf clean all
ADD https://github.com/SIPp/sipp/releases/download/v3.6.1/sipp-3.6.1.tar.gz /
RUN tar -xzf /sipp-3.6.1.tar.gz
WORKDIR /sipp-3.6.1
RUN /bin/bash build.sh --full
WORKDIR /
RUN rm -rf sipp-3*

WORKDIR /sipp
EXPOSE 5060-5070
EXPOSE 5060-5070/udp
ENTRYPOINT ["sipp"]
