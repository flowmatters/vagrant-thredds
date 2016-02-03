vagrant-thredds
===============

THREDDS Data Server in a Vagrant VM

What You'll need
================

1. Vagrant
2. VirtualBox
3. Disk space and memory for a VM

Usage
=====

Start the Vagrant machine with 'vagrant up'.

Put thredds.war file in ./webapps to install into Tomcat 7. Alternatively, leave it and the war will be downloaded at provisioning time.

Put data under `content/thredds/public/testdata`, or modify `content/thredds/catalog.xml` to point somewhere else. The data will need to be visible to the VM (eg by mapping a directory in the Vagrantfile).

localhost:8080 is mapped by the Vagrantfile to the running Tomcat in the VM.

Notes from vagrant-tomcat
=========================

I've used the 'bento/fedora-21' box, because that's what I had to hand. Fork and change if you need, it should work with any RHL / Centos / Fedora (if you change the references to yum into dnf).

It uses Puppet to install the tools.

Port mapping is done in the Vagrantfile.

Anything in the ./webapps, ./log, and ./conf folders isn't committed to Git, so the VM should stay small and can be readily destroyed at will (although I've not yet tested this... it's quite likely the conf folder will get overwritten)


