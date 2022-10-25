# Tutorial : Instal Tailwind CSS 3 dan Vue JS 3

**DESKRIPSI :**  
Materi ini membahas mengenai bagaimana tahapan menginstal dua Framework CSS dan JS, yaitu : `Tailwind CSS 3` dan `Vue JS 3`

>  **Catatan !!!**  
>  Versi Framework yang digunakan saat materi ini dibuat adalah :
>    - Tailwind CSS `v3.2.1`
>    - Vue JS `v3`

**PRASYARAT :**  
Sebelum melanjutkan materi, silahkan periksa terlebih dahulu persyaratan yang ada di dalam website resmi dari masing-masing platform
- Vue JS
  ```
  https://vuejs.org/
  ```
- Tailwind CSS
  ```
  https://tailwindcss.com/
  ```

---

## Instal Vue JS
Hal pertama untuk melakukan instalasi `Vue 3` versi saat materi ini dibuat, anda dapat dengan mudah dengan menuliskan baris kode dibawah ini pada `command line`, lalu tekan `Enter`
```
npm init vue@latest
```

Perintah ini akan menginstal dan menjalankan `create-vue`, `project scaffolding tool` resmi Vue. Anda akan disajikan dengan petunjuk untuk sejumlah fitur opsional seperti TypeScript dan dukungan pengujian:
```
✔️ Project name : … myproject-app
✔️ Add TypeScript? … _No_ / Yes
✔️ Add JSX Support? … No / _Yes_
✔️ Add Vue Router for Single Page Application development? … No / _Yes_
✔️ Add Pinia for state management? … _No_ / Yes
✔️ Add Vitest for Unit Testing? … _No_ / Yes
✔️ Add an End-to-End Testing Solution? … _No_ / Yes
✔️ Add ESLint for code quality? … No / _Yes_
✔️ Add Prettier for code formatting? … No / _Yes_
```

Jika Anda tidak yakin, cukup pilih `No` lalu tekan enter untuk saat ini. Setelah proyek dibuat, kita akan masuk kedalam folder proyek kita menggunakan `comand line` dengan perintah dibawah dan tekan `Enter`
```
cd myproject-app
```


## Instal Packages dan Tailwind CSS kedalam Vue JS
Setelah memastikan `comand line` anda berada didalam folder proyek `Vue 3` yang anda buat, selanjutnya menginstal Tailwind CSS dan `peer dependencies` melalui npm ke dalam proyek Vue 3 dengan perintah berikut
```
npm install -D tailwindcss postcss autoprefixer
```

Kemudian anda harus membuat file konfigurasi `tailwind.config` dan `postcss.config` dengan perintah berikut
```
npx tailwindcss init -p
```

### Konfigurasikan Jalur Template Tailwind
Tailwind CSS perlu mengetahui jenis ekstensi file dan letak file yang akan digunakan sebagai bagian dari Tailwind CSS. Langkah pertama buka file `tailwind.config.js` anda lalu tambahkan `script` seperti dibawah, dan `save`
```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./index.html", "./src/**/*.{vue,js,ts}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

### Tambahkan Arahan Tailwind ke CSS
Anda harus membuat sebuah file `.css` yang berisi perintah arahan dari Tailwind seperti dibawah. Saya biasanya membuat file `.css` ini dengan nama `tailwind.css` dan akan kita letakkan didalam folder `assets` dengan jalur `myproject-app/src/assets/tailwind.css` dan jangan lupa `save`

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Memanggil file CSS milik Tailwind
Terakhir anda perlu mengimport file CSS milik Tailwind ke dalam `main.js` agar bisa digunakan. Buka file `main.js` dengan jalur `myproject-app/src/main.js` lalu tambahkan `script` seperti dibawah, dan `save`
```
import { createApp } from 'vue'
import App from './App.vue'
import router from './router'

import './assets/main.css'
import "./assets/tailwind.css";

const app = createApp(App)
app.use(router)
app.mount('#app')
```

👨🏻‍💻 Selesai... selamat anda sudah bisa menginstal Vue JS dan Tailwind CSS 👋😎👏😋🤪👍
