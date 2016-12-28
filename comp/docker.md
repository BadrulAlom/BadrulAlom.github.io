---
layout: default
---

##Ubuntu installation of Docker, 64 bit VirtualBox and Kaggle image

Ok after numerous attempts at fixing issues I think I have become an expert on this, so let me document.

1. Firstly on the off-chance you are here as you've had had repeated issues with getting it to work then first make sure you have uninstalled Oracle VM VirtualBox
You can see what you have installed using:
    dpkg --list

You can then uninstall using:
    sudo apt-get purge virtualbox-5.1

2. Ok now let's re-install Virtual box...64 bit Virtual box. Go to: [the Oracle VirtualBox website](https://www.virtualbox.org/wiki/Linux_Downloads)
Notice this line "if you are running a 64-bit kernel, install the appropriate AMD64 package (it does not matter if you have an Intel or an AMD CPU)."

Do as suggested and install AMD64 bit version of Ubuntu

3. https://docs.docker.com/engine/installation/linux/ubuntulinux/ 
4. http://linuxpitstop.com/install-and-use-command-line-tool-vboxmanage-on-ubuntu-16-04/
5. Run: docker-machine create -d virtualbox --virtualbox-disk-size "50000" --virtualbox-cpu-count "4" --virtualbox-memory "8092" docker2
4. http://blog.kaggle.com/2016/02/05/how-to-get-started-with-data-science-in-containers/   -- for the last step replace the --ip="\*"  with --ip="0.0.0.0"
