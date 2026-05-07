1. Struktur Directory

- group_vars = konfigurasi semua package, versi, maupun repository yang bisa di update dan disesuaikan
- inventory = menyimpan target host yang akan di eksekusi
- roles = berisi konfigurasi tasks yang dijalankan
- ansible.cfg = menyimpan konfigurasi ansible secara global
- site.yml = menjalankan semua tasks yang ada di dir "roles"

2. Running task ansible
   Jalankan semua

- ansible-playbook site.yml -K

Hanya menjalankan PHP

- ansible-playbook site.yml --tags php -K

Hanya menjalankan nodejs

- ansible-playbook site.yml --tags nodejs -K

Hanya menjalankan Nginx

- ansible-playbook site.yml --tags nginx -K

Hanya menjalankan MariaDB

- ansible-playbook site.yml --tags mariadb -K

Hanya menjalankan Postgresql

- ansible-playbook site.yml --tags postgresql -K

Hanya menjalankan Supabase

- ansible-playbook site.yml --tags supabase -K

Hanya menjalankan redis

- ansible-playbook site.yml --tags redis -K

Hanya menjalankan rabbitmq

- ansible-playbook site.yml --tags rabbitmq -K

Hanya menjalankan docker

- ansible-playbook site.yml --tags docker -K
