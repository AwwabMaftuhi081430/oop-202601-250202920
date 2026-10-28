# Catatan Minggu 02: Struktur OOP — Class, Object, dan Encapsulation

## Yang saya kerjakan

Pada Minggu 2, saya mengerjakan class `Aset.java` pada sistem Aset-Pinjam. Saya membuat field dengan akses `private`, konstruktor untuk menginisialisasi kode dan nama aset, serta getter dan setter untuk mengakses dan mengubah data. Saya juga menambahkan validasi agar kode dan nama tidak boleh kosong serta status dan kondisi tidak boleh bernilai `null`. Selain itu, saya memastikan setiap aset memiliki status awal `TERSEDIA` dan kondisi awal `BAIK`.

## Keputusan desain

Saya menggunakan access modifier `private` pada field agar data aset tidak dapat diakses secara langsung dari luar class. Saya menyediakan getter untuk membaca data dan setter untuk mengubah data yang memang boleh diubah. Kode dan nama aset divalidasi di dalam konstruktor, sedangkan setter nama, status, dan kondisi juga memiliki validasi agar data tetap sesuai aturan.

Status awal aset ditetapkan menjadi `TERSEDIA`, sedangkan kondisi awal ditetapkan menjadi `BAIK`. Saya juga menggunakan `IllegalArgumentException` apabila data yang diberikan tidak valid. Dengan demikian, data aset dapat dikelola dengan lebih aman dan teratur melalui konsep encapsulation.

## Kendala

Kendala yang saya pelajari adalah bagaimana menerapkan encapsulation dan validasi pada class Java. Saya perlu memastikan bahwa field tidak bisa diakses secara langsung dan bahwa data yang diberikan kepada konstruktor maupun setter memenuhi ketentuan. Saya mengatasinya dengan menggunakan `private`, menyediakan getter dan setter, serta memeriksa nilai `null` dan string kosong sebelum data disimpan.

## Penggunaan AI

- **Alat yang dipakai:** ChatGPT.
- **Bagian yang dibantu AI:** Pemeriksaan dan perbaikan kode `Aset.java`, terutama field, konstruktor, getter, setter, dan validasi.
- **Prompt utama:**
  
  > Perbaiki syntax jika salah atau kurang pada kode Java class Aset.java, dengan tetap memperhatikan ketentuan field private, konstruktor, getter/setter, dan validasi.

- **Yang saya ubah atau tolak dari saran AI, dan alasannya:** Saya memprioritaskan implementasi yang sesuai dengan target tugas Minggu 2. Perubahan lanjutan seperti menjadikan `getJenis()` dan `hitungDenda()` sebagai metode abstrak perlu disesuaikan dengan ketentuan minggu pengerjaan agar tidak mengubah scope tugas terlalu dini.
- **Satu hal yang saya pahami lebih baik sekarang:** Encapsulation bukan hanya membuat field menjadi `private`, tetapi juga mengatur akses dan perubahan data melalui metode yang dilengkapi validasi sehingga data objek tetap konsisten.