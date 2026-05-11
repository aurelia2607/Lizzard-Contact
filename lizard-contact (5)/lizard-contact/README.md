# 🦎 Lizard Contact - Aplikasi Manajemen Kontak

Aplikasi desktop JavaFX untuk manajemen kontak dengan fitur lengkap.

## Tech Stack
- Java 17+
- JavaFX 11 (bundled di folder `lib/`)
- SQLite (via xerial sqlite-jdbc, bundled di folder `lib/`)
- Database: `contacts.db` (auto-dibuat saat pertama run)

---

## Cara Buka & Jalankan di IntelliJ IDEA

### 1. Buka Project
- **File → Open** → pilih folder `lizard-contact`
- IntelliJ akan mendeteksi `.iml` file secara otomatis

### 2. Set SDK (kalau belum)
- **File → Project Structure → Project**
- Set **Project SDK** ke **Java 17** atau **Java 21**
- Set **Project language level** ke 17

### 3. Pastikan Libraries Terbaca
- **File → Project Structure → Modules → Dependencies**
- Harus ada: `javafx.controls`, `javafx.fxml`, `javafx.graphics`, `javafx.base`, `javafx.media`, `sqlite-jdbc`
- Kalau belum, klik `+` → JARs or directories → pilih semua `.jar` dari folder `lib/`

### 4. Set VM Options di Run Configuration
- **Run → Edit Configurations → LizardContact**
- VM options harus berisi:
```
--module-path lib --add-modules javafx.controls,javafx.fxml,javafx.graphics,javafx.base,javafx.media --add-opens javafx.fxml/javafx.fxml=ALL-UNNAMED
```

### 5. Run!
- Klik **Run** (Shift+F10) atau pakai Run Configuration **LizardContact**

---

## Akun Default (sudah ada sample data)
| Username | Password  |
|----------|-----------|
| samuel   | samuel123 |

---

## Fitur Aplikasi
| Halaman        | Fitur                                                  |
|----------------|--------------------------------------------------------|
| Login          | Login & Register akun                                  |
| Dashboard      | Statistik ringkas + pie chart + kontak terbaru         |
| Daftar Kontak  | CRUD kontak, search, filter kategori & tipe, favorit   |
| Favorit        | Daftar kontak favorit, sort, search                    |
| Statistik      | Pie chart, bar chart, tabel rincian per kategori        |
| Riwayat        | Log semua aktivitas (tambah/edit/hapus/favorit)        |

---

## Struktur Project
```
lizard-contact/
├── lib/                          ← JARs (JavaFX + SQLite)
├── src/main/java/com/lizardcontact/
│   ├── MainApp.java
│   ├── controller/               ← Controller tiap halaman
│   ├── model/                    ← Contact, PersonalContact, BusinessContact, dll
│   ├── database/                 ← DatabaseHelper (SQLite CRUD)
│   └── util/                     ← SessionManager
├── src/main/resources/com/lizardcontact/
│   ├── fxml/                     ← Layout tiap halaman
│   └── css/                      ← style.css
├── lizard-contact.iml
└── contacts.db                   ← Database SQLite (auto-generate)
```
