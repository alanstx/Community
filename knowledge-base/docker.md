## Docker and Docker Compose installation manual

Source website: https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/

**0. Open terminal.**

**1. Uninstall old versions of Docker:**
```
$ sudo apt-get remove docker docker-engine docker.io
```

**2. Update the apt package index:**
```
$ sudo apt-get update
```

**3. Install packages to allow apt to use a repository over HTTPS:**
```
$ sudo  apt-get install \
        apt-transport-https \
        ca-certificates \
        curl \
        software-properties-common
```

**4. Add Docker’s official GPG key:**
```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Alternative way(in case of emergency):
Open following URL in browser(Chrome, if possible): https://download.docker.com/linux/ubuntu/gpg
```
$ cat DownloadedGpgFilePath | sudo apt-key add - 
```

**5. Verify that you now have the key using last 8 characters of the fingerprint:**
```
$ sudo apt-key fingerprint 0EBFCD88
```

You should get something like this:
```
pub   4096R/0EBFCD88 2017-02-22
      Key fingerprint = 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid                  Docker Release (CE deb) <docker@docker.com>
sub   4096R/F273FCD8 2017-02-22
```

**6. Use the following command to set up the stable repository:** 
```
$ sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"
```

**7. Install Docker CE:**
```
$ sudo apt-get update
```

If any errors occur, force using IPv4 by adding "-o Acquire::ForceIPv4=true update":
```
$ sudo apt-get update -o Acquire::ForceIPv4=true update
```

Next step:
```
$ sudo apt-get install docker-ce
```

As before, if any errors occured, force using IPv4:
```
$ sudo apt-get install docker-ce -o Acquire::ForceIPv4=true update
```

**8. Verify that Docker CE is installed correctly by running the hello-world image:**
```
$ sudo docker run hello-world
```

**9. If you don’t want to use sudo when you use the docker command, create a Unix group called docker and add users to it:** 

Create the docker group:
```
$ sudo groupadd docker
```

Add your user to the docker group.
```
$ sudo usermod -aG docker $USER
```

Log out and log back in so that your group membership is re-evaluated.
If testing on a virtual machine, it may be necessary to restart the virtual machine for changes to take affect.

**10. Install Docker Compose**
```
$ sudo apt install docker-compose
```

**11. Setup environment:**

From downloaded source code run:
```
$ docker-compose up
```

and point your browser to [http://localhost:8000](http://localhost:8000) and [http://localhost:4200](http://localhost:4200) 


**12. Enjoy!**

## Alternative method

**0. Open terminal.**

Type in the following commands:
```
$ sudo apt-get install docker
$ sudo apt-get install docker-compose
```

**1. Enjoy!**
