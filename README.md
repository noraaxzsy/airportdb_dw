# airportdb

Step Create Table:
1. Buka XAMPP dan Start MySQL dan Apache
2. Buka DBEAVER dan lakukan New Database Connection (Ctrl+Shift+N) 
3. Pilih MariaDB dan klik Next
4. Kosongkan isian Database dan Password
5. Klik Finish
6. Buat New SQL Script
7. Lakukan run query menggunakan perintah pada file airport_ddl.sql (total: 14 table)
8. Setelah create table berhasil dibuat lakukan load data pada table 

Folder TSV:
Pada file airport-db yang telah didownload, lakukan extract file pada file .zst agar file tsv didalamnya bisa kita lakukan load data. Untuk mempermudah melakukan load data, kelompokkan file tsv pada 1 folder dan letakkan pada directory yang sama dengan directory folder XAMPP Anda. (e.g. folder XAMPP pada directory D: maka folder tsv_file yang berisi file .tsv diletakkan pada directory D:\tsv_file 

Apabila tidak ingin repot" melakukan extract, Anda bisa mendownload tsv_file pada link g-drive yang telah diupload

Step Load Data:
1. Buka XAMPP dan Start MySQL dan Apache
2. Buka Command Prompt (cmd) pada windows
3. Arahkan directory ke folder bin pada XAMPP Anda (e.g. D:\XAMPP\mysql\bin)
4. Ketik perintah mysql -u root (Anda akan masuk ke MariaDB monitor)
5. Ketik perintah showdatabases;
6. Ketik perintah use airportdb;
7. Ketik perintah LOAD DATA INFILE '/tsv_file/nama_file.tsv' INTO TABLE nama_table FIELDS TERMINATED BY '\t' LINES TERMINATED BY '\n';
8. Lakukan Load Data sesuai dengan urutan table. Apabila table tersebut memiliki foreign key di table lain, maka lakukan load table referensi terlebih dahulu 
9. KHUSUS UNTUK LOAD DATA AIRLINES, sebelumnya terlebih dahulu lakukan perintah SET FOREIGN_KEY_CHECKS = 0; ALTER TABLE AIRLINE ADD FOREIGN KEY (base_airport) REFERENCES airport (airport_id); kemudian lakukan load file data tsv
10. Lakukan Load pada semua file data (estimasi waktu: 3 jam)

<img width="959" alt="image" src="https://github.com/noraaxzsy/airportdb_dw/assets/167008744/4a5a6082-277c-4341-9e87-25f79bf80c07">

Referensi cara lain melakukan Load menggunakan Python (Hanya sekali run):
https://www.linkedin.com/pulse/uploading-airportdb-free-sample-database-from-mysql-local-timbal/ 
