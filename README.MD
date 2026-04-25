# 💫 TERA BAILEYS

Custom WhatsApp library built on Baileys — enhanced, modernized, and elegant.

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="100%">

<div align="center">
  <h1>💫 TERA BAILEYS</h1>
  <p><em>A custom WhatsApp library built upon Baileys — enhanced, modernized, and elegant.</em></p>

<br><br>

  <p>
    <a href="https://whatsapp.com/channel/0029VbB5gkZ6GcGHtBbwmD3m">
      <img src="https://img.shields.io/badge/Join-WhatsApp%20Channel-25D366?logo=whatsapp&logoColor=white" alt="WhatsApp Channel" />
    </a>
  </p>
</div>

> [!CAUTION]
> The old Tera Baileys channel was closed due to an admin error, and all updates have been moved to the new channel (linked above).
> This project is built on top of the WhiskeySockets/Baileys project. All original core logic credits belong to that team. Tera Baileys extends it with UX and DX improvements.

---

## 📌 Overview

`tera-baileys` is an enhanced version of the Baileys library with cleaner API usage and modern features such as album messaging, newsletter controls, and full-size profile uploads — designed for modern WhatsApp automation.

> **Updates:**
> All update information is now available on the WhatsApp channel (see homepage section).

---

## 📦 Installation

```bash
npm install tera-baileys
```

### Importing

#### ESM

```js
import makeWASocket from 'tera-baileys';
```

#### CJS

```js
const { default: makeWASocket } = require('tera-baileys');
```

---

## 🌟 Key Features

| Category         | Description                                         |
| ---------------- | --------------------------------------------------- |
| Channels         | Send messages to WhatsApp channels seamlessly.      |
| 🖱️ Buttons          | Interactive messages with quick reply options.      |
| 🖼️ Albums           | Group images or videos into carousel-style albums.  |
| 👤 LID Grouping     | Use modern @lid addressing for group operations.    |
| 🤖 AI Message Style | Display messages with an AI-style icon.             |
| 📷 HD Profile Pics  | Upload full-size profile pictures without cropping. |
| 🔐 Pairing Code     | Generate custom alphanumeric pairing codes.         |
| 🛠️ Dev Experience   | Reduced logging noise and optimized performance.    |

---

## 🚀 Features & Usage

### 📬 Newsletter Control

Manage WhatsApp newsletters (channels), including creation and messaging.

<details>
<summary><strong>Example</strong></summary>

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

Send interactive messages with buttons to improve engagement.

<details>
<summary><strong>Example</strong></summary>

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

Send multiple images or videos as a single album message.

<details>
<summary><strong>Example</strong></summary>

```js
const media = [
  { image: { url: "https://example.com/pic1.jpg" } },
  { video: { url: "https://example.com/clip.mp4" } }
];

await sock.sendMessage(id, {
  album: media,
  caption: "Memories 💫"
});
```

</details>

---

### 🔐 Custom Pairing Code

Generate a pairing code for WhatsApp device linking.

<details>
<summary><strong>Example</strong></summary>

```js
const code = await sock.requestPairingCode("94xxxxxxxxxx", "TERA01");
console.log("Pairing Code:", code);
```

</details>

---

### 📊 Poll Creation

Create polls for quick voting in chats or groups.

<details>
<summary><strong>Example</strong></summary>

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

Share a location with coordinates and address information.

<details>
<summary><strong>Example</strong></summary>

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

Create groups, add members, and update group descriptions.

<details>
<summary><strong>Example</strong></summary>

```js
const group = await sock.groupCreate(
  "My New Group",
  [number1, number2]
);

await sock.groupAdd(group.id, [number3]);
await sock.groupUpdateDescription(group.id, "This is our awesome group!");
```

</details>

---

### 🐞 Found a Bug?

If you encounter a bug or issue, you can:

* Report it via the official issue tracker (coming soon)
* Contact the maintainer directly on WhatsApp
