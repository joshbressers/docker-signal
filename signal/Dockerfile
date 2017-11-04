FROM debian
ADD https://updates.signal.org/desktop/apt/keys.asc /root/signal-key.asc
ADD signal-xenial.list /root/signal-xenial.list
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y gnupg apt-transport-https libasound2
RUN apt-key add /root/signal-key.asc

# We do this here because the base image lacks the https transport for apt
RUN cp /root/signal-xenial.list /etc/apt/sources.list.d/signal-xenial.list
RUN apt-get update
RUN apt-get install -y signal-desktop
CMD signal-desktop
