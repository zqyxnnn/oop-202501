## **LAPORAN PRAKTIKUM MINGGU 1**

**Topik:** *Implementasi 3 Paradigma Pemrograman: Procedural, OOP, dan Functional*

---

### **Identitas**

* **Nama:** Zakkya Fauzan Alba'asithu
* **NIM:** 240202890
* **Kelas:** 3IKRA

---

### **Tujuan**

Mahasiswa memahami konsep dan perbedaan antara tiga paradigma pemrograman yaitu **procedural**, **object-oriented programming (OOP)**, dan **functional programming**.
Selain itu, mahasiswa mampu mengimplementasikan ketiganya dalam bahasa pemrograman Java dengan studi kasus daftar produk sederhana.

---

### **Dasar Teori**

1. **Pemrograman Prosedural** menekankan urutan langkah-langkah instruksi yang dijalankan secara berurutan untuk mencapai hasil tertentu.
2. **Pemrograman Berorientasi Objek (OOP)** mengorganisasi kode ke dalam *class* dan *object* agar lebih modular, reusable, dan terstruktur.
3. **Class** berfungsi sebagai cetak biru (template) dari objek, yang berisi atribut dan perilaku (metode).
4. **Functional Programming** berfokus pada fungsi dan ekspresi murni tanpa mengubah keadaan (immutable data).
5. Java mendukung ketiga paradigma ini, sehingga memudahkan pengembang dalam memilih pendekatan sesuai kebutuhan.

---

### **Langkah Praktikum**

1. Membuat tiga file program Java:

   * `HelloProcedural.java`
   * `HelloOOP.java`
   * `HelloFunctional.java`
2. Menuliskan kode untuk menampilkan daftar produk dan menghitung total harga.
3. Melakukan *compile* dan *run* masing-masing program menggunakan terminal/VS Code.
4. Melakukan *commit* ke repository Git dengan pesan:

   > `Implementasi 3 paradigma pemrograman: Procedural, OOP, Functional.`

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

**Output ketiga program (hasil sama):**

```
Nama: Fauzan, NIM: 240202890
Daftar Produk:
- Kentang Goreng: 10000
- Ayam Goreng: 15000
- Bebek Goreng: 18000
Total harga semua produk: 43000
```

<img width="1199" height="291" alt="Cuplikan layar 2025-10-04 164831" src="https://github.com/user-attachments/assets/20682751-e832-4f84-ba8f-fe8187366a26" />


---

### **Analisis**

* **HelloProcedural** menggunakan pendekatan tradisional, di mana semua data dan logika berada di dalam fungsi `main()`. Pendekatan ini sederhana, tetapi sulit dikembangkan untuk program besar.
* **HelloOOP** membagi kode ke dalam *class* `Produk`, membuat struktur program lebih rapi dan mudah diperluas. Ini menunjukkan prinsip **enkapsulasi** dan **abstraksi**.
* **HelloFunctional** memanfaatkan konsep *stream* dan *lambda expression* dari Java 8. Pendekatan ini membuat kode lebih ringkas dan deklaratif.
* Ketiga paradigma menghasilkan output yang sama, namun memiliki cara berpikir dan struktur yang berbeda.
* Kendala utama muncul saat memahami sintaks *stream* di paradigma fungsional. Solusinya adalah mempelajari dasar `IntStream` dan `lambda`.

---

### **Kesimpulan**

Melalui praktikum ini, mahasiswa memahami bahwa Java dapat menerapkan tiga paradigma pemrograman yang berbeda.
Pendekatan prosedural cocok untuk program sederhana, sedangkan OOP dan Functional lebih efisien dan mudah dikembangkan untuk program yang lebih kompleks.
Dengan OOP dan Functional, kode menjadi lebih modular, reusable, dan mudah dipelihara.

---

### **Quiz**

1. **Apa keunggulan paradigma OOP dibanding prosedural?**
   **Jawaban:** OOP memungkinkan penggunaan *class* dan *object* sehingga kode lebih terstruktur, reusable, dan mudah dipelihara.

2. **Bagaimana cara kerja `IntStream.range()` dalam program fungsional di atas?**
   **Jawaban:** `IntStream.range(0, produk.size())` menghasilkan deretan indeks dari 0 hingga ukuran list produk, yang kemudian digunakan untuk mencetak setiap item secara berurutan.

3. **Mengapa paradigma fungsional cocok untuk pemrosesan data dalam jumlah besar?**
   **Jawaban:** Karena paradigma fungsional menggunakan operasi berbasis *stream* yang efisien, mudah diparalelkan, dan tidak mengubah data asli (immutable).

---

Apakah kamu ingin saya **buatkan laporan ini dalam format Word (.docx)** agar bisa langsung kamu kumpulkan?
