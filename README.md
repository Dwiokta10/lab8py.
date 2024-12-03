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
