FROM node:20-bullseye

RUN /bin/echo -e "\n\
    alias ls='ls --color=auto'\n\
    alias la='ls -laF --group-directories-first'\n\
    alias egrep='egrep --color=auto'\n\
    alias fgrep='fgrep --color=auto'\n\
    alias grep='grep --color=auto'\n\
    " | tee -a /root/.bashrc /home/node/.bashrc