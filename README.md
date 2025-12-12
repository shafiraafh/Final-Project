# ======= FINAL PROJECT TSDW =======
## Kelompok 9

Nama Anggota Kelompok:
- (5052241002) Naomy Athaya Jovany 
- (5052241011) Shafira Fajriyatul Hasanah
- (5052241018) Gilbert Emanuel Sambira
- (5052241036) Agata Corinna Aulia W 

### 1. Deskripsi Proyek
Proyek ini bertujuan untuk menganalisis dua dataset yang mencakup informasi terkait pemesanan hotel dari dua jenis hotel yang berbeda: Hotel Resor (H1) dan Hotel Kota(H2). Dataset ini mencakup lebih dari 119.000 entri pemesanan yang mencakup periode antara 1 Juli 2015 hingga 31 Agustus 2017, mencakup pemesanan yang sudah terealisasi maupun yang dibatalkan. Dengan total 31 variabel yang menggambarkan pemesanan hotel, proyek ini bertujuan untuk memberikan wawasan lebih dalam tentang faktor-faktor yang mempengaruhi pembatalan pemesanan, pola lama menginap, tren musiman, dan hubungan antara harga (ADR), saluran pemesanan, dan permintaan hotel.

**Tujuan Utama dari Analisis ini**
1. Mengidentifikasi faktor-faktor yang mempengaruhi tingkat pembatalan pemesanan hotel.
2. Menganalisis pola musiman pemesanan hotel dan menentukan periode peak season.
3. Menilai lama menginap pelanggan berdasarkan jenis hotel dan segmen pasar.
4. Memahami saluran pemesanan yang paling sering digunakan oleh pelanggan, serta menganalisis hubungan antara saluran pemesanan dan tingkat pembatalan.
5. Menilai bagaimana harga kamar (ADR) berhubungan dengan permintaan hotel dan tren tarif selama periode tertentu.

Dengan menggunakan dataset yang mencakup informasi nyata mengenai pemesanan hotel, proyek ini memberikan wawasan yang relevan dan dapat digunakan untuk merumuskan strategi yang lebih baik dalam industri perhotelan.


### 2. Struktur Direktori
Proyek ini memiliki struktur direktori sebagai berikut:
- Data Raw: Menyimpan dataset mentah yang akan digunakan untuk analisis.
- Data Processed: Menyimpan dataset setelah dibersihkan dan diproses.
- Notebooks: Berisi analisis utama yang mencakup langkah-langkah eksplorasi dan pembuatan model.
- requirements.txt: Daftar semua package Python yang dibutuhkan untuk menjalankan proyek ini.
- README.d: Penjelasan mengenai proyek ini

### 3. Penggunaan
Berikut langkah-langkah untuk mennjalankan notebook:
1. Install file `FINAL_PROJECT_TSDW_KEL_9.ipynb`.
2. Pastikan file `hotels.csv` berada di folder yang sama dengan file notebook sebelum menjalankan notebook.
3. Buka file `FINAL_PROJECT_TSDW_KEL_9.ipynb` menggunakan Jupyter Notebook.
4. Jalankan setiap sel notebook  secara berurutan untuk memulai analisis data.
5. Untuk melihat hasil model, pastikan untuk mengikuti langkah-langkah di dalam notebook.

### 4. Hasil dan Analisis
**Temuan Utama**
1. **Faktor pembatalan terkuat** (berdasarkan urutan kekuatan pengaruh):
* Lead time >120 hari → cancellation rate >55% (semakin jauh booking, semakin besar risiko batal)
* Deposit type “Non Refundable” → cancellation rate >95% (hampir pasti batal karena tidak bisa refund)
* Tamu tidak memberikan special request sama sekali → cancellation rate 48% (vs <10% jika ada 2–3 request)
* Tamu yang pernah cancel sebelumnya → kemungkinan cancel lagi 4–5× lebih tinggi
* Distribution channel “TA/TO” (Travel Agent/Tour Operator) → cancellation rate tertinggi (42%)

2. **Pola musiman sangat jelas**:
* Resort Hotel: peak season Juli–Agustus (libur sekolah Eropa)
* City Hotel: peak season Mei–Oktober (business + city break)
* Low season keduanya: November–Februari

3. **Lama menginap**:
* Resort Hotel rata-rata 4 malam, City Hotel hanya 2,5 malam
* Segmen Group di Resort Hotel bisa menginap rata-rata 7–9 malam → kontribusi revenue sangat besar

4. **Channel pemesanan**:
* 79,2% booking melalui TA/TO (Online Travel Agent (Booking.com, Expedia, dll)
* Namun channel ini juga yang paling banyak cancel (42% vs Direct hanya 18%)

5. **Harga & demand**:
* ADR meningkat signifikan saat demand tinggi (Agustus di Resort Hotel >€220/malam vs Januari hanya ~€70)
* Hubungan sangat positif: semakin banyak booking → semakin tinggi harga yang bisa dipatok


**Keterbatasan Analisis**
* Tidak ada data biaya akuisisi per channel (misal komisi TA/TO 15–25%), sehingga belum bisa hitung profit bersih per channel
*Tidak ada data cuaca, event besar, atau hari libur nasional yang bisa menjelaskan lonjakan tertentu
* Data hanya sampai Agustus 2017 → tren mungkin sudah sedikit berubah pasca-pandemi
* Kolom agent dan company banyak NULL → sulit analisis lebih dalam per partner


**Saran Pengembangan & Rekomendasi Bisnis**
1. **Revenue Management**:
* Terapkan dynamic pricing lebih agresif di peak season (terbukti ADR bisa naik 2–3×)
* Berikan diskon early bird hanya untuk deposit “No Deposit” atau “Refundable”

2. **Kurangi cancellation**:
* Wajibkan minimal 1 special request saat booking online (terbukti sangat efektif menurunkan cancel)
* Beri insentif (upgrade kamar gratis / welcome drink) bagi tamu yang booking <60 hari sebelum kedatangan
* Batasi atau naikkan harga untuk booking lead time >180 hari via TA/TO

3. **Channel strategy**:
* Fokus dorong Direct Booking (website & call center) dengan benefit eksklusif (free cancellation sampai H-7, best price guarantee)
* Kurangi ketergantungan pada TA/TO untuk periode peak season

4. **Pengembangan selanjutnya**:
* Bangun model prediksi cancellation (target akurasi >85% mudah dicapai dengan Random Forest/XGBoost)
* Integrasikan data cuaca dan kalender event untuk forecasting yang lebih akurat
* Analisis segmentasi RFM (Recency–Frequency–Monetary) tamu untuk loyalty program


**Kesimpulan akhir**:
Hotel dapat meningkatkan revenue 15–30% hanya dengan menerapkan strategi pricing yang lebih dinamis dan kebijakan deposit yang lebih ketat pada segmen berisiko tinggi. Special request dan lead time adalah dua indikator paling powerful untuk memprediksi dan mencegah pembatalan.

### 5. Kontribusi
Berikut adalah kontribusi masing-masing anggota dalam proyek ini:
- Naomy (002)   : Explaratori Data Analysis (EDA), Notebook (.ipynb), requirements (.txt), dan README.md
- Shafira (011) : Pre-Processing Data, Notebook (.ipynb), requirements (.txt), dan README.md
- Gilbert (018) : Standarasisasi & Transformasi, Notebook (.ipynb), requirements (.txt), dan README.md
- Agata (036)   : Pre-Processing Data, Notebook (.ipynb), requirements (.txt), dan README.md