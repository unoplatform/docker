FROM mcr.microsoft.com/dotnet/core/sdk:3.1.401-focal-arm64v8
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
RUN echo "deb https://download.mono-project.com/repo/ubuntu stable-bionic main" | tee /etc/apt/sources.list.d/mono-official-stable.list
RUN apt-get update

# Install mono, msbuild and dependencies
RUN apt-get -y install sudo unzip python-is-python3 mono-devel msbuild libc6 ninja-build gcc zip

# Workaround for https://github.com/dotnet/sdk/issues/11108
RUN cd /usr/share/dotnet/sdk/3.1.401/Sdks/Microsoft.NET.Sdk.WindowsDesktop/targets && \
        mv Microsoft.WinFx.props Microsoft.WinFX.props && \
        mv Microsoft.WinFx.targets Microsoft.WinFX.targets
