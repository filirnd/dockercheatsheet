# Docker cheat sheet
Some useful docker tips and tricks

___


# Table of Contents
- ## [Tips](#tips)
  - [Docker container access to host services](#tip-1)
  - [Install docker on Fedora version >= 32. Cgroup error](#tip-2)

- ## [Useful Images](#images)
  - [Docker image with some useful network tools](#image-1)



___




# Tips <a name="tips"></a>
## Docker container access to host services <a name="tip-1"></a>
From linux host you can access to host services (localhost:port service on host) within a docker container by using special ip `172.17.0.1:<samehostserviceport>`

  ___

## Install docker on Fedora version >= 32. Cgroup error <a name="tip-2"></a>
Guide from https://poweruser.blog/how-to-install-docker-on-fedora-32-f2606c6934f1
- disable cgroups v2 via a kernel parameter:
  ```
  sudo grubby --update-kernel=ALL --args="systemd.unified_cgroup_hierarchy=0"
  reboot
  ```
- disable selinux:
  - Edit the /etc/selinux/config file, run:
  `sudo vi /etc/selinux/config`

  - Set SELINUX to disabled:
  `SELINUX=disabled`

  - Save and close the file in vi/vim. Reboot the Linux system:
  `sudo reboot`
  
  - Follow this instruction to install docker:
  https://docs.docker.com/engine/install/fedora/
  
  - Install docker-compose
  ```
  sudo dnf -y install docker-compose
  ```
  
  
___



# Useful Images <a name="images"></a>
## Docker image with some useful network tools <a name="image-1"></a>
https://hub.docker.com/r/praqma/network-multitool/
