FROM nginx:latest

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && \
    apt install -y apt-utils && \
    apt install -y iputils-ping && \
    apt install -y net-tools

ARG KTVERSION_FILE="/sbin/ktversion"

RUN echo "#!/usr/bin/env bash" > $KTVERSION_FILE && \
    echo -n "echo " >> $KTVERSION_FILE && \
    echo "$(nginx -v 2>&1 | awk 'BEGIN{ FS="[ /]"; }{ printf("%s\n", $4);}')" >> $KTVERSION_FILE && \
    chmod +x $KTVERSION_FILE

