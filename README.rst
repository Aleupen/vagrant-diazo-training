Here are the instructions for setting up the virtual machine that we will work on. 


Instruction on installing Vagrant for the Training
================================================

We rely on Vagrant to give the same development-environment to everyone.

You should do these steps before you come to Amsterdam to find out if they work and to not clog up the wireless there. Mail us if you encounter any problem!

Install and configure Vagrant
-----------------------------

Get the latest version from http://downloads.vagrantup.com for your operating system and install it.

Now your system has a command 'vagrant' that you can run in the terminal.

First create a directory where you want to to the training in

 $ mkdir training
 $ cd training

Download a clean virtual machine (Ubuntu 10.04 Lucid Lynx 32bit). It serves as a basis for your virtual machines and can be reused as often as you like.

 $ vagrant box add base http://files.vagrantup.com/lucid32.box

Setup Vagrant to automatically install the current guest-additions

 $ vagrant gem install vagrant-vbguest

Now extract the files from the attached zip into your training directory. It should now hold the files "README.rst", "Vagrantfile" and "provision.sh"

Start the VM that is configured in "Vagrantfile"

 $ vagrant up

This takes a long while since it not only sets up the VM but also updates your VM, installs various packages needed for diazo-development.

If you have the feeling that something has gone wrong and the installation has not finished correctly for some reason try this:

 $ vagrant provision

In case everything went ok, you can now login to the VM

 $ vagrant ssh

If you use Windows you'll have to login via putty (Install putty and follow the instructions her: http://vagrantup.com/v1/docs/getting-started/ssh.html)

You are now logged in as the user vagrant in /home/vagrant. We do all steps of the training as this user.

We installed Plone for you in the folder /home/vagrant/plone. You can run it now and access it from the browser.

 $ cd plone
 $ ./bin/instance fg

You can now point your browser at http://localhost:8080/Plone and see Plone. This works since the port 8080 is forwarded from the guest-system (the vagrant-ubuntu) to the host-system. The username and the password are both "admin" (Never do this on a production-site!!!).

You can also work on your own machine with your own python, Diazo, Django and Plone if you really want to but please-please-please make sure that you have a system that will work since we don't want to loose any time with installing.

See you in Amsterdam!


Cheers,
Douwe van der Meij
Kim Chee Leong

ps. This how-to for setting up Vagrant is largely copied from a instruction given by Philip Bauer on the Plone Conf 2012 training
