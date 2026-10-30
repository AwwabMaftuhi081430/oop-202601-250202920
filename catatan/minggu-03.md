# Catatan Minggu 03: Inheritance

## Yang saya kerjakan
Saya melengkapi tiga subclass dari `Aset`, yaitu `Ruang`, `Laptop`, dan `AlatLab`. Setiap class punya field khusus, konstruktor yang memanggil `super(kode, nama)`, getter, dan `getJenis()` yang mengembalikan `JenisAset` sesuai kelasnya. Validasi ditambahkan sesuai aturan tugas: kapasitas ruang > 0, spesifikasi dan nomor inventaris laptop tidak boleh kosong, laboratorium tidak boleh kosong, dan tingkat risiko tidak boleh null.

## Keputusan desain
- **Field di induk vs subclass.** `kode` dan `nama` dimiliki semua aset, jadi tetap di `Aset`. `kapasitas` hanya relevan untuk ruang, `spesifikasi` dan `nomorInventaris` untuk laptop, dan `laboratorium` serta `tingkatRisiko` untuk alat lab, jadi masing-masing di subclass.
- **Validasi `kode` dan `nama` tidak diulang di subclass.** Konstruktor subclass memanggil `super(kode, nama)`, sehingga validasi dari `Aset` tetap berlaku.
- **`kapasitas` pada `Ruang` saya buat `final`** karena tidak ada setter dan nilainya tidak berubah setelah objek dibuat.
- **Keterangan dosen (Javadoc dan komentar TODO) saya pertahankan** karena itu bagian dari berkas tugas.
- **Contoh inheritance yang kurang tepat dibanding komposisi:** [draf, sesuaikan dengan pemikiranmu] Saat ini `AlatLab` memuat `tingkatRisiko` lewat inheritance. Kalau kelak ada laptop yang dipakai di laboratorium dan berisiko tinggi, kelas itu tidak bisa meng-extend `Laptop` sekaligus `AlatLab`, karena Java hanya mengizinkan satu induk. Dengan komposisi, risiko dibuat sebagai komponen tersendiri (misalnya objek `ProfilRisiko`) yang dimiliki aset mana pun. Dengan begitu tidak perlu hierarki yang bercabang dan risikonya bisa diganti tanpa mengubah jenis asetnya.

## Kendala
- `AlatLab.java` tidak bisa dikompilasi karena ada baris yang rusak (konstruktor tanpa `throw new UnsupportedOperationException`, dan sisa string `");` yang berdiri sendiri). Akibatnya tes yang memakai `AlatLab` ikut gagal.
- `Laptop.getJenis()` dan `Ruang.getJenis()` memakai tipe `String`, padahal `Aset.getJenis()` mengembalikan `JenisAset`. Saya mengubah tipe kembalian dan nilai yang dikembalikan, lalu mencocokkan nama konstanta dengan `JenisAset.java`.
- Pesan `Unresolved compilation problems` awalnya membingungkan karena error muncul saat tes jalan, bukan saat kompilasi. Saya mengatasinya dengan membaca nama file dan nomor baris di stack trace, lalu memperbaiki error kompilasi di file itu.

## Penggunaan AI
- Alat yang dipakai: Claude dan chat gpt
- Bagian yang dibantu AI: menelusuri penyebab error kompilasi pada `AlatLab`, `Laptop`, dan `Ruang`, serta draf perbaikan konstruktor, validasi, dan `getJenis()`.
- Prompt utama:
  1. "bagaimana agar tidak failure" (disertai output Maven dan ketiga file)
  2. "laptop java ada error 1"
- Yang saya ubah atau tolak dari saran AI, dan alasannya: Saya memeriksa nama konstanta enum langsung di `JenisAset.java`, bukan hanya mengandalkan tebakan AI. [Tambahkan bila ada lagi, misalnya `private final` pada `Ruang` yang saya tulis sendiri.]
- Satu hal yang saya pahami lebih baik sekarang: saat meng-override method, tipe kembalian harus kompatibel dengan method induk. Karena itu `getJenis()` di subclass harus mengembalikan `JenisAset`, bukan `String`. [Ganti dengan pemahamanmu sendiri bila ada yang lebih tepat.]