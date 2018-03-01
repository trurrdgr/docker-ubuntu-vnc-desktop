## docker-ubuntu-vnc-desktop

Docker image to provide HTML5 VNC interface to access Ubuntu 16.04 LXDE desktop environment with added [netboot.xyz](https://netboot.xyz/) iso access in directory `/iso/netboot.xyz.iso`.

Quick Start
-------------------------

Run the docker image and open port `6080`

```
docker run -it --rm -p 6080:80 centminmod/docker-ubuntu-vnc-desktop
```

Browse http://127.0.0.1:6080/

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/lxde.png?v1" width=700/>


Connect with VNC Viewer and protect by VNC Password
------------------

Forward VNC service port 5900 to host by

```
docker run -it --rm -p 6080:80 -p 5900:5900 centminmod/docker-ubuntu-vnc-desktop
```

Now, open the vnc viewer and connect to port 5900. If you would like to protect vnc service by password, set environment variable `VNC_PASSWORD`, for example

```
docker run -it --rm -p 6080:80 -p 5900:5900 -e VNC_PASSWORD=mypassword centminmod/docker-ubuntu-vnc-desktop
```

A prompt will ask password either in the browser or vnc viewer.

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/lxde2.png?v1" width=700/>

## Dell iDRAC 6 IPMI Java Console Usage

Go into IcedTea web panel and lower the `Extended applet security` level for java applets

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-icedtea-web-panel-01.png?v1" width=700/>

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-icedtea-web-panel-02.png?v1" width=700/>

Launch Firefox browser and go to your IPMI web login and add a permenant exception for HTTPS based IPMI login

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-firefox-ipmi-01.png?v1" width=700/>

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-firefox-ipmi-02.png?v1" width=700/>

Launch console and open with `IceTea Java Web Start` + check trust publisher and content.

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-firefox-ipmi-03.png?v1" width=700/>

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-firefox-ipmi-04.png?v1" width=700/>

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-firefox-ipmi-05.png?v1" width=700/>

Answer yes to run java console applet

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-firefox-ipmi-06.png?v1" width=700/>

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-dell-kvm-virtualmedia-02.png?v1" width=700/>

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/dell-idrac-console/docker-ubuntu-vnc-centos7-01.png?v1" width=700/>

Screen Resolution
------------------

Resolution of virtual desktop adapts browser window size when first connecting the server. You may choose a fixed resolution by passing `RESOLUTION` environment variable, for example

```
docker run -it --rm -p 6080:80 -p 5900:5900 -e VNC_PASSWORD=mypassword -e RESOLUTION=1920x1080 centminmod/docker-ubuntu-vnc-desktop
```

## Troubleshooting


1. boot2docker connection issue, https://github.com/fcwu/docker-ubuntu-vnc-desktop/issues/2
2. Screen resolution is fitted to browser's window size when first connecting to the desktop. If you would like to change resolution, you have to re-create the container


## License

See the LICENSE file for details.
