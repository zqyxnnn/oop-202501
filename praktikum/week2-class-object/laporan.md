# **Laporan Praktikum Minggu 1**

**Topik:** *Implementasi Class dan Object pada Java*

---

## **Identitas**

* **Nama:** Zakkya Fauzan Alba’asithu
* **NIM:** 240202890
* **Kelas:** 3IKRA

---

## **Tujuan Praktikum**

* Mempelajari penerapan dasar **pemrograman berorientasi objek (OOP)** pada bahasa Java.
* Mengimplementasikan class dengan konsep **enkapsulasi** untuk menjaga keamanan data.
* Membuat program utama yang menampilkan data produk pertanian menggunakan objek dari class `Produk`.

---

## **Dasar Teori**

1. **Class** adalah rancangan (template) dari objek yang berisi atribut (data) dan method (perilaku).
2. **Object** merupakan hasil instansiasi dari class dan memiliki nilai spesifik untuk setiap atributnya.
3. **Enkapsulasi** adalah teknik penyembunyian data di mana atribut dibuat `private` dan diakses melalui `getter` serta `setter`.
4. **Constructor** digunakan untuk menginisialisasi nilai awal objek saat dibuat.
5. Dengan OOP, kode program menjadi lebih modular, mudah dikembangkan, dan lebih aman dari kesalahan manipulasi data.

---

## **Langkah-Langkah Praktikum**

1. Membuat struktur project dengan package `com.upb.agripos`.
2. Menambahkan sub-package `model` untuk class `Produk`.
3. Menulis atribut `kode`, `nama`, `harga`, dan `stok` dengan modifier `private`.
4. Menambahkan constructor serta method `getter` dan `setter`.
5. Membuat method `tambahStok()` dan `kurangiStok()` untuk pengelolaan stok.
6. Di package utama, membuat class `MainProduk` untuk menampilkan data produk dan identitas pembuat program.
7. Menjalankan program dan memastikan output tampil sesuai harapan.
8. Melakukan commit dengan pesan:

   > “Implementasi class Produk dan MainProduk dengan enkapsulasi serta output identitas.”

---

## **Kode Program**

### `MainProduk.java`

```java
package com.upb.agripos;

import com.upb.agripos.model.Produk;
import com.upb.agripos.util.CreditBy;

public class MainProduk {
    public static void main(String[] args) {
        Produk p1 = new Produk("BNH-001", "Benih Padi IR64", 25000, 100);
        Produk p2 = new Produk("PPK-101", "Pupuk Urea 50kg", 350000, 40);
        Produk p3 = new Produk("ALT-501", "Cangkul Baja", 90000, 15);

        System.out.println("Kode: " + p1.getKode() + ", Nama: " + p1.getNama() + ", Harga: " + p1.getHarga() + ", Stok: " + p1.getStok());
        System.out.println("Kode: " + p2.getKode() + ", Nama: " + p2.getNama() + ", Harga: " + p2.getHarga() + ", Stok: " + p2.getStok());
        System.out.println("Kode: " + p3.getKode() + ", Nama: " + p3.getNama() + ", Harga: " + p3.getHarga() + ", Stok: " + p3.getStok());

        CreditBy.print("240202890", "Zakkya Fauzan Alba'asithu");
    }
}
```

### `Produk.java`

```java
package com.upb.agripos.model;

public class Produk {
    private String kode;
    private String nama;
    private double harga;
    private int stok;

    public Produk(String kode, String nama, double harga, int stok) {
        this.kode = kode;
        this.nama = nama;
        this.harga = harga;
        this.stok = stok;
    }

    public String getKode() { return kode; }
    public void setKode(String kode) { this.kode = kode; }

    public String getNama() { return nama; }
    public void setNama(String nama) { this.nama = nama; }

    public double getHarga() { return harga; }
    public void setHarga(double harga) { this.harga = harga; }

    public int getStok() { return stok; }
    public void setStok(int stok) { this.stok = stok; }

    public void tambahStok(int jumlah) {
        this.stok += jumlah;
    }

    public void kurangiStok(int jumlah) {
        if (this.stok >= jumlah) {
            this.stok -= jumlah;
        } else {
            System.out.println("Stok tidak mencukupi!");
        }
    }
}
```

---

## **Hasil Eksekusi**

Output program di terminal:

```
Kode: BNH-001, Nama: Benih Padi IR64, Harga: 25000.0, Stok: 100
Kode: PPK-101, Nama: Pupuk Urea 50kg, Harga: 350000.0, Stok: 40
Kode: ALT-501, Nama: Cangkul Baja, Harga: 90000.0, Stok: 15
Program ini dibuat oleh: Zakkya Fauzan Alba'asithu (240202890)
```
<img width="743" height="321" alt="Cuplikan layar 2025-10-12 142936" src="https://github.com/user-attachments/assets/a2a94048-e850-4f58-9bd4-6ff6a98762db" />


---

## **Analisis Program**

* Atribut dibuat `private` untuk melindungi data produk agar tidak bisa diubah sembarangan dari luar class.
* Akses terhadap atribut dilakukan melalui `getter` dan `setter`, yang memastikan perubahan data tetap terkontrol.
* Class `MainProduk` berfungsi sebagai titik awal program untuk menampilkan daftar produk dan identitas pembuat.
* Struktur ini mencerminkan prinsip **enkapsulasi dan modularisasi** dalam OOP, yang memudahkan pengembangan aplikasi lebih lanjut seperti sistem inventori, penjualan, atau POS (Point of Sale).

---

## **Kesimpulan**

Dari percobaan ini, mahasiswa memahami penerapan **class**, **object**, dan **enkapsulasi** dalam Java.
Program yang dibuat mampu menampilkan data produk dengan struktur yang rapi dan aman.
Konsep ini menjadi dasar penting untuk membangun sistem informasi dengan arsitektur OOP yang efisien dan mudah dikelola.

---

## **Quiz**

1. **Mengapa atribut sebaiknya dideklarasikan sebagai private dalam class?**
   **Jawaban:**
   Agar data tidak dapat diakses atau dimodifikasi langsung dari luar class. Dengan menjadikannya `private`, akses hanya dapat dilakukan melalui method yang telah disediakan (getter/setter), sehingga data lebih aman dan konsisten.

2. **Apa fungsi getter dan setter dalam enkapsulasi?**
   **Jawaban:**
   Getter berfungsi untuk mengambil (membaca) nilai atribut, sedangkan setter berfungsi untuk mengubah (menulis) nilai atribut. Keduanya memastikan data dapat diakses dengan cara yang terkendali sesuai logika program.

3. **Bagaimana cara class Produk mendukung pengembangan aplikasi POS yang lebih kompleks?**
   **Jawaban:**
   Class `Produk` dapat menjadi dasar dari modul inventori dalam sistem POS. Dengan menambahkan fitur seperti penghitungan total harga, manajemen stok otomatis, dan integrasi dengan transaksi penjualan, class ini dapat dikembangkan menjadi komponen inti dari aplikasi POS yang lebih lengkap.
