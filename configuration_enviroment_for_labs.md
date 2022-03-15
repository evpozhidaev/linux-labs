# Настройка окружения для лабараторных работ

Для лабораторных работ используется связка Virtualbox + Vagrant

https://www.vagrantup.com/docs/index 
https://learn.hashicorp.com/tutorials/vagrant/getting-started-index

https://terminalblues.dev/LVM-Lab-Setup-With-VirtualBox  
 
Устанвока box'а локально:
vagrant box add box_name file:///d:/path/to/file.box
Ошибка с кодировкой:
TO DO
1. Установите переменную окружения VAGRANT_HOME , например 'c:\HashiCorp';
2. В файле C:\HashiCorp\Vagrant\embedded\gems\2.2.3\gems\vagrant-2.2.3\bin\vagrant после #!/usr/bin/env добавить две строки:
Encoding.default_external = Encoding.find('Windows-1251')
Encoding.default_internal = Encoding.find('Windows-1251')
