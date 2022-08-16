FROM ubuntu:18.04

ENV PERL5LIB=/bioinf-tools/vcftools-0.1.15/install/share/perl/5.24.1/:/bioinf-tools/cortex/scripts/analyse_variants/bioinf-perl/lib:/bioinf-tools/cortex/scripts/calling/:$PERL5LIB
ENV PATH=/bioinf-tools/:/bioinf-tools/cortex/bin/:/bioinf-tools/cortex/scripts/analyse_variants/seq-align/bin/:/bioinf-tools/vcftools-0.1.15/install/bin:/bioinf-tools/enaBrowserTools/python3:/clockwork/scripts/:$PATH
ENV LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH

RUN apt update \
    && apt install -y software-properties-common \
    && apt-add-repository universe \
    && apt update \
    && apt install -y git

ARG TAG="fe62f000f4eb478549e3a36f786f5be0c9a2b168"
RUN git clone https://github.com/iqbal-lab-org/clockwork.git /clockwork

WORKDIR /clockwork

# install dependencies
RUN git checkout "$TAG" && scripts/install_dependencies.sh /bioinf-tools

# install clockwork
WORKDIR /clockwork/python
RUN python3 setup.py install && clockwork version
