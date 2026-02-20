# RadarBox24 Feeder packages for:</br>- Raspberry Pi OS (arm64 and armhf)</br>- Debian amd64</br>- Ubuntu amd64

RBFeeder is a ADS-B client software used by [AirNav](https://www.radarbox.com/) 
to decode Mode S messages and send to our processing servers.

You can find more information about usage in [RadarBox](https://www.radarbox.com/) website.

This software is based on open-source softwares provided by 
Oliver Jowett (mutability) [dump1090-mutability](https://github.com/mutability/dump1090)
 and [FlightAware dump1090-fa](https://github.com/flightaware/dump1090)

It is designed to build as a Debian package, but should also be buildable on
many other Linux or Unix-like systems.

protobuf-c-compiler libncurses-dev libjansson-dev libglib2.0-dev libprotobuf-c-dev libcurl4-openssl-dev dh-sysuser devscripts librtlsdr-dev

## Building under bullseye

```bash
$ git clone https://github.com/abcd567a/rbfeeder.git

$ cd rbfeeder

$ sudo apt-get install build-essential fakeroot debhelper librtlsdr-dev pkg-config dh-systemd libncurses5-dev protobuf-c-compiler libjansson-dev libglib2.0-dev libprotobuf-c-dev libcurl4-openssl-dev dh-sysuser devscripts librtlsdr-dev
$ dpkg-buildpackage -b --no-sign
```

## Building under Debian (bookworm, trixie, and forky)

```bash
$ sudo apt update 
$ sudo apt install git debhelper dh-sysuser protobuf-c-compiler \
                 libncurses5-dev libncursesw5-dev libjansson-dev \
                 libprotobuf-c-dev libcurl4-openssl-dev librtlsdr-dev \
                 build-essential dh-autoreconf dpkg-dev libev-dev \
                 libudns-dev pkg-config libglib2.0-dev sysuser-helper 


$ sudo reboot

$ git clone --depth 1 https://github.com/abcd567a/rbfeeder.git
$ cd rbfeeder
$ sudo dpkg-buildpackage -b 
```

## Building under Ubuntu (jammy and noble)

```bash
$ sudo apt update 
$ sudo apt install git debhelper dh-sysuser protobuf-c-compiler \
                 libncurses5-dev libncursesw5-dev libjansson-dev \
                 libprotobuf-c-dev libcurl4-openssl-dev librtlsdr-dev \
                 build-essential dh-autoreconf dpkg-dev \
                 libev-dev libudns-dev \
                 pkg-config libglib2.0-dev sysuser-helper

Only on Noble: $ sudo apt install libgcc-14-dev libpcre3-dev librtlsdr2
Only on Jammy: $ sudo apt install librtlsdr0 

$ sudo reboot

$ git clone --depth 1 https://github.com/abcd567a/rbfeeder.git
$ cd rbfeeder
$ sudo dpkg-buildpackage -b 

```

## INSTALLING

```bash
$ sudo dpkg -i rbfeeder_1.0.20_*.deb

$ sudo usermod -aG plugdev rbfeeder

$ sudo wget -O /etc/udev/rules.d/rtl-sdr.rules https://github.com/abcd567a/temp/raw/main/rtl-sdr.rules

$ sudo reboot 

```

</br>

</br>

</br>


