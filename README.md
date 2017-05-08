docker-ubuntu-vnc-desktop
=========================

Docker image to provide HTML5 VNC interface to access Ubuntu 16.04 LXDE desktop environment.

Quick Start
-------------------------

Run the docker image and open port `6080`

```
docker run -it --rm -p 6080:80 centminmod/ubuntu-desktop-lxde-vnc
```

Browse http://127.0.0.1:6080/

<img src="https://raw.github.com/centminmod/docker-ubuntu-vnc-desktop/master/screenshots/lxde.png?v1" width=700/>


Connect with VNC Viewer and protect by VNC Password
------------------

Forward VNC service port 5900 to host by

```
docker run -it --rm -p 6080:80 -p 5900:5900 centminmod/ubuntu-desktop-lxde-vnc
```

Now, open the vnc viewer and connect to port 5900. If you would like to protect vnc service by password, set environment variable `VNC_PASSWORD`, for example

```
docker run -it --rm -p 6080:80 -p 5900:5900 -e VNC_PASSWORD=mypassword centminmod/ubuntu-desktop-lxde-vnc
```

A prompt will ask password either in the browser or vnc viewer.


Troubleshooting
==================

1. boot2docker connection issue, https://github.com/fcwu/docker-ubuntu-vnc-desktop/issues/2


License
==================

See the LICENSE file for details.
