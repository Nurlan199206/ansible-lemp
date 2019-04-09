# nginx-php-fpm installation on CentOS 6/7 or Ubuntu 18.04/Debian9

You need minimum 1GB RAM for succesfully run playbook.

Software version.

Ansible 2.7.5

Ubuntu 18.04

php 7.0/7.1/7.2/7.3

nginx 1.14

mysql  Ver 14.14 Distrib 5.7.25,



run command: 

yum install git ansible mc python2-PyMySQL -y

or

apt update && apt install git ansible mc -y
mkdir /etc/ansible/roles

for Debian like distros

git clone https://github.com/Nurlan199206/ansible-lemp

and

ansible-playbook --connection=local -s /etc/ansible/roles/ansible-lemp/nginx.yml



for successfully run playbook, dont forget add in /etc/ansible/ansible.cfg after [defaults]

invalid_task_attribute_failed=False

=========*PHP-Version check*==========
For change PHP versions change ```/etc/nginx/sites-available/default```

```fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;``` to ```php7.1``` or ```7.3``` or create hosts for every php versions

