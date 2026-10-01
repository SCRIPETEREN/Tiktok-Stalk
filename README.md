# TikTok Stalk - TikTok Profile Scraper

> **GitHub Repository Title**
>
> ```text
> TikTok Stalk - TikTok Profile Scraper
> ```
>
> **Repository Name**
>
> ```text
> tiktok-stalk
> ```
>
> **GitHub Repository Description**
>
> ```text
> Node.js CLI scraper to retrieve public TikTok profile information, account statistics, and top videos from a username.
> ```

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-16%2B-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js">
  <img src="https://img.shields.io/badge/Axios-HTTP%20Client-5A29E4?style=for-the-badge&logo=axios&logoColor=white" alt="Axios">
  <img src="https://img.shields.io/badge/TikTok-Profile%20Scraper-000000?style=for-the-badge&logo=tiktok&logoColor=white" alt="TikTok">
  <img src="https://img.shields.io/badge/Creator-SCRIPETEREN-181717?style=for-the-badge&logo=github&logoColor=white" alt="Creator">
</p>

<p align="center">
  <b>Node.js CLI scraper untuk mengambil informasi profil TikTok publik.</b><br>
  Mengambil data profile, statistik akun, dan tiga video dengan jumlah views tertinggi dari username TikTok.
</p>

---

## Fitur

- Mengambil informasi profil TikTok berdasarkan username
- Mendukung input username dengan atau tanpa karakter `@`
- Mengambil TikTok User ID
- Mengambil username TikTok
- Mengambil nickname akun
- Mengambil avatar profile
- Mengambil bio atau signature akun
- Mengambil status akun verified
- Mengambil status akun private
- Mengambil status commerce account
- Mengambil status TikTok Seller
- Mengambil region akun jika tersedia
- Mengambil language akun jika tersedia
- Mengambil waktu pembuatan akun jika tersedia
- Mengambil URL profile TikTok
- Mengambil jumlah following
- Mengambil jumlah followers
- Mengambil total likes atau heart count
- Mengambil jumlah video
- Menampilkan jumlah followers, likes, dan video dalam format ringkas
- Mengambil tiga video dengan jumlah views tertinggi dari data yang tersedia
- Mengambil ID video
- Mengambil deskripsi video
- Mengambil jumlah views, likes, comments, dan shares video
- Mengambil durasi video
- Mengambil cover video
- Mengambil URL video jika tersedia pada response
- Mengambil waktu upload video
- Output dalam format JSON
- Penanganan error untuk username kosong, user tidak ditemukan, akun private, atau request yang diblokir

---

## Teknologi

Project ini menggunakan:

- [Node.js](https://nodejs.org/)
- [Axios](https://axios-http.com/)
- TikTok public profile page
- TikTok hydration data pada tag `__UNIVERSAL_DATA_FOR_REHYDRATION__`

---

## Struktur Project

```text
tiktok-stalk/
├── tiktok-stalk.js
├── package.json
├── package-lock.json
├── .gitignore
├── README.md
└── LICENSE
```

---

## Instalasi

Clone repository:

```bash
git clone [https://github.com/SCRIPETEREN/tiktok-stalk.git](https://github.com/SCRIPETEREN/tiktok-stalk.git)
```

Masuk ke folder project:

```bash
cd tiktok-stalk
```

Install dependency:

```bash
npm install
```

Jika belum memiliki `package.json`, install Axios secara manual:

```bash
npm install axios
```

---

## package.json

Buat file `package.json` dengan isi berikut:

```json
{
  "name": "tiktok-stalk",
  "version": "1.0.0",
  "description": "Node.js CLI scraper untuk mengambil data profil TikTok publik, statistik akun, dan top videos.",
  "main": "tiktok-stalk.js",
  "scripts": {
    "start": "node tiktok-stalk.js"
  },
  "keywords": [
    "tiktok",
    "tiktok-stalk",
    "tiktok-scraper",
    "tiktok-profile",
    "profile-scraper",
    "nodejs",
    "axios"
  ],
  "author": "SCRIPETEREN",
  "license": "MIT",
  "dependencies": {
    "axios": "^1.7.9"
  }
}
```

Install package:

```bash
npm install
```

---

## Cara Penggunaan

Format dasar:

```bash
node tiktok-stalk.js <username>
```

Contoh input username tanpa `@`:

```bash
node tiktok-stalk.js username
```

Contoh input username menggunakan `@`:

```bash
node tiktok-stalk.js @username
```

Menjalankan melalui NPM:

```bash
npm start username
```

Atau:

```bash
npm start -- @username
```

---

## Contoh Output

Contoh hasil ketika profile ditemukan:

```json
{
  "status": true,
  "data": {
    "profile": {
      "id": "1234567890123456789",
      "username": "username",
      "nickname": "Nama TikTok",
      "avatar": "[https://example.com/avatar.jpeg](https://example.com/avatar.jpeg)",
      "signature": "Contoh bio TikTok",
      "bioDescription": "Contoh bio TikTok",
      "verified": false,
      "privateAccount": false,
      "commerceUser": false,
      "ttSeller": false,
      "region": "ID",
      "language": "id",
      "createTime": "2024-01-01T00:00:00.000Z",
      "profileLink": "[https://www.tiktok.com/@username](https://www.tiktok.com/@username)"
    },
    "stats": {
      "followingCount": 120,
      "followerCount": 12500,
      "heartCount": 250000,
      "videoCount": 150,
      "heartCountFormatted": "250.0K",
      "followerCountFormatted": "12.5K",
      "videoCountFormatted": "150"
    },
    "topVideos": [
      {
        "id": "1234567890123456789",
        "description": "Contoh deskripsi video TikTok",
        "playCount": 1000000,
        "diggCount": 50000,
        "commentCount": 1000,
        "shareCount": 2500,
        "duration": 30,
        "coverUrl": "[https://example.com/cover.jpeg](https://example.com/cover.jpeg)",
        "videoUrl": "[https://example.com/video.mp4](https://example.com/video.mp4)",
        "createTime": "2025-01-01T00:00:00.000Z"
      }
    ]
  }
}
```

---

## Struktur Response

Response sukses memiliki format:

```json
{
  "status": true,
  "data": {
    "profile": {},
    "stats": {},
    "topVideos": []
  }
}
```

### Profile

| Field | Keterangan |
|---|---|
| `id` | ID unik akun TikTok |
| `username` | Username atau unique ID TikTok |
| `nickname` | Nama tampilan akun |
| `avatar` | URL foto profil |
| `signature` | Bio atau signature account |
| `bioDescription` | Deskripsi bio profile |
| `verified` | Status verified akun |
| `privateAccount` | Status akun private |
| `commerceUser` | Status akun commerce |
| `ttSeller` | Status TikTok Seller |
| `region` | Region account jika tersedia |
| `language` | Bahasa account jika tersedia |
| `createTime` | Waktu pembuatan account dalam format ISO |
| `profileLink` | URL profile TikTok |

### Stats

| Field | Keterangan |
|---|---|
| `followingCount` | Jumlah akun yang diikuti |
| `followerCount` | Jumlah followers |
| `heartCount` | Total likes atau hearts akun |
| `videoCount` | Total video akun |
| `heartCountFormatted` | Total likes format ringkas |
| `followerCountFormatted` | Total followers format ringkas |
| `videoCountFormatted` | Total video format ringkas |

### Top Videos

Script mengurutkan video berdasarkan `playCount` dari tertinggi ke terendah, lalu mengambil maksimal tiga video.

| Field | Keterangan |
|---|---|
| `id` | ID video TikTok |
| `description` | Caption atau deskripsi video |
| `playCount` | Jumlah views |
| `diggCount` | Jumlah likes |
| `commentCount` | Jumlah komentar |
| `shareCount` | Jumlah share |
| `duration` | Durasi video dalam detik |
| `coverUrl` | URL cover video |
| `videoUrl` | URL video jika tersedia |
| `createTime` | Waktu upload dalam format ISO |

---

## Format Angka

Script memiliki function `formatNumber()` untuk menampilkan angka besar dalam format lebih ringkas.

Contoh:

| Nilai Asli | Hasil |
|---|---|
| `500` | `500` |
| `1500` | `1.5K` |
| `12500` | `12.5K` |
| `1000000` | `1.0M` |
| `2500000` | `2.5M` |

---

## Error Handling

Script menangani beberapa kondisi error berikut:

- Username belum diberikan
- Username tidak ditemukan
- Account private
- TikTok memblokir request
- Gagal mengambil HTML profile
- Gagal mengekstrak hydration data
- Response TikTok berubah atau tidak memiliki data profile
- HTTP error
- Timeout request
- JSON parsing error

Contoh menjalankan tanpa username:

```bash
node tiktok-stalk.js
```

Output:

```json
{
  "status": false,
  "message": "Usage: node tiktok-stalk.js <username>"
}
```

Contoh ketika data profile tidak dapat diambil:

```json
{
  "status": false,
  "message": "Failed to extract profile data. User may not exist or TikTok blocked the request."
}
```

Contoh ketika user tidak ditemukan atau akun private:

```json
{
  "status": false,
  "message": "User not found or account is private"
}
```

Contoh ketika TikTok mengembalikan status 404:

```json
{
  "status": false,
  "message": "User not found"
}
```

---

## Cara Kerja

Script membentuk URL profile TikTok berdasarkan username:

```text
[https://www.tiktok.com/@username](https://www.tiktok.com/@username)
```

Kemudian script mengambil HTML profile menggunakan Axios.

Data profile diekstrak dari tag berikut:

```html
<script id="__UNIVERSAL_DATA_FOR_REHYDRATION__" type="application/json">
```

Data JSON dari tag tersebut diproses untuk memperoleh:

```text
__DEFAULT_SCOPE__.webapp.user-detail.userInfo
```

Data yang digunakan adalah:

```text
userInfo.user
userInfo.stats
userInfo.posts
```

Video yang tersedia di `userInfo.posts` akan diurutkan berdasarkan jumlah views:

```js
.sort((a, b) => (b.stats?.playCount || 0) - (a.stats?.playCount || 0))
.slice(0, 3)
```

---

## Batasan

- Script hanya dapat mengambil data profile yang tersedia secara publik.
- TikTok dapat memblokir request otomatis berdasarkan IP, User-Agent, cookies, atau rate request.
- TikTok dapat mengubah struktur HTML dan hydration JSON kapan saja.
- Field `posts` tidak selalu tersedia pada response profile.
- URL video dapat tidak tersedia, kadaluarsa, membutuhkan parameter tertentu, atau tidak bisa langsung diputar.
- Account private, banned, restricted, atau tidak ditemukan mungkin tidak menghasilkan data.
- Data statistik yang ditampilkan bergantung pada data yang TikTok tampilkan untuk profile tersebut.
- Jangan melakukan request berlebihan dalam waktu singkat.

---

## Rekomendasi Pengembangan

Beberapa pengembangan yang dapat ditambahkan:

- Menambahkan retry ketika request gagal
- Menambahkan proxy support
- Menambahkan cookie input melalui environment variable
- Menambahkan random User-Agent
- Menambahkan rate limit
- Menambahkan cache hasil request
- Menambahkan output CSV
- Menambahkan output file JSON
- Menambahkan command untuk mengambil lebih banyak video
- Menambahkan command untuk mengambil followers atau following jika tersedia
- Menambahkan Express API endpoint
- Menambahkan Telegram bot atau WhatsApp bot integration
- Menambahkan pilihan jumlah top video

---

## Penggunaan Sebagai Module

Agar file dapat digunakan pada project Node.js lain, pisahkan logic utama dan export function yang diperlukan.

Ubah bagian paling bawah dari:

```js
main()
```

Menjadi:

```js
if (require.main === module) {
  main()
}

module.exports = {
  formatNumber
}
```

Contoh penggunaan pada file lain:

```js
const { formatNumber } = require("./tiktok-stalk")

console.log(formatNumber(1500))
console.log(formatNumber(2500000))
```

Output:

```text
1.5K
2.5M
```

Untuk penggunaan module yang lebih lengkap, disarankan memindahkan proses pengambilan profile ke function khusus.

Contoh refactor:

```js
async function getTikTokProfile(username) {
  const cleanUsername = username.replace("@", "").trim()
  const apiUrl = `https://www.tiktok.com/@${cleanUsername}`

  const response = await axios.get(apiUrl, {
    timeout: 15000,
    headers: {
      "User-Agent": "Mozilla/5.0"
    }
  })

  const html = response.data

  const jsonMatch = html.match(
    /<script id="__UNIVERSAL_DATA_FOR_REHYDRATION__" type="application/json">(.*?)</script>/
  )

  if (!jsonMatch || !jsonMatch) {
    throw new Error("Failed to extract profile data")
  }

  const raw = JSON.parse(jsonMatch)

  return raw?.__DEFAULT_SCOPE__?.["webapp.user-detail"]?.userInfo || null
}
```

---

## .gitignore

Buat file `.gitignore` dengan isi berikut:

```gitignore
node_modules/
.env
npm-debug.log*
yarn-debug.log*
yarn-error.log*
.DS_Store
```

---

## License

Project ini menggunakan lisensi MIT.

Buat file `LICENSE`:

```text
MIT License

Copyright (c) 2026 SCRIPETEREN

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files, to deal in the Software
without restriction, including without limitation the rights to use, copy,
modify, merge, publish, distribute, sublicense, and/or sell copies of the
Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## Creator

```text
SCRIPETEREN
```

```text
[https://github.com/SCRIPETEREN](https://github.com/SCRIPETEREN)
```

---

## Disclaimer

Repository ini dibuat untuk pembelajaran Node.js, HTTP request, parsing JSON, dan pengolahan data profile TikTok yang tersedia secara publik.

Gunakan script secara bertanggung jawab. Jangan gunakan untuk melakukan spam, stalking berlebihan, pelanggaran privasi, pengumpulan data tanpa izin, atau aktivitas yang melanggar ketentuan TikTok maupun hukum yang berlaku.

<p align="center">
  Made by <a href="https://github.com/SCRIPETEREN">SCRIPETEREN</a>
</p>