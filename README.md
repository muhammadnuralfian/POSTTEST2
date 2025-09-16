# POSTTEST2
## DESSKRIPSI PROGRAM
Program ini dibuat untuk mengelola jadwal service kendaraan secara sederhana menggunakan bahasa pemrograman Java dengan konsep Object-Oriented Programming (OOP). Sistem ini memungkinkan pengguna untuk menambahkan, melihat, dan menghapus data jadwal service yang berisi informasi seperti nama pelanggan, jenis kendaraan, tanggal service, serta keterangan tambahan.

## Fitur utama
* Operasi CRUD: Program mampu melakukan operasi Create, Read, Update, dan Delete terhadap data jadwal service yang tersimpan.
* Manajemen Data Service: Mengelola informasi lengkap tentang jadwal service kendaraan, termasuk nama pelanggan, jenis kendaraan, tanggal service, dan keterangan tambahan.
* Pencarian Data: Fitur pencarian yang memungkinkan pengguna mencari data service berdasarkan nama pelanggan atau jenis kendaraan (case-insensitive / tidak peduli huruf besar-kecil).
  ## Arsitektur MVC
  * Model: Class Service yang merepresentasikan struktur data jadwal service dengan properti dan constructor.
  * View: Class Main yang menangani tampilan antarmuka pengguna (menu utama) dan input/output.
  * Controller: Class ServiceManager yang menangani logika bisnis dan operasi CRUD.

    ## STRUKTUR PACKAGE
    * package main: Berisi class Main yang menyimpan menu utama pengguna.
    * package service: Menyimpan class ServiceManager dengan logika operasi CRUD.
    * package model: Menyimpan class Service dengan struktur data dan constructor.

    ## Validasi Input
    * hanyaHurufDanSpasi(): Memvalidasi bahwa input hanya mengandung huruf dan spasi (untuk nama pelanggan dan jenis kendaraan).
    * hanyaAngka(): Memvalidasi bahwa input hanya berupa angka (misalnya untuk ID Service).
    * Batas Panjang Input: Membatasi panjang input untuk setiap field (nama pelanggan max 30 karakter, jenis kendaraan max 20 karakter).
    * Format Tanggal: Memastikan input tanggal sesuai format yang benar (misalnya dd/MM/yyyy).
   
    ## Access Modifier & Properties
    * Menggunakan access modifier private untuk properti class, dengan getter dan setter.
    * Terdapat beberapa properti dalam class Service: id, namaPelanggan, jenisKendaraan, tanggalService, dan keterangan.
    * Menerapkan constructor untuk inisialisasi objek Service.
   
    ## Penjelasan Kode main
      <details>
      <summary><h3>Penjelasan Kode Versi Post-Test 2</h3></summary>
        <img width="1099" height="767" alt="Cuplikan layar 2025-09-16 205648" src="https://github.com/user-attachments/assets/2087f769-11d9-4320-bd7f-4b19d534e8e1" />
        Program Main.java berfungsi sebagai entry point sistem manajemen jadwal service kendaraan. Di dalamnya terdapat menu berbasis teks yang memungkinkan pengguna melihat semua jadwal, menambah, mengubah, menghapus, serta mencari jadwal berdasarkan nama pemilik. Objek Service digunakan untuk mengelola data, sementara seedDefault() menambahkan data awal agar daftar tidak kosong. Input pengguna ditangani dengan Scanner, dan validasi menggunakan try-catch memastikan program tetap berjalan meskipun terjadi kesalahan input.
        <img width="1121" height="728" alt="Cuplikan layar 2025-09-16 205700" src="https://github.com/user-attachments/assets/105772ab-bc6b-4955-be84-7e91925293a2" />
        Potongan kode tersebut menangani dua menu utama. Pada case 1, program menampilkan semua jadwal service yang tersimpan menggunakan manager.getAll(). Jika data kosong, muncul pesan “Belum ada data service”, sedangkan jika ada, program menampilkan daftar jadwal secara lengkap. Pada case 2, program memungkinkan pengguna menambah jadwal baru dengan menginput nama pemilik, jenis kendaraan, tanggal service, dan jenis service. Program memeriksa apakah semua input terisi; jika ada yang kosong, muncul peringatan. Jika valid, data baru dibuat dalam objek Model lalu ditambahkan ke daftar melalui manager.add(), dan ditampilkan pesan bahwa jadwal berhasil ditambahkan.
        <img width="1047" height="819" alt="Cuplikan layar 2025-09-16 205713" src="https://github.com/user-attachments/assets/5ee5c08f-4b97-4a0f-b937-ebef9300f6a1" />
        Potongan kode ini menambahkan fitur menu lanjutan. Pada case 3, pengguna bisa mengubah data berdasarkan ID yang dimasukkan, kemudian diproses dengan manager.updateData(). Pada case 4, pengguna bisa menghapus data berdasarkan ID melalui manager.delete(), dengan hasil berupa pesan sukses atau data tidak ditemukan. Pada case 5, program menyediakan pencarian data berdasarkan nama pemilik; jika ditemukan akan ditampilkan seluruh hasil pencarian, jika tidak maka muncul pesan “Tidak ditemukan data.” Pada case 6, program menutup scanner, menampilkan pesan “Terima kasih”, lalu menghentikan program. Jika pengguna memilih menu yang tidak tersedia, bagian default akan menampilkan pesan “Pilihan tidak valid.”
      </details>
      
      ## Penjelasan kode model.java
       <details>
       <summary><h3>Penjelasan Kode Versi Post-Test 2</h3></summary>
       <img width="1047" height="802" alt="Cuplikan layar 2025-09-16 212823" src="https://github.com/user-attachments/assets/bde09e3a-12cc-4d9d-9545-67e7ed3ea5fa" />
       Kode ini mendefinisikan class Model sebagai representasi data utama dalam program. Class ini memiliki atribut seperti id, owner, vehicleType, date, dan serviceType. Nilai id dibuat otomatis menggunakan counter agar setiap data baru memiliki identitas unik. Konstruktor digunakan untuk menginisialisasi data ketika objek dibuat, sementara getter dan setter dipakai untuk mengambil atau mengubah nilai atribut. Method toString() berfungsi menampilkan data dalam format yang rapi sehingga mudah dibaca saat dicetak ke layar. Dengan demikian, class ini berperan sebagai blueprint atau cetakan data yang dikelola program.
       </details>

     ## Penjelasan kode service.java
     <details>
           <summary><h3>Penjelasan Kode Versi Post-Test 2</h3></summary>
         <img width="1168" height="732" alt="Cuplikan layar 2025-09-16 213755" src="https://github.com/user-attachments/assets/7abc5521-222b-4054-900f-e955145188d3" />
         Kode tersebut merupakan class Service yang berfungsi untuk mengelola data layanan/service. Class ini memiliki beberapa fungsi utama: menyimpan data dalam ArrayList, menyediakan data default melalui method seedDefault(), menambah data dengan add(), mengambil semua data dengan getAll(), menghapus data berdasarkan ID dengan delete(), serta mencari data berdasarkan ID dengan findById(). Intinya, class ini bertindak sebagai penyimpan dan pengelola data untuk aplikasi service kendaraan.
          <details>


  
           
     
