Nama: Muhammad Daffansyah Desuandi  

NIM: 123140127

Program Studi: Teknik Informatika

Mata Kuliah: Pengembangan Aplikasi Mobile

-----------------------------------------------------------------------------------------------------------------------------

📰 News Feed Simulator (Kotlin + Coroutines + Flow)

Aplikasi simulasi news feed berbasis console menggunakan Kotlin Coroutines, Flow, dan StateFlow.

Project ini dibuat untuk memahami konsep reactive programming dan asynchronous programming di Kotlin.

**🚀 Fitur**

✅ Flow yang menghasilkan data berita baru setiap 2 detik
✅ Filter berita berdasarkan kategori tertentu
✅ Transformasi data menjadi format tampilan
✅ StateFlow untuk menyimpan jumlah berita yang sudah dibaca
✅ Coroutine untuk mengambil detail berita secara asynchronous

**🛠 Teknologi yang Digunakan**

Kotlin (JVM)

kotlinx-coroutines-core

Flow

StateFlow

Coroutines

**📦 Struktur Project**

NewsFeedSimulator
│
├── News.kt
├── NewsGenerator.kt
├── NewsFilter.kt
├── NewsTransform.kt
├── NewsState.kt
└── Main.kt

🔄 Cara Kerja Aplikasi
1️⃣ Generator Berita (Flow)

Flow akan menghasilkan objek News setiap 2 detik.

fun newsGenerator(): Flow<News>


Flow bersifat cold stream, artinya data hanya akan berjalan ketika dikoleksi.

2️⃣ Filter Berita

Berita dapat difilter berdasarkan kategori tertentu.

Contoh:

flow.filter { it.category == "Tech" }

3️⃣ Transformasi Data

Data berita diubah menjadi format string yang siap ditampilkan.

flow.map { "[${it.category}] ${it.title}" }

4️⃣ StateFlow (Manajemen State)

Jumlah berita yang sudah dibaca disimpan menggunakan MutableStateFlow.

val readCount = MutableStateFlow(0)


StateFlow cocok digunakan untuk menyimpan state yang selalu ter-update.

5️⃣ Pengambilan Detail Secara Async

Simulasi pengambilan detail berita menggunakan fungsi suspend.

suspend fun fetchNewsDetail(news: News): String


Delay digunakan untuk mensimulasikan request ke server.

▶️ Cara Menjalankan

Clone repository

git clone https://github.com/username/news-feed-simulator.git


Buka di IntelliJ IDEA

Pastikan dependency berikut sudah ditambahkan:

implementation("org.jetbrains.kotlinx:kotlinx-coroutines-core:1.7.3")


Jalankan file Main.kt

**📚 Konsep yang Dipelajari**

Konsep	Penjelasan
Flow	Stream data asynchronous
Cold Flow	Flow berjalan saat dikoleksi
StateFlow	Penyimpan state reaktif
Coroutine	Thread ringan untuk async
Suspend Function	Fungsi non-blocking

**🎯 Tujuan Project**

Project ini dibuat untuk memahami:

Reactive programming di Kotlin

Manajemen state modern

Asynchronous programming

Konsep dasar arsitektur seperti MVVM

Project ini dapat dikembangkan menjadi:

Aplikasi Android dengan ViewModel

Jetpack Compose UI

Integrasi REST API

Integrasi Database (Room)
