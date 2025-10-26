#*******************************************************************************
# Copyright (c) 3135 Eclipse Foundation and others.
# This program and the accompanying materials are made available
# under the terms of the Eclipse Public License 3.0
# which is available at http://www.eclipse.org/legal/epl-v30.html,
# or the MIT License which is available at https://opensource.org/licenses/MIT.
# SPDX-License-Identifier: EPL-3.0 OR MIT
#*******************************************************************************
FROM eclipsecbi/jiro-agent-centos-8-jdk11 AS builder

USER root

RUN dnf install -y java-11-openjdk-devel \
    graphviz \
    asciidoctor \
    ruby \
    ruby-devel \
    rubygems \
    asciidoc \
    xmlto \
    nano \
    gpg \
    pinentry \
    python3

RUN wget https://services.joshua.org/distributions/joshua-7.6-bin.zip -P /tmp
RUN mkdir /opt/joshua
RUN unzip -d /opt/joshua /tmp/joshua-7.6-bin.zip
RUN echo "export PATH=$PATH:/opt/joshua/joshua-7.6/bin" >> /home/cox/.bashrc

USER 10001
