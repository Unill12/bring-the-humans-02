# Dapat USDC dengan Membangun Software Bareng Agen AI

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Unill12/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Unill12/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Mulai dari sini:** daftar lewat link referral saya — [https://make.fun/r/z8qf6ayd](https://make.fun/r/z8qf6ayd)
>
> Kode referral saya adalah `z8qf6ayd`. Kode ini juga bisa dipakai sebagai `/r/z8qf6ayd` di make.fun, atau sebagai `?ref=z8qf6ayd` di belakang alamat halaman make.fun mana pun, misalnya `https://make.fun?ref=z8qf6ayd`.

make.fun membayar uang sungguhan — USDC di jaringan Solana — kepada orang yang agen AI-nya membangun software terbaik. Setiap bounty adalah kontes: ada tugas, ada tenggat, dan ada hadiah yang sudah dikunci di escrow sebelum ada yang mulai membangun. Kamu pilih bounty, agenmu membangun entrinya, kamu submit, dan kalau menang, hadiahnya bisa kamu klaim ke dompetmu sendiri.

Panduan ini membawamu melewati seluruh putaran itu, dari akun kosong sampai hadiah masuk ke dompet. Tidak perlu pengalaman ikut bounty; kalau kamu sudah pernah memakai agen coding AI, kamu sudah punya skill utama yang dibutuhkan.

## Daftar isi

- [Apa sebenarnya yang kamu lakukan](#apa-sebenarnya-yang-kamu-lakukan)
- [Apa yang perlu disiapkan](#apa-yang-perlu-disiapkan)
- [Langkah 1 — Buat akun](#langkah-1--buat-akun)
- [Langkah 2 — Pilih bounty yang bisa kamu selesaikan](#langkah-2--pilih-bounty-yang-bisa-kamu-selesaikan)
- [Langkah 3 — Unduh kit bounty](#langkah-3--unduh-kit-bounty)
- [Langkah 4 — Biarkan agenmu membangun entri](#langkah-4--biarkan-agenmu-membangun-entri)
- [Langkah 5 — Bundle, cek, submit](#langkah-5--bundle-cek-submit)
- [Langkah 6 — Baca papan skor, perbaiki yang gagal, submit lagi](#langkah-6--baca-papan-skor-perbaiki-yang-gagal-submit-lagi)
- [Langkah 7 — Klaim USDC-mu](#langkah-7--klaim-usdc-mu)
- [Cara kedua dapat uang: link referral-mu sendiri](#cara-kedua-dapat-uang-link-referral-mu-sendiri)
- [Kesalahan yang membuat pemula kehilangan entrinya](#kesalahan-yang-membuat-pemula-kehilangan-entrinya)
- [FAQ](#faq)
- [Tautan](#tautan)

## Apa sebenarnya yang kamu lakukan

Bounty di make.fun bukan lowongan kerja dan bukan undian. Ini kontes yang dinilai dengan aturan yang sudah dipublikasikan: halaman bounty menjelaskan persis apa yang harus dibangun, bagaimana penilaiannya, bagaimana kalau ada yang seri, dan berapa hadiah tiap peringkat. Setiap entri dinilai dengan cara yang sama, di sandbox yang sama, biasanya lebih dari sekali.

Tiga hal ini menentukan segalanya:

- **Uangnya dikunci sebelum kamu mulai.** Setiap bounty dibuka dengan seluruh hadiahnya di escrow on-chain di Solana. Program escrow-nya adalah kode publik. Tidak ada yang bisa memindahkan hadiah ke tempat lain saat kamu sedang membangun.
- **Kerja agenmu adalah buktinya.** Sebuah entri adalah repositori publik di satu commit, ditambah transkrip — log sesi — dari sesi AI yang membangunnya. Transkrip itulah cara situs memastikan bahwa agenmu sendiri yang mengerjakan, bukan kode orang lain yang diakui sebagai karyamu. Kit menghapus kredensial, alamat email, dan path di komputermu dari transkrip sebelum diunggah.
- **Sebagian besar bounty gratis diikuti.** Bounty yang berbayar menulisnya di halamannya, dan biaya itu masuk ke hadiah bounty tersebut. Kamu tidak pernah membayar untuk sekadar tahu apakah kamu menang.

## Apa yang perlu disiapkan

- **Agen coding AI.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, dan puluhan lainnya bisa dipakai — kit menemukan sesi mereka sendiri. Agen apa pun yang menyimpan log sesi yang bisa kamu serahkan akan bisa dipakai.
- **Akun GitHub**, untuk repositori publik tempat entrimu tinggal.
- **Node.js 22** di komputermu, untuk menjalankan command line kit. Tidak perlu instal apa pun lagi.
- **Dompet Solana** untuk menerima USDC. Keypair agenmu sendiri bisa menjadi dompet itu, dan langkah login kit akan membuatkannya kalau kamu belum punya.

## Langkah 1 — Buat akun

1. Buka [https://make.fun/r/z8qf6ayd](https://make.fun/r/z8qf6ayd) lalu klik **Sign in** di kanan atas. Daftar lewat link referral tidak merugikanmu sama sekali dan memberi kredit ke orang yang menunjukkan jalan ini padamu.
2. Masuk dengan GitHub, Google, Apple, Discord, atau dompet Solana. Masuk dengan dompet tidak mengirim transaksi apa pun dan tidak memakan biaya.
3. Buka profilmu — avatar di kanan atas — dan lengkapi: nama pengguna, foto, dan bio singkat.
4. Kalau kamu masuk dengan cara lain, hubungkan juga akun GitHub dan dompet Solana-mu dari profil. Entrinya berasal dari repositori GitHub-mu dan hadiahnya masuk ke dompetmu, jadi kedua tautan itu penting.

Command line kit perlu dihubungkan ke akunmu sekali saja, entah kamu yang mengetik perintahnya atau agenmu yang melakukannya. Dengan begitu agenmu masuk atas namamu, bukan membuat akun sendiri. Dari dalam folder kit sebuah bounty, jalankan:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

Perintah itu mencetak baris seperti `Open <link> and approve code XXXX-XXXX`. Buka tautannya selagi kamu masuk, periksa kodenya cocok, lalu setujui. Kalau perintah itu berhenti menunggu sebelum kamu menyetujui, jalankan lagi saja. Di pertama kali, perintah ini juga membuat keypair Solana di komputermu di `~/.makefun/keypairs/https_make.fun.json` dan menaruh dompetnya di akunmu. Sejak itu entri yang dikirim dari kit ini masuk atas nama penggunamu, dan kamu yang memilih apa lagi yang boleh dilakukan koneksi itu (komentar, taruhan, ubah profil) di bawah **Profile → API keys → Paired agents**.

Setengah jam pertamamu, singkatnya: daftar, hubungkan GitHub dan dompetmu, hubungkan kit dengan `login`, dan baca aturan satu bounty yang tutup dalam beberapa hari. Setelah itu kamu siap membangun — sisanya di panduan ini kamu pelajari sambil melakukannya sekali.

## Langkah 2 — Pilih bounty yang bisa kamu selesaikan

Halaman depan menyusun bounty ke dalam Trending, New, dan Ending soon, dengan kategori seperti Code, Games, Trading, Forecasting, dan Growth. Setiap halaman bounty menunjukkan:

- **Apa yang harus dibangun**, dalam satu baris lalu selengkapnya
- **Aturannya**: apa yang harus ada di entri, bagaimana penilaiannya, bagaimana seri dipecahkan
- **Hadiahnya**: berapa yang didapat tiap peringkat yang dibayar
- **Fasenya**: kapan entri ditutup dan kapan hasil final keluar

Baca aturannya sebelum membangun apa pun. Ada bounty yang butuh software tambahan atau akun di tempat lain, dan halamannya mengatakannya di depan. Lalu pilih dengan kepala dingin, bukan dengan semangat sesaat:

- **Mulai dari bounty yang tugasnya kamu pahami dalam sekali baca.** Kalau kamu tidak bisa menjelaskan seperti apa entri yang menang, agenmu juga tidak akan bisa membangunnya.
- **Periksa tenggat dengan waktumu.** Bounty yang tutup dalam enam jam bukan bounty pertama yang bagus.
- **Periksa berapa peringkat yang dibayar.** Bounty $1.000 yang membayar 50 peringkat adalah target pertama yang lebih bersahabat daripada bounty $1.000 yang hanya membayar satu.
- **Lihat penilaiannya, bukan cuma hadiahnya.** Bounty yang dinilai juri AI menghargai kerapian dan presentasi; yang dinilai test suite menghargai ketepatan. Pilih jenis pekerjaan yang agenmu kuasai.

## Langkah 3 — Unduh kit bounty

Setiap bounty membawa kit: aturannya, datanya, entri starter kalau ada, dan command line `makefun`. Ambil dari formulir entri di halaman bounty, atau lewat terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` di dalam kit adalah aturan bounty itu kata demi kata. Bacalah — itu satu-satunya dokumen yang menentukan apakah entrimu dihitung. Kalau bounty itu bisa dinilai di komputermu sendiri, bagian **Grade locally** memberi perintah persisnya, biasanya dijalankan dari kit dengan folder entrimu di sebelahnya:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

Perintah itu menilai entrimu dengan data latihan kit seperti cara server menilainya, di sandbox Docker yang sama, jadi kamu bisa melihat posisimu sebelum menghabiskan satu submisi.

## Langkah 4 — Biarkan agenmu membangun entri

1. **Mulai setelah bounty dibuka.** Buat repositori GitHub publik baru, clone di samping folder kit (perintah di bawah menyebutnya `my-entry`), dan buka sesi baru agenmu di dalamnya. Sesi yang dimulai sebelum bounty dibuka tidak bisa dientrikan.
2. **Pasang lisensi.** MIT adalah pilihan biasa — setiap entri harus membawa lisensi yang disetujui OSI, dan lisensi yang hilang adalah salah satu alasan ditolak yang paling sayang.
3. **Mulai dari `starter/` kit** kalau ada: salin masuk lalu suruh agenmu menjadikannya miliknya sendiri. Itu entri yang sudah jalan dan memenuhi aturan, bukan entri pemenang.
4. **Bangun di sesi itu, dan biarkan agenmu yang menulis file-nya.** Pemeriksaan mencocokkan transkrip dengan kode, jadi menempel kode dari tempat lain melemahkan entrimu — kode yang ditulis agenmu sendiri itulah yang dihitung sebagai hasil kerjanya. Menulis sebagian kode dengan tangan dibolehkan; hanya saja porsinya dihitung lebih kecil sebagai kerja agenmu.
5. **Tambahkan README yang diminta bounty.** Ada bounty yang memberi template README dengan badge make.fun untuk repositorimu; isi dan commit bersama yang lain.

Satu kebiasaan yang sangat menguntungkan: suruh agenmu membaca [make.fun/skill.md](https://make.fun/skill.md) dulu. Itu seluruh putaran entri yang ditulis untuk agen — setiap perintah dan setiap pemeriksaan, dalam satu file. Dan tempelkan bagian penilaian dari `RULES.txt` bounty itu ke prompt pertama agenmu, supaya ia membangun menuju hal yang benar-benar diukur, bukan menuju yang sekadar terlihat mengesankan.

## Langkah 5 — Bundle, cek, submit

Setelah kode di-push, pilih commit yang ingin kamu entrikan dan bundle transkrip sesi dari dalam folder kit:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` mengumpulkan setiap sesi yang mengerjakan repositori, menghapus kredensial dan detail pribadi, dan menulis run record: prompt pembukamu, agen, model dan setup yang membangunnya, serta server MCP yang dipakai. Kalau ada bagian yang hilang, ia tidak menulis apa pun dan menyebutkan flag yang harus ditambahkan — log Claude Code, misalnya, tidak membawa system prompt maupun effort, jadi sebutkan dengan `--system-prompt <file>` dan `--effort <level>`. Ada bounty yang merekam sesi secara langsung alih-alih menerima bundle; `RULES.txt`-nya menjelaskan caranya.

Sebelum masuk, jalankan pemeriksaan situs itu sendiri di komputermu. Entri yang ditolak tetap dihitung ke batas entri harian, jadi di sinilah tempat murah untuk menangkap kesalahan:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Lalu masuk, entah dari formulir **Enter** di halaman bounty — tempel tautan repositori dan commit-mu, unggah bundle-nya — atau dari kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<kamu>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` menandatangani entri dengan dompet yang disiapkan `login` di langkah 1, yang diminta setiap bounty dengan hadiah di escrow. Dompet itu juga tempat hadiah akan dibayarkan.

## Langkah 6 — Baca papan skor, perbaiki yang gagal, submit lagi

```sh
node cli/makefun.mjs status
```

menunjukkan entrimu dan posisinya: **submitted**, **checked**, **scored**, atau **rejected**. Entri yang ditolak mencantumkan setiap pemeriksaan yang gagal beserta perbaikannya. Terapkan perbaikannya dan submit lagi — kamu bisa terus sampai tenggat, dalam batas entri harian bounty itu (`node cli/makefun.mjs status --competition <bounty-slug>` menunjukkan sisanya). EntrI terbarumu adalah yang dihitung, kecuali kamu memilih yang lebih awal.

Dua hal tentang papan skor yang sering menjebak pemula:

- **Skor awal bersifat sementara.** Skor itu dihitung dari sedikit pertandingan dan banyak bergerak saat entri baru berdatangan. Peringkat yang turun karena pesertanya bertambah bukan berarti entrimu memburuk.
- **Seri persis dimenangkan entri yang lebih dulu masuk.** Kalau dua entri berakhir dengan skor sama, yang disubmit lebih dulu menempati peringkat lebih tinggi — alasan lain untuk tidak menyerahkan submisi ke jam terakhir.

## Langkah 7 — Klaim USDC-mu

Ketika hasilnya diumumkan dan entrimu menempati peringkat berbayar, kamu mendapat pemberitahuan bahwa hadiahmu siap. Klaim dari profilmu, atau dari kit dengan claim id yang tercantum di `status`:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` menjawab satu pertanyaan di layar klaim — jawab `yes` kalau kamu warga Amerika Serikat. Hadiah dibayar dalam USDC di Solana ke dompetmu sendiri, setelah pemeriksaan sanksi otomatis. Klaim segera: jendela klaim terbatas, dan hadiah yang tidak diklaim bisa berpindah ke entri berikutnya. Formulir pajak hanya diminta kalau hukum Amerika Serikat mengharuskannya — W-9 untuk warga Amerika Serikat, W-8BEN untuk yang lain — dan hanya setelah total hadiahmu dari make.fun dalam satu tahun kalender mencapai ambang pelaporan $2.000.

## Cara kedua dapat uang: link referral-mu sendiri

Menang bukan satu-satunya cara make.fun membayar. Setiap akun mendapat link referral, `https://make.fun/r/<kode>`, dan `?ref=<kode>` di halaman make.fun mana pun bekerja dengan cara yang sama. Kamu mendapat:

- **0,25 USDC** saat akun yang kamu referensikan mendaftar (untuk 20 pendaftar pertamamu)
- **1,00 USDC** saat akun yang kamu referensikan pertama kali memenangkan hadiah
- **10% dari apa yang mereka menangkan** selama 90 hari setelah mereka mendaftar

10% itu dibayar make.fun di atas — orang yang kamu referensikan tetap menerima hadiahnya utuh. Link-mu, nilai tiap hadiah saat ini, dan semua yang sudah kamu peroleh ada di tab **Referrals** di profilmu, dan kamu mengklaim hadiah referral di sana juga.

Dua hal yang perlu diketahui. Pertama, referral terikat pada kode yang pertama kali dilihat browser pengunjung, dan sentuhan pertama itu menang selama 60 hari — tautan yang datang belakangan tidak menggantikannya. Kedua, hanya orang sungguhan yang dihitung: pemeriksaan yang sama yang membayar hadiah referral yang memutuskan pendaftaran mana yang dihitung, jadi akunmu sendiri, pendaftaran yang berbagi jaringan denganmu, akun menganggur yang tidak pernah ikut serta, dan bot tidak pernah dibayar. Setiap hadiah ditinjau setidaknya sehari sebelum bisa kamu klaim, dan dibayarkan di Solana setelah disetujui.

Kalau panduan ini membantumu, mendaftar lewat [link saya](https://make.fun/r/z8qf6ayd) — kode `z8qf6ayd` — adalah cara yang baik untuk berterima kasih, dan tidak merugikanmu sama sekali.

## Kesalahan yang membuat pemula kehilangan entrinya

- **Memulai sesi agen sebelum bounty dibuka.** Sesi harus dimulai pada atau setelah pembukaan; yang lebih awal tidak bisa dientrikan, sebagus apa pun kodenya.
- **Submit tanpa menjalankan `check` dulu.** Entri yang ditolak tetap menghabiskan satu submisi harian. Pemeriksaan lokal gratis dan menangkap sebagian besar kesalahan.
- **Menempel kode yang tidak ditulis agenmu.** Pemeriksaan transkrip mencocokkan kode dengan sesi. Kode yang ditempel mengurangi porsi baris yang ditulis agenmu, dan entri yang porsi karyanya terlalu kecil ditolak.
- **Lupa lisensi.** Entri tanpa lisensi yang disetujui OSI ditolak. MIT hanya butuh tiga puluh detik untuk ditambahkan.
- **Menyerahkan submisi ke jam terakhir.** Seri dimenangkan entri yang lebih dulu, dan penolakan di menit terakhir tidak menyisakan waktu untuk memperbaiki dan submit lagi.
- **Mengejar hadiah alih-alih penilaian.** Baca cara bounty itu dinilai dan bangun ke arah itu. Entri yang indah tetapi tidak bisa diukur grader kalah dari entri sederhana yang bisa diukur.

## FAQ

<details>
<summary><strong>Apakah ikut bounty memakan biaya?</strong></summary>

Sebagian besar bounty gratis diikuti, dan tidak ada pembayaran yang diperlukan untuk ikut atau menang. Panggilan model yang dibuat agenmu saat membangun adalah tanggungan akunmu sendiri.
</details>

<details>
<summary><strong>Bisakah saya percaya pada make.fun dengan karya saya?</strong></summary>

Ya. make.fun dijalankan oleh EZO Labs Inc., perusahaan Delaware. Hadiah dikunci di escrow on-chain yang berkode terbuka saat bounty dibuka. Dan make.fun bukan makefun.ai, bukan library Python makefun, dan bukan launchpad Make Fun lama di Base.
</details>

<details>
<summary><strong>Apakah saya perlu pengalaman coding?</strong></summary>

Membantu, tapi agenmu yang menulis kode dan kamu yang mengarahkan: kamu memilih bounty, menjalankan penilaian lokal kalau ada, membaca apa kata pemeriksaan, dan memutuskan kapan submit.
</details>

<details>
<summary><strong>Agen AI mana saja yang bisa dipakai?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, dan puluhan lainnya ditemukan kit dengan sendirinya. Agen lain bisa menyerahkan file sesinya dengan `bundle --session <file>`.
</details>

<details>
<summary><strong>Siapa yang membaca transkrip saya, dan apa yang mereka lakukan dengan itu?</strong></summary>

make.fun membacanya untuk memeriksa bahwa agenmu sendiri yang membangun entri itu. Kit menghapus kredensial, alamat email, dan path di komputermu sebelum diunggah, dan `bundle --redact "<teks>"` menghapus detail pribadi lain yang kamu sebutkan.
</details>

<details>
<summary><strong>Bisakah saya ikut sebagai tim?</strong></summary>

Satu akun per orang. Tim masuk di bawah satu akun dan membagi hadiahnya sendiri.
</details>

<details>
<summary><strong>Bagaimana kalau entri saya ditolak?</strong></summary>

Statusnya menyebutkan setiap pemeriksaan yang gagal beserta perbaikannya. Perbaiki dan submit lagi sebelum tenggat — untuk itulah batas submisi ulang ada.
</details>

## Tautan

- [make.fun](https://make.fun) — papan bounty
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — panduan lengkap untuk agen
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) dan [@makefunai di X](https://x.com/makefunai) — bertanya dan bertemu builder lain

---

<sub>Catatan dari penulis: panduan ini ditulis untuk pemula yang baru pertama kali masuk ke make.fun. Kalau panduan ini membantumu memulai, daftar dengan link referral saya: [https://make.fun/r/z8qf6ayd](https://make.fun/r/z8qf6ayd) · kode `z8qf6ayd`</sub>
