FROM mcr.microsoft.com/dotnet/sdk:5.0.102-1-focal
RUN apt-get update
RUN apt-get -y install gnupg2
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
RUN echo "deb https://download.mono-project.com/repo/ubuntu stable-bionic main" | tee /etc/apt/sources.list.d/mono-official-stable.list
RUN apt-get update

# Install mono, msbuild and dependencies
RUN apt-get -y install sudo unzip python-is-python3 mono-devel msbuild libc6 ninja-build gcc 

# Install node and puppeteer dependencies
RUN curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash - && \
        apt-get update && \
        sudo apt install -y nodejs gconf-service libasound2 libatk1.0-0 libc6 libcairo2 libcups2 \
        libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 \
        libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 \
        libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 \
        libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils wget \
        libgbm-dev libgbm1
