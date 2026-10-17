# Aplikasi Kelola Data People (Java Swing & MySQL)

Aplikasi desktop GUI sederhana berbasis Java Swing yang terhubung dengan database MySQL. Aplikasi ini dikembangkan untuk mengelola data individu (People) secara CRUD (Create, Read, Update, Delete) dengan fitur validasi input dan konfirmasi tindakan.

## Fitur Utama

1. **Integrasi Database MySQL**: Seluruh data tersimpan secara langsung di database (db_people) tanpa menggunakan ArrayList.

2. **Operasi CRUD Lengkap**:
   * **Create**: Menambahkan data baru ke database.
   * **Read**: Menampilkan seluruh data ke dalam JTable.
   * **Update**: Memperbarui data yang ada di database.
   * **Delete**: Menghapus data dari database dengan dialog konfirmasi terlebih dahulu.

3. **Validasi Input**:
   * **Cek Form Kosong**: Menampilkan pesan peringatan jika ada field input yang belum diisi.
   * **Cek ID Duplikat**: Menampilkan pesan error jika ID yang dimasukkan saat penambahan data baru sudah terdaftar di database.
   * **Validasi Tipe Data**: Memastikan kolom tahun lahir diisi dengan karakter angka.

## Prasyarat & Teknologi

* Java Development Kit (JDK): Versi 8 atau lebih baru.
* IDE: IntelliJ IDEA (Disarankan untuk dukungan GUI Designer).
* DBMS: MySQL (XAMPP / Laragon / MySQL Server).
* Driver: MySQL Connector/J (.jar).

## Skema & Seed Data Database

Berikut adalah script SQL untuk membuat database, tabel, serta data awal (seed data):

```sql
-- Database: db_people

CREATE DATABASE db_people;
USE db_people;

CREATE TABLE person (
  id varchar(255) PRIMARY KEY,
  nama varchar(255) NOT NULL,
  thn_lahir int NOT NULL,
  kategori varchar(255) NOT NULL,
  email varchar(255) NOT NULL
);

INSERT INTO person (id, nama, thn_lahir, kategori, email) VALUES
('P001', 'Budi Santoso', 1988, 'Full-time', 'budi.santoso@example.com'),
('P002', 'Siti Rahmawati', 1995, 'Full-time', 'siti.rahmawati@example.com'),
('P003', 'Ahmad Rizky', 2002, 'Internship', 'ahmad.rizky@example.com'),
('P004', 'Dewi Lestari', 1985, 'Contract', 'dewi.lestari@example.com'),
('P005', 'Eko Prasetyo', 1998, 'Part-time', 'eko.prasetyo@example.com'),
('P006', 'Fitriani', 2003, 'Internship', 'fitriani@example.com'),
('P007', 'Gita Gutawa', 1992, 'Full-time', 'gita.gutawa@example.com'),
('P008', 'Hendra Wijaya', 1990, 'Contract', 'hendra.wijaya@example.com'),
('P009', 'Indah Permata', 1999, 'Part-time', 'indah.permata@example.com'),
('P010', 'Joko Widodo', 1987, 'Full-time', 'joko.widodo@example.com');
```

## Struktur File Proyek

```
src/
├── Database.java       # Pengatur koneksi JDBC dan query SQL
├── Person.java         # Class model untuk entitas Person
├── PersonMenu.java     # Logic GUI, Event Listener, dan Validasi
└── PersonMenu.form     # Layout GUI Designer (IntelliJ IDEA)
```