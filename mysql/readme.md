# Конфигурирование MySQL
### 1. Создание нового пользователя
```shell
$ mysql -u database_main_user -p # Авторизовываемся в клиенте mysql

# NEXT STEPS VIA MYSQL CLIENT
$ CREATE DATABASE `database_name`;
$ CREATE USER 'user_name'@'localhost' IDENTIFIED BY 'GENERATED_PASSWORD';
$ GRANT ALL PRIVILEGES ON database_name . * TO 'user_name'@'localhost';
$ FLUSH PRIVILEGES;
```

### 2. Простое конфигурирование mysql
```shell
# В файл конфигурации mysql в секцию innodb:
set-variable = innodb_buffer_pool_size=250M 
set-variable = innodb_additional_mem_pool_size=50M 
set-variable = innodb_file_io_threads=8 
set-variable = innodb_lock_wait_timeout=50 
set-variable = innodb_log_buffer_size=8M 
set-variable = innodb_flush_log_at_trx_commit=0 
```

### 3. Temp folder (если много памяти ОЗУ)
```shell
$ mkdir /mnt/tmpfs/
$ chmod 777 /mnt/tmpfs/
$ sudo mount -t tmpfs -o size=SIZE_MEMORY_M tmpfs /mnt/tmpfs/
```


