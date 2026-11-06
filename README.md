# Presentasi BMC Rumah Yatim x Marketplace

Presentasi berbasis kode (HTML, CSS, JavaScript biasa, tanpa framework). Isinya intro foto tim dengan lagu Korea, 14 slide dari PPT, sound whoosh di setiap transisi, beberapa plot twist, dan video penutup.

## Isi folder

```
bmc-rumah-yatim-presentasi/
├── index.html        semua kode (tampilan, animasi, logika)
├── img/              foto tim dan poster program
├── audio/            song.mp3 (lagu intro), whoosh.mp3, twist.mp3
├── video/            closing.mp4 (video penutup)
└── README.md         panduan ini
```

Jangan ubah nama file atau folder. Kode memanggil file-file itu dengan nama persis seperti di atas.

## Cara mencoba di komputer

**Cara cepat:** klik dua kali `index.html`. Tekan "Mulai presentasi". Suara tetap jalan, tapi sound whoosh bisa sedikit terlambat.

**Cara yang disarankan** (suara paling pas), jalankan server lokal dari dalam folder ini:

```
python3 -m http.server 8000
```

Lalu buka `http://localhost:8000` di Chrome. Kalau memakai VS Code, ekstensi Live Server juga bisa.

Tombol yang berlaku saat presentasi:

| Tombol | Fungsi |
| --- | --- |
| klik, spasi, panah kanan | maju |
| panah kiri, atau klik sisi kiri layar | mundur ke slide sebelumnya |
| F | layar penuh |
| M | bisukan atau nyalakan suara |

## Cara memasang di GitHub dan membuat link

Pakai GitHub Pages supaya presentasi punya link yang bisa dibuka di laptop mana saja.

### Lewat browser (tanpa install apa pun)

1. Masuk ke github.com, klik **New repository**.
2. Isi nama, misalnya `presentasi-bmc-rumah-yatim`. Pilih **Public**. Klik **Create repository**.
3. Di halaman repo, klik **uploading an existing file** (atau **Add file** lalu **Upload files**).
4. Buka folder `bmc-rumah-yatim-presentasi` di komputermu, pilih **isinya** (`index.html`, `img`, `audio`, `video`, `README.md`), lalu seret ke halaman GitHub. Tunggu semua file selesai terunggah.
5. Klik **Commit changes**.
6. Buka **Settings**, lalu **Pages** di menu kiri.
7. Di bagian **Build and deployment**, pilih Source **Deploy from a branch**. Pilih branch **main** dan folder **/ (root)**, lalu klik **Save**.
8. Tunggu 1 sampai 3 menit, lalu muat ulang halaman Pages. Link-nya muncul di bagian atas:

```
https://USERNAME.github.io/presentasi-bmc-rumah-yatim/
```

Ganti `USERNAME` dengan nama akun GitHub-mu.

### Lewat Git (terminal)

Buat repo kosong di GitHub dulu, lalu dari dalam folder presentasi:

```
git init
git add .
git commit -m "Presentasi BMC Rumah Yatim x Marketplace"
git branch -M main
git remote add origin https://github.com/USERNAME/presentasi-bmc-rumah-yatim.git
git push -u origin main
```

Setelah itu lanjut dari langkah 6 di atas untuk mengaktifkan Pages.

### Update setelah ada perubahan

Ganti file yang berubah di repo (lewat **Add file**, **Upload files** dengan nama file yang sama, atau `git add . && git commit -m "update" && git push`). Pages ikut berubah dalam beberapa menit. Kalau tampilan belum berubah, tekan Ctrl+Shift+R.

## Cara mengubah isi

Semua ada di `index.html`. Buka dengan VS Code atau editor teks, lalu pakai Ctrl+F.

| Mau ubah | Cari kata ini | Catatan |
| --- | --- | --- |
| Kata-kata selipan | `id="t1"` sampai `id="t9"` | Ubah teks di dalam `<span class="ln"` dan `<p class="sub"`. |
| Lama tiap selipan tampil | `var steps = [` | Angka `auto:` dalam milidetik (3400 = 3,4 detik). |
| Urutan slide dan selipan | `var steps = [` | Pindahkan barisnya. Baris dengan `kind: 'slide'` adalah slide, `kind: 'teaser'` adalah selipan. |
| Buang slide "Mie Instan" | `id: 'wrong'` | Hapus satu baris itu dari `steps`. Selipan sesudahnya (`id="t4"`, "Oke, yang benar") sebaiknya diganti juga. |
| Buang efek ngeleg lalu sound | `lag: true` | Hapus tulisan `lag: true` di baris `s8`. |
| Kalimat di bawah nama saat intro | `class="tg"` | Ada empat, satu per orang. |
| Waktu foto muncul di intro | `function introRun` | Angka dalam milidetik. Lagu aslinya 22,6 detik. |
| Warna utama | `--yolk:` | Daftar warna ada di blok yang sama: `--tomato`, `--mint`, `--sky`, dan seterusnya. |

### Mengganti file

- **Foto tim:** timpa `img/jafar.jpg`, `jejen.jpg`, `bagud.jpg`, `nida.jpg` dengan file baru yang namanya sama. Ukuran terbaik 800 x 1000 piksel (rasio 4:5).
- **Lagu intro:** timpa `audio/song.mp3`. Kalau durasinya beda dari 22,6 detik, sesuaikan angka di `function introRun`.
- **Sound whoosh dan sound kejutan:** timpa `audio/whoosh.mp3` dan `audio/twist.mp3`.
- **Video penutup:** timpa `video/closing.mp4`. Pakai format MP4 (H.264). Unggah lewat browser dibatasi 25 MB per file.

## Kalau ada masalah

- **Tidak ada suara:** pastikan sudah menekan tombol "Mulai presentasi" (browser memblokir suara sebelum ada klik), volume laptop menyala, dan belum menekan M.
- **Link Pages menampilkan 404:** tunggu beberapa menit setelah Save. Pastikan `index.html` ada di paling atas repo, bukan di dalam folder lagi, dan namanya huruf kecil semua.
- **Gambar, audio, atau video tidak muncul:** cek struktur folder di repo. Folder `img`, `audio`, `video` harus sejajar dengan `index.html`.
- **Tulisan terlihat beda:** font dimuat dari Google Fonts, jadi perlu internet. Tanpa internet, tampilan memakai font cadangan.
- **Video penutup tidak mau jalan di browser lama:** pakai Chrome, Edge, atau Safari versi terbaru.

## Catatan penting sebelum repo dibuat publik

- GitHub Pages di akun gratis hanya bisa untuk repo **Public**. Artinya foto tim, lagu, sound, dan video di repo bisa diunduh siapa saja yang tahu link-nya. Pastikan semua anggota tim setuju fotonya dipasang.
- Lagu drama Korea dan sound Jokowi bukan milik kalian. Untuk presentasi tugas biasanya tidak bermasalah, tapi kalau ragu, hapus kedua file itu (atau ganti dengan yang bebas hak cipta) sebelum repo dibuat publik. Presentasi tetap jalan, hanya tanpa suara itu.
- Isi teks slide diambil dari file PPT asli tanpa diubah. Ada satu angka yang tidak sama di PPT aslinya: Lazada tertulis 15% (proporsi 13,64%) di slide 9, tapi 5% (Rp 250.000.000) di slide 12. Samakan di PPT dan di `index.html` kalau mau konsisten.
