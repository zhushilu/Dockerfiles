#
#  Author: Hari Sekhon
#  Date: 2016-01-16 09:58:07 +0000 (Sat, 16 Jan 2016)
#
#  vim:ts=4:sts=4:sw=4:et
#
#  https://github.com/harisekhon/Dockerfiles
#
#  If you're using my code you're welcome to connect with me on LinkedIn and optionally send me feedback to help improve or steer this or other code I publish
#
#  https://www.linkedin.com/in/harisekhon
#

FROM harisekhon/nagios-plugins:fedora
MAINTAINER Hari Sekhon (https://www.linkedin.com/in/harisekhon)

LABEL Description="Fedora + my GitHub repos pre-built"

# unit test for lib-java fails when sh is found in /usr/bin/sh as /usr/bin is earlier in the path than /bin
ENV PATH /bin:$PATH:/github/nagios-plugins:/github/devops-perl-tools:/github/devops-python-tools:/github/bash-tools:/github/spotify

ENV JAVA_HOME=/usr

RUN mkdir -pv /github

WORKDIR /github

COPY build.sh /

RUN /build.sh

COPY profile.d/java.sh /etc/profile.d/

CMD ["/bin/bash"]
