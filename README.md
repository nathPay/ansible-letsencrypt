# ansible-letsencrypt

An easy way to setup enable https with Letsencrypt certificate.

Up to 3 services in one run using `LETSENCRYPT_DOMAIN_NAME_X` and `PROXY_PORT_X` variables.

## How to use it ?

### Install ansible:

On Ubuntu
```
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```

### Modify host:

Modify the `hosts` file by removing `ubuntu@XXX.XXX.XXX.XXX` and adding the address hostname@address of your server. (same as ssh host)

/!\ Don't forget to add your public ssh key to your server `~/.ssh/authorized_keys`

Modify `group_vars/nginx-letsencrypt.yml` with the your email, domain name and port forwarding (using nginx)

### Start ansible:

Use the following command to start script:

`ansible-playbook -i hosts site.yml -K` (the -K is not mandatory, use it only if sudo have a password)

You will need to provide sudo password of your host.

And Voilà!