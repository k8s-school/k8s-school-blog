+++
menutitle = "Install Docker"
date = 2018-12-29T17:15:52Z
weight = 8
chapter = false
pre = "<b>- </b>"
+++

# Install Docker

In this session, we will install and setup docker in a simple and easy way on Ubuntu 16.04.

* Add gpg key to aptitude
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

* Add repository
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

* Refresh repository
```
sudo apt-get update
```

* Verify whether docker is available in repo or not
```
sudo apt-cache policy docker-ce
```
```
docker-ce:
  Installed: (none)
  Candidate: 5:18.09.0~3-0~ubuntu-xenial
  Version table:
     5:18.09.0~3-0~ubuntu-xenial 500
...
```

* Install docker
```
sudo apt-get install -y docker-ce
```

* Make sure docker is running
```
sudo systemctl status docker
```
```
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Wed 2018-12-26 17:14:59 UTC; 4min 27s ago
     Docs: https://docs.docker.com
 Main PID: 1191 (dockerd)
    Tasks: 10
   Memory: 76.4M
      CPU: 625ms
   CGroup: /system.slice/docker.service
           └─1191 /usr/bin/dockerd -H unix://
...
```

* Add user to docker group so that this user can execute docker commands.
```
sudo usermod -aG docker ${USER}
```

* Logout the session and login again to refresh the group membership.

* Verify docker by executing info command.
```
docker info |grep 'Server Version'
```
```
Server Version: 18.09.0
```