FROM nginx:latest

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && \
    apt install -y apt-utils && \
    apt install -y iputils-ping && \
    apt install -y net-tools