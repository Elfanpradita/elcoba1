# SSH Reverse Tunnel: Akses Server Lokal dari VPS

## **📝 Deskripsi**
Dokumen ini menjelaskan cara mengakses **server lokal** yang tidak memiliki IP publik melalui **VPS dengan IP publik** menggunakan **SSH Reverse Tunnel**.

## **🌐 Informasi Server**
- **VPS**: `root@64.23.149.217`
- **Server Lokal**: `elfan@local-server`
- **Port yang digunakan**: `2222`

---

## **🔹 Langkah 1: Buat SSH Reverse Tunnel**
### **📌 Jalankan di Server Lokal**
```bash
ssh -R 2222:localhost:22 root@64.23.149.217
```
- Ini akan membuka port **2222** di VPS dan meneruskan koneksi ke **port 22** di server lokal.
- Masukkan password VPS jika diminta.

📢 **Catatan:** Jangan tutup sesi SSH ini agar koneksi tetap aktif.

---

## **🔹 Langkah 2: Akses Server Lokal dari VPS**
### **📌 Jalankan di VPS**
```bash
ssh -p 2222 elfan@localhost
```
- `-p 2222` → Menggunakan port yang sudah dibuka untuk menghubungkan ke server lokal.
- `elfan@localhost` → Login sebagai user **elfan** di server lokal.

Jika berhasil, sekarang kamu sudah masuk ke server lokal melalui VPS! 🎉

---

## **🔹 Langkah 3: Buat Reverse Tunnel Permanen (Opsional)**
Agar SSH Reverse Tunnel tetap aktif meskipun koneksi terputus atau server restart, gunakan **autossh**.

### **1️⃣ Install autossh di Server Lokal**
```bash
sudo apt update && sudo apt install autossh -y
```

### **2️⃣ Buat Service di Systemd**
Buat file service:
```bash
sudo nano /etc/systemd/system/reverse-ssh.service
```
Isi dengan:
```
[Unit]
Description=Reverse SSH Tunnel to VPS
After=network.target

[Service]
User=elfan
ExecStart=/usr/bin/autossh -N -R 2222:localhost:22 root@64.23.149.217 -o ServerAliveInterval=60 -o ServerAliveCountMax=3
Restart=always
RestartSec=5

[Install]
WantedBy=multi-user.target
```

### **3️⃣ Aktifkan Service**
```bash
sudo systemctl daemon-reload
sudo systemctl enable reverse-ssh
sudo systemctl start reverse-ssh
```

🚀 **Sekarang SSH Reverse Tunnel akan berjalan otomatis saat server lokal menyala!**

---

## **🎯 Testing & Troubleshooting**
- **Cek status service:**
  ```bash
  sudo systemctl status reverse-ssh
  ```
- **Cek apakah port 2222 terbuka di VPS:**
  ```bash
  netstat -tlnp | grep 2222
  ```
- **Jika gagal terhubung, pastikan:**
  - Firewall di VPS dan server lokal tidak memblokir SSH.
  - SSH di VPS mengizinkan port forwarding (`/etc/ssh/sshd_config` → `GatewayPorts yes`).

---

### **✅ Selesai!** 🚀 Sekarang kamu bisa mengakses server lokal melalui VPS kapan saja!

