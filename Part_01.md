# Epitech Workshop Vagrant - Part 1

## Let's start with something simple

### What is Vagrant?

I'll explain quickly.

### First steps

#### Let's create the ssh key

Create it in the folder you want to work in.

We will use the relative path to the key.
```bash
ssh-keygen -f ./.ssh/id_rsa
```

#### Let's create a box

```bash
vagrant box add generic/alpine312
vagrant init generic/alpine312
vagrant up
vagrant ssh
#### After that we will destroy the box
vagrant destroy
```

#### Some problems ? I have some solutions

```bash
sudo systemctl enable --now libvirtd
sudo systemctl enable --now virtnetworkd
```

#### The Vagrantfile

It's a ruby file, so you can use ruby in it.

```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "generic/alpine312"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2
  SHELL
end
```
This allow to create a box with apache2 installed and the port 80 forwarded to the port 8080 of the host.

You can specify a lot of things in the Vagrantfile, you can find the documentation [here](https://developer.hashicorp.com/vagrant/docs/vagrantfile).

