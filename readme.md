dpkg --add-architecture i386
apt install -y gnupg wget
wget -nc https://dl.winehq.org/wine-builds/winehq.key
apt-key add winehq.key
echo 'deb https://dl.winehq.org/wine-builds/ubuntu/ bionic main' | tee /etc/apt/sources.list.d/wine.list
apt update
apt install -y --install-recommends winehq-stable
