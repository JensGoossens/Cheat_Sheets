#Vagrant
Vagrant commando's 
 
 Functie| Commando
 ----------| -------------------
 Toevoegen van een bestand aan vagrant| ```vagrant box add -name "naam die je wilt geven" "Naam Box"```
 Toevoegen vagrant toestel aan in virtualbox directory| ```vagrant init "naam die je gekozen hebt"```
 Toevoegen machine aan virtualbox en machine laten draaien | ```vagrant up```
 Overzicht over de vm's die aanstaan | ```vagrant status```
 Inloggen via vagrant op uw machine via ssh | ```vagrant ssh```
 Vagrant file wegdoen (je kan ze ook zo proper houden) | ```vagrant destroy -f```
 Machine opslaan maar niet afsluiten |```vagrant suspend```
 Machine volledig uitschakelen | ```vagrant halt```
 Weten hoe je uw virtuele machine hebt genoemt |  ```vagrant boxlist```
 Wijzigingen in vagrantfile snel toevoegen | ```vim vagrantfile```
 Wijzigingen doorvoeren in draaiende machine | ```vagrant provision```

#Ansible
##Database installeren + aanmaken

Deze code komt in `main.yml` in de map `db`.

```- name: Install MySQL 
  yum: pkg={{item}} state=installed
  with_items:
    - mariadb
    - mariadb-server
    - MySQL-python

- name: Start MySQL service
  service: name=mariadb state=running enabled=yes

- name: Create application database
  mysql_db: name={{dbname}} state=present

- name: Create application database user
  mysql_user: name={{dbuser}} password={{dbpasswd}}
                priv=*.*:ALL host='localhost' state=present```

##Install Apache

Deze code komt in `main.yml` in de map `web`.

```- name: Install Apache 
  yum: pkg={{item}} state=installed
  with_items:
    - httpd
    - php
    - php-xml
    - php-mysql

- name: Start Apache service
  service: name=httpd state=running enabled=yes

- name: Enable firewalld
  service: name=firewalld state=started enabled=yes 

- name: Configure firewall
  firewalld: service={{item[0]}} state=enabled permanent={{ item[1] }} 
  with_nested:
    - [ http,https ]
    - [ true,false ]

- name: Install unzip
  yum: pkg=unzip state=latest 

- name: Unzip WordPress
  unarchive: src=wordpress.zip dest=/var/www/html```
