### Dokumentasi Otomatisasi Jaringan di SMKN1 Magelang Menggunakan Ansible

------------


**Tips untuk menjalankan**

| imbuhan | penjelasan   |
| ------------ | ------------ |
| `--limit`  |   untuk menjalankan pada perangkat tertentu (panggil berdasarkan inventory) |
| `--diff`  |  untuk menunjukkan perbedaan dari sebelum dan sesudah |
|  `-v  `  |  verbose, untuk debugging |
|  `--tags `  |  menjalankan yang ada tags tersebut saja |
| `--skip-tags `|  : menjalankan yang tidak ada tags tersebut |


------------
##### Penggunaan
1. Menjalankan normal semuanya
`ansible-playbook playbook/site.yml`

2. Menjalankan playbook untuk pengujian skalabilitas
- 5 buah
`ansible-playbook playbook/site.yml --limit BLOK_EIL --tags otomatis`
- 10 Buah
`ansible-playbook playbook/site.yml --limit "BLOK_EIL, BLOK_SER" --tags otomatis`
- 15 Buah
`ansible-playbook playbook/site.yml --tags otomatis"`

3. Menjalankan playbook untuk pengujian keandalan sistem
- Skenario A
`ansible-playbook playbook/site.yml --limit R_EIL --tags dhcp`
- Skenario B
`ansible-playbook playbook/site.yml --limit M_BMO --tags acl`
- Skenario C
`ansible-playbook playbook/site.yml --limit M_SER --tags vlan --skip-tags manual`
- Pemulihan total M_EIL
`ansible-playbook playbook/site.yml --limit M_EIL --tags otomatis`
4. Menjalankan playbook untuk pengujian modulartias
`ansible-playbook playbook/site.yml --tags otomatis`
atau
`ansible-playbook playbook/site.yml --limit BLOK_ALT --tags otomatis`
