CEPH Hands-on Lab

Лаба тестировалась в следующем окружении:
ubuntu20.04 + Virtualbox + Vagrant
WIN10 + Virtualbox + Vagrant и gitbash

Для добавления дисков в VM необходимо экспортировать переменную disks, проще всего через git bash:
export VAGRANT_EXPERIMENTAL="disks"

Для запуска в windows необходимо экспортировать переменную VAGRANT_HOME:
export VAGRANT_HOME=/d/Vagrant

Также в Vagrantfile после строк 
# -*- mode: ruby -*-
# vi: set ft=ruby :

Добавить строки с кодировкой:
Encoding.default_external = Encoding.find('Windows-1251')
Encoding.default_internal = Encoding.find('Windows-1251')
