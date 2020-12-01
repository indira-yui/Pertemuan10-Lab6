_________________________________________________________________________________

# LAB 6

![Latihan 1](gambar/gambar1.jpg) <br>

Pada tugas LAB 6, saya akan membuat sebuah program menambahkan data ke sebuah list dengan sistem library root yang nantinya akan seperti ini. <br>


## Langkah - Langkah
* Membuat file library root-nya dengan nama folder yaitu (data) <br>

![New Folder](gambar/gambar2.jpg) <br>

![New Folder](gambar/gambar3.jpg) <br>

* Lalu, membuat file python dengan nama (lab6.py) atau bisa juga memberikan nama lainnya <br>

![File Python](gambar/gambar4.jpg) <br>

Setelah itu, coding file tersebut dengan syntax seperti di bawah ini : <br>

```python
data = []
data = {}

def tambah():
        print("=======Tambah Data=======")
        nama    =input("Nama                :  ")
        nim     =input("Nim                 :  ")
        tugas   =int(input("Masukan Nilai Tugas :  "))
        uts     =int(input("Masukan Nilai UTS   :  "))
        uas     =int(input("Masukan Nilai UAS   :  "))
        akhir   = (0.30 * tugas) + (0.35 * uts) + (0.35 * uas)
        data[nama] = nim ,tugas, uts, uas, akhir

def lihat():
    if data.items():
        print("=======Daftar Nilai Mahasiswa=======")
        print("================================================================================================")
        print(" |NO   |     NAMA      |    NIM    |     TUGAS    |     UTS     |       UAS    |    AKHIR     | ")
        print("================================================================================================")
        i=0
        for x in data.items():
            i+=1
            print(" | {6:2}  |  {0:12s} | {1:9s} | {2:11}  | {3:11} | {4:11}  |  {5:11} |".format(x[0], x[1][0], x[1][1], x[1][2], x[1][3], x[1][4], i))
            print("============================================================================================")
    else:
        print("=======Daftar Nilai Mahasiswa======")
        print("================================================================================================")
        print(" |NO   |     NAMA      |    NIM    |     TUGAS    |     UTS     |       UAS    |    AKHIR     | ")
        print("================================================================================================")
        print("|                                      TIDAK ADA DATA                                         |")
        print("===============================================================================================")

def ubah():
        print('=======Ubah Data Mahasiswa=======')
        nama = input('Nama                :  ')
        if nama in data.keys():
            nim     =input('Nim                 :  ')
            tugas   =int(input("Masukan Nilai Tugas :  "))
            uts     =int(input("Masukan Nilai UTS   :  "))
            uas     =int(input("Masukan Nilai UAS   :  "))
            akhir   =(0.30 * tugas) + (0.35 * uts) + (0.35 * uas)
            data[nama] = nim, tugas, uts, uas, akhir
        else:
            print("Data Nilai Tidak Ada".format(nama))

def hapus():
        print("=======Hapus Data Mahasiswa=======")
        nama=input("Nama :  ")
        if nama in data.keys():
            del data[nama]
        else:
            print("Data Nilai Tidak Ada".format(nama))

```
Jika sudah memasukan semua syntax diatas jangan di-run terlebih dahulu nanti file tersebut akan rusak/tidak dapat dijalankan dan hasilnya akan error. <br>

* Selanjutnya, membuat file python tetapi di luar folder (data) untuk menjalankan file sebelumnya di-coding. File yang telah dibuat berikan nama (main.py) karena akan menjadi file yang akan menjalankan file library root yang telah dibuat sebelumnya <br>

![File Python](gambar/gambar5.jpg) <br>

* Lanjutkan dengan coding file tersebut dengan syntax seperti di bawah ini : <br>

```python
from data import lab6

print("PROGRAM MENAMPILKAN DAFATR NILAI MAHASISWA")
while True:
    print("")
    c =input("(L)lihat, (T)ambah, (U)bah, (H)apus, (K)eluar : ")
    if c.lower() == 't':
        lab6.tambah()

    elif c.lower() == 'u':
        lab6.ubah()

    elif c.lower() == 'l':
        lab6.lihat()

    elif c.lower() == 'h':
        lab6.hapus()

    elif c.lower() == 'k':
        print("Keluar")
        break

```

Terlihat di awal terdapat syntax seperti ini: <br>
```
from data import lab6
```

Singkat penjelasan, fungsinya untuk menjalankan file library rootnya yaitu dari folder bernama (data) untuk membuka file (lab6.py). Jika sudah save dan run. Outputnya akan terlihat seperti di bawah ini. <br>

![Output](gambar/gambar6.jpg) <br>

___________________________________________________________________________________________________