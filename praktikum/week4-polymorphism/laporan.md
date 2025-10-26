# **Laporan Praktikum Minggu 4**

**Topik:** Polymorphism dan Overloading

---

## **Identitas**

* **Nama**  : Zakkya Fauzan Alba’asithu
* **NIM**   : 240202890
* **Kelas** : 3IKRA

---

## **Tujuan**

Mahasiswa memahami dan mampu menerapkan konsep **Polymorphism**, **Overriding**, serta **Overloading** dalam program Java menggunakan studi kasus sistem **POS (Point of Sales)** produk pertanian.

---

## **Dasar Teori**

1. **Polymorphism** adalah kemampuan suatu objek untuk memiliki banyak bentuk; method yang sama dapat berperilaku berbeda tergantung objek yang memanggilnya.
2. **Overriding** adalah proses mendefinisikan ulang method pada subclass yang telah ada di superclass dengan implementasi berbeda.
3. **Overloading** adalah mendefinisikan beberapa method dengan nama sama tetapi parameter berbeda dalam satu class.
4. **Dynamic Binding** membuat Java menentukan method mana yang dipanggil berdasarkan tipe objek aktual saat runtime.
5. Polymorphism membuat kode menjadi fleksibel, mudah diperluas, dan mendukung prinsip *Open-Closed* dalam OOP.

---

## **Langkah Praktikum**

1. Buka project **AgriPos** di IDE (IntelliJ/NetBeans).
2. Pastikan sudah terdapat class-class model: `Produk`, `Benih`, `Pupuk`, `AlatPertanian`, dan `ObatHama`.
3. Buat file baru bernama `MainPolymorphism.java` di package `com.upb.agripos`.
4. Tambahkan kode untuk mendemonstrasikan konsep polymorphism, overloading, dan overriding.
5. Jalankan program untuk melihat hasil output perbedaan perilaku tiap objek.
6. Gunakan commit message:

   ```
   Implementasi Polymorphism dan Overloading pada produk pertanian
   ```

---

## **Kode Program**

```java
package com.upb.agripos;

import com.upb.agripos.model.*;
import com.upb.agripos.util.CreditBy;

public class MainPolymorphism {

    public static void main(String[] args) {
        // Membuat array produk (polymorphism)
        Produk[] daftarProduk = new Produk[4];
        daftarProduk[0] = new Pupuk("NPK Super", 75000, 20, "Organik");
        daftarProduk[1] = new Benih("Benih Padi Unggul", 50000, 30, "Padi");
        daftarProduk[2] = new AlatPertanian("Cangkul Baja", 120000, 15, "Menggemburkan tanah");
        daftarProduk[3] = new ObatHama("AntiUlatMax", 60000, 25, "Ulat daun");

        // Menampilkan info semua produk (dynamic binding)
        for (Produk p : daftarProduk) {
            System.out.println(p.getInfo());
        }

        System.out.println("\n=== Demonstrasi Overloading ===");
        daftarProduk[0].tambahStok(10);
        daftarProduk[1].tambahStok(5, true);

        System.out.println("\n=== Setelah Tambah Stok ===");
        for (Produk p : daftarProduk) {
            System.out.println(p.getInfo());
        }

        CreditBy.print("240202890", "Zakkya Fauzan Albaasithu");
    }
}
```

---

## **Hasil Eksekusi**

Contoh hasil output program:

```
Produk: NPK Super
Harga: 75000
Stok: 20
Jenis: Organik

Produk: Benih Padi Unggul
Harga: 50000
Stok: 30
Jenis: Padi

Produk: Cangkul Baja
Harga: 120000
Stok: 15
Kegunaan: Menggemburkan tanah

Produk: AntiUlatMax
Harga: 60000
Stok: 25
Target Hama: Ulat daun

=== Demonstrasi Overloading ===
Tambah stok sebanyak 10 unit berhasil.
Tambah stok 5 unit (dengan notifikasi aktif).

=== Setelah Tambah Stok ===
Produk: NPK Super (stok baru: 30)
Produk: Benih Padi Unggul (stok baru: 35)
Produk: Cangkul Baja (stok tetap: 15)
Produk: AntiUlatMax (stok tetap: 25)

Created by: Zakkya Fauzan Albaasithu (240202890)
```

<img width="1919" height="1079" alt="Screenshot 2025-10-27 010659" src="https://github.com/user-attachments/assets/ce06f247-72a2-4909-a655-46d18d374e5f" />


---

## **Analisis**

* Kode ini menunjukkan **polymorphism**, di mana array `Produk[]` dapat menampung berbagai subclass seperti `Benih`, `Pupuk`, `AlatPertanian`, dan `ObatHama`.
* Method `getInfo()` di setiap subclass menampilkan hasil berbeda sesuai jenis produk (contoh: “Jenis: Organik” atau “Kegunaan: Menggemburkan tanah”).
* Method `tambahStok()` memperlihatkan **overloading** karena memiliki dua versi dengan parameter berbeda.
* Dibanding minggu sebelumnya (inheritance), minggu ini fokus pada bagaimana satu referensi superclass (`Produk`) dapat menampung berbagai bentuk subclass.
* Kendala yang dihadapi: kadang terjadi error *cannot find symbol* karena class subclass belum diimport; diselesaikan dengan pengecekan struktur package dan import statement.

---

## **Kesimpulan**

Dengan menerapkan **Polymorphism**, **Overriding**, dan **Overloading**, program menjadi lebih **fleksibel**, **efisien**, dan **mudah dikembangkan**.
Setiap subclass dapat menampilkan perilaku uniknya meskipun diakses melalui referensi superclass yang sama.

---

## **Quiz**

1. **Apa perbedaan overloading dan overriding?**
   **Jawaban:**
   Overloading terjadi ketika dua atau lebih method memiliki nama sama namun parameter berbeda, sedangkan overriding adalah penggantian implementasi method superclass di subclass.

2. **Bagaimana Java menentukan method mana yang dipanggil dalam dynamic binding?**
   **Jawaban:**
   Java menentukan method berdasarkan **tipe objek sebenarnya** pada saat runtime, bukan berdasarkan tipe referensinya.

3. **Berikan contoh kasus polymorphism dalam sistem POS selain produk pertanian.**
   **Jawaban:**
   Contohnya pada sistem POS restoran, di mana superclass `MenuItem` memiliki subclass seperti `Makanan`, `Minuman`, dan `Dessert`, masing-masing menampilkan detail dan harga berbeda.
