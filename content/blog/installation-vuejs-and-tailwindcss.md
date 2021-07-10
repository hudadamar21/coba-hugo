---
title: "Installation Vuejs dan Tailwindcss"
description: "Pada tahap ini kalian akan menginstall vuejs dan tailwindcss dengan melakukan setup keseluruhan stuff stuff sampai website dapat ditampilkan."
date: 2021-07-10T08:56:15+07:00
draft: false
thumbnail: "https://firebasestorage.googleapis.com/v0/b/saxtile.appspot.com/o/68eV1uG7dtXIzJ3lNqNphaT23op1%2FInstallation%20Tailwindcss%20jit%20m.png?alt=media&token=61d3848f-2710-45f5-8f0c-6cd6d646ae30"
tags:
- vuejs
- tailwindcss
---

<br/>

## Persiapan
Pertama-tama sebelum menginstall Vuejs dan tailwindcss kalian harus menginstall Nodejs dan npm terlabih dahulu.

Install nodejs cukup mudah, kalian hanya perlu download pada laman dibawah ini:

[download dan install nodejs](https://nodejs.org/en/)

<br/>

Setelah menginstall nodejs kalian harus memastikan nodejs dan npm sudah terinstall.

Kalian hanya perlu ketikan baris kode ini di cmd/gitbash
```bash
node --version
```
```bash
npm --version
```

<br />

## Install Vuejs

Pada tutorial kali ini kalian akan menginstall Vuejs menggunakan Vitejs.

Kenapa menggunakan Vitejs?

Kalian bisa lihat penjelasannya lengkapnya disini: [Why Vite?](https://vitejs.dev/guide/why.html)

Dengan menggunakan Vitejs kalian dapat menjalankan server dengan sangat cepat hanya beberapa detik dan dependencies yang terinclude hanya sedikit jadi lebih hemat untuk penyimpanan.

<br/>

### Init Vitejs App

ketikan script ini pada cmd/gitbash dan pilih <filename>vue</filename>
```bash
 npm init @vitejs/app first-vuejs-app
```

masuk ke directory <filename>first-vuejs-app</filename>
```bash
cd first-vuejs-app
```

untuk menginstall semua dependecies yang dibutuhkan
```bash
npm install
```

untuk menjalankan server vuejs yang akan jalan pada <span class="underline">http://localhost:3000</span>
```bash
npm run dev
```

<br/>

### First look Vuejs App
![firstlook-vuejs](/content/firstlook-vuejs-app.png)


## Install Tailwindcss
Setelah menginstall Vuejs sekarang kalian akan menginstall tailwindcss, untuk menginstall tailwind kalian perlu beberapa package tambahan seperti postcss dan autoprefixer.

pastikan kalian sudah berada didalam directory project vuejs.

ketikan script ini di cmd/gitbash:
```bash
npm install -D tailwindcss@latest postcss@latest autoprefixer@latest
```

<br>

### Membuat file konfigurasi

membuat file <filename>tailwind.config.js</filename> dan <filename>postcss.config.js</filename> secara otomatis dengan mengetikan:
```bash
npx tailwindcss init -p
```

ini akan membuatkan file <filename>tailwind.config.js</filename>
```javascript
module.exports = {
  purge: [],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {
    extend: {},
  },
  plugins: [],
}
```

dan membuatkan file <filename>postcss.config.js</filename> yang sudah memasukan plugin tailwindcss dan autoprefix.
```javascript
// postcss.config.js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

<br/>

### Hapus css yang tidak terpakai dengan purge

pada file <filename>tailwind.config.js</filename>, ubah option purge menjadi seperti ini.

```javascript
  // tailwind.config.js
  module.exports = {
   purge: ['./index.html', './src/**/*.{vue,js,ts,jsx,tsx}'],
    darkMode: false, // or 'media' or 'class'
    theme: {
      extend: {},
    },
    variants: {
      extend: {},
    },
    plugins: [],
  } 
```

<br/>

### Masukan Tailwind pada css file

buat dulu file <filename>/src/tailwind.css</filename> dan masukan kode ini.
```css
/* ./src/tailwind.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

pada file <filename>/src/main.js</filename> masukan file <filename>tailwind.css</filename> dengan import
```javascript
// src/main.js
import { createApp } from 'vue'
import App from './App.vue'
import './tailwind.css'

createApp(App).mount('#app')
````

<br/>

Ok, Sekarang tailwind sudah siap digunakan.

untuk memastikan mari kita coba masukan class tailwind dengan mengubah file <filename>/src/App.vue</filename>

```html

<!-- /src/App.vue --> 
<template>
  <div class="bg-blue-600 h-screen grid place-items-center">
    <h1 class="text-6xl font-bold text-white">First Vuejs + Tailwind App</h1>
  </div>
</template>

<script>
export default {

}
</script>

<style>
</style>

```

jika tampilkan kalian seperti ini, berarti tailwindcss sudah bisa digunakan. congrats!! :D
![firstlook-tailwind](/content/firstlook-tailwind.png)

<br/>

## Kesimpulan
pada tutorial pertama ini kalian menginstall vuejs menggunakan vitejs dan menginstall tailwindcss beserta package pendukungnya seperti postcss dan autoprefixer.

kalian juga sudah mengkonfigurasi tailwindcss, dari mengkonfigurasi agar menghapus css yang tidak terpakai sampai tailwindcss siap untuk digunakan.

<br/>

sampai nanti di tutorial selanjutnya di series:

<filename>Membuat Website Pertamamu Menggunakan Vuejs 3 + Vite dan Tailwindcss</filename>
