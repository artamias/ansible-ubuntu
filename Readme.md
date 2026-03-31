# Report Provisioning menggunakan ansible

1. Struktur Directory
- site.yml                  = root file untuk menjalanan ansbile
- ansible.cfg               = main konfigurasi ansible secara global
- inventory/host.ini        = menyimpan daftar server yang akan di remote
- group_vars = all.yml      = variable global (php, nginx, linux) yang bisa disesuaikan
- roles/common/main.yml     = instalasi packages linux
- roles/mariadb/main.yml    = instalasi mariadb
- roles/nginx/main.yml      = instalasi nginx
- roles/php/main.yml        = instalasi php multiversion dan composer untuk laravel

2. Running task ansible
# Jalankan semua
- ansible-playbook site.yml

# Hanya menjalankan PHP
- ansible-playbook site.yml --tags php

# Hanya menjalankan Nginx
- ansible-playbook site.yml --tags nginx

# Hanya menjalankan MariaDB
- ansible-playbook site.yml --tags mariadb

3. Berikut yang di isi di group_vars/secrets.yml
# MariaDB root
- vault_mariadb_root_password: "123"

# Mariadb user (laravel)
- vault_mariadb_user_password: "123"