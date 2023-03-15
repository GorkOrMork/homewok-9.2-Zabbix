# Домашнее задание к занятию "9.2. Zabbix" - Вебер Сергей


### Задание 1

1 Установка репозитория Zabbix

# wget https://repo.zabbix.com/zabbix/6.4/debian/pool/main/z/zabbix-release/zabbix-release_6.4-1+debian11_all.deb
# dpkg -i zabbix-release_6.4-1+debian11_all.deb
# apt update

2 Установка Zabbix сервера, веб-интерфейса и агента

# apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-nginx-conf zabbix-sql-scripts zabbix-agent

3 Создание базы данных

# sudo -u postgres createuser --pwprompt zabbix
# sudo -u postgres createdb -O zabbix zabbix

4 На хосте Zabbix сервера импортирую начальную схему и данные

# zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix

5 Запуск процессов Zabbix сервера и агента

# systemctl restart zabbix-server zabbix-agent nginx php7.4-fpm
# systemctl enable zabbix-server zabbix-agent nginx php7.4-fpm


![image](https://user-images.githubusercontent.com/109193124/225293440-5881c8ca-b823-4f60-8b01-3c001f257c12.png)

![image](https://user-images.githubusercontent.com/109193124/225293532-7325149d-4b96-4179-9cd3-33edf633d3cc.png)


### Задание 2

1 Установка репозитория

#wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bubuntu22.04_all.deb
#dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
#apt update

2 Установка Zabbix-агента

#apt install zabbix-agent

3 Рестарт сервиса и добавление в загрузку systemd

#systemctl restart zabbix-agent
#systemctl enable zabbix-agent

![image](https://user-images.githubusercontent.com/109193124/225293807-2106b632-db1c-485e-b65d-5a4b7366f005.png)

![image](https://user-images.githubusercontent.com/109193124/225293866-8c13a1b4-c0ac-401d-b00c-06cfaa4f39ac.png)

![image](https://user-images.githubusercontent.com/109193124/225293951-0ceeece1-619f-4b2e-9316-5739f98e7ca9.png)

