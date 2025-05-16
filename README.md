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
Sumber Data: https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee

Setup Environment:
1. Install dependensi
```
pip install -r requirements.txt
```
2. Jalankan perintah berikut pada Command Prompt untuk memanggil (pull) Docker image untuk menjalankan Metabase.
```
docker pull metabase/metabase:v0.54.5
```
3. Jalankan container Metabase
```
docker run -d -p 3000:3000 --name metabase metabase/metabase:v0.54.5
```
4. Akses Metabase dari browser: http://localhost:3000
5. Lakukan setup awal dan hubungkan ke database Supabase PostgreSQL. Login ke Supabase untuk akses database: https://supabase.com/dashboard/sign-in
6. Hubungkan Python ke PostgreSQL Supabase menggunakan SQLAlchemy untuk mengirim dataset:
```
from sqlalchemy import create_engine
import pandas as pd

URL = "postgresql://username:password@host:port/dbname"  # Ganti dengan koneksi kamu
engine = create_engine(URL)

df.to_sql('employee_attrition', engine, if_exists='replace', index=False)

7. Jalankan model prediksi menggunakan script predict.py:
```
python prediction.py
```
## Business Dashboard
Dashboard yang dibuat menyajikan data dalam format angka aktual dan grafik visual. Berikut adalah penjelasan mengenai setiap fitur yang terdapat pada dashboard tersebut:

1. Indikator Kinerja Utama (KPI) terkait jumlah data real-time.
<div align="center">
  <img src="https://github.com/user-attachments/assets/88f500b6-dcf9-4b54-b42f-78a4ca2be613" width="600"/>
</div>

Fitur ini berfungsi untuk menampilkan data aktual terkini yang meliputi:
* Jumlah Karyawan yang bekerja
* Jumlah karyawan yang Attrition
* Attrition Rate yang diperoleh dari perbandingan antara jumlah karyawan yang keluar dengan total jumlah karyawan.
* Rata-rata rating kepuasan karyawan terhadap lingkungan kerjanya.
* Rata-rata umur pegawai yang mengalami attrition
* Rata-rata lama bekerja pegawai yang mengalami attrition.

2. Visualisasi data interaktif dalam bentuk diagram dan tabel.
<div align="center">
  <img src="https://github.com/user-attachments/assets/7b480c60-8556-4afe-b9e1-433df1b4794c" width="600"/>
</div>

* Pie Chart Attrition by Gender: Menampilkan perbandingan jumlah karyawan yang keluar berdasarkan jenis kelamin.
* Bar Chart Attrition by Current Manager: Menggambarkan tahun keberapa karyawan mengalami attrition berdasarkan manajer terkini.
* Pie Chart Attrition by Department: Menunjukkan divisi atau departemen dengan jumlah attrition tertinggi.
* Bar Chart Attrition by Salary Range: Menampilkan distribusi attrition berdasarkan rentang gaji karyawan.
* Pivot Table Environment Satisfaction: Menyajikan tingkat kepuasan kerja karyawan yang keluar berdasarkan lingkungan kerja.
* Bar Chart Attrition by Marital Status: Memberikan gambaran jumlah attrition berdasarkan status pernikahan karyawan.
* Pie Chart Attrition by Business Travel: Memvisualisasikan frekuensi perjalanan dinas yang berkorelasi dengan tingkat attrition.
* Bar Chart Attrition by Education Field: Menampilkan komposisi attrition berdasarkan latar belakang pendidikan terakhir.
* Pivot Table Training Times Last Year: Menggambarkan jumlah pelatihan yang diikuti oleh karyawan yang keluar selama satu tahun terakhir.
* Bar Chart Attrition by Job Role: Memperlihatkan perbandingan jumlah karyawan yang keluar berdasarkan posisi mereka di perusahaan.

## Conclusion
Berdasarkan dashboard yang telah dibuat, didapatkan beberapa insight terkait karyawan yang mengalami attrition yaitu:

1. Attrition Rate perusahaan saat ini adalah 16.9%, dengan total 179 karyawan keluar.
2. Rata-rata kepuasan kerja dari karyawan yang keluar berada di angka 2.61 dari 4, menunjukkan tingkat kepuasan yang tergolong rendah.
3. Karyawan yang keluar memiliki rata-rata usia 33 tahun dan rata-rata total lama masa kerja 8 tahun.
4. Sebagian besar yang keluar adalah laki-laki, dengan masa kerja dengan manajer saat ini hanya 0–2.5 tahun.
5. Departemen dengan attrition tertinggi adalah Research, diikuti oleh Sales.
6. Mayoritas karyawan yang keluar memiliki gaji sekitar $2.5k, mengindikasikan potensi korelasi antara pendapatan dan tingkat keluar.
7. Kepuasan terhadap lingkungan kerja berada di kisaran rating 1-1.5 dari 4, menunjukkan ketidakpuasan signifikan.
8. Status lajang (single) mendominasi populasi karyawan yang keluar.
9. Karyawan dengan frekuensi perjalanan rendah (rarely travels) menunjukkan tingkat keluar yang lebih tinggi.
10. Bidang pendidikan (Education Field) terbanyak dari karyawan yang keluar adalah Life Sciences.
11. Mayoritas karyawan yang keluar hanya memiliki 1.5–2.5 kali pelatihan dalam setahun.
12. Role pekerjaan dengan tingkat keluar tertinggi adalah Laboratory Technician, disusul Sales Executive dan Research Scientist.

## Rekomendasi Action Items
* **Perkuat Hubungan antara Karyawan dan Manajer di Awal Masa Kerja.**
Fokuslah pada program coaching atau pembinaan dan komunikasi terbuka sejak 0–2.5 tahun pertama, agar tercipta hubungan kerja yang nyaman dan saling percaya.
* **Ciptakan Lingkungan Kerja yang Lebih Nyaman.**
Rating kepuasan terhadap lingkungan kerja masih rendah, hanya di angka 1–1.5 dari 4. Perusahaan sebaiknya meninjau kembali kenyamanan fasilitas, kebersihan, serta suasana kerja tim dan hubungan antar rekan.
* **Berikan Perhatian Khusus pada Posisi dan Departemen dengan Turnover Tinggi.**
Misalnya, posisi seperti Laboratory Technician, Sales Executive, dan departemen Research. Perlu strategi khusus untuk menjaga karyawan tetap betah di bagian-bagian ini.
* **Tingkatkan Program Pelatihan dan Pengembangan Karyawan.**
Banyak karyawan keluar setelah hanya mendapatkan 1.5–2.5 pelatihan per tahun. Dengan meningkatkan jumlah dan kualitas pelatihan, karyawan akan merasa lebih berkembang dan termotivasi untuk bertahan.
* **Lakukan Evaluasi dan Penyesuaian Gaji.**
Karena sebagian besar karyawan yang keluar bergaji sekitar $2.5k, perusahaan perlu memastikan struktur gaji tetap kompetitif dan sesuai dengan beban kerja, terutama untuk posisi-posisi yang rawan ditinggalkan.
