# Sistem Manajemen Stok Restoran - Warung Makan Barokah

## 📋 Deskripsi Proyek
Proyek ini merupakan **Study Case Praktikum OOP** yang mengimplementasikan konsep-konsep Object Oriented Programming (OOP) menggunakan bahasa **Java**.  
Sistem ini dirancang untuk mengelola stok menu di sebuah warung makan kecil bernama **Warung Makan Barokah**.

Fokus utama proyek ini adalah:
- Demonstrasi **Inheritance**
- **Polymorphism** (method overriding & abstract class)
- **Encapsulation** dengan validasi data
- Penggunaan **array** dan **Scanner** untuk interaksi dengan user

---

## 🎯 Tujuan Pembelajaran
- Memahami konsep **Abstract Class** dan **Method Abstract**
- Mengimplementasikan **Inheritance** antar kelas menu
- Menggunakan **Polymorphism** melalui overriding method `tampilkanInfo()`, `getKategori()`, dan `getKeterangan()`
- Menerapkan **Encapsulation** dengan setter yang memiliki validasi
- Membuat program berbasis menu (menu-driven program)

---

## 📁 Struktur Proyek

StokRestoran/
└── stok/
    ├── MainStokRestoran.java
    └── menu/
        ├── MenuRestoran.java
        ├── Makanan.java
        ├── Minuman.java
        └── Dessert.java
---

## 🏗️ Penjelasan Class

### 1. `MenuRestoran.java` (Abstract Class)
- **Superclass** untuk semua jenis menu
- Berisi atribut protected: `id`, `nama`, `stok`, `harga`
- Memiliki setter dengan **validasi** (nama tidak boleh kosong, stok tidak boleh negatif, harga > 0)
- Method umum: `tambahStok()`, `kurangiStok()`, `isStokHabis()`
- Method abstract wajib di-override:
  - `getKategori()`
  - `getKeterangan()`

### 2. Subclass yang Meng-extend `MenuRestoran`

| Class       | Atribut Tambahan       | Keterangan Tambahan                  |
|-------------|------------------------|--------------------------------------|
| `Makanan`   | `jenisHidangan`        | Nasi, Mie, Lauk, Sayur, dll         |
| `Minuman`   | `dingin` (boolean)     | Dingin/Ek atau Panas                 |
| `Dessert`   | `rasa`                 | Coklat, Vanilla, Strawberry, dll    |

Semua subclass meng-override:
- `getKategori()`
- `getKeterangan()`
- `tampilkanInfo()` (menambahkan detail spesifik)

---

## ✨ Fitur yang Tersedia

1. **Tampilkan semua menu & stok**
2. **Cari menu berdasarkan ID**
3. **Tampilkan menu per kategori** (Makanan / Minuman / Dessert)
4. **Tambah stok** menu tertentu
5. **Kurangi stok** (simulasi penjualan) + hitung pendapatan
6. **Tampilkan menu stok menipis** (stok ≤ 5)
7. **Tampilkan menu stok habis**

---

## 🚀 Cara Menjalankan Program

### Persiapan
1. Pastikan sudah terinstall **JDK 8** atau lebih baru
2. Compile semua file Java

### Cara Compile & Run

```bash
# Masuk ke folder stok
cd StokRestoran/stok

# Compile semua file
javac -d . menu/*.java MainStokRestoran.java

# Jalankan program
java stok.MainStokRestoran
