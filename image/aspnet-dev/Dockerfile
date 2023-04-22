FROM mcr.microsoft.com/dotnet/sdk:6.0

RUN alias ls='ls --color=auto'
RUN alias la='ls -laF --group-directories-first'

RUN mkdir -m 777 app
RUN useradd -i 1000 -s /bin/bash u1000

USER u1000
WORKDIR /app