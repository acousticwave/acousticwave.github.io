---
title: "Google Chrome Remote Desktop on Ubuntu 20.04"
excerpt: "Setting up Chrome-Remote-Desktop on Ubuntu 20.04"

categories:
  - Blog
tags:
  - Blog
last_modified_at: 2021-05-23T17:00:00-05:00
---



## 1. Installing Chrome on Ubuntu 20.04

- Enter the following command in a terminal to get an install file

```
$ wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```

- Install the package via dpkg

```
$ sudo dpkg -i google-chrome-stable_current_amd64.deb
```



## 2. Headless

- Run Chrome browser and move to `https://remotedesktop.google.com/headless`, then you will face "**Set up another computer**" as shown in the following Figure

![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-remote-1.png)

([Image Link](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-remote-1.png))

- Click "Begin" button
- Click the Debian Linux link to download deb package for installation of Chrome-Remote-Desktop

![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-remote-2.png)

([Image Link](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-remote-2.png))

- Install the dowloaded deb package

```
$ sudo dpkg -i ~/Downloads/Chrome-remote-desktop_current_amd64.deb
$ sudo apt-get -f install
```

- Click "Next" button
- Click "Authorize" button

![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-remote-3.png)

([Image Link](![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-remote-3.png)))

- Copy the Debian Linux command and paste it in a terminal. It will ask you PIN Numbers and this will be required to make a connection beween the remote PC and other PC

![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-remote-4.png)

([Image Link](![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-remote-4.png)))

- Now, your remote PC is ready to make a connection!



## 3. Make a Remote Connection

- On your other PC (in my case, on my Macbook), open Chrome browser and remote-desktop extensio

![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-mac-1.png)

([Image Link](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-mac-1.png))

- Click the your remote PC and put the defined PIN numbers
- It will ask you Xsession or Ubuntu

![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-mac-2.png)

([Image Link](![](https://github.com/acousticwave/acousticwave.github.io/blob/master/assets/images/2021-05-23-chrome-remote-desktop-ubuntu-20-04-mac-2.png)))

- Both will not directly show status displayed on you remote PC



## 4. Make a Connection with Ubuntu Desktop (Teamviewer like)

- Download monkeypatching for Ubuntu20.04 ([chrome_remote_desktop_monkeypatching_20.04.sh](https://jehyunlee.github.io/2020/04/08/Python-General-4-ChromeRemoteDesktopLinux/chrome_remote_desktop_monkeypatching_20.04.sh))

- chmod +x

  ```
  $ chmode +x chrome_remote_desktop_monkeypatching_20.04.sh
  ```

- Stop Chrome-remote-desktop

  ```
  $ /opt/google/chrome-remote-desktop/chrome-remote-desktop --stop
  ```

- Run monkeypatching

  ```
  $ sudo ./chrome_remote_desktop_monkeypatching_20.04.sh
  ```

- Start Chrome-remote-desktop

  ```
  $ /opt/google/chrome-remote-desktop/chrome-remote-desktop --start
  ```

- Now, if you make a connection, it will show ubuntu desktop like Teamviewer.



## References

- [Setting up Chrome remote desktop for Ubuntu 20.04](https://goodtogreate.tistory.com/entry/%ED%81%AC%EB%A1%AC-%EC%9B%90%EA%B2%A9%EB%8D%B0%EC%8A%A4%ED%81%AC%ED%83%91-Ubuntu-2004%EC%97%90%EC%84%9C-%EC%84%A4%EC%A0%95) (in Korean)
- https://jehyunlee.github.io/2020/04/08/Python-General-4-ChromeRemoteDesktopLinux

