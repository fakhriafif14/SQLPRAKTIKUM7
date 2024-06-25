# SQLpraktikum7
```
NIM     : 312310632
NAMA    : Fakhri Afif 
KELAS   : TI.23.A6
MATKUL  : BASIS DATA
```


# Sub Query
## Latihan

![image](praktikum7/ss1.png)

### ERD

![image](praktikum7/ss7.png)


![image](praktikum7/ss8.png)


## TABEL DAN INPUT DATA

#### TABEL KARYAWAN
![image](praktikum7/ss3.png)

#### TABEL DEPARTEMEN
![image](/praktikum7/s2.png)

#### TABEL PERUSAHAAN
![image](praktikum7/ss4.png)

#### TABEL PROJECT
![image](praktikum7/ss5.png)

#### TABEL PROJECT_DETAIL
![image](praktikum7/ss6.png)

### MENGIDENTIFIKASI QUERY

Berikut adalah contoh query SQL NYA:


-- Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika
```sql
SELECT k1.*
FROM karyawan k1
JOIN karyawan k2 ON k1.id_dept = k2.id_dept
WHERE k2.nama = 'Dika';
```

output :


![image](praktikum7/ss9.png)


-- Tampilkan data karyawan yang gajinya lebih besar dari rata-rata gaji semua karyawan. Urutkan menurun berdasarkan besaran gaji.
```sql
SELECT *
FROM karyawan
WHERE gaji_pokok > (SELECT AVG(gaji_pokok) FROM karyawan)
ORDER BY gaji_pokok DESC;
```

output :


![image](praktikum7/ss10.png)



-- Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di departemen yang sama dengan karyawan dengan nama yang mengandung huruf 'K'.
```sql
SELECT k.nik, k.nama
FROM karyawan k
JOIN departemen d ON k.id_dept = d.id_dept
WHERE d.id_dept IN ( SELECT id_dept FROM karyawan WHERE nama LIKE '%K%' );
```

output :


![image](praktikum7/ss11.png)



-- Tampilkan data karyawan yang bekerja pada departemen yang ada di kantor pusat.
```sql
SELECT k.*
FROM karyawan k
JOIN departemen d ON k.id_dept = d.id_dept
WHERE d.id_p = 'P01';
```

output :


![image](praktikum7/ss12.png)


-- Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di departemen yang sama dengan karyawan dengan nama yang mengandung huruf 'K' dan gajinya lebih besar dari rata-rata gaji semua karyawan.
```sql
SELECT nik, nama
FROM karyawan 
WHERE nama = 'Dika';
```


output :


![image](praktikum7/ss13.png)



Pastikan untuk menyesuaikan nama tabel dan kolom dengan struktur tabel yang sebenarnya dalam database Anda.
