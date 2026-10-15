# Catatan Minggu 01: Paradigma Pemrograman dan Setup

## Yang saya kerjakan

Saya mempelajari perbedaan paradigma prosedural, OOP, dan functional melalui program sapaan Aset-Pinjam. Saya membaca struktur tiga class minggu 1 serta tes `Minggu01Test` untuk memahami hasil yang diwajibkan. Saya juga menyiapkan rancangan agar ketiga implementasi menghasilkan teks yang sama dan memuat nama serta NIM.

Status saat catatan dibuat: implementasi tiga class dan data pada `mahasiswa.properties` masih perlu diselesaikan, kemudian diverifikasi dengan `scripts/uji.ps1`.

Praktikum ini harus lolos tools sebagai berikut
1. Java/JDK21 ( paste ke cmd -> `winget install --id Microsoft.OpenJDK.21 --exact` )
2. Maven ( Download -> https://maven.apache.org/download.cgi -> pilih Binary zip archive )
3. Git

Pastikan semua dimasukan ke System Environment dengan cara :
1. Start
2. cari Edit the system environment variables
3. Environment Variables.
4. Verifikasi

```text
java -version
mvn -v
git --version
```

## Keputusan desain

Saya memilih format sapaan berikut untuk ketiga paradigma:

```text
Hello Aset-Pinjam, saya <nama> (<nim>)
```


Format yang sama digunakan agar perbedaan hanya terletak pada cara program dibangun, bukan hasil akhirnya. Gaya prosedural menggunakan method statis, gaya OOP menyimpan nama dan NIM dalam field private, sedangkan gaya functional menghasilkan lambda bertipe `Function<String, String>`.

## Kendala

Saya perlu memahami seluruh codebase atau repository ini untuk mata kuliah OOP 20261. Saya juga perlu memahami bahwa ketiga gaya wajib menghasilkan `String` yang persis sama meskipun struktur implementasinya berbeda. Saya kemudian bertanya ke teman saya untuk membatu saya mengatasi masalah tersebut. Kemudian teman saya bilang kalau Saya harus mengatasinya dengan membaca assertion pada `Minggu01Test` dan menelusuri cara pemanggilan setiap method.

## Penggunaan AI

- Alat yang dipakai: Copilot dan ChatGPT
- Bagian yang dibantu AI: Memahami garis besarnya mata kuliah OOP ini, menginstall JDK 21 dan maven untuk praktikum, dan memberi contoh satu implementasi `HelloOOP`.
- Prompt utama:
  1. Kamu adalah pembimbing untuk urusan IT utamanya programming.Carikan kode untuk install JDK 21 di CMD dan maven. Jika tidak ada, carikan cara step by step nya.
