# Attrition Employees Dashboard - Jaya Jaya Maju
## Business Understanding
Jaya Jaya Maju adalah perusahaan multinasional yang telah berdiri sejak tahun 2000 dan memiliki lebih dari 1.000 karyawan yang tersebar di seluruh penjuru negeri. Meskipun telah berkembang menjadi perusahaan besar, Jaya Jaya Maju masih menghadapi tantangan serius dalam hal manajemen karyawan. Salah satu masalah utamanya adalah **tingginya tingkat attrition (karyawan keluar)** yang mencapai lebih dari 10% dari total karyawan aktif.

Ketika tingkat pengunduran diri karyawan (attrition rate) berada pada level yang tinggi, perusahaan menghadapi berbagai tantangan serius. Misalnya, proses rekrutmen yang harus dilakukan secara berulang menimbulkan pengeluaran yang besar, sementara karyawan yang tersisa berisiko mengalami penurunan motivasi dan semangat kerja akibat seringnya pergantian anggota tim. Dalam jangka panjang, peningkatan beban kerja karena kekosongan posisi dapat memicu stres hingga burnout. 

Jika tidak segera ditangani, kondisi ini dapat menghambat efisiensi kerja, menurunkan performa organisasi secara keseluruhan, dan merusak reputasi perusahaan. Oleh karena itu, perusahaan perlu mengidentifikasi dan memahami penyebab utama tingginya attrition rate agar dapat menyusun strategi yang efektif dalam mengelolanya.

## Permasalahan Bisnis
Berdasarkan permasalahan bisnis di atas, diperlukan sebuah solusi yang mampu mengidentifikasi faktor-faktor yang memengaruhi tingginya attrition rate. Permasalahan tersebut dapat dirumuskan ke dalam beberapa pertanyaan utama yang menjadi acuan dalam mencari solusi, yaitu:
* Berapa banyak karyawan yang keluar dan bagaimana profil demografis mereka?
* Apa pola attrition berdasarkan faktor pekerjaan seperti departemen, peran, dan lembur?
* Bagaimana hubungan antara gaji, pelatihan, dan promosi dengan tingkat attrition?
* Sejauh mana lingkungan kerja, jarak rumah, dan perjalanan bisnis memengaruhi keputusan karyawan untuk keluar?
* Apakah lama masa kerja berkorelasi dengan kemungkinan karyawan keluar?

## Cakupan Proyek 
Proyek ini bertujuan untuk membangun sebuah dashboard bisnis yang digunakan untuk memantau data karyawan yang berkontribusi terhadap tingkat attrition di perusahaan. Melalui visualisasi data yang ditampilkan dalam dashboard, perusahaan dapat memperoleh insight yang relevan guna mendukung pengambilan kebijakan strategis dalam menekan angka attrition.

Dashboard ini akan dibuat menggunakan Metabase, yang terintegrasi dengan database PostgreSQL melalui platform Supabase. Dalam Metabase, data akan diolah menjadi model data terlebih dahulu sebelum ditampilkan dalam berbagai komponen dashboard, seperti:
* Indikator Kinerja Utama (KPI) terkait jumlah dan status data.
* Visualisasi data interaktif dalam bentuk diagram dan tabel.

## Persiapan
Sumber Data:

Setup Environment:
1. Instalasi library Pandas SQLAlchemy.
2. Untuk **menghubungkan aplikasi Python dengan database PostgreSQL di Supabase** menggunakan **SQLAlchemy** seperti kode dibawah ini. Setelah terhubung, data yang disimpan dalam variabel df (DataFrame) akan dipindahkan ke dalam tabel **employee_attrition** di database Supabase.
```
from sqlalchemy import create_engine

URL = [your_database_password_here]  # Ganti dengan password yang sesuai

engine = create_engine(URL)
df.to_sql('employee_attrition', engine)
```
   
3. Membuat container Metabase versi metabase/metabase:latest pada Docker dan dijalankan di port 3000:3000.

## Business Dashboard
Dashboard yang dibuat menyajikan data dalam format angka aktual dan grafik visual. Berikut adalah penjelasan mengenai setiap fitur yang terdapat pada dashboard tersebut:

![Image](https://github.com/user-attachments/assets/88f500b6-dcf9-4b54-b42f-78a4ca2be613)


