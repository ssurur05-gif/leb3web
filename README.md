[readme.md](https://github.com/user-attachments/files/33138826/readme.md)
# leb3web# Laporan Praktikum - Lab3Web

**Nama:** [Miftahussurur]  
**NIM:** [312510285]  
**Kelas:** [I252A]  
**Mata Kuliah:** Pemrograman Web  

---

## Daftar Isi
- [Tugas Praktikum](#tugas-praktikum)
  - [1. Eksperimen Kode CSS](#1-eksperimen-kode-css)
  - [2. Perbedaan Selektor `h1` dan `#intro h1`](#2-perbedaan-selektor-h1-dan-intro-h1)
  - [3. Prioritas Penggunaan CSS (Internal, Eksternal, dan Inline)](#3-prioritas-penggunaan-css-internal-eksternal-dan-inline)
  - [4. Prioritas Selektor ID vs Class](#4-prioritas-selektor-id-vs-class)
- [Langkah Kerja dan Pengujian](#langkah-kerja-dan-pengujian)

---

## Tugas Praktikum

### 1. Eksperimen Kode CSS
Dalam praktikum ini, telah dilakukan modifikasi dan penambahan beberapa properti CSS (mengacu pada CSS Cheat Sheet), seperti pengaturan warna latar belakang (`background-color`), gaya teks (`font-family`, `font-size`, `color`), tata letak (`margin`, `padding`), serta properti border.

*Screenshot hasil eksperimen penambahan properti CSS:*  
![Hasil Eksperimen CSS](screenshots/eksperimen-css.png)

---

### 2. Perbedaan Selektor `h1` dan `#intro h1`

- **`h1 { ... }` (Element Selector):**
  Deklarasi ini bersifat global. Kode CSS akan diterapkan ke **semua elemen `<h1>`** yang ada di dalam seluruh dokumen HTML tanpa terkecuali.

- **`#intro h1 { ... }` (Descendant Selector dengan ID):**
  Deklarasi ini bersifat spesifik. Kode CSS **hanya akan diterapkan pada elemen `<h1>`** yang berada di dalam elemen parent yang memiliki `id="intro"`. Elemen `<h1>` di luar elemen `#intro` tidak akan terkena dampaknya.

---

### 3. Prioritas Penggunaan CSS (Internal, Eksternal, dan Inline)

Jika terdapat CSS Inline, Internal, dan Eksternal yang diterapkan pada elemen yang sama, browser menerapkan aturan **Spesifisitas dan Hierarki CSS (Cascading)**:

**Urutan Prioritas Eksekusi Browser:**
1. **Inline CSS** (Prioritas tertinggi, nilai spesifisitas = 1000)
2. **Internal CSS** dan **Eksternal CSS** (Tergantung urutan pemanggilan di elemen `<head>`. Mana yang ditulis paling akhir akan menimpa/override gaya sebelumnya).

#### Contoh Kasus:
```html
<!DOCTYPE html>
<html lang="id">
<head>
    <!-- CSS Eksternal -->
    <link rel="stylesheet" href="style.css"> 
    
    <!-- CSS Internal -->
    <style>
        p { color: green; }
    </style>
</head>
<body>
    <!-- Inline CSS -->
    <p style="color: red;">Teks ini akan berwarna merah.</p>
</body>
</html>
