# Dwi Okta Ramadhani
# TI.24.A.1

# "Program Menampilkan Daftar Nilai Mahasiswa"
# Deskripsi Program
Program sederhana ini dibuat menggunakan bahasa python Dictionary dengan fitur:

Pengguna untuk mengelola data mahasiswa, termasuk menambah, mengubah, menghapus, dan menampilkan nilai mahasiswa
## Flowchart Program
![Flowchart](https://github.com/Dwiokta10/Praktikum7/blob/main/flowchat%20Praktikum%207.png)
# Kode Program
```python
# Daftar nilai mahasiswa
mahasiswa = {}

# Fungsi untuk menambah data
def tambah(nama, nilai):
    mahasiswa[nama] = nilai
    print(f"Data mahasiswa {nama} dengan nilai {nilai} telah ditambahkan.")

# Fungsi untuk menampilkan data
def tampilkan():
    if mahasiswa:
        print("Daftar Mahasiswa dan Nilai:")
        for nama, nilai in mahasiswa.items():
            print(f"Nama: {nama}, Nilai: {nilai}")
    else:
        print("Tidak ada data mahasiswa.")

# Fungsi untuk menghapus data berdasarkan nama
def hapus(nama):
    if nama in mahasiswa:
        del mahasiswa[nama]
        print(f"Data mahasiswa {nama} telah dihapus.")
    else:
        print(f"Mahasiswa dengan nama {nama} tidak ditemukan.")

# Fungsi untuk mengubah data berdasarkan nama
def ubah(nama, nilai_baru):
    if nama in mahasiswa:
        mahasiswa[nama] = nilai_baru
        print(f"Data mahasiswa {nama} telah diubah menjadi nilai {nilai_baru}.")
    else:
        print(f"Mahasiswa dengan nama {nama} tidak ditemukan.")

# Menu untuk interaksi dengan pengguna
def menu():
    while True:
        print("\nMenu:")
        print("1. Tambah Data")
        print("2. Tampilkan Data")
        print("3. Hapus Data")
        print("4. Ubah Data")
        print("5. Keluar")
        pilihan = input("Pilih menu (1/2/3/4/5): ")

        if pilihan == '1':
            nama = input("Masukkan nama mahasiswa: ")
            nilai = input("Masukkan nilai mahasiswa: ")
            tambah(nama, nilai)
        elif pilihan == '2':
            tampilkan()
        elif pilihan == '3':
            nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
            hapus(nama)
        elif pilihan == '4':
            nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
            nilai_baru = input("Masukkan nilai baru: ")
            ubah(nama, nilai_baru)
        elif pilihan == '5':
            print("Keluar dari program.")
            break
        else:
            print("Pilihan tidak valid. Silakan coba lagi.")

# Menjalankan program
menu()

```
# Output Program
```
PS C:\Users\acer\Documents\KULIAH\PEMROGRAMAN\Pratikum 7> python -u "c:\Users\acer\Documents\KULIAH\PEMROGRAMAN\Pratikum 7\daftarnilaimhs.py"

Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 1
Masukkan nama mahasiswa: Adila
Masukkan nilai mahasiswa: 98
Data mahasiswa Adila dengan nilai 98 telah ditambahkan.

Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 1
Masukkan nama mahasiswa: Indira
Masukkan nilai mahasiswa: 90
Data mahasiswa Indira dengan nilai 90 telah ditambahkan.

Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 1
Masukkan nama mahasiswa: Maya
Masukkan nilai mahasiswa: 98
Data mahasiswa Maya dengan nilai 98 telah ditambahkan.

Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 1
Masukkan nama mahasiswa: Andi
Masukkan nilai mahasiswa: 98
Data mahasiswa Andi dengan nilai 98 telah ditambahkan.

Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 1
Masukkan nama mahasiswa: Yandi
Masukkan nilai mahasiswa: 96
Data mahasiswa Yandi dengan nilai 96 telah ditambahkan.

Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 1
Masukkan nama mahasiswa: Pelisa
Masukkan nilai mahasiswa: 98
Data mahasiswa Pelisa dengan nilai 98 telah ditambahkan.

Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 2
Daftar Mahasiswa dan Nilai:
Nama: Adila, Nilai: 98
Nama: Indira, Nilai: 90
Nama: Maya, Nilai: 98
Nama: Andi, Nilai: 98
Nama: Yandi, Nilai: 96
Nama: Pelisa, Nilai: 98

Menu:
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Pilih menu (1/2/3/4/5): 5
Keluar dari Program, Terimakasih.
PS C:\Users\acer\Documents\KULIAH\PEMROGRAMAN\Pratikum 7> 

``` 
# Cara Kerja Program
1. *Inisialisasi*:
   - Program dimulai dengan mendeklarasikan dictionary kosong mahasiswa untuk menyimpan data mahasiswa.

2. *Menu Utama*:
   - Program menampilkan menu interaktif yang memungkinkan pengguna untuk memilih salah satu dari lima opsi:
     - *Tambah Data*: Menambah data mahasiswa baru ke dalam dictionary.
     - *Tampilkan Data*: Menampilkan seluruh daftar mahasiswa beserta nilai mereka.
     - *Hapus Data*: Menghapus data mahasiswa berdasarkan nama.
     - *Ubah Data*: Mengubah nilai mahasiswa berdasarkan nama.
     - *Keluar*: Keluar dari program.

3. *Fungsi-fungsi Utama*:
   - *tambah(nama, nilai)*: Fungsi ini digunakan untuk menambah data mahasiswa ke dalam dictionary. Nama mahasiswa menjadi key, dan nilai mahasiswa menjadi value.
   - *tampilkan()*: Fungsi ini menampilkan seluruh data mahasiswa dalam dictionary. Jika dictionary kosong, program akan memberi pesan bahwa tidak ada data mahasiswa.
   - *hapus(nama)*: Fungsi ini menghapus data mahasiswa berdasarkan nama yang diberikan. Jika nama ditemukan, data akan dihapus; jika tidak, program memberi pesan bahwa nama tersebut tidak ditemukan.
   - *ubah(nama, nilai_baru)*: Fungsi ini mengubah nilai mahasiswa berdasarkan nama. Jika nama ditemukan, nilai mahasiswa akan diperbarui dengan nilai baru yang diberikan.

4. *Proses Pengguna*:
   - Pengguna akan dipandu melalui menu untuk memilih tindakan yang ingin dilakukan.
   - Setelah memilih tindakan, pengguna akan diminta untuk memasukkan data yang diperlukan (nama mahasiswa dan nilai).
   - Setelah selesai dengan tindakan yang dipilih, program akan kembali menampilkan menu utama.
   - Program akan terus berjalan hingga pengguna memilih opsi "Keluar" untuk keluar dari aplikasi.
