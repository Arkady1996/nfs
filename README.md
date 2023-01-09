Стенд Vagrant с NFS

Цель задания
Научиться самостоятельно разворачивать сервис NFS и подключать к нему клиентов

Описание задания
 
- `vagrant up` должен поднимать 2 настроенных виртуальных машины (сервер NFS и клиента) без дополнительных ручных действий;
 
-  на сервере NFS должна быть подготовлена и экспортирована
директория;
 
- в экспортированной директории должна быть поддиректория с именем __upload__ с правами на запись в неё;
 
- экспортированная директория должна автоматически монтироваться на клиенте при старте виртуальной машины (systemd, autofs или fstab -
любым способом);
 
- монтирование и работа NFS на клиенте должна быть организована с использованием NFSv3 по протоколу UDP;
 
- firewall должен быть включен и настроен как на клиенте, так и на сервере.


Содержимое:

nfss-script.sh - файл для автоматической конфигурации сервера

nfsc-script.sh - файл для автоматической конфигурации клиента

Vagrantfile - файл для создания виртуальных машин


PS
Для тестирования работы добавил запись логов в директории:

/srv/share/upload/server/ (/mnt/upload/client/)
/srv/share/upload/client/ (/mnt/upload/client/)