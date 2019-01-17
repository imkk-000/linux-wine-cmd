# Command for install wine
```sh
# install wine
dpkg --add-architecture i386
apt install -y gnupg wget
wget -nc https://dl.winehq.org/wine-builds/winehq.key
apt-key add winehq.key
echo 'deb https://dl.winehq.org/wine-builds/ubuntu/ bionic main' | tee /etc/apt/sources.list.d/wine.list
apt update
apt install -y --install-recommends winehq-stable

# download winetricks
cd "${HOME}/Downloads"
wget https://raw.githubusercontent.com/Winetricks/winetricks/master/src/winetricks
chmod +x winetricks

# download wine-mono
# link: https://wiki.winehq.org/Mono

# install dotnet 11, 40
WINEARCH=win32 WINEPREFIX=~/.wine32 sh winetricks dotnet40
WINEARCH=win32 WINEPREFIX=~/.wine32 sh winetricks dotnet11
```
