Dokumentasi Otomatisasi Jaringan di SMKN1 Magelang Menggunakan Ansible

Tips untuk menjalankan
--limit     : untuk menjalankan pada perangkat tertentu (panggil berdasarkan inventory)
--diff      : untuk menunjukkan perbedaan dari sebelum dan sesudah
-v          : verbose, untuk debugging
--tags      : menjalankan yang ada tags tersebut saja
--skip-tags : menjalankan yang tidak ada tags tersebut


1. Menjalankan normal semuanya
ansible-playbook playbook/site.yml

2. Menjalankan playbook untuk pengujian skalabilitas
2.a. 5 buah
ansible-playbook playbook/site.yml --limit BLOK_EIL
2.b. 10 Buah
ansible-playbook playbook/site.yml --limit "BLOK_EIL, BLOK_SER"
2.c. 15 Buah
pakai cara normal

3. Menjalankan playbook untuk pengujian keandalan sistem

4. Menjalankan playbook untuk pengujian modulartias
