### Ansible Role to setup php,composer and laravel application

This code is tested on the AWS ubuntu machine.

# Requirements
  - Anisble Server - EC2 Ubuntu Instance (Ansible should be installed)
  - PHP Server - EC2 Ubuntu Instance
  - All variables are declared under `group_vars/all.yaml`

# Prerequistie
  - Update inventory file `inventories/dev/hosts`
  - Generate the public key for the user ubuntu `ssh-keygen` on Ansible Server
  - Copy the `id_rsa.pub` from `cd ~./ssh` and paste it on the PHP Server `vi ~/.ssh/authorized_keys` or you can use the priavte key and run this playbook which will automatically copy the public key on the target hosts

# Using Private Key Directly

- Copy the private key on the ansible server
```
chmod 600 nidhi.pem
scp -r -i /Users/nidhi/Documents/devops4solutions/AWS/nidhi.pem /Users/nidhi/Documents/devops4solutions/AWS/nidhi.pem ubuntu@18.219.xxx.xxx:~/.

```
  
# How to Run with private key
```
cd Ansible-playbook
ansible-playbook main.yml -i inventories/dev/hosts --user ubuntu --key-file /home/ubuntu/nidhi.pem

```

# 

# Access the application

Make sure security group of AWS EC2 PHP Server is open for port 80.

```
curl http://publicip

```
