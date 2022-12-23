FROM kasmweb/core-ubuntu-focal:1.12.0
USER root

ENV HOME /home/kasm-default-profile
ENV STARTUPDIR /dockerstartup
ENV INST_SCRIPTS $STARTUPDIR/install
WORKDIR $HOME

######### Customize Container Here ###########


RUN apt update
RUN apt -y upgrade
RUN apt -y install openvpn
RUN apt -y install git
RUN apt -y install wget
RUN apt -y install terminator
RUN apt -y install firefox
RUN apt-get install netcat -y
COPY assets/kali.png /usr/share/extra/backgrounds/bg_default.png






######### End Customizations ###########

RUN chown 1000:0 $HOME
RUN $STARTUPDIR/set_user_permission.sh $HOME

ENV HOME /home/kasm-user
WORKDIR $HOME
RUN mkdir -p $HOME && chown -R 1000:0 $HOME

USER 1000