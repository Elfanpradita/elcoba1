# 📌 Belajar Pemrograman Web dengan Docker

Selamat datang di proyek **Pemrograman Web** menggunakan **Docker**! 🚀

Di sini kita akan belajar **HTML dasar, CSS, dan JavaScript**, serta ke depannya akan ada **setup VPS** untuk mengonlinekan website kita. Semoga bermanfaat! 😊

## 🛠️ Cara Menjalankan Project

### 1️⃣ Build dan Jalankan Container

Jalankan perintah berikut untuk membangun dan menjalankan container:

```sh
docker-compose up -d
```

> **Note:** Perintah ini akan menjalankan container secara **background (-d)**.

### 2️⃣ Matikan dan Hapus Container

Jika ingin menghentikan semua container, gunakan:

```sh
docker-compose down
```

## 🎯 Akses Website

Setelah container berjalan, buka browser dan akses **localhost** atau **IP server** di **port 80**.

- **Di Komputer Lokal:** `http://localhost`
- **Di Server:** `http://<IP-SERVER>`

## 🔧 Command Penting

Berikut beberapa perintah yang sering digunakan untuk konfigurasi proyek:

**Masuk ke dalam Container:**

```sh
docker exec -it sample bash
```

**Generate Key untuk Laravel:**

```sh
php artisan key:generate
```

**Buat Storage Link:**

```sh
php artisan storage:link
```

**Jalankan Migrasi Database:**

```sh
php artisan migrate
```

**Atur Hak Akses Folder Storage & Bootstrap:**

```sh
chown -R www-data:www-data storage/*
chown -R www-data:www-data bootstrap/*
```

**Inisialisasi Proyek:**

```sh
php artisan project:init
```

## 📢 Hubungi Elpun

Jika ada pertanyaan atau ingin berdiskusi lebih lanjut, silakan bergabung di komunitas kami:

🔹 **Discord:** [discord.gg/gMb8bt5e](https://discord.gg/gMb8bt5e)

🔹 **YouTube:** [@Elpun378](https://www.youtube.com/@Elpun378)

---

💡 **Happy Coding!** 🎉

**Credit:** Elpun aka Elfan 🚀\
From Elpun also known as Elfan Tampan 😎

Tuhan Memberkati semoga sukses dalam segala urusan baik kita. Amin.
