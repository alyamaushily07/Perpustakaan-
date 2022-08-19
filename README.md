# Perpustakaan-
C:\Users\ASUS>mysql -u root -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 8
Server version: 10.4.21-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> create database perpus;
Query OK, 1 row affected (0.034 sec)

MariaDB [(none)]> use perpus;
Database changed
MariaDB [perpus]> create table Buku;
ERROR 1113 (42000): A table must have at least 1 column
MariaDB [perpus]> create table Buku(Id_Buku int(12), nama_Buku varchar(100), primary key(Id_Buku), Jenis_Buku varchar(100));
Query OK, 0 rows affected (0.322 sec)

MariaDB [perpus]> insert into Buku(Id__Buku, nama_Buku, Jenis_Buku) values (1,"OmniscientReader", "Fantasy"),
    -> (2,"Suddenly,_I_Became_a_Princess", "Isekai"), (3,"My_S-Class_Hunter", "Action"), (4,"Detective_Conan", "Misteri");
ERROR 1054 (42S22): Unknown column 'Id__Buku' in 'field list'
MariaDB [perpus]> insert into Buku(Id_Buku, nama_Buku, Jenis_Buku) values (1,"OmniscientReader", "Fantasy"),
    ->     -> (2,"Suddenly,_I_Became_a_Princess", "Isekai"), (3,"My_S-Class_Hunter", "Action"), (4,"Detective_Conan", "Misteri");
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '-> (2,"Suddenly,_I_Became_a_Princess", "Isekai"), (3,"My_S-Class_Hunter", "Ac...' at line 2
MariaDB [perpus]>  insert into Buku(Id_Buku, nama_Buku, Jenis_Buku) values (1,"OmniscientReader", "Fantasy"),
    ->     ->     -> (2,"Suddenly_I_Became_a_Princess", "Isekai"), (3,"My_S-Class_Hunter", "Action"), (4,"Detective_Conan", "Misteri");
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '->     -> (2,"Suddenly_I_Became_a_Princess", "Isekai"), (3,"My_S-Class_Hunter...' at line 2
MariaDB [perpus]> insert into Buku(Id_Buku, nama_Buku, Jenis_Buku) values (1,"OmniscientReader", "Fantasy"),(2,"Suddenly_I_Became_a_Princess", "Isekai"), (3,"My_S-Class_Hunter", "Action"), (4,"Detective_Conan", "Misteri");
Query OK, 4 rows affected (0.078 sec)
Records: 4  Duplicates: 0  Warnings: 0

MariaDB [perpus]> select*from Buku;
+---------+------------------------------+------------+
| Id_Buku | nama_Buku                    | Jenis_Buku |
+---------+------------------------------+------------+
|       1 | OmniscientReader             | Fantasy    |
|       2 | Suddenly_I_Became_a_Princess | Isekai     |
|       3 | My_S-Class_Hunter            | Action     |
|       4 | Detective_Conan              | Misteri    |
+---------+------------------------------+------------+
4 rows in set (0.000 sec)

MariaDB [perpus]> insert into Buku(Id__Buku, nama_Buku, Jenis_Buku) values (5,"Detektif_futo","misteri");
ERROR 1054 (42S22): Unknown column 'Id__Buku' in 'field list'
MariaDB [perpus]> insert into Buku(Id_Buku, nama_Buku, Jenis_Buku) values (5,"Detektif_futo","misteri");
Query OK, 1 row affected (0.073 sec)

MariaDB [perpus]> update Buku set Jenis_buku="jepang" where id="5";
ERROR 1054 (42S22): Unknown column 'id' in 'where clause'
MariaDB [perpus]> update Buku set Jenis_buku="jepang" where Id_Buku="5";
Query OK, 1 row affected (0.116 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [perpus]> select*from Buku;
+---------+------------------------------+------------+
| Id_Buku | nama_Buku                    | Jenis_Buku |
+---------+------------------------------+------------+
|       1 | OmniscientReader             | Fantasy    |
|       2 | Suddenly_I_Became_a_Princess | Isekai     |
|       3 | My_S-Class_Hunter            | Action     |
|       4 | Detective_Conan              | Misteri    |
|       5 | Detektif_futo                | jepang     |
+---------+------------------------------+------------+
5 rows in set (0.000 sec)

MariaDB [perpus]> delete from Buku where Id_Buku="5";
Query OK, 1 row affected (0.089 sec)

MariaDB [perpus]> select*from Buku;
+---------+------------------------------+------------+
| Id_Buku | nama_Buku                    | Jenis_Buku |
+---------+------------------------------+------------+
|       1 | OmniscientReader             | Fantasy    |
|       2 | Suddenly_I_Became_a_Princess | Isekai     |
|       3 | My_S-Class_Hunter            | Action     |
|       4 | Detective_Conan              | Misteri    |
+---------+------------------------------+------------+
4 rows in set (0.000 sec)

MariaDB [perpus]> show tables;
+------------------+
| Tables_in_perpus |
+------------------+
| buku             |
+------------------+
1 row in set (0.001 sec)

MariaDB [perpus]>
MariaDB [perpus]> Createcreate table Petugas(Id_Petugas int(12), Nama varchar(100), primary key(Id_Petugas));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'Createcreate table Petugas(Id_Petugas int(12), Nama varchar(100), primary key...' at line 1
MariaDB [perpus]> create table Buku(Id_Buku int(12), nama_Buku varchar(100), primary key(Id_Buku), Jenis_Buku varchar(100));
ERROR 1050 (42S01): Table 'buku' already exists
MariaDB [perpus]> create table Petugas(Id_Petugas int(12), Nama varchar(100), primary key(Id_Petugas));
Query OK, 0 rows affected (0.276 sec)
MariaDB [perpus]> update Petugas set Nama ="Ayla" where Id_Petugas="103";
Query OK, 1 row affected (0.067 sec)
Rows matched: 1  Changed: 1  Warnings: 0

MariaDB [perpus]> Select * from Petugas;
+------------+-------+
| Id_Petugas | Nama  |
+------------+-------+
|        100 | Putri |
|        101 | Putra |
|        102 | Alya  |
|        103 | Ayla  |
+------------+-------+
4 rows in set (0.000 sec)

MariaDB [perpus]> create table Anggota(Id_Anggota int(12), Nama varchar(100));
Query OK, 0 rows affected (0.403 sec)

MariaDB [perpus]> insert into Anggota(Id_Anggota, Nama) values (201, "Riskha"), (202,"Nadya"), (203,"Aryo"), (204,"Izar");
Query OK, 4 rows affected (0.054 sec)
Records: 4  Duplicates: 0  Warnings: 0

MariaDB [perpus]>  Select * from Anggota;
+------------+--------+
| Id_Anggota | Nama   |
+------------+--------+
|        201 | Riskha |
|        202 | Nadya  |
|        203 | Aryo   |
|        204 | Izar   |
+------------+--------+
4 rows in set (0.000 sec)

MariaDB [perpus]> show tables;
+------------------+
| Tables_in_perpus |
+------------------+
| anggota          |
| buku             |
| petugas          |
+------------------+
3 rows in set (0.001 sec)
