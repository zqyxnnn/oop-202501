# Laporan Praktikum Minggu 3

---

# **Topik:** Inheritance (Pewarisan dalam Pemrograman Berorientasi Objek)

---

## **Identitas**

* **Nama**  : Zakkya Fauzan Alba’asithu
* **NIM**   : 240202890
* **Kelas** : 3IKRA

---

## **Tujuan**

Mahasiswa memahami konsep *inheritance* (pewarisan) dalam pemrograman berorientasi objek (OOP) dan dapat mengimplementasikan pewarisan antar kelas pada sistem informasi produk pertanian seperti *Benih*, *Pupuk*, dan *Alat Pertanian*.

---

## **Dasar Teori**

1. **Inheritance (pewarisan)** adalah mekanisme OOP yang memungkinkan sebuah class mewarisi atribut dan method dari class lain (superclass).
2. **Superclass** adalah class induk yang menyediakan atribut dan method yang dapat digunakan kembali oleh subclass.
3. **Subclass** adalah class turunan yang mewarisi atribut dan method dari superclass serta dapat menambahkan atau mengubah perilakunya sendiri.
4. **Polymorphism** memungkinkan pemanggilan method yang sama menghasilkan output berbeda tergantung objeknya.
5. **Code reusability** menjadi keuntungan utama dari inheritance karena mengurangi duplikasi kode.

---

## **Langkah Praktikum**

1. Buka project Java bernama **AgriPos** di IDE (misalnya IntelliJ IDEA atau NetBeans).
2. Pastikan struktur package sesuai:

   ```
   com.upb.agripos
   com.upb.agripos.model
   com.upb.agripos.util
   ```
3. Buat file `MainInheritance.java` di package `com.upb.agripos`.
4. Tambahkan kode berikut untuk mengimplementasikan konsep inheritance antara `Produk` (superclass) dan subclass `Benih`, `Pupuk`, `AlatPertanian`.
5. Jalankan program untuk menampilkan deskripsi setiap produk dan identitas pembuat.
6. Gunakan commit message:

   ```
   Implementasi Inheritance pada produk pertanian
   ```

---

## **Kode Program**

```java
package com.upb.agripos;

import com.upb.agripos.model.*;
import com.upb.agripos.util.CreditBy;

public class MainInheritance {
    public static void main(String[] args) {
        Benih benih = new Benih("BNH-001", "Benih Padi IR64", 25000, 100, "IR64");
        Pupuk pupuk = new Pupuk("PPK-101", "Pupuk Urea", 350000, 40, "Urea");
        AlatPertanian alat = new AlatPertanian("ALT-501", "Cangkul Baja", 90000, 15, "Baja");

        System.out.println(benih.deskripsi());
        System.out.println(pupuk.deskripsi());
        System.out.println(alat.deskripsi());

        CreditBy.print("240202890", "Zakkya Fauzan Alba'asithu");
    }
}
```

---

## **Hasil Eksekusi**

Contoh output di terminal:

```
Produk: Benih Padi IR64
Kode: BNH-001
Harga: 25000
Stok: 100
Jenis Benih: IR64

Produk: Pupuk Urea
Kode: PPK-101
Harga: 350000
Stok: 40
Jenis Pupuk: Urea

Produk: Cangkul Baja
Kode: ALT-501
Harga: 90000
Stok: 15
Material: Baja

Created by: Zakkya Fauzan Alba’asithu (240202890)
```

<img width="1919" height="1079" alt="Screenshot 2025-10-27 005242" src="https://github.com/user-attachments/assets/d113cf6f-4bcc-483c-a28d-956fda8ea144" />


---

## **Analisis**

* Kode di atas memanfaatkan **inheritance** untuk menghubungkan class `Produk` (superclass) dengan `Benih`, `Pupuk`, dan `AlatPertanian` (subclass).
* Masing-masing subclass meng-*override* method `deskripsi()` dari superclass untuk menampilkan informasi spesifik produknya.
* Dibandingkan minggu sebelumnya (misalnya saat membahas *encapsulation*), minggu ini program menjadi lebih efisien karena tidak perlu menduplikasi atribut dan method umum pada setiap kelas produk.
* Kendala yang sempat muncul adalah *error import package*, yang diatasi dengan memastikan struktur folder dan nama package sudah sesuai.

---

## **Kesimpulan**

Dengan menerapkan konsep *inheritance*, kode program menjadi lebih **terstruktur**, **mudah dikembangkan**, dan **menghindari duplikasi**.
Setiap produk pertanian dapat memiliki atribut dan perilaku khusus tanpa perlu menulis ulang atribut dasar yang sama dari class `Produk`.

---

## Quiz
(1. Apa keuntungan menggunakan inheritance dibanding membuat class terpisah tanpa hubungan?
    **Jawaban:** Mengurangi duplikasi kode dan memudahkan pemeliharaan karena atribut dan method umum cukup dibuat sekali di superclass.  

2. Bagaimana cara subclass memanggil konstruktor superclass?  
   **Jawaban:** Dengan menggunakan keyword super() di dalam konstruktor subclass

3. Berikan contoh kasus di POS pertanian selain Benih, Pupuk, dan Alat Pertanian yang bisa dijadikan subclass.
   **Jawaban:** ObatHama, BibitSayur, atau PestisidaOrganik  )
