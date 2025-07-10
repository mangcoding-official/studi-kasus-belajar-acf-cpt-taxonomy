---
Tentu, mari kita jelaskan konsep-konsep inti WordPress ini dengan analogi yang lebih akrab bagi developer magang, lalu kita terapkan pada studi kasus e-learning.

### Memahami Pondasi WordPress: CPT, Taxonomy, dan ACF

Di WordPress, kamu akan sering berurusan dengan tiga elemen kunci ini saat membangun fitur kustom:

1.  **Custom Post Types (CPT)**
    * **Apa itu?** Di WordPress, secara *default* sudah ada "Post" (untuk artikel blog) dan "Page" (untuk halaman statis). Nah, **"Post" ini sebenarnya adalah salah satu jenis CPT bawaan.**
    * Kadang, kita butuh jenis konten yang berbeda. Misalnya, untuk website toko online, kamu butguh "Produk". Atau untuk sistem e-learning, kamu butuh "Kursus" dan "Pelajaran".
    * **Analoginya:** Kalau di aplikasi biasa, kamu harus bikin tabel database manual (`CREATE TABLE products ...`). Di WordPress, **CPT itu ibaratnya kamu bikin "tabel" atau "entitas" baru secara instan, lengkap dengan menu khusus di admin WordPress**, jadi kamu bisa mengelola jenis konten itu secara terpisah dari Postingan blog biasa.
    * **Intinya:** CPT memungkinkan kita membuat jenis konten baru (`entity` atau `model`) selain `Post` dan `Page`.

2.  **Custom Taxonomies**
    * **Apa itu?** Kalau kamu punya banyak Postingan, kamu pasti mengelompokkannya pakai "Kategori" atau "Tag" bawaan WordPress.
    * **Analoginya:** **Custom Taxonomy itu persis seperti "Kategori" dan "Tag" bawaan WordPress, tapi untuk CPT buatan kita.** Jadi, kalau kita punya CPT "Produk", kita bisa bikin Taxonomy "Merek" atau "Ukuran" untuk mengelompokkan produk kita.
    * **Intinya:** Taxonomy berfungsi untuk **mengelompokkan atau mengklasifikasikan konten** dari CPT kita, mirip seperti kategori.

3.  **Advanced Custom Fields (ACF)**
    * **Apa itu?** Setelah kamu punya "tabel" (CPT), kamu pasti butuh "kolom-kolom" data di dalam tabel itu. Misalnya, untuk CPT "Produk", kamu butuh kolom `harga`, `stok`, `warna`. WordPress CPT secara default hanya punya `judul` dan `konten`.
    * **Analoginya:** **ACF ini seperti tool canggih yang memungkinkan kita "menambahkan kolom-kolom custom" ke CPT atau Taxonomy kita, dan yang paling penting, kamu bisa mendefinisikan jenis datanya (teks, angka, gambar, link, dll.) tanpa harus ngoding database atau form manual.** Kamu tinggal klik-klik saja di admin.
    * **Intinya:** ACF adalah cara mudah untuk **mendefinisikan dan mengelola "kolom" atau "field" tambahan** untuk CPT atau Taxonomy kita.

### Hubungan Antar Mereka

Ketiga komponen ini **berelasi dan saling melengkapi**. Kamu butuh **CPT** untuk jenis konten baru, **Taxonomy** untuk mengorganisirnya, dan **ACF** untuk menambahkan detail spesifik ke setiap item konten tersebut. Hasilnya adalah struktur data yang terdefinisi dengan baik dan mudah diatur di WordPress.

---

## Studi Kasus: "Edutech Pro" - Platform E-Learning Sederhana

**Tujuan:** Membangun *backend* WordPress yang bisa mengelola kursus dan pelajaran online untuk sebuah platform e-learning.

### Apa yang Harus Kalian Pelajari & Buat

1.  **Custom Post Types (CPT):**
    * Buat dua jenis konten baru: **"Course" (Kursus)** dan **"Lesson" (Pelajaran)**.
    * Ini akan **dibuat via kode PHP** karena kalian adalah developer. Pelajari fungsi `register_post_type()` dan pahami argumen pentingnya seperti `labels`, `public`, dan `supports`.

2.  **Custom Taxonomies:**
    * Buat dua sistem kategori kustom untuk "Kursus" dan "Pelajaran": **"Subject" (Mata Kuliah)** dan **"Level" (Tingkat Kesulitan)**.
    * Ini juga akan **dibuat via kode PHP**. Pelajari fungsi `register_taxonomy()` dan cara mengaitkannya dengan CPT yang sudah kamu buat.

3.  **Advanced Custom Fields (ACF):**
    * Instal **plugin ACF versi gratis**.
    * Gunakan plugin ini untuk **menambahkan kolom-kolom data tambahan** ke CPT "Course" dan "Lesson".
    * **Untuk "Course", tambahkan kolom:** `Course ID` (Text), `Instructor` (Post Object - tautkan ke User), `Prerequisites` (Relationship/Post Object - tautkan ke Course lain), `Estimated Duration` (Number), `Course Image` (Image), `Short Description` (Text Area).
    * **Untuk "Lesson", tambahkan kolom:** `Video URL` (URL), `Lesson Files` (File), `Reading Time (minutes)` (Number).

### Hasil Akhir yang Diharapkan

Setelah semua ini terimplementasi, kalian akan memiliki *backend* WordPress yang terstruktur, di mana guru bisa dengan mudah menambahkan "Kursus" dan "Pelajaran" baru beserta semua detailnya. Data ini kemudian bisa diakses oleh aplikasi *frontend* (misalnya aplikasi web atau mobile terpisah) melalui WordPress REST API bawaan.

Ini adalah keterampilan fundamental dalam pengembangan WordPress modern untuk membangun aplikasi berbasis data. Ada pertanyaan lain tentang studi kasus ini?
