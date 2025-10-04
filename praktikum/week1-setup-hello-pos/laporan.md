## **LAPORAN PRAKTIKUM MINGGU 1**

**Topik:** *Penerapan Tiga Paradigma Pemrograman: Prosedural, OOP, dan Fungsional*

---

### **Identitas**

* **Nama:** Zakkya Fauzan Alba'asithu
* **NIM:** 240202890
* **Kelas:** 3IKRA

---

### **Tujuan**

Kegiatan praktikum minggu pertama ini bertujuan untuk memperkenalkan mahasiswa pada tiga gaya pemrograman yang umum digunakan, yaitu **prosedural**, **berorientasi objek (OOP)**, dan **fungsional**.
Melalui percobaan ini, mahasiswa diharapkan dapat memahami cara kerja masing-masing paradigma serta mampu membandingkan penerapannya dalam bahasa Java.

---

### **Dasar Teori**

1. **Pemrograman Prosedural** merupakan pendekatan tradisional di mana program dijalankan secara berurutan dari satu instruksi ke instruksi berikutnya.
2. **OOP (Object-Oriented Programming)** menekankan penggunaan objek sebagai representasi dari entitas dunia nyata. Setiap objek memiliki atribut dan perilaku.
3. **Class** digunakan sebagai template atau cetakan dari objek, berisi variabel dan metode untuk menggambarkan karakteristik serta fungsi objek tersebut.
4. **Pemrograman Fungsional** lebih fokus pada pemrosesan data menggunakan fungsi murni, di mana setiap operasi tidak mengubah data awal.
5. Java dapat menerapkan ketiga paradigma ini, sehingga fleksibel untuk berbagai jenis proyek.

---

### **Langkah Praktikum**

1. Membuat tiga program terpisah: `HelloProcedural.java`, `HelloOOP.java`, dan `HelloFunctional.java`.
2. Masing-masing program menampilkan daftar produk dengan harga serta menghitung total harga seluruh produk.
3. Program dijalankan menggunakan terminal untuk memastikan tidak ada kesalahan sintaks.
4. Hasil kemudian dikonfirmasi dan dikumpulkan dalam bentuk laporan praktikum.
---

### **Kode Program**

#### **1. HelloProcedural.java**

```java
public class HelloProcedural {
   public static void main(String[] args) {
      String nim = "240202880";
      String nama = "Ray";
      String[] produk = {"Kentang Goreng", "Ayam Goreng", "Bebek Goreng"};
      int[] harga = {10000, 15000, 18000};
      int total = 0;

      System.out.println("Nama: " + nama + ", NIM: " + nim);
      System.out.println("Daftar Produk:");
      for (int i = 0; i < produk.length; i++) {
         System.out.println("- " + produk[i] + ": " + harga[i]);
         total += harga[i];
      }
      System.out.println("Total harga semua produk: " + total);
   }
}
```

#### **2. HelloOOP.java**

```java
class Produk {
   String nama;
   int harga;

   Produk(String nama, int harga) {
      this.nama = nama;
      this.harga = harga;
   }
}

public class HelloOOP {
   public static void main(String[] args) {
      String nim = "240202890";
      String namaMhs = "Fauzan";

      Produk[] daftar = {
         new Produk("Kentang Goreng", 10000),
         new Produk("Ayam Goreng", 15000),
         new Produk("Bebek Goreng", 18000)
      };

      int total = 0;
      System.out.println("Nama: " + namaMhs + ", NIM: " + nim);
      System.out.println("Daftar Produk:");
      for (Produk p : daftar) {
         System.out.println("- " + p.nama + ": " + p.harga);
         total += p.harga;
      }
      System.out.println("Total harga semua produk: " + total);
   }
}
```

#### **3. HelloFunctional.java**

```java
import java.util.*;
import java.util.stream.*;

public class HelloFunctional {
   public static void main(String[] args) {
      String nim = "240202890";
      String nama = "Fauzan";

      List<String> produk = Arrays.asList("Kentang Goreng", "Ayam Goreng", "Bebek Goreng");
      List<Integer> harga = Arrays.asList(10000, 15000, 18000);

      System.out.println("Nama: " + nama + ", NIM: " + nim);
      System.out.println("Daftar Produk:");
      IntStream.range(0, produk.size())
         .forEach(i -> System.out.println("- " + produk.get(i) + ": " + harga.get(i)));

      int total = harga.stream().mapToInt(Integer::intValue).sum();
      System.out.println("Total harga semua produk: " + total);
   }
}
```

---

### **Hasil Eksekusi**

**Keluaran dari program:**

```
Nama: Fauzan, NIM: 240202890
Daftar Produk:
- Kentang Goreng: 10000
- Ayam Goreng: 15000
- Bebek Goreng: 18000
Total harga semua produk: 43000
```
<img width="1199" height="291" alt="Cuplikan layar 2025-10-04 164831" src="https://github.com/user-attachments/assets/b54fea6c-0125-4e6b-859f-1b3ee67e8b18" />

Semua program menampilkan hasil yang sama, hanya berbeda dalam struktur dan cara penulisannya.

---

### **Analisis**

* Pada **program prosedural**, semua perintah ditulis langsung di dalam fungsi utama tanpa pembagian struktur. Pendekatan ini mudah dipahami namun sulit diperluas.
* **Pendekatan OOP** lebih teratur karena menggunakan *class* `Produk`. Data dan logika dipisahkan dengan jelas, sehingga program lebih mudah dikembangkan.
* **Versi fungsional** menggunakan konsep *stream* dan *lambda expression*, yang membuat kode lebih pendek dan efisien untuk operasi data berulang.
* Dari ketiga pendekatan, terlihat bahwa Java dapat menyesuaikan berbagai gaya pemrograman sesuai kebutuhan.
* Tantangan yang dihadapi adalah memahami sintaks pada *stream API*, namun setelah dipahami, penggunaannya terasa lebih sederhana.

---

### **Kesimpulan**

Praktikum ini menunjukkan bahwa satu masalah yang sama dapat diselesaikan dengan berbagai paradigma pemrograman.
Setiap pendekatan memiliki kelebihan:

* Prosedural mudah untuk program sederhana,
* OOP unggul dalam struktur dan pemeliharaan kode,
* Functional cocok untuk pemrosesan data yang efisien dan ringkas.

Dengan memahami ketiganya, mahasiswa dapat memilih paradigma yang paling sesuai untuk kebutuhan proyek tertentu.

---

### **Quiz**

1. **Mengapa paradigma OOP memudahkan proses pengembangan perangkat lunak besar?**
   **Jawaban:** Karena OOP membagi program menjadi bagian-bagian kecil (objek) yang bisa digunakan kembali dan lebih mudah diuji secara terpisah.

2. **Apa fungsi `mapToInt()` pada kode functional di atas?**
   **Jawaban:** Fungsi tersebut mengubah daftar objek `Integer` menjadi *stream* bilangan bulat agar bisa dijumlahkan dengan mudah menggunakan `.sum()`.

3. **Apa keuntungan penggunaan *stream API* dibanding perulangan biasa?**
   **Jawaban:** Stream API membuat kode lebih deklaratif, singkat, dan mendukung pemrosesan paralel tanpa perlu membuat loop manual.

---
