# Epitech Workshop Vagrant - Part 0

## Some links

What | Link
--- | ---
Vagrant Documentation | https://developer.hashicorp.com/vagrant/docs

## Installation

### Linux

#### Debian/Ubuntu

```bash
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install vagrant
```

#### MacOS

Find someone to do it with you, it's a great time to make friends!
