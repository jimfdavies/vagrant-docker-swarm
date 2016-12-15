Introduction
============

The Vagrantfile and boot script init.sh in this repo are to help you to set up
the [Docker Engine Swarm tutorial](https://docs.docker.com/engine/swarm/swarm-tutorial/).
   
Three virtual machines will be created and configured
as [described here](https://docs.docker.com/engine/swarm/swarm-tutorial/#/set-up).

Note that Docker is installed using Centos 7 as the base VM image and Docker's own
install script is used.

Pre-requisites
--------------
* [Vagrant](https://www.vagrantup.com/docs/installation/) (and allow Vagrant to install VirtualBox for you)

Setup
-----

    cd <your local code directory>
    git clone https://github.com/jimfdavies/vagrant-docker-swarm.git
    cd vagrant-docker-swarm
    vagrant up

Usage
-----
The three running VMs are named ```manager1```, ```worker1``` and ```worker2```.

SSH into ```manager1```:

    vagrant ssh manager1

Obtain the IP from the Private Network (should be on ```eth1``` and 172.28.128.X/24)

    ip addr show eth1

You can now follow the Docker Swarm tutorial [from here](https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm/).

To SSH into the workers:

    vagrant ssh worker1
    vagrant ssh worker2

When you're finished, log out of the SSH sessions and stop:

    vagrant halt

...or destroy the VMs.

    vagrant destroy
