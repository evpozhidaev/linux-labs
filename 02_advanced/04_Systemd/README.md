## Темы
Изучение системы инициализации linux на примере systemd  

Эксурс в sysV init  
Архитектура systemd (utilities, daemons, targets, core, libraries)
Systemd targets levels  


## Практика
systemd-analyze blame  
systemctl isolate target.name  
Написать unit-файл сервиса, который будет запускать bash-скрипт (скрипт каждые 10 секунд пишет с помощью logger сообщения в messages)  
Создать unit-файл сервиса который можно запускать в нескольких экземплярах  

## Статьи по теме
[Systemd wikipedia](https://ru.wikipedia.org/wiki/Systemd)  
[Systemd manual](https://wiki.archlinux.org/title/Systemd_(%D0%A0%D1%83%D1%81%D1%81%D0%BA%D0%B8%D0%B9))  
[Learning to love systemd](https://opensource.com/article/20/4/systemd)  
Ленард Паттеринг - Systmd for Administrator
