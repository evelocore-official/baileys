<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%">

<div align="center">
  <h1>💫 TERA BAILEYS </h1>
  <p><em>Custom WhatsApp library built upon Baileys — enhanced, modernized, and elegant.</em></p>
</p>

  <br><br>

<p>
  <!-- WhatsApp Channel -->
  <a href="https://whatsapp.com/channel/0029VbB5gkZ6GcGHtBbwmD3m">
    <img src="https://img.shields.io/badge/Join-WhatsApp%20Channel-25D366?logo=whatsapp&logoColor=white" alt="WhatsApp Channel" />
  </a>
</p>
</div>

<div align="center">
  <img src="https://user-images.githubusercontent.com/74038190/212257468-1e9a91f1-b636-4676-a213-39d67b2d5d67.gif" width="100%">
</div>

> [!CAUTION]
> `tera-baileys` The old channel was banned due to an error by one of the admins, so we moved the information to the new channel.
> Built on top of the WhiskeySockets/Baileys project. All original core logic credits go to their team. tera-baileys extends it with thoughtful UX and DX improvements.
> 🙌 Contributors outside the Baileys code
Thanks to the following awesome contributors who help improve this project 💖
---


## 📌 Overview
>  `tera-baileys` is a refined version of the Baileys library with cleaner API usage, exclusive features like album messaging, newsletter controls, and full-size profile uploads — tailored for modern WhatsApp automation needs.

> **Update** 
> All update information is now redirected to the WhatsApp channel check at the bottom of the "homepage".

> Udpate changelog see on our WhatsApp channel

---

## 📦 Installation

### Via `package.json`

Fork Baileys (NPM) **@whiskeysockets/baileys** / **@adiwajshing/baileys**

```json
@whiskeysockets/baileys
"dependencies": {
    "@whiskeysockets/baileys": "npm:tera-baileys"
}
```
```json
@adiwajsing/baileys
"dependencies": {
    "@adiwajshing/baileys": "npm:tera-baileys"
}
```

Or via terminal non fork
```bash
npm install elaina-bail@npm:tera-baileys
```

Importing (for those who don't fork another repository)
ESM & CJS

> ESM
```bash
import makeWASocket from 'tera-baileys
```

> CJS
```bash
const { default: makeWASocket } = require('tera-baileys')
```
---
🌟 Key Features
| Category | Description |
|---|---|
|channels | Seamlessly send messages to WhatsApp Channels. |
| 🖱️ Buttons | Create interactive messages with button options and quick replies. |
| 🖼️ Albums | Send grouped images or videos as an album (carousel-like format). |
| 👤 LID Grouping | Handle group operations using the latest @lid addressing style. |
| 🤖 AI Message Style | Add a stylized “AI” icon to messages. |
| 📷 HD Profile Pics | Upload full-size profile pictures without cropping. |
| 🔐 Pairing Code | Generate custom alphanumeric pairing codes. |
| 🛠️ Dev Experience | Reduced noise from logs with optimized libsignal printouts. |
---

## 🚀 Features & Usage

### 📬 Newsletter Control
Kelola WhatsApp Newsletter (Channel), mulai dari pembuatan hingga interaksi pesan.

<details>
<summary><strong>Lihat Contoh</strong></summary>

```js
// Create a newsletter
await sock.newsletterCreate("Tera Updates");

// Update description
await sock.newsletterUpdateDescription(
  "tera@newsletter",
  "Fresh updates weekly"
);

// React to a channel message
await sock.newsletterReactMessage(
  "tera@newsletter",
  "175",
  "🔥"
);
```
</details>

---

### 📌 Interactive Messaging
Kirim pesan interaktif menggunakan tombol untuk meningkatkan interaksi pengguna.

<details>
<summary><strong>Lihat Contoh</strong></summary>

```js
const buttons = [
  { buttonId: "btn1", buttonText: { displayText: "Click Me" }, type: 1 },
  { buttonId: "btn2", buttonText: { displayText: "Visit Site" }, type: 1 }
];

await sock.sendMessage(id, {
  text: "Choose one:",
  footer: "From Tera with love 💜",
  buttons,
  headerType: 1
});
```

</details>

---

### 🖼️ Send Album
Kirim beberapa media (gambar atau video) dalam satu pesan album.

<details>
<summary><strong>Lihat Contoh</strong></summary>

```js
const media = [
  { image: { url: "https://example.com/pic1.jpg" } },
  { video: { url: "https://example.com/clip.mp4" } }
];

await sock.sendMessage(
  id,
  { album: media, caption: "Memories 💫" }
);
```

</details>

---

### 🔐 Custom Pairing Code
Pairing perangkat WhatsApp menggunakan kode kustom.

<details>
<summary><strong>Lihat Contoh</strong></summary>

```js
const code = await sock.requestPairingCode("94xxxxxxxxxx","TERA01");

console.log("Pairing Code:", code);
```

</details>

---

### 📊 Poll Creation
Buat polling untuk voting cepat di chat atau grup.

<details>
<summary><strong>Lihat Contoh</strong></summary>

```js
await sock.sendMessage(id, {
  poll: {
    name: "Favorite Color?",
    values: ["Red", "Blue", "Green"],
    selectableCount: 1
  }
});
```

</details>

---

### 📍 Location Sharing
Bagikan lokasi lengkap dengan koordinat dan alamat.

<details>
<summary><strong>Lihat Contoh</strong></summary>

```js
await sock.sendMessage(id, {
  location: {
    degreesLatitude: 37.422,
    degreesLongitude: -122.084,
    name: "Googleplex",
    address: "1600 Amphitheatre Pkwy, Mountain View"
  }
});
```

</details>

---

### 👥 Group Management
Kelola grup WhatsApp: membuat grup, menambah anggota, dan memperbarui deskripsi.


<details>
<summary><strong>Lihat Contoh</strong></summary>

```js
const group = await sock.groupCreate(
  "My New Group",
  [number1, number2]
);

await sock.groupAdd(group.id, [number3]);
await sock.groupUpdateDescription(group.id,"This is our awesome group!"
);
```

</details>

---

### 🐞 Menemukan Bug?

Jika Anda menemukan bug atau kendala saat menggunakan proyek ini, silakan lakukan salah satu opsi berikut:

- **Buka Issue** melalui website resmi (segera hadir)
- **Hubungi maintainer langsung** melalui WhatsApp

<p align="center">
  <a href="https://wa.me/94786802371" target="_blank" rel="noopener noreferrer">
    <img
      alt="Chat on WhatsApp"
      src="https://img.shields.io/badge/Chat%20on%20WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white"
    />
  </a>
</p>
<details>
<summary>🙏 <strong>TQTO (Thanks To)</strong></summary>

Terima kasih kepada semua pihak yang telah memberikan dukungan, inspirasi, serta kontribusi—baik secara langsung maupun tidak langsung—dalam pengembangan proyek ini:

- **Allah SWT** — atas segala rahmat, kemudahan, dan perlindungan-Nya.
- **Orang Tua** — atas kasih sayang, doa, dan dukungan yang tiada henti.
- **RexxHayanasi (Saya)** — pengembang utama proyek ini.

</details>

<table>
<tr>
<td align="center">
<a href="https://github.com/nimesh-piyumal">
<img src="https://avatars.githubusercontent.com/u/150516773?v=4" width="80px;" style="border-radius:50%;" alt="Rexx"/>
<br />
<sub><b>Nimesh Piyumal [ developer project ]</b></sub>
</a>
</td>
</tr>
</table>

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%" style="transform: rotate(180deg);">
