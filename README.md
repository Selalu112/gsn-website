# CV Global Sinergi Nusantara — Website V1

Website company profile resmi **CV Global Sinergi Nusantara (GSN)** — HTML, CSS, JavaScript tanpa framework dan tanpa database. Disiapkan untuk **GitHub + Cloudflare Pages**.

## Halaman

- `index.html` — beranda premium, informasi perusahaan, ringkasan layanan, dokumentasi, alur kerja.
- `tentang.html` — profil, visi, misi, nilai, standar kualitas.
- `layanan.html` — konstruksi, infrastruktur, sewa alat berat dan material.
- `portofolio.html` — galeri dengan filter dan pembesaran gambar.
- `kontak.html` — informasi kontak dan formulir terhubung WhatsApp.

## Deploy otomatis dengan GitHub + Cloudflare Pages

**1. Buat repository GitHub**

Buka https://github.com/new lalu buat repository bernama `gsn-website` (public atau private sesuai pilihan Anda). Jangan membuat repo lain bernama sama jika sudah ada. Upload isi paket ini sehingga `README.md` dan folder `public/` ada di root repository. Disarankan branch `main`.

Atau melalui terminal di folder hasil ekstraksi:

```bash
git init
git add .
git commit -m "Initial GSN website"
git branch -M main
git remote add origin https://github.com/USERNAME/gsn-website.git
git push -u origin main
```

Ganti `USERNAME` dengan username GitHub sendiri.

**2. Integrasikan di Cloudflare**

Buka https://dash.cloudflare.com/ → **Workers & Pages** → **Create application** → **Pages** → **Connect to Git** atau **Import an existing Git repository**. Hubungkan GitHub lalu pilih repository `gsn-website`.

Isi pengaturan:

| Pengaturan | Nilai |
| --- | --- |
| Production branch | `main` |
| Framework preset | None |
| Build command | `exit 0` (atau kosong) |
| Build output directory | `public` |
| Root directory | default / repository root |

Klik **Save and Deploy**. Cloudflare akan memberikan alamat `*.pages.dev` sesudah deploy berhasil. Push berikutnya ke `main` akan memicu deploy otomatis.

**Penting:** Jangan memilih Direct Upload jika Anda menginginkan Git integration otomatis; buat proyek melalui *Connect to Git* sejak awal.

## Pratinjau lokal

Buka `public/index.html` di browser, atau jalankan server lokal dari folder website:

```bash
python -m http.server 8000 --directory public
```

Buka http://localhost:8000 di browser.

## Konten dan aset

- Logo diolah dari gambar yang diberikan pemilik GSN (hanya dioptimalkan untuk header dan favicon).
- Foto dari company profile GSN yang diberikan pemilik, bukan foto proyek dari situs lain.
- Nomor WhatsApp: `6281338055805` berdasarkan nomor di PDF; perubahan kontak dapat dicari di file-file HTML dan `public/script.js`.
- Dokumentasi proyek belum mencantumkan nama, lokasi, tahun, pelanggan, atau nilai kontrak karena belum diberikan dalam company profile.
- Formulir kontak bekerja **tanpa backend**: membentuk pesan dan membuka WhatsApp. Pengunjung masih harus mengirim pesan dari aplikasi WhatsApp mereka; website **tidak** menyimpan data formulir.
- Status unit dan harga sewa/perkiraan biaya proyek perlu dikonfirmasi melalui GSN; tidak ada harga yang dibuat-buat.
- Jika domain kustom sudah ada, tambahkan domain melalui Pages > Custom domains, lalu perbarui metadata OG dan tambahkan sitemap absolut sesuai domain.

## Checklist sebelum publikasi final

- [ ] Periksa ejaan nama perusahaan, email, nomor WhatsApp, dan alamat.
- [ ] Periksa status penggunaan gambar/foto company profile untuk website publik.
- [ ] Tambahkan identitas proyek dan dokumentasi tambahan yang disetujui.
- [ ] Tambahkan legalitas/perizinan, sertifikasi, dan tim dengan data yang terverifikasi jika ingin ditampilkan.
- [ ] Uji formulir WhatsApp di Android/iOS serta desktop.
- [ ] Hubungkan domain resmi apabila sudah dipilih.

## Teknologi

Vanilla HTML5, CSS3, JavaScript ES2020. Tidak ada proses build, rahasia API, akun admin, atau database. `_headers` disiapkan untuk Cloudflare Pages.