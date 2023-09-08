# Infrastructure as code, laboratory work :)

## Vagrant, развернуть виртуалки

### Первичная установка vagrant и virtualbox
Если у вас Ubuntu 22.04 выполните `sudo apt install vagrant virtualbox-qt virtualbox linux-generic-hwe-22.04`, эта команда установит всё необходимое, в том числе ядро со всеми модулями.

Добавить себя в группу `sudo usermod -a -G vboxusers $(whoami)`

Перезагрузка.

### Запуск виртуалок

Образ centos 8 я качал с оф. сайта.

Добавить образ:

```sh
vagrant box add centos/8 path/to/file
```

Запуск:

```sh
vagrant up
```

## Ansible

### Первичная установка

Для работы необходим модуль venv (если ubuntu 22.04 то `sudo apt install python3.10-venv`)

- Первичная инициализация: `make init`
- Если ничего не работает: `make reset`

`source ./venv/bin/activate` для активации venv.

`deactivate` ну вы поняли.

### Запуск плейбука

Перед запуском плейбука убедитесь что можете попасть на хосты по ssh

```sh
./default_playbook.yml -Kk
```

Пароль от ssh по умолчанию `vagrant`
