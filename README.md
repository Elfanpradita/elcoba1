# 📌 Project PemWeb dengan Docker

Selamat datang di repository ini! 🚀 Kita akan belajar Pemrograman Web (PemWeb) menggunakan **HTML dasar, CSS, dan JavaScript**, serta ke depannya akan melakukan **setup VPS** untuk mengonlinekan website. Semoga membantu! 🎉

---

## 🔥 Cara Menjalankan Project ini

### 1️⃣ Clone Repository

Jalankan perintah berikut untuk meng-clone repository ini ke komputer atau server kamu:

```bash
git clone git@github.com:username/repository.git
cd repository
```

### 2️⃣ Build dan Jalankan Docker

Jalankan perintah berikut untuk membangun dan menjalankan container Docker:

```bash
docker-compose up --build -d
```

### 3️⃣ Menghentikan Docker

Gunakan perintah ini untuk menghentikan semua container yang berjalan:

```bash
docker-compose down
```

---

## 🚀 Command Penting

### Masuk ke dalam Container

```bash
docker exec -it sample bash
```

### Setup Laravel

```bash
php artisan key:generate
php artisan storage:link
php artisan migrate
```

### Set Permission Storage & Bootstrap

```bash
chown -R www-data:www-data storage/*
chown -R www-data:www-data bootstrap/*
```

### Inisialisasi Project

```bash
php artisan project:init
```

---

## 🌍 Akses Website

Setelah container berjalan, kamu bisa mengakses website melalui:

- **[http://localhost](http://localhost)** (jika diakses dari komputer lokal)
- **http\://IP\_SERVER** (jika diakses dari server lain)

Port default yang digunakan adalah **80**, jadi cukup akses langsung tanpa perlu menuliskan port.

---

## 📢 Contact Elpun

📌 **Discord:** [https://discord.gg/gMb8bt5e](https://discord.gg/gMb8bt5e)\
📌 **YouTube:** [@Elpun378](https://www.youtube.com/@Elpun378)

**Happy Coding!** 🚀

From Elpun also known as Elfan Tampan 😎

Tuhan Memberkati semoga sukses dalam segala urusan baik kita. Amin.

