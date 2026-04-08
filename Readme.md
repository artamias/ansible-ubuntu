# Report Provisioning menggunakan ansible

1. Struktur Directory
- group_vars  = konfigurasi semua package, versi, maupun repository yang bisa di update dan disesuaikan
- inventory   = menyimpan target host yang akan di eksekusi
- roles       = berisi konfigurasi tasks yang dijalankan
- ansible.cfg = menyimpan konfigurasi ansible secara global
- site.yml    = menjalankan semua tasks yang ada di dir "roles"

2. Running task ansible
Jalankan semua
- ansible-playbook site.yml

Hanya menjalankan PHP
- ansible-playbook site.yml --tags php

Hanya menjalankan nodejs
- ansible-playbook site.yml --tags nodejs

Hanya menjalankan Nginx
- ansible-playbook site.yml --tags nginx

Hanya menjalankan MariaDB
- ansible-playbook site.yml --tags mariadb

Hanya menjalankan Postgresql
- ansible-playbook site.yml --tags postgresql

Hanya menjalankan Supabase
- ansible-playbook site.yml --tags supabase

Hanya menjalankan redis
- ansible-playbook site.yml --tags redis

Hanya menjalankan rabbitmq
- ansible-playbook site.yml --tags rabbitmq

Hanya menjalankan docker
- ansible-playbook site.yml --tags docker

4. Sudah include dengan pembuatan laravel beserta konfigurasi nginx

3. NOTE
karena menginstall portainer yang berjalan di port 8000, di docker compose Supabase (supabase-kong) mengganti port menjadi 8001 dan 8444

kong:
container_name: supabase-kong
ports:
    - 8001:8000/tcp # ganti bind port-nya
    - 8444:8443/tcp # ganti bind port-nya