# Dwi Okta Ramadhani
# TI.24.A.1

# "Program Menampilkan Daftar Nilai Mahasiswa"
# Deskripsi Program
Program Sederhana dengan Python Menggunakan Class
Program ini dibuat dengan bahasa pemrograman Python dan menggunakan konsep class. Class di sini berfungsi sebagai tempat untuk menyimpan data dan berbagai aksi yang akan dilakukan pada data tersebut. Di dalam class, kita bisa mendefinisikan berbagai macam data dan fungsi untuk mengolah data.
```

Apa itu Class?
Class itu seperti cetakan atau blueprint. Dari class ini,
kita bisa membuat objek-objek yang memiliki data dan fungsi yang sudah ditentukan sebelumnya.
```

Fitur-Fitur Program:
    Menambah Data: Menambah data baru ke dalam sistem.
    Menampilkan Data: Menampilkan data yang sudah ada.
    Menghapus Data: Menghapus data yang ada.
    Mengubah Data: Mengubah data yang sudah ada.
    Keluar: Keluar dari program.
Dengan menggunakan class, program ini bisa lebih terorganisir dan mudah untuk mengelola data.
``

## Flowchart Program
![Flowchart](https://github.com/Dwiokta10/lab8py./blob/main/flowchartlab8.png)
# Kode Program
```python
class DaftarNilaiMahasiswa:
    def _init_(self):
        # Menyimpan data dalam bentuk dictionary, dengan NIM sebagai key
        self.data = {}

    def tambah(self, nim, nama, nilai_tugas, nilai_uts, nilai_uas):
        if nim in self.data:
            print(f"Data dengan NIM {nim} sudah ada.")
        else:
            # Menghitung nilai akhir berdasarkan bobot
            nilai_akhir = (nilai_tugas * 0.30) + (nilai_uts * 0.35) + (nilai_uas * 0.35)
            self.data[nim] = {
                'nama': nama,
                'nilai_tugas': nilai_tugas,
                'nilai_uts': nilai_uts,
                'nilai_uas': nilai_uas,
                'nilai_akhir': nilai_akhir  # Menyimpan nilai akhir dalam bentuk persentase
            }
            print(f"Data dengan NIM {nim}, nama {nama}, dan nilai tugas {nilai_tugas}, UTS {nilai_uts}, UAS {nilai_uas} berhasil ditambahkan.")

    def tampilkan(self):
        if not self.data:
            print("Belum ada data yang ditambahkan.")
        else:
            print("\n===========================================")
            print("Daftar Nilai Mahasiswa:")
            print("===========================================")
            # Menampilkan header
            print(f"{'NIM':<12} {'Nama':<20} {'Tugas':<8} {'UTS':<8} {'UAS':<8} {'Nilai Akhir':<12}")
            print("-------------------------------------------")
            for nim, info in self.data.items():
                # Menampilkan NIM, Nama, nilai tugas, nilai UTS, nilai UAS, dan nilai akhir
                print(f"{nim:<12} {info['nama']:<20} {info['nilai_tugas']:<8} {info['nilai_uts']:<8} {info['nilai_uas']:<8} {info['nilai_akhir']:<12.2f}")
            print("===========================================")

    def hapus(self, nim):
        if nim in self.data:
            del self.data[nim]
            print(f"Data dengan NIM {nim} berhasil dihapus.")
        else:
            print(f"Data dengan NIM {nim} tidak ditemukan.")

    def ubah(self, nim, nilai_tugas_baru, nilai_uts_baru, nilai_uas_baru):
        if nim in self.data:
            # Menghitung nilai akhir berdasarkan nilai baru dan bobot
            nilai_akhir_baru = (nilai_tugas_baru * 0.30) + (nilai_uts_baru * 0.35) + (nilai_uas_baru * 0.35)
            self.data[nim]['nilai_tugas'] = nilai_tugas_baru
            self.data[nim]['nilai_uts'] = nilai_uts_baru
            self.data[nim]['nilai_uas'] = nilai_uas_baru
            self.data[nim]['nilai_akhir'] = nilai_akhir_baru
            print(f"Data dengan NIM {nim} berhasil diubah dengan nilai tugas {nilai_tugas_baru}, UTS {nilai_uts_baru}, dan UAS {nilai_uas_baru}. Nilai akhir: {nilai_akhir_baru:.2f}.")
        else:
            print(f"Data dengan NIM {nim} tidak ditemukan.")


# Contoh penggunaan program
if _name_ == "_main_":
    daftar_nilai = DaftarNilaiMahasiswa()
    
    while True:
        print("\nMenu:")
        print("1. Tambah data")
        print("2. Tampilkan data")
        print("3. Hapus data")
        print("4. Ubah data")
        print("5. Keluar")
        
        pilihan = input("Pilih menu (1-5): ")
        
        if pilihan == "1":
            nim = input("Masukkan NIM: ")
            nama = input("Masukkan nama: ")
            nilai_tugas = float(input("Masukkan nilai tugas: "))
            nilai_uts = float(input("Masukkan nilai UTS: "))
            nilai_uas = float(input("Masukkan nilai UAS: "))
            daftar_nilai.tambah(nim, nama, nilai_tugas, nilai_uts, nilai_uas)
        elif pilihan == "2":
            daftar_nilai.tampilkan()
        elif pilihan == "3":
            nim = input("Masukkan NIM yang akan dihapus: ")
            daftar_nilai.hapus(nim)
        elif pilihan == "4":
            nim = input("Masukkan NIM yang akan diubah: ")
            nilai_tugas_baru = float(input("Masukkan nilai tugas baru: "))
            nilai_uts_baru = float(input("Masukkan nilai UTS baru: "))
            nilai_uas_baru = float(input("Masukkan nilai UAS baru: "))
            daftar_nilai.ubah(nim, nilai_tugas_baru, nilai_uts_baru, nilai_uas_baru)
        elif pilihan == "5":
            print("\nProgram selesai. TERIMAKASIH.")
            break
        else:
            print("Pilihan tidak valid. Silakan coba lagi.")

```
# Output Program
```
"c:/Users/acer/Documents/KULIAH/PEMROGRAMAN/Praktikum 8/classdftrmhs.py"

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan NIM: 312410012
Masukkan nama: Amanda
Masukkan nilai tugas: 90
Masukkan nilai UTS: 95
Masukkan nilai UAS: 96
Data dengan NIM 312410012, nama Amanda, dan nilai tugas 90.0, UTS 95.0, UAS 96.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan NIM: 312410071
Masukkan nama: Hoshi
Masukkan nilai tugas: 98
Masukkan nilai UTS: 94
Masukkan nilai UAS: 90
Data dengan NIM 312410071, nama Hoshi, dan nilai tugas 98.0, UTS 94.0, UAS 90.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan NIM: 312419876
Masukkan nama: Uzumaki
Masukkan nilai tugas: 87
Masukkan nilai UTS: 90
Masukkan nilai UAS: 93
Data dengan NIM 312419876, nama Uzumaki, dan nilai tugas 87.0, UTS 90.0, UAS 93.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan NIM: 312418752
Masukkan nama: Uciha
Masukkan nilai tugas: 89
Masukkan nilai UTS: 94
Masukkan nilai UAS: 95
Data dengan NIM 312418752, nama Uciha, dan nilai tugas 89.0, UTS 94.0, UAS 95.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan NIM: 312418743
Masukkan nama: Sasuke
Masukkan nilai tugas: 98
Masukkan nilai UTS: 87
Masukkan nilai UAS: 85
Data dengan NIM 312418743, nama Sasuke, dan nilai tugas 98.0, UTS 87.0, UAS 85.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan NIM: 312413490
Masukkan nama: Gara
Masukkan nilai tugas: 90
Masukkan nilai UTS: 98
Masukkan nilai UAS: 99
Data dengan NIM 312413490, nama Gara, dan nilai tugas 90.0, UTS 98.0, UAS 99.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan NIM: 312410052
Masukkan nama: liana
Masukkan nilai tugas: 99
Masukkan nilai UTS: 98
Masukkan nilai UAS: 95
Data dengan NIM 312410052, nama liana, dan nilai tugas 99.0, UTS 98.0, UAS 95.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan NIM: 312410021
Masukkan nama: Zeje
Masukkan nilai tugas: 89
Masukkan nilai UTS: 90
Masukkan nilai UAS: 96
Data dengan NIM 312410021, nama Zeje, dan nilai tugas 89.0, UTS 90.0, UAS 96.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan NIM: 312410089 
Masukkan nama: Sqoup   
Masukkan nilai tugas: 89
Masukkan nilai UTS: 97
Masukkan nilai UAS: 96
Data dengan NIM 312410089, nama Sqoup, dan nilai tugas 89.0, UTS 97.0, UAS 96.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 2

===========================================
Daftar Nilai Mahasiswa:
===========================================
NIM          Nama                 Tugas    UTS      UAS      Nilai Akhir 
-------------------------------------------
312410012    Amanda               90.0     95.0     96.0     93.85
312410071    Hoshi                98.0     94.0     90.0     93.80
312419876    Uzumaki              87.0     90.0     93.0     90.15
312418752    Uciha                89.0     94.0     95.0     92.85
312418743    Sasuke               98.0     87.0     85.0     89.60       
312413490    Gara                 90.0     98.0     99.0     95.95
312410052    liana                99.0     98.0     95.0     97.25
312410021    Zeje                 89.0     90.0     96.0     91.80
312410089    Sqoup                89.0     97.0     96.0     94.25
===========================================

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 5

Program selesai. TERIMAKASIH.
PS C:\Users\acer\Documents\KULIAH\PEMROGRAMAN\Praktikum 8> 
```
# Diagram Class
```
+-------------------------+
|  DaftarNilaiMahasiswa   |
+-------------------------+
| - data: dict            |
+-------------------------+
| + _init_()            |
| + tambah(nama, nilai)   |
| + tampilkan()           |
| + hapus(nama)           |
| + ubah(nama, nilai_baru)|
+-------------------------+
```

# Cara Kerja Program
1. Inisialisasi Program:
Program dimulai dengan pembuatan objek dari class DaftarNilaiMahasiswa. Kelas ini memiliki atribut self.data, yaitu sebuah dictionary yang digunakan untuk menyimpan data mahasiswa, di mana NIM adalah key dan informasi lainnya adalah value.
2. Menu Pilihan
Program menampilkan menu interaktif untuk memilih aksi:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
3. Proses Berdasarkan Pilihan
Tambah Data (Opsi 1):
Pengguna memasukkan NIM, nama, nilai tugas, nilai UTS, dan nilai UAS.
Program menghitung nilai akhir dan menyimpan data dalam dictionary jika NIM belum ada.
Tampilkan Data (Opsi 2):
Program menampilkan data mahasiswa yang telah disimpan dalam format tabel.
Hapus Data (Opsi 3):
Pengguna memasukkan NIM yang akan dihapus.
Program menghapus data mahasiswa jika NIM ditemukan.
Ubah Data (Opsi 4):
Pengguna memasukkan NIM dan nilai baru untuk tugas, UTS, dan UAS.
Program menghitung ulang nilai akhir dan memperbarui data.
Keluar (Opsi 5):
Program berhenti dan keluar dari loop.
4. Program Berulang
Setelah tiap aksi, menu ditampilkan lagi hingga pengguna memilih untuk keluar.Print "Progam selesai. TERIMAKASIH"
