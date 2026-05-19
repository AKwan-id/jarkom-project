# 📡 Praktik Jaringan Komputer - Cisco Packet Tracer

Repository ini berisi dokumentasi hasil praktik **Jaringan Komputer** menggunakan **Cisco Packet Tracer**.  
Dokumentasi difokuskan pada tugas yang telah dikerjakan, yaitu konfigurasi topologi jaringan, pengaturan alamat IP, gateway, komunikasi antar-network, serta pengujian layanan jaringan.

---

## 👨‍🎓 Identitas Mahasiswa

| Keterangan | Data |
|---|---|
| Nama | Ahmad Kurniawan |
| NIM | A18.2025.00191 |
| Mata Kuliah | Jaringan Komputer |
| Tools | Cisco Packet Tracer |

---

## 📁 Struktur File

```text
.
├── README.md
├── P1 JarKom.pkt
└── P2 JarKom.pkt
```

---

# 📌 Praktik 1 - Konfigurasi Dua Network dengan Router

## 📖 Deskripsi

Praktik 1 membahas konfigurasi dua jaringan berbeda menggunakan Cisco Packet Tracer.  
Jaringan yang dibuat terdiri dari **Network A / Lantai Dasar** dan **Network B / Lantai Atas**.

Kedua network dihubungkan menggunakan router agar perangkat pada jaringan yang berbeda dapat saling berkomunikasi.

Alamat network ditentukan berdasarkan instruksi tugas menggunakan 5 digit terakhir NIM, yaitu `00191`.

| Digit | Nilai |
|---|---:|
| A | 0 |
| B | 0 |
| C | 1 |
| D | 9 |
| E | 1 |

## ⚙️ Konfigurasi Network

| Network | Network Address | Subnet Mask | Gateway Router |
|---|---:|---:|---:|
| Network A / Lantai Dasar | `10.0.0.0` | `255.255.255.0` | `10.0.0.254` |
| Network B / Lantai Atas | `10.0.19.0` | `255.255.255.0` | `10.0.19.254` |

## 🧩 Struktur Topologi

| Komponen | Keterangan |
|---|---|
| Router0 | Menghubungkan Network A dan Network B |
| Switch0 | Menghubungkan perangkat pada Network A |
| Switch1 | Menghubungkan perangkat pada Network B |
| PC0 dan PC1 | Host pada Network A |
| PC6 dan PC7 | Host pada Network B |
| Server0 dan Server1 | Server pada Network B |

## 📄 File

```text
P1 JarKom.pkt
```

## 🧪 Pengujian

Pengujian dilakukan menggunakan fitur **ICMP / Add Simple PDU** pada Cisco Packet Tracer.

| Pengujian | Hasil |
|---|---|
| Komunikasi Network A ke Network B | `Successful` |
| Komunikasi Network B ke Network A | `Successful` |

Status `Successful` menunjukkan bahwa kedua network berhasil saling terhubung melalui router.

## 🎯 Fokus Pembelajaran

- Konfigurasi dua network berbeda.
- Pengaturan IP address dan subnet mask.
- Pengaturan gateway pada host dan router.
- Komunikasi antar-network menggunakan router.
- Pengujian koneksi menggunakan ICMP.

---

# 📌 Praktik 2 - Simulasi 3 Network dengan Web Server dan DNS Server

## 📖 Deskripsi

Praktik 2 membahas simulasi jaringan dengan **tiga network berbeda**.  
Network A digunakan sebagai jaringan utama yang berisi PC, Web Server, dan DNS Server.  
Network B dan Network C berisi beberapa PC yang terhubung melalui router.

Praktik ini juga menguji layanan **Web Server** dan **DNS Server** agar client dapat mengakses halaman web menggunakan domain lokal.

## ⚙️ Konfigurasi Network

| Network | Network Address | Subnet Mask | Gateway Router |
|---|---:|---:|---:|
| Network A | `192.168.0.0` | `255.255.255.0` | `192.168.0.254` |
| Network B | `192.168.10.0` | `255.255.255.0` | `192.168.10.254` |
| Network C | `192.168.100.0` | `255.255.255.0` | `192.168.100.254` |

## 🧩 Struktur Topologi

| Network | Perangkat yang Terlihat pada Topologi |
|---|---|
| Network A | 2 PC, 1 Web Server, 1 DNS Server, dan 1 switch |
| Network B | 3 PC dan 1 switch |
| Network C | 2 PC dan 1 switch |
| Router0 | Menghubungkan Network A, Network B, dan Network C |

## 🌐 Layanan Web Server

Web Server dikonfigurasi menggunakan file `index.html`.

Isi halaman web:

```html
<h1>WawanGanteng</h1>
<p>Web Server berhasil berjalan.</p>
<p>Simulasi 3 network sukses.</p>
```

Domain yang digunakan untuk mengakses Web Server:

```text
http://wawanganteng.local
```

## 🗂️ Layanan DNS Server

DNS Server digunakan untuk mengarahkan domain lokal ke alamat IP Web Server.

| Domain | Alamat IP Tujuan |
|---|---:|
| `wawanganteng.local` | `192.168.0.10` |
| `www.wawanganteng.local` | `192.168.0.10` |

Status layanan DNS:

```text
On
```

## 📄 File

```text
P2 JarKom.pkt
```

## 🧪 Pengujian

Pengujian dilakukan menggunakan perintah `ping`, fitur ICMP, dan browser pada Cisco Packet Tracer.

| Pengujian | Hasil |
|---|---|
| Ping dari PC0 ke `192.168.10.1` | Berhasil, `0% loss` |
| Ping dari PC0 ke `192.168.100.1` | Berhasil, `0% loss` |
| Akses `wawanganteng.local` melalui browser | Berhasil menampilkan halaman web |
| Akses domain melalui DNS | Domain mengarah ke Web Server `192.168.0.10` |
| Pengujian ICMP pada PDU List | `Successful` |

## 🎯 Fokus Pembelajaran

- Konfigurasi tiga network berbeda.
- Pengaturan gateway router pada setiap network.
- Komunikasi antar-network.
- Konfigurasi Web Server.
- Konfigurasi DNS Server.
- Pengujian akses domain lokal melalui browser.
- Pengujian koneksi menggunakan `ping` dan ICMP.

---

## 🛠️ Teknologi yang Digunakan

| Teknologi / Komponen | Fungsi |
|---|---|
| Cisco Packet Tracer | Membuat dan menguji simulasi jaringan |
| Router | Menghubungkan network yang berbeda |
| Switch | Menghubungkan perangkat dalam satu network |
| PC | Perangkat client untuk pengujian jaringan |
| Server | Menjalankan layanan Web Server dan DNS Server |
| ICMP / Ping | Menguji konektivitas antarperangkat |
| DNS | Mengarahkan nama domain lokal ke alamat IP |
| HTTP | Mengakses halaman web dari Web Server |

---

## ✅ Kesimpulan

Praktik 1 berhasil menghubungkan dua network berbeda menggunakan router.  
Network A menggunakan alamat `10.0.0.0/24`, sedangkan Network B menggunakan alamat `10.0.19.0/24`.  
Pengujian ICMP menunjukkan status `Successful`.

Praktik 2 berhasil menghubungkan tiga network berbeda dan menjalankan layanan Web Server serta DNS Server.  
Pengujian ping menunjukkan `0% loss`, dan domain lokal `wawanganteng.local` berhasil digunakan untuk mengakses halaman Web Server.

---

## 👤 Author

| Keterangan | Data |
|---|---|
| Nama | Ahmad Kurniawan |
| NIM | A18.2025.00191 |
| Mata Kuliah | Jaringan Komputer |
