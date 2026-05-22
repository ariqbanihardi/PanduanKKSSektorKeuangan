---
description: >-
  Bab tentang Panduan Tim Tanggap Insiden Siber untuk meningkatkan ketahanan
  siber organisasi khususnya melalui peningkatan kapabilitas domain Deteksi dan
  Domain Penanggulangan & Pemulihan
---

# Bab TTIS

Bab ini dibuat khusus sebagai panduan praktis pembentukan, pengoperasian, pelaporan, eskalasi, dan pengukuran kinerja **Tim Tanggap Insiden Siber (TTIS)** atau _Computer Security Incident Response Team_ (CSIRT) pada industri sektor keuangan Indonesia. Dengan panduan ini diharapkan organisasi dapat mengoptimalkan fungsi sehingga dapat meningkatkan ketahanan siber organisasi melalui peningkatan kapabilitas Deteksi dan Penanggulangan & Pemulihan di dalam kerangka pengukuran IKAS, serta menghubungkan kebutuhan kepatuhan dengan kesiapan operasional saat insiden siber terjadi.

### 10.1 Posisi TTIS dalam KKS Sektor Keuangan

Dalam konteks sektor keuangan, TTIS tidak boleh dipahami hanya sebagai tim teknis TI. TTIS adalah kapabilitas organisasi lintas fungsi yang bertanggung jawab memastikan insiden siber dapat dideteksi, dianalisis, diprioritaskan, ditangani, dipulihkan, dilaporkan, dan dijadikan pembelajaran. Pada lembaga sektor keuangan, TTIS perlu terhubung dengan layanan dan proses kritikal seperti:

* core banking/core insurance/core financing/core capital market platform;
* mobile banking, internet banking, ATM, EDC, QRIS, kanal pembayaran, API, dan open finance;
* sistem treasury, settlement, switching, rekonsiliasi, fraud monitoring, dan anti-fraud;
* data center, DRC, cloud, jaringan cabang, endpoint pegawai, dan layanan pihak ketiga;
* sistem pelaporan regulator, sistem pelayanan nasabah, call center, dan komunikasi publik.

{% hint style="info" %}
**Prinsip sektor keuangan:** TTIS harus memadukan perspektif _cybersecurity_, keberlangsungan bisnis, perlindungan data nasabah, integritas transaksi, anti-fraud, dan stabilitas layanan. Keputusan teknis seperti isolasi server, pemutusan koneksi API, pemblokiran akun, atau aktivasi DRC harus mempertimbangkan dampaknya terhadap nasabah, transaksi berjalan, likuiditas, reputasi, dan kewajiban pelaporan.
{% endhint %}

### 10.2 Dasar Regulasi dan Standar Rujukan

Panduan TTIS ini menggunakan beberapa rujukan utama:

| Rujukan                                                                               | Posisi dalam Panduan                                                                                        | Implikasi untuk Industri Sektor Keuangan                                                                                                            |
| ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Peraturan BSSN No. 1 Tahun 2024 tentang Pengelolaan Insiden Siber                     | Dasar nasional pengelolaan insiden siber, pembentukan TTIS, registrasi, pelaporan, penanganan, dan kesiapan | Lembaga perlu membentuk TTIS organisasi, menyusun rencana tanggap insiden, melaporkan insiden sesuai ketentuan, dan menguji kesiapan secara berkala |
| Peraturan BSSN No. 10 Tahun 2023 tentang Pengukuran Tingkat Kematangan Keamanan Siber | Dasar pengukuran kematangan, termasuk Domain Deteksi dan Penanggulangan & Pemulihan                         | TTIS menjadi komponen operasional yang membuktikan bahwa kontrol IKAS tidak hanya berbentuk dokumen                                                 |
| RFC 2350                                                                              | Format profil CSIRT/TTIS, memuat kontak, mandat, konstituen, layanan, kebijakan, dan formulir pelaporan     | Diperlukan sebagai dokumen profil TTIS, termasuk dalam persyaratan registrasi TTIS                                                                  |
| NIST SP 800-61 Rev. 3 dan NIST CSF 2.0                                                | Rekomendasi integrasi respons insiden ke dalam manajemen risiko siber                                       | Respons insiden perlu terintegrasi dengan tata kelola, identifikasi, proteksi, deteksi, respons, dan pemulihan                                      |
| ISO/IEC 27035-1:2023                                                                  | Prinsip dan proses manajemen insiden keamanan informasi                                                     | Memperkuat proses persiapan, deteksi, pelaporan, asesmen, respons, dan pembelajaran pascainsiden                                                    |
| FIRST CSIRT Services Framework v2.1                                                   | Kerangka layanan CSIRT                                                                                      | Membantu menentukan portofolio layanan TTIS sesuai mandat dan konstituen                                                                            |
| ENISA How to Set Up CSIRT and SOC                                                     | Panduan praktik pendirian dan peningkatan CSIRT/SOC                                                         | Menjadi referensi praktis untuk model operasi, pengembangan kapabilitas, dan integrasi SOC-CSIRT                                                    |
| FIRST Traffic Light Protocol (TLP) 2.0                                                | Skema distribusi informasi sensitif                                                                         | Mendukung pengendalian penyebaran informasi insiden, IoC, kerentanan, dan rekomendasi mitigasi                                                      |

### 10.3 Definisi Operasional

Dalam panduan ini:

* **Insiden Siber** adalah kejadian atau rangkaian kejadian yang mengganggu atau mengancam berjalannya sistem elektronik.
* **TTIS/CSIRT organisasi** adalah tim pada lembaga sektor keuangan yang bertanggung jawab menangani insiden siber dalam ruang lingkup organisasi.
* **Konstituen** adalah pihak yang menerima layanan TTIS. Pada lembaga sektor keuangan, konstituen dapat mencakup unit bisnis, unit TI, cabang, anak perusahaan, unit digital, unit operasional transaksi, unit fraud, dan dalam kondisi tertentu pihak ketiga yang terikat kontrak.
* **Rencana tanggap insiden siber** adalah dokumen yang menetapkan tahapan penanganan, jenis insiden, peran dan tanggung jawab, sumber daya, proses pemulihan sistem/data kritikal, dan kontak internal/eksternal.
* **Rencana keberlangsungan kegiatan** adalah dokumen yang memastikan fungsi dan layanan bisnis kritikal tetap berjalan atau dapat dipulihkan sesuai prioritas, RTO, dan RPO yang ditetapkan.

### 10.4 Prinsip Desain TTIS untuk Sektor Keuangan

| Prinsip                      | Penjelasan                                                                                                         | Contoh Implementasi                                                      |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| Mandat formal                | TTIS dibentuk berdasarkan keputusan pimpinan/direksi dan memiliki kewenangan operasional yang jelas                | SK Direksi, piagam TTIS, pendelegasian kewenangan isolasi aset kritikal  |
| Berbasis risiko              | Prioritas respons mengacu pada dampak terhadap layanan kritikal, data nasabah, integritas transaksi, dan kepatuhan | Severity matrix, risk acceptance, eskalasi risiko tinggi                 |
| Terintegrasi dengan BCM/DRP  | Pemulihan insiden siber harus selaras dengan keberlangsungan bisnis dan pemulihan teknologi                        | Runbook aktivasi DRC, rekonsiliasi transaksi, pemulihan batch/settlement |
| Evidence-based               | Setiap keputusan respons didukung bukti teknis, log, tiket, artefak, dan timeline                                  | Chain of custody, forensics image, SIEM case, EDR telemetry              |
| Koordinatif                  | TTIS bekerja dengan SOC, TI, bisnis, fraud, legal, DPO, compliance, vendor, dan regulator liaison                  | Incident command system, war room, stakeholder register                  |
| Aman dalam berbagi informasi | Informasi insiden, IoC, dan kerentanan dibagikan sesuai kebutuhan dan klasifikasi                                  | Kode distribusi informasi/TLP, NDA vendor, kanal komunikasi aman         |
| Pembelajaran berkelanjutan   | Setiap insiden menghasilkan perbaikan kontrol, playbook, deteksi, dan pelatihan                                    | Post-incident review, lessons learned, action tracker                    |

### 10.5 Model Operasional TTIS

Lembaga sektor keuangan dapat memilih model TTIS sesuai ukuran, kompleksitas, dan risiko layanan digitalnya.

| Model              | Cocok Untuk                                                    | Kelebihan                                                   | Risiko yang Harus Dikelola                                                                                  |
| ------------------ | -------------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Terpusat           | Bank/PUJK dengan struktur TI terpusat                          | Konsistensi kontrol, command cepat, standardisasi playbook  | Risiko bottleneck, perlu cakupan 24/7 untuk layanan digital kritikal                                        |
| Federated          | Konglomerasi keuangan, grup usaha, bank dengan anak perusahaan | Dekat dengan risiko unit bisnis, cocok untuk banyak entitas | Perlu tata kelola eskalasi dan standar minimum yang sama                                                    |
| Hybrid SOC-CSIRT   | Organisasi dengan SOC internal/managed SOC                     | Deteksi dan respons lebih terintegrasi                      | Perlu kejelasan batas tugas SOC sebagai deteksi dan CSIRT sebagai orkestrator respons                       |
| Managed/Co-sourced | Lembaga kecil/menengah atau BPR/BPRS dengan keterbatasan SDM   | Akses ke keahlian, forensik, dan monitoring eksternal       | Akuntabilitas tetap di organisasi; kontrak harus mengatur SLA, bukti, kerahasiaan, akses log, dan pelaporan |

{% hint style="info" %}
**Catatan implementasi:** penggunaan penyedia jasa eksternal tidak memindahkan tanggung jawab tata kelola. Pimpinan lembaga tetap perlu menetapkan pemilik proses, kontak eskalasi, kewenangan pengambilan keputusan, serta mekanisme audit terhadap layanan eksternal.
{% endhint %}

### 10.6 Struktur Organisasi dan Peran Minimal

Struktur TTIS sektor keuangan sebaiknya dirancang dengan dua lapisan: lapisan **operasional teknis** dan lapisan **manajemen krisis/keputusan bisnis**.

| Peran                         | Tanggung Jawab Utama                                                                 | Unit yang Umumnya Terlibat                      |
| ----------------------------- | ------------------------------------------------------------------------------------ | ----------------------------------------------- |
| Sponsor Direksi/Komite TI     | Memberikan mandat, prioritas, sumber daya, dan keputusan strategis                   | Direksi, Komite TI, Komite Manajemen Risiko     |
| CSIRT/TTIS Manager            | Memimpin kapabilitas TTIS, memastikan kesiapan, koordinasi, pelaporan, dan perbaikan | CISO, Kepala Keamanan TI, Kepala Operasional TI |
| Incident Commander            | Memimpin penanganan insiden aktif dan mengoordinasikan war room                      | TTIS, SOC, TI Operasional                       |
| SOC/Monitoring Lead           | Mengelola deteksi, alert enrichment, SIEM/EDR/NDR, dan eskalasi awal                 | SOC internal/MSSP                               |
| Forensic & Evidence Lead      | Mengamankan bukti, melakukan akuisisi forensik, menjaga chain of custody             | Digital Forensic, Security Engineering          |
| Infrastructure/Network Lead   | Melakukan isolasi, segmentasi, pemulihan infrastruktur, dan hardening                | Network, Data Center, Cloud, Endpoint           |
| Application/API Lead          | Menangani aplikasi, API, DevSecOps, patch, konfigurasi, dan validasi fungsi          | App Owner, DevOps, QA                           |
| IAM Lead                      | Menangani akun, kredensial, akses istimewa, dan reset/rotasi kunci                   | IAM, HRIS, Privileged Access Management         |
| Data Protection/Privacy Lead  | Menilai dampak data pribadi dan koordinasi perlindungan data                         | DPO, Legal, Compliance                          |
| Fraud & Transaction Risk Lead | Menganalisis dampak transaksi, fraud pattern, blokir akun, dan rekonsiliasi          | Fraud, Payment Ops, Treasury, Operations        |
| BCM/DR Lead                   | Mengaktifkan BCP/DRP dan memastikan RTO/RPO                                          | BCM, DRC, IT Service Continuity                 |
| Legal & Regulatory Liaison    | Mengelola kewajiban pelaporan dan komunikasi regulator                               | Legal, Compliance, Regulator Reporting          |
| Corporate Communication       | Menyiapkan komunikasi internal, nasabah, media, dan pemangku kepentingan             | Corporate Secretary, PR, Customer Care          |
| Vendor/Third-Party Lead       | Mengelola koordinasi vendor, cloud provider, payment gateway, dan outsourcer         | Procurement, Vendor Management, TI              |

### 10.7 RACI Minimal Penanganan Insiden

| Aktivitas                 | Incident Commander | SOC | TI Ops | App Owner | Fraud Ops | Legal/Compliance | BCM | Komunikasi | Direksi |
| ------------------------- | ------------------ | --- | ------ | --------- | --------- | ---------------- | --- | ---------- | ------- |
| Validasi alert            | A                  | R   | C      | C         | C         | I                | I   | I          | I       |
| Klasifikasi severity      | A                  | R   | C      | C         | C         | C                | C   | I          | I       |
| Aktivasi war room         | A/R                | C   | C      | C         | C         | C                | C   | C          | I       |
| Isolasi aset              | A                  | C   | R      | C         | C         | I                | I   | I          | I       |
| Blokir transaksi/akun     | A                  | C   | C      | C         | R         | C                | I   | I          | I       |
| Pelaporan regulator       | C                  | I   | I      | I         | C         | A/R              | C   | I          | I       |
| Aktivasi DRC/BCP          | C                  | I   | R      | R         | C         | I                | A/R | I          | C       |
| Komunikasi publik/nasabah | C                  | I   | I      | I         | C         | C                | C   | A/R        | C       |
| Post-incident review      | A/R                | R   | R      | R         | C         | C                | C   | C          | I       |

Keterangan: **R** = Responsible, **A** = Accountable, **C** = Consulted, **I** = Informed.

### 10.8 Portofolio Layanan TTIS

Mengacu pada praktik CSIRT internasional, layanan TTIS dapat dikelompokkan menjadi layanan inti dan layanan pendukung.

| Kelompok Layanan                    | Layanan                                                                       | Output Minimal                                           |
| ----------------------------------- | ----------------------------------------------------------------------------- | -------------------------------------------------------- |
| Penerimaan dan triage laporan       | Menerima laporan insiden, memvalidasi, mengategorikan, dan memprioritaskan    | Tiket insiden, nomor kasus, severity, initial assessment |
| Analisis insiden                    | Analisis log, IoC, artefak, vektor serangan, akun terdampak, sistem terdampak | Laporan analisis awal, timeline, hipotesis root cause    |
| Koordinasi respons                  | Koordinasi lintas unit, vendor, regulator liaison, dan pihak terdampak        | War room, action tracker, keputusan containment          |
| Mitigasi dan pemulihan              | Isolasi, eradikasi, patch, reset kredensial, pemulihan sistem/data            | Recovery report, validasi fungsi, evidence restore       |
| Analisis artefak dan bukti forensik | Akuisisi bukti, preservasi log, analisis malware, image disk/memory           | Chain of custody, forensic report                        |
| Dukungan manajemen krisis           | Eskalasi ke manajemen, dukungan pengambilan keputusan, komunikasi risiko      | Executive brief, situation report, board update          |
| Manajemen kerentanan                | Intake kerentanan, validasi, prioritas patch, koordinasi disclosure           | Vulnerability case, remediation tracker                  |
| Situational awareness               | Akuisisi dan korelasi threat intelligence, advisori, tren ancaman             | Bulletin, IoC feed, threat brief                         |
| Knowledge transfer                  | Awareness, pelatihan, simulasi, tabletop exercise, lessons learned            | Materi pelatihan, hasil simulasi, improvement plan       |

### 10.9 Dokumen Wajib dan Artefak Minimum TTIS

| Dokumen/Artefak               | Isi Minimum                                                                                           | Pemilik                            |
| ----------------------------- | ----------------------------------------------------------------------------------------------------- | ---------------------------------- |
| SK/Piagam TTIS                | Mandat, ruang lingkup, struktur, kewenangan, tanggung jawab                                           | Direksi/CISO                       |
| Profil RFC 2350               | Nama tim, kontak, zona waktu, konstituen, layanan, kebijakan, metode pelaporan                        | TTIS Manager                       |
| Rencana Tanggap Insiden Siber | Tahapan, jenis insiden, peran, perangkat, proses pemulihan, kontak internal/eksternal                 | TTIS Manager/BCM                   |
| Severity Matrix               | Kriteria dampak layanan, data, transaksi, reputasi, hukum, dan regulator                              | Risk/TTIS                          |
| Playbook Insiden              | Prosedur per jenis insiden: ransomware, data breach, DDoS, cloud compromise, API abuse, fraud digital | TTIS/SOC/App Owner                 |
| Incident Report Form          | Kontak pelapor, deskripsi, kronologi, dampak, aset terdampak, bukti awal                              | SOC/Service Desk                   |
| Chain of Custody Form         | Identitas bukti, waktu akuisisi, hash, penyimpan, perpindahan bukti                                   | Forensic Lead                      |
| Communication Matrix          | Pihak internal/eksternal, kanal, SLA, klasifikasi informasi                                           | Corporate Communication/Compliance |
| Post-Incident Review Template | Kronologi, root cause, dampak, efektivitas respons, tindakan perbaikan                                | Incident Commander                 |
| Action Tracker                | Gap, action owner, target date, status, bukti penutupan                                               | PMO/Risk                           |

### 10.10 Siklus Operasional Penanganan Insiden

Siklus di bawah ini menggabungkan ketentuan BSSN, prinsip ISO/IEC 27035, NIST SP 800-61 Rev. 3, dan praktik CSIRT.

{% stepper %}
{% step %}
### Persiapan

Menjamin organisasi siap menangani insiden: membentuk TTIS, menyusun rencana tanggap, playbook, severity matrix, kontak eskalasi, akses log, pelatihan, dan simulasi.

**Output:** Piagam TTIS, RFC 2350, playbook, daftar kontak, hasil simulasi.
{% endstep %}

{% step %}
### Deteksi dan Pelaporan

Menemukan indikasi insiden dan menerima laporan melalui monitoring SIEM/EDR/NDR, laporan pengguna/nasabah/vendor, threat intelligence, atau service desk.

**Output:** Tiket insiden, initial evidence, alert enrichment.
{% endstep %}

{% step %}
### Triage dan Analisis

Memastikan insiden, menentukan severity, ruang lingkup, dan dampak melalui validasi alert, korelasi log, analisis aset, analisis transaksi, dan analisis data terdampak.

**Output:** Severity, impact assessment, initial situation report.
{% endstep %}

{% step %}
### Eskalasi dan Koordinasi

Mengaktifkan struktur respons sesuai tingkat krisis melalui war room, penunjukan incident commander, eskalasi direksi, regulator liaison, dan vendor coordination.

**Output:** Keputusan respons, action tracker, communication plan.
{% endstep %}

{% step %}
### Containment

Mencegah perluasan dampak melalui isolasi host, blokir akun, segmentasi jaringan, revoke token/API key, pemutusan koneksi vendor, dan rate limit.

**Output:** Bukti containment, risiko residual.
{% endstep %}

{% step %}
### Eradikasi

Menghapus penyebab dan vektor serangan melalui patch, hardening, malware removal, credential reset, image ulang endpoint/server, dan rule update.

**Output:** Root cause sementara, bukti eradikasi.
{% endstep %}

{% step %}
### Pemulihan

Memulihkan layanan secara aman melalui restore dari backup, failover/DRC, validasi integritas data, rekonsiliasi transaksi, dan monitoring ketat.

**Output:** Recovery report, validasi RTO/RPO, service restoration.
{% endstep %}

{% step %}
### Pelaporan

Memenuhi kewajiban pelaporan dan koordinasi melalui laporan ke TTIS sektoral/nasional sesuai ketentuan, laporan regulator sektor, dan laporan internal direksi.

**Output:** Incident report, notifikasi, bukti pengiriman.
{% endstep %}

{% step %}
### Pembelajaran

Memperbaiki kontrol dan mencegah kejadian berulang melalui post-incident review, lessons learned, update playbook, update deteksi, dan update risk register.

**Output:** PIR report, corrective action plan, closure evidence.
{% endstep %}
{% endstepper %}

### 10.11 Klasifikasi Severity Insiden untuk Sektor Keuangan

Severity matrix harus disetujui oleh manajemen dan digunakan konsisten oleh SOC, TTIS, TI, bisnis, fraud, dan compliance.

| Severity         | Kriteria Dampak                                                                                                                                           | Contoh Insiden                                                                                                                                      | Eskalasi Minimum                                                                               |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Critical / Sev-1 | Gangguan luas pada layanan kritikal; potensi dampak sistemik; data nasabah skala besar; ransomware aktif pada sistem kritikal; fraud masif; IIV terdampak | Core banking tidak dapat beroperasi, mobile banking nasional down akibat serangan, ransomware pada data center, compromise payment switch/API utama | Direksi, Incident Commander, TTIS sektoral/nasional sesuai ketentuan, regulator sektor, BCM/DR |
| High / Sev-2     | Gangguan signifikan pada layanan penting; risiko tinggi terhadap data atau transaksi; kompromi akun privilese; insiden pada pihak ketiga kritikal         | Credential stuffing dengan banyak akun terdampak, cloud key leak, DDoS pada kanal digital, kebocoran data terbatas tetapi sensitif                  | CISO, TTIS Manager, Legal/Compliance, Fraud, Vendor Lead                                       |
| Medium / Sev-3   | Dampak terbatas pada unit/sistem non-kritikal; tidak ada bukti eksfiltrasi luas; pemulihan dapat dilakukan dengan kontrol standar                         | Malware pada endpoint terbatas, phishing pegawai, vulnerability exploited pada sistem pendukung                                                     | SOC Lead, App/Infra Owner, Risk                                                                |
| Low / Sev-4      | Peristiwa keamanan atau alert yang belum berdampak material; false positive terkendali; percobaan serangan tertahan                                       | Port scanning, blocked malware, phishing gagal                                                                                                      | SOC/Service Desk                                                                               |

{% hint style="info" %}
**Rekomendasi:** gunakan severity berdasarkan kombinasi dampak pada _confidentiality_, _integrity_, _availability_, dampak transaksi, dampak nasabah, dampak reputasi, dampak hukum/regulator, serta potensi penyebaran ke entitas lain dalam sektor keuangan.
{% endhint %}

### 10.12 Pelaporan, Eskalasi, dan Koordinasi Eksternal

Pelaporan insiden perlu dibedakan antara pelaporan internal, pelaporan kepada regulator sektor, pelaporan kepada TTIS sektoral/nasional, pelaporan kepada pihak terdampak, dan komunikasi publik.

| Jenis Pelaporan                  | Kapan Dilakukan                                                                     | Isi Minimum                                                            | Kanal/Penerima                                                                                           |
| -------------------------------- | ----------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Pelaporan awal internal          | Saat insiden tervalidasi minimal Sev-3 atau sesuai kebijakan                        | Waktu deteksi, aset, gejala, tindakan awal, potensi dampak             | Incident Commander, CISO, pemilik sistem                                                                 |
| Eskalasi manajemen               | Sev-1/Sev-2, potensi gangguan layanan/data/transaksi                                | Executive brief, opsi keputusan, risiko residual                       | Direksi, Komite Krisis, Komite TI/Risiko                                                                 |
| Pelaporan TTIS sektoral/nasional | Insiden risiko tinggi dan/atau IIV sesuai ketentuan BSSN                            | Kontak pelapor, deskripsi, kronologi, dampak serangan, analisis risiko | TTIS sektoral dengan tembusan TTIS nasional; bila TTIS sektoral belum terbentuk mengikuti ketentuan BSSN |
| Pelaporan regulator sektor       | Sesuai ketentuan OJK/BI/KL sektor yang berlaku                                      | Ringkasan insiden, dampak, mitigasi, pemulihan, rencana perbaikan      | Kanal pelaporan regulator masing-masing                                                                  |
| Pemberitahuan pihak terdampak    | Saat informasi diperlukan untuk mengurangi dampak atau memenuhi kewajiban           | Jenis indikasi insiden, aset/sistem terdampak, rekomendasi mitigasi    | Nasabah/mitra/vendor/pihak terdampak sesuai klasifikasi informasi                                        |
| Komunikasi publik                | Saat diperlukan untuk mencegah kepanikan, memberi arahan, atau menjaga transparansi | Pesan yang telah divalidasi legal, compliance, bisnis, dan teknis      | Media statement, website, kanal resmi, customer care                                                     |

**Konten minimum laporan insiden:** kontak pelapor, deskripsi insiden, kronologi insiden, dampak serangan, aset terdampak, tindakan awal, status containment, kebutuhan bantuan, klasifikasi distribusi informasi, dan kontak koordinasi 24/7.

### 10.13 Integrasi TTIS dengan OJK, BI, BSSN, dan Ekosistem Sektor Keuangan

Dalam industri sektor keuangan, koordinasi eksternal perlu dirancang sebelum insiden terjadi. Organisasi perlu memiliki daftar kontak dan prosedur untuk berkoordinasi dengan:

1. **Regulator sektor** sesuai jenis lembaga dan aktivitas, antara lain OJK dan/atau BI.
2. **TTIS sektoral/nasional** sesuai ketentuan BSSN.
3. **Aparat penegak hukum** apabila insiden mengandung unsur tindak pidana, pemerasan, pencurian data, atau fraud.
4. **Vendor kritikal** seperti cloud provider, payment gateway, switching, managed security service provider, core system vendor, data center, dan telecom provider.
5. **Mitra ekosistem** seperti bank koresponden, peserta sistem pembayaran, merchant aggregator, lembaga switching, asuransi siber, dan forensik eksternal.
6. **Nasabah/pihak terdampak** sesuai kebutuhan mitigasi dan kewajiban pelindungan konsumen/data.

{% hint style="info" %}
**Contoh praktik sektor keuangan:** OJK telah memublikasikan profil, layanan, kontak, dan RFC 2350 OJK-CSIRT. Dokumen tersebut dapat dijadikan contoh format profil dan layanan CSIRT, namun setiap lembaga tetap perlu menyusun profil TTIS organisasinya sendiri sesuai mandat, konstituen, dan ruang lingkup layanan internal.
{% endhint %}

### 10.14 Playbook Minimum untuk Industri Sektor Keuangan

TTIS perlu memiliki playbook yang diuji dan diperbarui berkala. Minimum playbook yang direkomendasikan:

| Playbook                             | Fokus Risiko                                                            | Aktivitas Kunci                                                                                                 |
| ------------------------------------ | ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Ransomware                           | Enkripsi sistem kritikal, eksfiltrasi data, gangguan layanan            | Isolasi jaringan, preservasi bukti, blokir lateral movement, validasi backup, aktivasi DRC, komunikasi krisis   |
| Data Breach/Data Exfiltration        | Kebocoran data nasabah, data transaksi, rahasia bank/rahasia perusahaan | Scope data, stop exfiltration, forensik, legal assessment, notifikasi sesuai ketentuan, perbaikan kontrol akses |
| Credential Stuffing/Account Takeover | Pengambilalihan akun nasabah/pegawai                                    | Rate limit, step-up authentication, blokir IP/bot, reset kredensial, fraud monitoring, komunikasi nasabah       |
| DDoS pada Kanal Digital              | Gangguan mobile banking, internet banking, API, website                 | DDoS scrubbing, traffic reroute, koordinasi ISP/CDN, status layanan, fallback channel                           |
| Fraud Digital Terkoordinasi          | Transaksi ilegal, mule account, manipulasi kanal digital                | Freeze/hold transaksi, analisis pola fraud, koordinasi fraud ops, legal hold, laporan internal/regulator        |
| Cloud/SaaS Compromise                | Token/API key bocor, privilege escalation, data exposure                | Revoke key/token, audit IAM, snapshot bukti, hardening cloud, review konfigurasi bucket/storage                 |
| Supply Chain/Vendor Incident         | Insiden pada vendor kritikal atau integrasi pihak ketiga                | Putus/limit koneksi, evaluasi dampak, audit log integrasi, vendor escalation, klausul kontrak insiden           |
| Vulnerability Exploitation           | Eksploitasi CVE kritikal pada internet-facing system                    | Emergency patch, virtual patching, WAF rule, threat hunt, vulnerability disclosure handling                     |
| Insider Misuse                       | Penyalahgunaan akses pegawai/kontraktor                                 | Suspend access, preservasi log, koordinasi HR/legal, investigasi aktivitas, review SoD                          |
| Core/Payment Outage karena Serangan  | Layanan kritikal tidak tersedia atau data tidak sinkron                 | Aktivasi BCP/DR, rekonsiliasi transaksi, failover, validasi integritas data, komunikasi bisnis/nasabah          |

### 10.15 Bukti Digital dan Chain of Custody

Pengelolaan bukti sangat penting untuk investigasi, audit, pembelajaran, klaim asuransi, pelaporan regulator, dan kemungkinan proses hukum.

| Bukti              | Contoh                                                         | Perlakuan Minimum                                               |
| ------------------ | -------------------------------------------------------------- | --------------------------------------------------------------- |
| Log keamanan       | SIEM, EDR, NDR, WAF, firewall, IAM, VPN, email gateway         | Ekspor dengan timestamp, hash, penyimpanan aman, akses terbatas |
| Bukti sistem       | Disk image, memory dump, snapshot VM/cloud, konfigurasi        | Akuisisi forensik, dokumentasi alat, hash, chain of custody     |
| Bukti aplikasi     | Application log, API gateway log, database audit trail         | Preservasi sebelum rotasi log, korelasi dengan user/session     |
| Bukti transaksi    | Payment logs, transaction journal, fraud case, settlement file | Rekonsiliasi, legal hold, perlindungan data nasabah             |
| Bukti komunikasi   | Email phishing, tiket, chat war room, instruksi vendor         | Arsipkan sesuai klasifikasi dan kebijakan retensi               |
| Bukti pihak ketiga | Vendor report, cloud audit log, CDN/DDoS report                | Validasi integritas, kaitkan dengan SLA/kontrak                 |

**Aturan minimum:** jangan melakukan perubahan pada sistem terdampak sebelum bukti kritikal diamankan, kecuali tindakan segera diperlukan untuk mencegah dampak yang lebih besar. Setiap tindakan darurat harus dicatat dalam timeline insiden.

### 10.16 Komunikasi Insiden dan Kode Distribusi Informasi

Informasi insiden siber sering kali sensitif karena dapat berisi celah keamanan, IoC, data nasabah, taktik penyerang, dan kelemahan kontrol. TTIS perlu menetapkan klasifikasi distribusi informasi. Secara praktis, organisasi dapat mengadopsi TLP 2.0 untuk melengkapi kode distribusi informasi yang diwajibkan dalam ketentuan nasional.

| Label            | Penggunaan Praktis                                                                                                                         |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| TLP:RED          | Hanya untuk penerima tertentu di war room/komite krisis. Contoh: detail kunci privat bocor, bukti data nasabah, strategi negosiasi krisis. |
| TLP:AMBER+STRICT | Boleh dibagikan secara need-to-know hanya dalam organisasi. Contoh: detail teknis insiden, sistem rentan, akun privilese terdampak.        |
| TLP:AMBER        | Boleh dibagikan need-to-know dalam organisasi dan pihak yang perlu membantu seperti vendor/mitra terikat NDA.                              |
| TLP:GREEN        | Boleh dibagikan dalam komunitas tepercaya untuk pencegahan, misalnya IoC tanpa data sensitif.                                              |
| TLP:CLEAR        | Dapat dipublikasikan, misalnya advisory umum tanpa detail eksploitasi sensitif.                                                            |

### 10.17 Integrasi dengan SOC, Threat Intelligence, dan Fraud Monitoring

TTIS harus dirancang sebagai orkestrator respons, bukan pengganti seluruh fungsi keamanan. Integrasi minimum:

| Fungsi                   | Integrasi dengan TTIS                                                 | Output                                                |
| ------------------------ | --------------------------------------------------------------------- | ----------------------------------------------------- |
| SOC/SIEM                 | Alert triage, correlation rule, use case detection, dashboard insiden | Case, timeline, IoC, alert quality                    |
| EDR/NDR/XDR              | Investigasi endpoint/network, containment teknis                      | Host isolation, process tree, network trace           |
| Threat Intelligence      | IoC, TTP, kampanye ancaman, sektor-targeted threat                    | Threat brief, detection rule, blocking list           |
| Vulnerability Management | CVE kritikal, emergency patch, compensating control                   | Risk-based patch plan, exception tracking             |
| Fraud Monitoring         | Korelasi serangan siber dengan transaksi tidak sah                    | Fraud case, blocked transaction, mule account pattern |
| IAM/PAM                  | Reset akun, revoke session, review akses privilese                    | Access containment, access recertification            |
| BCM/DR                   | Recovery service, failover, RTO/RPO, crisis exercise                  | DR activation, recovery validation                    |

### 10.18 Simulasi dan Uji Kesiapan

Simulasi perlu dilakukan secara berkala dan mencakup skenario teknis, bisnis, komunikasi, dan pelaporan. Untuk entitas dengan layanan kritikal, simulasi minimal sebaiknya mencakup:

| Jenis Uji                  | Tujuan                                                                      | Frekuensi Rekomendasi                    | Bukti                                             |
| -------------------------- | --------------------------------------------------------------------------- | ---------------------------------------- | ------------------------------------------------- |
| Tabletop exercise          | Menguji alur keputusan, eskalasi, pelaporan, dan komunikasi                 | Minimal tahunan                          | Skenario, daftar hadir, notulen, gap list         |
| Technical drill            | Menguji playbook teknis seperti isolasi host, restore, failover, revoke key | Minimal tahunan atau per perubahan besar | Log aksi, hasil uji, screenshot, tiket            |
| Crisis communication drill | Menguji pesan nasabah, media, call center, dan regulator liaison            | Minimal tahunan                          | Draft statement, approval log, call tree test     |
| Backup/restore test        | Menguji integritas backup dan RTO/RPO                                       | Sesuai kritikalitas layanan              | Restore report, rekonsiliasi data                 |
| Red team/purple team       | Menguji deteksi, respons, dan koordinasi terhadap serangan realistis        | Berdasarkan risiko                       | Attack narrative, detection gap, improvement plan |

### 10.19 KPI dan KRI TTIS

| Area              | Indikator                                                       | Tujuan                             |
| ----------------- | --------------------------------------------------------------- | ---------------------------------- |
| Deteksi           | MTTD, jumlah alert tervalidasi, false positive rate             | Mengukur kualitas deteksi          |
| Respons           | MTTA, MTTC, MTTR, waktu aktivasi war room                       | Mengukur kecepatan respons         |
| Pemulihan         | Pemenuhan RTO/RPO, durasi gangguan, jumlah layanan terdampak    | Mengukur resiliensi layanan        |
| Pelaporan         | Ketepatan waktu laporan, kelengkapan laporan, bukti pengiriman  | Mengukur kepatuhan dan koordinasi  |
| Kualitas playbook | Persentase playbook diuji, temuan simulasi, action closure rate | Mengukur kesiapan operasional      |
| Bukti & forensik  | Persentase kasus dengan chain of custody lengkap                | Mengukur akuntabilitas investigasi |
| Pembelajaran      | Jumlah kontrol diperbaiki, recurrence rate, aging action plan   | Mengukur perbaikan berkelanjutan   |

### 10.20 Tingkat Kematangan TTIS

| Level         | Ciri Kematangan TTIS                                                                                   | Target Perbaikan                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ |
| 1 Awal        | Respons ad hoc, kontak tidak lengkap, playbook belum tersedia                                          | Bentuk TTIS, tetapkan mandat, kontak, dan alur eskalasi            |
| 2 Berulang    | Prosedur dasar ada, namun belum konsisten dan belum diuji                                              | Standarkan playbook, severity matrix, incident ticketing           |
| 3 Terdefinisi | TTIS formal, RFC 2350 tersedia, rencana tanggap ditetapkan, simulasi dilakukan                         | Integrasikan SOC, BCM, vendor, fraud, legal, dan regulator liaison |
| 4 Terkelola   | KPI/KRI berjalan, playbook diuji berkala, lessons learned ditindaklanjuti                              | Otomasi case management, SOAR terbatas, threat intel terintegrasi  |
| 5 Inovatif    | Respons terotomasi, intelijen ancaman proaktif, purple team berkelanjutan, pembelajaran menjadi budaya | Optimasi berbasis data, sectoral sharing, advanced analytics       |

### 10.21 Checklist Minimum Pembentukan TTIS Organisasi

| No | Checklist                                                           | Status | Bukti                                   |
| -: | ------------------------------------------------------------------- | ------ | --------------------------------------- |
|  1 | SK/Piagam TTIS disahkan pimpinan                                    | ☐      | SK/Piagam                               |
|  2 | Struktur, peran, RACI, dan kontak 24/7 ditetapkan                   | ☐      | Struktur organisasi, call tree          |
|  3 | Profil RFC 2350 tersedia dan diperbarui                             | ☐      | Dokumen RFC 2350                        |
|  4 | Permohonan registrasi TTIS disiapkan/diajukan sesuai ketentuan      | ☐      | Formulir, surat, bukti pengajuan        |
|  5 | Rencana tanggap insiden siber disetujui pimpinan                    | ☐      | Dokumen rencana tanggap                 |
|  6 | Rencana keberlangsungan kegiatan terintegrasi dengan insiden siber  | ☐      | BCP/DRP, RTO/RPO                        |
|  7 | Severity matrix dan kriteria pelaporan ditetapkan                   | ☐      | Severity matrix                         |
|  8 | Playbook minimum tersedia dan diuji                                 | ☐      | Playbook, hasil uji                     |
|  9 | Integrasi SOC/SIEM/EDR/NDR dengan proses tiket insiden              | ☐      | Screenshot sistem, tiket uji            |
| 10 | Prosedur forensik dan chain of custody tersedia                     | ☐      | Form chain of custody                   |
| 11 | Mekanisme pelaporan regulator dan TTIS sektoral/nasional ditetapkan | ☐      | SOP pelaporan, daftar kontak            |
| 12 | Kode distribusi informasi/TLP digunakan                             | ☐      | Template laporan, klasifikasi informasi |
| 13 | Simulasi tabletop/technical drill dilakukan                         | ☐      | Laporan simulasi                        |
| 14 | Post-incident review dan action tracker berjalan                    | ☐      | PIR report, action tracker              |
| 15 | KPI/KRI TTIS dilaporkan ke manajemen                                | ☐      | Dashboard, laporan komite               |

### 10.22 Template Ringkas Laporan Insiden Siber

```markdown
# Laporan Insiden Siber

## 1. Informasi Pelapor
- Nama pelapor:
- Unit/organisasi:
- Kontak 24/7:
- Tanggal dan waktu laporan:
- Klasifikasi informasi/TLP:

## 2. Ringkasan Insiden
- Nomor tiket/kasus:
- Tanggal dan waktu deteksi:
- Jenis insiden:
- Severity:
- Status terkini:
- Sistem/aset terdampak:

## 3. Kronologi
| Waktu | Peristiwa | Sumber Bukti | PIC |
|---|---|---|---|

## 4. Dampak
- Dampak layanan:
- Dampak data:
- Dampak transaksi:
- Dampak nasabah/pihak ketiga:
- Dampak reputasi/hukum/regulator:

## 5. Tindakan yang Telah Dilakukan
- Deteksi dan validasi:
- Containment:
- Eradikasi:
- Pemulihan:
- Komunikasi/pelaporan:

## 6. Bukti Pendukung
- Log:
- Artefak:
- Screenshot:
- Hash/chain of custody:

## 7. Kebutuhan Bantuan/Eskalasi
- Bantuan teknis:
- Bantuan koordinasi:
- Keputusan manajemen yang dibutuhkan:

## 8. Rencana Tindak Lanjut
| Aksi | PIC | Target | Status |
|---|---|---|---|
```

### 10.23 Advisory Insight: TTIS sebagai Tulang Punggung Ketahanan Siber

{% hint style="info" %}
**Advisory Insight:** dalam sektor keuangan, insiden siber jarang berhenti sebagai isu teknologi. Insiden dapat berubah menjadi gangguan operasional, fraud, kebocoran data, krisis reputasi, isu hukum, dan risiko sistemik. Karena itu, TTIS harus diberi mandat lintas fungsi, bukan hanya menjadi tim teknis yang bekerja setelah insiden terjadi. Ukuran keberhasilan TTIS bukan hanya seberapa cepat sistem dipulihkan, tetapi juga seberapa baik organisasi melindungi nasabah, menjaga integritas transaksi, memenuhi kewajiban pelaporan, dan memperbaiki kontrol agar kejadian tidak berulang.
{% endhint %}

***

