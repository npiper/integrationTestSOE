centos-packer
=============

CentOS 6.5 / 7.0 x64 + Chef + VirtualBox / VMWare for Packer Template

## Packer Build for VirtualBox

```
cd centos6 or centos7
packer validate [ CentOS_6.5.json | CentOS_7.0.json ]
packer build [ -only virtualbox-iso | -only vmware-iso ]  [ CentOS_6.5.json | CentOS_7.0.json ]
```

## Add Vagrant Box

```
box add BOXNAME INSANEWORKS-CentOS-6.5-x86_64-v20141012-virtualbox.box
box add BOXNAME INSANEWORKS-CentOS-7.0-x86_64-v20141012-virtualbox.box
or
box add BOXNAME INSANEWORKS-CentOS-6.5-x86_64-v20141012-vmware.box
box add BOXNAME INSANEWORKS-CentOS-7.0-x86_64-v20141012-vmware.box
```

## Vagrant Cloud

```
mkdir centos
cd centos
vagrant init insaneworks/centos
or
vagrant init insaneworks/centos7
vagrant up
```


## or Public URL Init

```
mkdir centos
cd centos
vagrant init INSANEWORKS-CentOS-6.5-x86_64-v20141012 http://www.insaneworks.co.jp/pub/boxes/INSANEWORKS-CentOS-6.5-x86_64-v20141012-virtualbox.box
vagrant init INSANEWORKS-CentOS-7.0-x86_64-v20141012 http://www.insaneworks.co.jp/pub/boxes/INSANEWORKS-CentOS-7.0-x86_64-v20141012-virtualbox.box
or
vagrant init INSANEWORKS-CentOS-6.5-x86_64-v20141012 http://www.insaneworks.co.jp/pub/boxes/INSANEWORKS-CentOS-6.5-x86_64-v20141012-vmware.box
vagrant init INSANEWORKS-CentOS-7.0-x86_64-v20141012 http://www.insaneworks.co.jp/pub/boxes/INSANEWORKS-CentOS-7.0-x86_64-v20141012-vmware.box
vagrant up
```

## or Edit Vagrantfile (Vagrant 1.5.0 or Higher)

```diff
   # please see the online documentation at vagrantup.com.

   # Every Vagrant virtual environment requires a box to build off of.
-  config.vm.box = "base"
+  config.vm.box = "insaneworks/centos" or "insaneworks/centos7"

   # Create a forwarded port mapping which allows access to a specific port
   # within the machine from a port on the host machine. In the example below,
```

```
vagrant up
```

Enjoy!!
