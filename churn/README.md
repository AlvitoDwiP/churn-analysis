# Customer Churn Analysis – Management Perspective

## Business Problem
Perusahaan berbasis subscription menghadapi risiko churn yang berdampak langsung pada stabilitas pendapatan dan peningkatan biaya akuisisi customer. Analisis ini bertujuan untuk memahami pola churn, mengidentifikasi segmen customer dengan risiko churn tertinggi, serta mengevaluasi faktor perilaku dan layanan yang terkait dengan churn sebagai dasar pengambilan keputusan manajemen.

## Dataset
Dataset yang digunakan adalah dataset publik **Telco Customer Churn**, merepresentasikan data customer pada satu titik waktu (snapshot). Setiap baris merepresentasikan satu customer unik, dengan informasi meliputi:
- Demografi dan segmentasi customer
- Detail kontrak dan layanan
- Aktivitas dan pengalaman customer
- Status churn (Yes/No)

Dataset ini cocok untuk analisis deskriptif dan diagnostik, bukan time-series.

## Analytical Approach
Analisis dilakukan secara bertahap dan terstruktur:

**Notebook 01 – Data Overview & Quality Check**
- Memahami struktur dan isi data
- Validasi kualitas data dan tipe variabel
- Identifikasi keterbatasan data (missing values, tipe data)
- Penetapan baseline churn

**Notebook 02 – Churn by Segment (Management Analysis)**
- Identifikasi segmen dengan tingkat churn tertinggi
- Perbandingan churn berdasarkan:
  - Jenis kontrak
  - Layanan internet
  - Karakteristik demografis utama
- Penentuan segmen prioritas untuk analisis lanjutan

**Notebook 03 – Churn Driver Analysis (Diagnostic)**
- Perbandingan karakteristik churn vs non-churn
- Evaluasi faktor perilaku dan layanan yang terkait dengan churn:
  - Tenure
  - Monthly Charges
  - Contract type
  - TechSupport dan OnlineSecurity
- Analisis terfokus pada segmen berisiko tinggi (Month-to-month)

## Key Findings
- Customer dengan kontrak **Month-to-month** memiliki churn tertinggi (±43%), jauh lebih tinggi dibandingkan kontrak jangka panjang.
- Customer churn memiliki tenure jauh lebih pendek (±18 bulan) dibandingkan non-churn (±38 bulan).
- Customer tanpa TechSupport dan OnlineSecurity menunjukkan churn di atas 40%, hampir tiga kali lebih tinggi dibanding customer dengan layanan tersebut.
- Monthly Charges pada customer churn lebih tinggi dibandingkan non-churn.

## Business Implications
Risiko churn paling terkonsentrasi pada customer dengan:
- Komitmen berlangganan rendah
- Beban biaya bulanan yang relatif lebih tinggi
- Keterbatasan dukungan dan perlindungan layanan

Tanpa intervensi yang terarah, segmen ini berpotensi memberikan dampak signifikan terhadap stabilitas pendapatan serta meningkatkan biaya akuisisi customer.

## Management Recommendations
- Memprioritaskan strategi retensi pada customer dengan kontrak Month-to-month, khususnya pada fase awal berlangganan.
- Mengevaluasi struktur harga dan value proposition pada segmen dengan Monthly Charges tinggi.
- Meningkatkan adopsi layanan TechSupport dan OnlineSecurity sebagai bagian dari strategi retensi dan peningkatan pengalaman customer.

## Outputs
- Executive Summary: ringkasan temuan dan rekomendasi level eksekutif
- Visual Highlights (folder `visuals/charts`):
  - Churn by Contract Type
  - Churn by Service
  - Tenure: Churn vs Non-Churn
  - Monthly Charges: Churn vs Non-Churn

## Tools & Technologies
- Python (pandas, matplotlib)
- Jupyter Notebook / Google Colab
- GitHub untuk version control

## Notes on Data Handling
Nilai kosong dan nilai ekstrem dipertahankan untuk menjaga representasi kondisi bisnis yang sebenarnya. Analisis ini bersifat deskriptif dan diagnostik, sehingga tidak dilakukan imputasi atau transformasi agresif terhadap data.
