---
description: >-
  Bab tentang Panduan Pengoptimalan fungsi Tim Tanggap Insiden Siber (TTIS)
  untuk meningkatkan ketahanan siber organisasi khususnya melalui peningkatan
  kapabilitas Penanggulangan & Pemulihan.
---

# Bab VI

Bab ini dibuat khusus sebagai panduan praktis pembentukan, pengoperasian, pelaporan, eskalasi, dan pengukuran kinerja **Tim Tanggap Insiden Siber (TTIS)** atau _Computer Security Incident Response Team_ (CSIRT) pada industri sektor keuangan Indonesia. Dengan panduan ini diharapkan organisasi dapat mengoptimalkan fungsi sehingga dapat meningkatkan ketahanan siber organisasi melalui peningkatan kapabilitas Penanggulangan & Pemulihan di dalam kerangka pengukuran IKAS, serta menghubungkan kebutuhan kepatuhan dengan kesiapan operasional saat insiden siber terjadi.

TTIS adalah tim atau unit resmi organisasi yang bertugas mencegah, mengelola, dan menanggulangi gangguan serta serangan keamanan siber dari organisasi. TTIS Organisasi yang terdaftar resmi terhubung dengan ekosistem TTIS nasional sesuai dengan pengaturan, dan menjadi bagian dari upaya pemerintah dalam meningkatkan ketahanan dan keamanan siber Negara Kesatuan Republik Indonesia.

### 6.1 Posisi TTIS dalam KKS Sektor Keuangan

Dalam konteks sektor keuangan, TTIS tidak boleh dipahami hanya sebagai tim teknis TI. TTIS adalah kapabilitas organisasi lintas fungsi yang bertanggung jawab memastikan insiden siber dapat dideteksi, dianalisis, diprioritaskan, ditangani, dipulihkan, dilaporkan, dan dijadikan pembelajaran. Pada lembaga sektor keuangan, TTIS perlu terhubung dengan layanan dan proses kritikal yang dikelola organisasi seperti:

* core banking/core insurance/core financing/core capital market platform;
* mobile banking, internet banking, ATM, EDC, QRIS, kanal pembayaran, API, dan open finance;
* sistem treasury, settlement, switching, rekonsiliasi, fraud monitoring, dan anti-fraud;
* data center, DRC, cloud, jaringan cabang, endpoint pegawai, dan layanan pihak ketiga;
* sistem pelaporan regulator, sistem pelayanan nasabah, call center, dan komunikasi publik.

{% hint style="info" %}
**Prinsip TTIS pada sektor keuangan:** TTIS harus memadukan perspektif _cybersecurity_, keberlangsungan bisnis, perlindungan data nasabah, integritas transaksi, anti-fraud, dan stabilitas layanan. Keputusan teknis seperti isolasi server, pemutusan koneksi API, pemblokiran akun, atau aktivasi DRC harus mempertimbangkan dampaknya terhadap nasabah, transaksi yang terus berjalan, likuiditas, reputasi, dan kewajiban pelaporan.
{% endhint %}

### 6.2 Dasar Regulasi dan Standar Rujukan

Panduan Pengoptimalan fungsi TTIS ini menggunakan beberapa rujukan utama:

<table><thead><tr><th valign="top">Rujukan</th><th valign="top">Posisi dalam Panduan</th><th valign="top">Implikasi untuk Industri Sektor Keuangan</th></tr></thead><tbody><tr><td valign="top">Peraturan BSSN No. 1 Tahun 2024 tentang Pengelolaan Insiden Siber</td><td valign="top">Dasar nasional pengelolaan insiden siber, pembentukan TTIS, registrasi, pelaporan, penanganan, dan kesiapan</td><td valign="top">Lembaga perlu membentuk TTIS organisasi, menyusun rencana tanggap insiden, melaporkan insiden sesuai ketentuan, dan menguji kesiapan secara berkala</td></tr><tr><td valign="top">Peraturan BSSN No. 10 Tahun 2023 tentang Pengukuran Tingkat Kematangan Keamanan Siber</td><td valign="top">Dasar pengukuran kematangan, khususya pada domain terkait, seperti Domain Deteksi dan Penanggulangan &#x26; Pemulihan</td><td valign="top">TTIS menjadi komponen operasional yang membuktikan bahwa kontrol IKAS tidak hanya berbentuk dokumen</td></tr><tr><td valign="top">RFC 2350</td><td valign="top">Format profil CSIRT/TTIS, memuat kontak, mandat, konstituen, layanan, kebijakan, dan formulir pelaporan</td><td valign="top">Diperlukan sebagai dokumen profil TTIS, termasuk dalam persyaratan registrasi TTIS</td></tr><tr><td valign="top">NIST SP 800-61 Rev. 3 dan NIST CSF 2.0</td><td valign="top">Rekomendasi integrasi respons insiden ke dalam manajemen risiko siber</td><td valign="top">Respons insiden perlu terintegrasi dengan tata kelola, identifikasi, proteksi, deteksi, respons, dan pemulihan</td></tr><tr><td valign="top">ISO/IEC 27035-1:2023</td><td valign="top">Prinsip dan proses manajemen insiden keamanan informasi</td><td valign="top">Memperkuat proses persiapan, deteksi, pelaporan, asesmen, respons, dan pembelajaran pascainsiden</td></tr><tr><td valign="top">FIRST CSIRT Services Framework v2.1</td><td valign="top">Kerangka layanan CSIRT</td><td valign="top">Membantu menentukan portofolio layanan TTIS sesuai mandat dan konstituen</td></tr><tr><td valign="top">ENISA How to Set Up CSIRT and SOC</td><td valign="top">Panduan praktik pendirian dan peningkatan CSIRT/SOC</td><td valign="top">Menjadi referensi praktis untuk model operasi, pengembangan kapabilitas, dan integrasi SOC-CSIRT</td></tr><tr><td valign="top">FIRST Traffic Light Protocol (TLP) 2.0</td><td valign="top">Skema distribusi informasi sensitif</td><td valign="top">Mendukung pengendalian penyebaran informasi insiden, IoC, kerentanan, dan rekomendasi mitigasi</td></tr></tbody></table>

### 6.3 Definisi Umum dalam Operasional TTIS

Dalam Panduan Pengoptimalan fungsi TTIS untuk meningkatkan ketahanan siber organisasi, beberapa definisi umum yang digunakan dalam operasional TTIS adalah sebagai berikut.

* **Insiden Siber** adalah kejadian atau rangkaian kejadian yang mengganggu atau mengancam berjalannya sistem elektronik.
* **TTIS/CSIRT organisasi** adalah tim pada lembaga sektor keuangan yang bertanggung jawab menangani insiden siber dalam ruang lingkup organisasi.
* **Konstituen** adalah pihak yang menerima layanan TTIS. Pada lembaga sektor keuangan, konstituen dapat mencakup unit bisnis, unit TI, cabang, anak perusahaan, unit digital, unit operasional transaksi, unit fraud, dan dalam kondisi tertentu pihak ketiga yang terikat kontrak.
* **Rencana tanggap insiden siber** adalah dokumen yang menetapkan tahapan penanganan, jenis insiden, peran dan tanggung jawab, sumber daya, proses pemulihan sistem/data kritikal, dan kontak internal/eksternal.
* **Rencana keberlangsungan kegiatan** adalah dokumen yang memastikan fungsi dan layanan bisnis kritikal tetap berjalan atau dapat dipulihkan sesuai prioritas, RTO, dan RPO yang ditetapkan.

### 6.4 Prinsip Desain TTIS untuk Sektor Keuangan

<table data-view="cards"><thead><tr><th valign="top">Prinsip</th><th valign="top">Penjelasan</th></tr></thead><tbody><tr><td valign="top"><strong>Mandat formal</strong></td><td valign="top">TTIS dibentuk berdasarkan keputusan pimpinan/direksi dan memiliki kewenangan operasional yang jelas</td></tr><tr><td valign="top"><strong>Berbasis risiko</strong></td><td valign="top">Prioritas respons mengacu pada dampak terhadap layanan kritikal, data nasabah, integritas transaksi, dan kepatuhan</td></tr><tr><td valign="top"><strong>Terintegrasi dengan BCM/DRP</strong></td><td valign="top">Pemulihan insiden siber harus selaras dengan keberlangsungan bisnis dan pemulihan teknologi</td></tr><tr><td valign="top"><strong>Evidence-based</strong></td><td valign="top">Setiap keputusan respons didukung bukti teknis, log, tiket, artefak, dan timeline</td></tr><tr><td valign="top"><strong>Koordinatif</strong></td><td valign="top">TTIS bekerja dengan SOC, TI, bisnis, fraud, legal, DPO, compliance, vendor, dan regulator liaison</td></tr><tr><td valign="top"><strong>Aman dalam berbagi informasi</strong></td><td valign="top">Informasi insiden, IoC, dan kerentanan dibagikan sesuai kebutuhan dan klasifikasi menggunakan kode distribusi informasi/TLP, NDA vendor, serta kanal komunikasi yang aman</td></tr><tr><td valign="top"><strong>Pembelajaran berkelanjutan</strong></td><td valign="top">Setiap insiden menghasilkan perbaikan kontrol, playbook, deteksi, dan pelatihan</td></tr></tbody></table>

### 6.5 Model Operasional TTIS

Model operasional Tim Tanggap Insiden Siber (TTIS) perlu dipilih berdasarkan karakteristik organisasi, subsektor industri, tingkat kritikalitas layanan, eksposur digital, volume transaksi, ketergantungan pihak ketiga, serta kemampuan sumber daya internal. **Tidak terdapat satu model yang cocok untuk seluruh entitas sektor keuangan.** Bank umum berskala besar, penyelenggara sistem pembayaran, pelaku pasar uang/valas, penyelenggara aset kripto, BPR/BPRS, dan lembaga jasa keuangan non-bank memiliki kebutuhan, risiko, dan kapasitas yang berbeda. Oleh karena itu, panduan ini merekomendasikan pendekatan proporsional, dimana semakin kritikal layanan, semakin tinggi eksposur digital, dan semakin besar dampak sistemik, maka semakin kuat kebutuhan organisasi untuk memiliki kapabilitas TTIS internal yang formal, teruji, dan terintegrasi dengan SOC, manajemen krisis, serta fungsi bisnis.

Secara umum, organisasi sektor keuangan dapat memilih atau mengombinasikan empat model operasional TTIS, yaitu **Terpusat**, **Federated**, **Hybrid SOC-CSIRT**, dan **Managed/Co-sourced**. Pemilihan model tidak hanya mempertimbangkan struktur organisasi, tetapi juga kemampuan menjalankan fungsi deteksi, triage, eskalasi, containment, forensik, eradikasi, pemulihan, pelaporan regulator, komunikasi krisis, dan pembelajaran pascainsiden.

{% hint style="info" %}
Model TTIS yang tepat bagi sebuah organisasi bukan model yang paling kompleks, tetapi model yang paling mampu memastikan insiden dapat dideteksi cepat, diputuskan secara tepat, ditangani terkoordinasi, dipulihkan sesuai prioritas bisnis, dan dilaporkan sesuai kewajiban regulator.
{% endhint %}

#### Karakteristik Model Operasional TTIS

<table><thead><tr><th valign="top">Model Operasional</th><th valign="top">Karakteristik Utama</th><th valign="top">Kesesuaian</th><th valign="top">Risiko yang Perlu Dikendalikan</th></tr></thead><tbody><tr><td valign="top"><strong>Terpusat</strong></td><td valign="top">Satu tim TTIS pusat bertanggung jawab atas koordinasi, pengambilan keputusan, penanganan, dokumentasi, pelaporan, dan pembelajaran insiden untuk seluruh organisasi.</td><td valign="top">Cocok untuk organisasi dengan struktur relatif sederhana, jumlah sistem terkendali, layanan tidak terlalu tersebar, dan kebutuhan pengendalian yang kuat dari kantor pusat.</td><td valign="top">Berisiko menjadi bottleneck apabila volume insiden tinggi, unit bisnis tersebar, atau sistem sangat beragam.</td></tr><tr><td valign="top"><strong>Federated</strong></td><td valign="top">TTIS pusat menetapkan kebijakan, standar, koordinasi, dan pelaporan, sementara unit bisnis, wilayah, anak perusahaan, atau entitas tertentu memiliki incident response focal point sendiri.</td><td valign="top">Cocok untuk konglomerasi keuangan, grup usaha, bank besar dengan banyak unit digital, atau organisasi dengan banyak entitas dan variasi layanan.</td><td valign="top">Berisiko terjadi inkonsistensi prosedur, kualitas bukti, klasifikasi severity, dan eskalasi apabila governance pusat lemah.</td></tr><tr><td valign="top"><strong>Hybrid SOC-CSIRT</strong></td><td valign="top">SOC menjalankan monitoring, deteksi, triage, dan analisis awal, sedangkan TTIS/CSIRT memimpin penanganan insiden, koordinasi lintas fungsi, forensik, pemulihan, pelaporan, dan perbaikan pascainsiden.</td><td valign="top">Cocok untuk entitas dengan layanan digital kritikal, kebutuhan monitoring 24/7, volume transaksi tinggi, ancaman kompleks, dan kewajiban pelaporan insiden yang ketat.</td><td valign="top">Berisiko terjadi overlap antara SOC dan TTIS jika batas peran, eskalasi, dan incident command tidak didefinisikan jelas.</td></tr><tr><td valign="top"><strong>Managed / Co-sourced</strong></td><td valign="top">Sebagian fungsi deteksi, analisis, forensik, threat intelligence, SOC, atau incident response didukung oleh penyedia eksternal, sementara akuntabilitas tetap berada pada organisasi.</td><td valign="top">Cocok untuk organisasi dengan keterbatasan SDM, anggaran, dan kapasitas teknis, atau organisasi yang membutuhkan kapabilitas khusus secara cepat.</td><td valign="top">Berisiko ketergantungan vendor, keterlambatan eskalasi, isu kerahasiaan data, dan lemahnya kendali apabila SLA, kontrak, akses, dan joint playbook tidak kuat.</td></tr></tbody></table>

{% hint style="warning" %}
**Penggunaan penyedia jasa Pihak Ketiga / Eksternal tidak otomatis memindahkan tanggung jawab tata kelola organisasi.** Pimpinan organisasi tetap perlu menetapkan pemilik proses, kontak eskalasi, kewenangan pengambilan keputusan, serta mekanisme audit terhadap layanan eksternal.
{% endhint %}

#### Faktor Penentu Pemilihan Model Operasional TTIS

Pemilihan model operasional TTIS perlu mempertimbangkan beberapa faktor utama. Pertama, **kritikalitas layanan**, yaitu apakah sistem mendukung transaksi real-time, layanan nasabah, sistem pembayaran, pasar keuangan, data pribadi berskala besar, atau layanan yang berdampak luas. Kedua, **kompleksitas arsitektur**, termasuk penggunaan cloud, API, microservices, data center, sistem legacy, koneksi pihak ketiga, dan integrasi lintas kanal. Ketiga, **volume dan kecepatan insiden**, yaitu seberapa sering organisasi menghadapi alert, anomali transaksi, serangan malware, DDoS, phishing, fraud digital, atau kebocoran data. Keempat, **ketersediaan resource**, meliputi SDM keamanan siber, SOC, analis forensik, incident commander, legal, compliance, risk, dan komunikasi krisis. Kelima, **kewajiban regulasi**, termasuk kebutuhan pelaporan insiden, maturitas KKS, pelindungan data pribadi, dan ketentuan sektor.

<table><thead><tr><th width="211.491943359375" valign="top">Kondisi Organisasi</th><th valign="top">Implikasi terhadap Pemilihan Model TTIS</th></tr></thead><tbody><tr><td valign="top"><strong>Menyelenggarakan</strong> <strong>Layanan kritikal dan harus tersedia 24/7</strong></td><td valign="top">Mendorong penggunaan Hybrid SOC-CSIRT atau Federated dengan struktur komando (command structure) yang kuat.</td></tr><tr><td valign="top"><strong>Organisasi besar, multi-unit, multi-anak perusahaan, atau multi-lokasi</strong></td><td valign="top">Lebih sesuai menggunakan Federated atau Hybrid SOC-CSIRT agar respons lokal tetap cepat tetapi governance pusat tetap konsisten.</td></tr><tr><td valign="top"><strong>Resource internal terbatas</strong></td><td valign="top">Dapat menggunakan Managed/Co-sourced, tetapi tetap harus memiliki internal incident coordinator, risk owner, dan decision authority.</td></tr><tr><td valign="top"><strong>Volume alert dan insiden tinggi</strong></td><td valign="top">Membutuhkan SOC atau managed SOC yang terintegrasi dengan TTIS, playbook, dan prosedur eskalasi.</td></tr><tr><td valign="top"><strong>Ketergantungan tinggi pada vendor/cloud/data center</strong></td><td valign="top">Model apa pun harus dilengkapi joint incident response procedure, SLA insiden, hak akses log, bukti forensik, dan kewajiban pelaporan vendor.</td></tr></tbody></table>

#### Rekomendasi Model Berdasarkan Subsektor Keuangan

<table><thead><tr><th valign="top">Subsektor</th><th valign="top">Karakteristik Risiko dan Operasional</th><th valign="top">Model yang Direkomendasikan</th><th valign="top">Catatan Implementasi</th></tr></thead><tbody><tr><td valign="top"><strong>Bank Umum</strong></td><td valign="top">Memiliki core banking, mobile/internet banking, API, jaringan kantor, ATM/CRM, data nasabah besar, integrasi sistem pembayaran, dan kewajiban pelaporan insiden yang ketat.</td><td valign="top"><strong>Hybrid SOC-CSIRT</strong> untuk bank menengah-besar; <strong>Federated</strong> untuk bank grup/konglomerasi; <strong>Managed/Co-sourced</strong> terbatas untuk kapabilitas khusus.</td><td valign="top">Bank umum sebaiknya memiliki TTIS internal yang kuat, incident commander, SOC 24/7 atau managed SOC, integrasi fraud monitoring, dan playbook untuk ransomware, DDoS, data leak, mobile banking compromise, dan anomali transaksi.</td></tr><tr><td valign="top"><strong>BPR/BPRS</strong></td><td valign="top">Skala dan resource umumnya lebih terbatas, namun tetap mengelola data nasabah, core banking, layanan digital, vendor TI, dan risiko gangguan operasional.</td><td valign="top"><strong>Terpusat</strong> untuk BPR/BPRS dengan kapasitas internal memadai; <strong>Managed/Co-sourced</strong> untuk monitoring, forensik, dan dukungan teknis; dapat dikembangkan menjadi <strong>Hybrid ringan</strong>.</td><td valign="top">Minimal harus ada incident coordinator internal, daftar kontak darurat, prosedur eskalasi, vendor support SLA, backup-restore test, dan mekanisme pelaporan kepada manajemen serta regulator.</td></tr><tr><td valign="top"><strong>PJP/PIP/PSP</strong></td><td valign="top">Layanan pembayaran bersifat real-time, volume transaksi tinggi, keterhubungan luas, risiko fraud, API exposure, settlement, switching, dan dampak reputasi cepat.</td><td valign="top"><strong>Hybrid SOC-CSIRT</strong> sebagai model utama; <strong>Federated</strong> apabila memiliki banyak platform/produk/entitas; dukungan managed untuk threat intelligence dan DDoS response.</td><td valign="top">Harus kuat pada monitoring 24/7, korelasi cyber-fraud, API security, playbook gangguan transaksi, koordinasi settlement, dan rapid escalation ke manajemen serta otoritas.</td></tr><tr><td valign="top"><strong>Pelaku Pasar Uang/Valas dan Pihak Lain di bawah Pengawasan BI</strong></td><td valign="top">Mengelola transaksi bernilai tinggi, konektivitas ke sistem pasar, integritas instruksi transaksi, rekonsiliasi, dan risiko operasional yang dapat berdampak pada kepercayaan pasar.</td><td valign="top"><strong>Hybrid SOC-CSIRT</strong> untuk entitas dengan volume dan nilai transaksi tinggi; <strong>Terpusat</strong> dengan dukungan managed untuk entitas yang lebih sederhana.</td><td valign="top">Fokus pada integritas transaksi, monitoring anomali, privileged access, rekonsiliasi, business continuity, dan prosedur komunikasi insiden kepada otoritas serta counterparties.</td></tr><tr><td valign="top"><strong>ITSK, Aset Keuangan Digital, Aset Kripto, dan Agregator Jasa Keuangan</strong></td><td valign="top">Berbasis teknologi, API, cloud, data sharing, digital onboarding, consent, aplikasi publik, aset digital, dompet, custody, dan potensi serangan terhadap aplikasi serta integrasi pihak ketiga.</td><td valign="top"><strong>Hybrid SOC-CSIRT</strong> untuk penyelenggara berskala besar atau berisiko tinggi; <strong>Managed/Co-sourced</strong> untuk startup/scale-up dengan internal governance yang tetap kuat.</td><td valign="top">Perlu playbook untuk API abuse, credential compromise, smart contract/platform compromise, data leak, wallet/custody incident, account takeover, cloud misconfiguration, dan third-party breach.</td></tr><tr><td valign="top"><strong>LJKNB: Pembiayaan, Modal Ventura, LKM</strong></td><td valign="top">Mengelola data debitur/nasabah, aplikasi pembiayaan, scoring, collection, integrasi mitra, kanal digital, dan penggunaan vendor TI yang cukup tinggi.</td><td valign="top"><strong>Terpusat</strong> untuk organisasi menengah; <strong>Managed/Co-sourced</strong> untuk SOC/forensik; <strong>Hybrid ringan</strong> untuk entitas digital-intensive.</td><td valign="top">Fokus pada perlindungan data pribadi, keamanan aplikasi pembiayaan, akses vendor, fraud digital, phishing, ransomware, backup, dan koordinasi dengan penyedia layanan TI.</td></tr><tr><td valign="top"><strong>LJKNB: Penjaminan</strong></td><td valign="top">Memiliki sistem penjaminan, data mitra, data penerima jaminan, integrasi dengan bank/lembaga pembiayaan, dan risiko gangguan proses klaim/penjaminan.</td><td valign="top"><strong>Terpusat</strong> dengan dukungan managed untuk monitoring dan forensik; <strong>Federated ringan</strong> apabila memiliki unit/cabang atau entitas grup.</td><td valign="top">Perlu penguatan koordinasi dengan mitra, kontrol akses data, backup, incident notification clause, dan prosedur pemulihan layanan klaim/penjaminan.</td></tr><tr><td valign="top"><strong>PPDP: Perusahaan Perasuransian, Lembaga Penjamin, dan Dana Pensiun</strong></td><td valign="top">Mengelola data peserta/pemegang polis, data klaim, data kesehatan/keuangan, layanan peserta, investasi, pembayaran manfaat, serta banyak proses outsourcing.</td><td valign="top"><strong>Terpusat</strong> untuk organisasi menengah; <strong>Federated</strong> untuk grup asuransi besar; <strong>Managed/Co-sourced</strong> untuk SOC, forensik, dan security testing.</td><td valign="top">Fokus pada data breach response, ransomware, pemulihan layanan klaim/manfaat, keamanan portal nasabah/peserta, vendor TPA/outsourcing, dan komunikasi krisis.</td></tr></tbody></table>

#### **Rekomendasi Model Berdasarkan Ketersediaan Resource**

<table><thead><tr><th valign="top">Kondisi Resource</th><th valign="top">Ciri Organisasi</th><th valign="top">Model yang Disarankan</th><th valign="top">Kapabilitas Minimum yang Harus Ada</th></tr></thead><tbody><tr><td valign="top"><strong>Resource Terbatas</strong></td><td valign="top">Tim TI kecil, belum memiliki SOC, belum memiliki analis forensik, bergantung pada vendor, dan insiden dikelola secara ad hoc.</td><td valign="top"><strong>Managed/Co-sourced</strong> dengan koordinator internal; atau <strong>Terpusat sederhana</strong>.</td><td valign="top">Incident coordinator, daftar kontak eskalasi, prosedur pelaporan, kontrak dukungan insiden, backup-restore, evidence preservation, dan tabletop exercise dasar.</td></tr><tr><td valign="top"><strong>Resource Menengah</strong></td><td valign="top">Memiliki fungsi keamanan TI, monitoring terbatas, beberapa spesialis teknis, prosedur insiden dasar, dan dukungan vendor untuk area tertentu.</td><td valign="top"><strong>Terpusat</strong> atau <strong>Hybrid SOC-CSIRT</strong> dengan managed SOC/DFIR.</td><td valign="top">TTIS formal, playbook insiden utama, severity matrix, log management, vulnerability handling, forensik dasar, crisis communication, dan post-incident review.</td></tr><tr><td valign="top"><strong>Resource Mapan</strong></td><td valign="top">Memiliki SOC, CISO/Head of Cybersecurity, tim keamanan aplikasi/infrastruktur, incident commander, risk-compliance support, dan anggaran keamanan siber berkelanjutan.</td><td valign="top"><strong>Hybrid SOC-CSIRT</strong> sebagai model utama; <strong>Federated</strong> apabila organisasi multi-unit.</td><td valign="top">SOC 24/7, SIEM, threat intelligence, incident command, forensic readiness, playbook teruji, crisis management, vendor assurance, dan recovery exercise.</td></tr><tr><td valign="top"><strong>Resource Lanjut</strong></td><td valign="top">Memiliki SOC 24/7 matang, CTI, DFIR, red/purple team, automation, security engineering, BCM kuat, dan integrasi cyber-fraud-risk.</td><td valign="top"><strong>Federated Hybrid SOC-CSIRT</strong> dengan orchestration dan continuous improvement.</td><td valign="top">SOAR, automated containment, threat hunting, purple teaming, continuous control monitoring, joint exercise dengan vendor/regulator, dan pembelajaran pascainsiden terintegrasi.</td></tr></tbody></table>

#### Decision Guide Pemilihan Model bagi Organisasi

**Gunakan model Terpusat apabila:** organisasi memiliki struktur sederhana, jumlah sistem kritikal terbatas, dan membutuhkan kontrol yang kuat dari satu fungsi pusat.

**Gunakan model Federated apabila:** organisasi memiliki banyak unit bisnis, anak perusahaan, lokasi, platform, atau layanan dengan kebutuhan respons lokal yang cepat tetapi tetap memerlukan standar pusat.

**Gunakan model Hybrid SOC-CSIRT apabila:** organisasi memiliki layanan digital kritikal, volume transaksi tinggi, kebutuhan monitoring 24/7, dan ancaman yang memerlukan deteksi serta respons cepat.

**Gunakan model Managed/Co-sourced apabila:** organisasi memiliki keterbatasan resource internal atau membutuhkan kapabilitas spesialis, namun tetap harus menjaga akuntabilitas, keputusan, dan koordinasi insiden di internal organisasi.

#### Rekomendasi Umum Pemilihan Model Operasional TTIS

* Setiap organisasi yang memberikan layanan digital di sektor keuangan  **minimal harus memiliki fungsi TTIS internal**, meskipun sebagian kemampuan teknis didukung oleh pihak eksternal.
* Entitas dengan layanan kritikal dan transaksi real-time sebaiknya mengarah pada Hybrid SOC-CSIRT dengan monitoring 24/7 dan incident command yang jelas.
* Organisasi besar atau konglomerasi keuangan sebaiknya mempertimbangkan Federated Hybrid SOC-CSIRT agar respons lokal cepat dan standar pusat tetap konsisten.
* Organisasi dengan resource terbatas dapat memulai dari Managed/Co-sourced, tetapi wajib memiliki incident coordinator, risk owner, escalation matrix, dan kontrak dukungan insiden yang jelas.
* Model apa pun yang dipilih, harus dilengkapi dengan RACI, severity matrix, playbook, evidence handling, crisis communication, regulatory reporting procedure, dan post-incident review.

{% hint style="info" %}
Pemilihan model operasional TTIS harus mengikuti prinsip proporsionalitas. Semakin tinggi kritikalitas layanan, eksposur digital, volume transaksi, dan dampak terhadap nasabah atau stabilitas sistem keuangan, semakin besar kebutuhan organisasi untuk memiliki kapabilitas TTIS internal yang kuat dan terintegrasi. Namun, bagi organisasi dengan resource terbatas, model managed atau co-sourced tetap dapat digunakan sepanjang akuntabilitas, keputusan, bukti, dan pelaporan tetap dikendalikan oleh organisasi.
{% endhint %}

### 6.6 Struktur Organisasi dan Peran

Struktur TTIS untuk industri di sektor keuangan sebaiknya dirancang dengan  lapisan **operasional teknis** dan lapisan **manajemen** untuk pengambilan kebijakan ketika terjadi krisis yang keputusan berpengaruh terhadap bisnis. Tabel berikut dapat digunakan sebagai pedoman pembagian peran berdasarkan struktur organisasi yang umum ada di sektor keuangan.

<table><thead><tr><th width="147.311767578125" valign="top">Peran</th><th width="224.2315673828125" valign="top">Tanggung Jawab Utama</th><th valign="top">Unit yang Umumnya Terlibat</th></tr></thead><tbody><tr><td valign="top">Direksi / Management / Komite TI</td><td valign="top">Memberikan mandat, prioritas, sumber daya, dan keputusan strategis</td><td valign="top">Direksi, Komite TI, Komite Manajemen Risiko</td></tr><tr><td valign="top">CSIRT/TTIS Manager</td><td valign="top">Memimpin kapabilitas TTIS, memastikan kesiapan, koordinasi, pelaporan, dan perbaikan</td><td valign="top">CISO, Kepala Keamanan TI, Kepala Operasional TI</td></tr><tr><td valign="top">Incident Commander</td><td valign="top">Memimpin penanganan insiden aktif dan mengoordinasikan <em>war room</em></td><td valign="top">TTIS, SOC, TI Operasional</td></tr><tr><td valign="top">SOC / Monitoring Lead</td><td valign="top">Mengelola deteksi, alert <em>enrichment</em>, SIEM/EDR/NDR, dan eskalasi awal</td><td valign="top">SOC internal / MSSP</td></tr><tr><td valign="top">Forensic &#x26; Evidence Lead</td><td valign="top">Mengamankan bukti, melakukan akuisisi forensik, menjaga chain of custody</td><td valign="top">Tim Digital Forensic, Security Engineering</td></tr><tr><td valign="top">Infrastructure / Network Lead</td><td valign="top">Melakukan isolasi, segmentasi, pemulihan infrastruktur, dan hardening</td><td valign="top">Tim Network &#x26; Infra, Pengelola Data Center, Cloud, Endpoint</td></tr><tr><td valign="top">Application / API Lead</td><td valign="top">Menangani aplikasi, API, DevSecOps, patch, konfigurasi, dan validasi fungsi</td><td valign="top">App Owner, DevOps, QA</td></tr><tr><td valign="top">IAM Lead</td><td valign="top">Menangani akun, kredensial, akses istimewa, dan reset/rotasi kunci</td><td valign="top">IAM, HRIS, Privileged Access Management</td></tr><tr><td valign="top">Data Protection / Privacy Lead</td><td valign="top">Menilai dampak data pribadi dan koordinasi perlindungan data</td><td valign="top">DPO, Legal, Compliance</td></tr><tr><td valign="top">Fraud &#x26; Transaction Risk Lead</td><td valign="top">Menganalisis dampak transaksi, fraud pattern, blokir akun, dan rekonsiliasi</td><td valign="top">Fraud, Payment Ops, Treasury, Operations</td></tr><tr><td valign="top">BCM / DR Lead</td><td valign="top">Mengaktifkan BCP / DRP dan memastikan RTO / RPO</td><td valign="top">BCM, DRC, IT Service Continuity</td></tr><tr><td valign="top">Legal &#x26; Regulatory Liaison</td><td valign="top">Mengelola kewajiban pelaporan dan komunikasi regulator</td><td valign="top">Legal, Compliance, Regulator Reporting</td></tr><tr><td valign="top">Corporate Communication</td><td valign="top">Menyiapkan komunikasi internal, nasabah, media, dan pemangku kepentingan</td><td valign="top">Corporate Secretary, PR, Customer Care</td></tr><tr><td valign="top">Vendor / Third-Party Lead</td><td valign="top">Mengelola koordinasi vendor, cloud provider, payment gateway, dan outsourcer</td><td valign="top">Procurement, Vendor Management, TI</td></tr></tbody></table>

### 6.7 RACI Matriks Penanganan Insiden

Panduan ini juga merekomendasikan penggunaan **RACI Matrix** dalam penanganan insiden siber untuk memperjelas peran setiap pihak yang terlibat dalam penanganan insiden siber. **Responsible** sebagai pelaksana, **Accountable** sebagai penanggung jawab akhir atau pengambil keputusan, **Consulted** sebagai pihak yang memberikan masukan atau validasi, dan **Informed** sebagai pihak yang perlu menerima informasi. Pendekatan diperlukan karena insiden siber yang terjadi pada sektor keuangan sering kali melibatkan banyak fungsi sekaligus, seperti SOC, TI, aplikasi, operasional bisnis, manajemen risiko, kepatuhan, hukum, pelindungan data pribadi, komunikasi publik, vendor, regulator, dan manajemen krisis.&#x20;

NIST SP 800-61 Revision 3 menekankan bahwa rekomendasi incident response juga perlu diintegrasikan ke dalam praktik manajemen risiko keamanan siber agar organisasi lebih siap merespons insiden, mengurangi jumlah dan dampak insiden, serta meningkatkan efisiensi dan efektivitas deteksi, respons, dan pemulihan. Oleh sebab itu, RACI Matrix membantu mekanisme operasional untuk mempercepat pengambilan keputusan, menjaga koordinasi lintas fungsi, dan memastikan pembelajaran pascainsiden masuk ke dalam peningkatan kontrol.

| Aktivitas                   | Incident Commander | Tim SOC | Tim TI Ops | App Owner | Fraud Ops | Tim Legal / Compliance | Tim BCM | Tim Komunikasi | Direksi / Management |
| --------------------------- | ------------------ | ------- | ---------- | --------- | --------- | ---------------------- | ------- | -------------- | -------------------- |
| Validasi alert              | A                  | R       | C          | C         | C         | I                      | I       | I              | I                    |
| Klasifikasi severity        | A                  | R       | C          | C         | C         | C                      | C       | I              | I                    |
| Aktivasi war room           | A/R                | C       | C          | C         | C         | C                      | C       | C              | I                    |
| Isolasi aset                | A                  | C       | R          | C         | C         | I                      | I       | I              | I                    |
| Blokir transaksi / akun     | A                  | C       | C          | C         | R         | C                      | I       | I              | I                    |
| Pelaporan regulator         | C                  | I       | I          | I         | C         | A/R                    | C       | I              | I                    |
| Aktivasi DRC / BCP          | C                  | I       | R          | R         | C         | I                      | A/R     | I              | C                    |
| Komunikasi publik / nasabah | C                  | I       | I          | I         | C         | C                      | C       | A/R            | C                    |
| Post-incident review        | A/R                | R       | R          | R         | C         | C                      | C       | C              | I                    |

Keterangan: **R** = Responsible, **A** = Accountable, **C** = Consulted, **I** = Informed.

{% hint style="warning" %}
Pada saat insiden terjadi, ketidakjelasan peran dapat memperlambat eskalasi, memperbesar dampak, dan menghambat pemulihan. RACI Matrix memastikan bahwa keputusan kritikal seperti deklarasi insiden, isolasi sistem, penghentian sementara layanan, komunikasi kepada nasabah, pelaporan kepada regulator, dan pemulihan layanan memiliki penanggung jawab yang jelas.
{% endhint %}

### 6.8 Portofolio Layanan TTIS

Mengacu pada praktik CSIRT internasional dan Pengaturan Pengelolaan Insiden Siber yang dikeluarkan oleh BSSN, layanan TTIS dapat dikelompokkan menjadi layanan inti dan layanan pendukung. Berikut adalah kelompok layanan dan ekspektasi output minimal yang diharapkan dari setiap kelompok layanan.

<table><thead><tr><th valign="top">Kelompok Layanan</th><th valign="top">Layanan</th><th valign="top">Output Minimal</th></tr></thead><tbody><tr><td valign="top">Penerimaan dan triage laporan</td><td valign="top">Menerima laporan insiden, memvalidasi, mengategorikan, dan memprioritaskan</td><td valign="top">Tiket insiden, nomor kasus, severity, initial assessment</td></tr><tr><td valign="top">Analisis insiden</td><td valign="top">Analisis log, IoC, artefak, vektor serangan, akun terdampak, sistem terdampak</td><td valign="top">Laporan analisis awal, timeline, hipotesis root cause</td></tr><tr><td valign="top">Koordinasi respons</td><td valign="top">Koordinasi lintas unit, vendor, regulator liaison, dan pihak terdampak</td><td valign="top">War room, action tracker, keputusan containment</td></tr><tr><td valign="top">Mitigasi dan pemulihan</td><td valign="top">Isolasi, eradikasi, patch, reset kredensial, pemulihan sistem/data</td><td valign="top">Recovery report, validasi fungsi, evidence restore</td></tr><tr><td valign="top">Analisis artefak dan bukti forensik</td><td valign="top">Akuisisi bukti, preservasi log, analisis malware, image disk/memory</td><td valign="top">Chain of custody, forensic report</td></tr><tr><td valign="top">Dukungan manajemen krisis</td><td valign="top">Eskalasi ke manajemen, dukungan pengambilan keputusan, komunikasi risiko</td><td valign="top">Executive brief, situation report, board update</td></tr><tr><td valign="top">Manajemen kerentanan</td><td valign="top">Intake kerentanan, validasi, prioritas patch, koordinasi disclosure</td><td valign="top">Vulnerability case, remediation tracker</td></tr><tr><td valign="top">Situational awareness</td><td valign="top">Akuisisi dan korelasi threat intelligence, advisori, tren ancaman</td><td valign="top">Bulletin, IoC feed, threat brief</td></tr><tr><td valign="top">Knowledge transfer</td><td valign="top">Awareness, pelatihan, simulasi, tabletop exercise, lessons learned</td><td valign="top">Materi pelatihan, hasil simulasi, improvement plan</td></tr></tbody></table>

### 6.9 Dokumen Wajib TTIS

<table><thead><tr><th width="149.035400390625" valign="top">Dokumen</th><th valign="top">Substansi</th><th valign="top">Pemilik</th></tr></thead><tbody><tr><td valign="top">SK/Piagam TTIS</td><td valign="top">Mandat, ruang lingkup, struktur, kewenangan, tanggung jawab</td><td valign="top">Direksi/CISO</td></tr><tr><td valign="top">Profil RFC 2350</td><td valign="top">Nama tim, kontak, zona waktu, konstituen, layanan, kebijakan, metode pelaporan</td><td valign="top">TTIS Manager</td></tr><tr><td valign="top">Rencana Tanggap Insiden Siber</td><td valign="top">Tahapan, jenis insiden, peran, perangkat, proses pemulihan, kontak internal/eksternal</td><td valign="top">TTIS Manager/ BCM</td></tr><tr><td valign="top">Severity Matrix</td><td valign="top">Kriteria dampak layanan, data, transaksi, reputasi, hukum, dan regulator</td><td valign="top">Risk Management/ TTIS</td></tr><tr><td valign="top">Playbook Insiden</td><td valign="top">Prosedur per jenis insiden: ransomware, data breach, DDoS, cloud compromise, API abuse, fraud digital</td><td valign="top">TTIS/ SOC/ App Owner</td></tr><tr><td valign="top">Incident Report Form</td><td valign="top">Kontak pelapor, deskripsi, kronologi, dampak, aset terdampak, bukti awal</td><td valign="top">SOC/ Service Desk</td></tr><tr><td valign="top">Chain of Custody Form</td><td valign="top">Identitas bukti, waktu akuisisi, hash, penyimpan, perpindahan bukti</td><td valign="top">Forensic Lead</td></tr><tr><td valign="top">Communication Matrix</td><td valign="top">Pihak internal/eksternal, kanal, SLA, klasifikasi informasi</td><td valign="top">Corporate Communication/ Compliance</td></tr><tr><td valign="top">Post-Incident Review Template</td><td valign="top">Kronologi, root cause, dampak, efektivitas respons, tindakan perbaikan</td><td valign="top">Incident Commander</td></tr><tr><td valign="top">Action Tracker</td><td valign="top">Gap, action owner, target date, status, bukti penutupan</td><td valign="top">PMO/ Risk Management</td></tr></tbody></table>

### 6.10 Siklus Operasional Penanganan Insiden

Siklus di bawah ini menggabungkan ketentuan BSSN, prinsip improvement ISO/IEC 27035, NIST SP 800-61 Rev. 3, dan praktik CSIRT.

{% stepper %}
{% step %}
### Persiapan

Menjamin organisasi siap menangani insiden: membentuk TTIS, menyusun rencana tanggap, playbook, severity matrix, kontak eskalasi, akses log, pelatihan, dan simulasi.

**Output:** Dokumen Pengesahan TTIS, RFC 2350, playbook, daftar kontak, hasil simulasi.
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

### 6.11 Rekomendasi Klasifikasi Severity Insiden untuk Sektor Keuangan

Klasifikasi Severity Insiden dapat berupa Severity matrix yang disetujui oleh manajemen dan digunakan secara konsisten oleh unit terkait seperti SOC, TTIS, TI, bisnis, fraud, dan compliance. Rekomendasi Klasifikasi Severity Insiden untuk Industri di Sektor Keuangan dalam pedoman ini adalah sebagai berikut.

<table><thead><tr><th width="114.921630859375" valign="top">Severity</th><th valign="top">Kriteria Dampak</th><th valign="top">Contoh Insiden</th><th valign="top">Eskalasi Minimum</th></tr></thead><tbody><tr><td valign="top">Critical</td><td valign="top">Gangguan luas pada layanan kritikal; potensi dampak sistemik; data nasabah skala besar; ransomware aktif pada sistem kritikal; fraud masif; IIV terdampak</td><td valign="top">Core banking tidak dapat beroperasi, mobile banking nasional down akibat serangan, ransomware pada data center, compromise payment switch/API utama</td><td valign="top">Direksi, Incident Commander, BCM/DR, TTIS sektoral/ nasional sesuai ketentuan, Regulator sektor (BI/OJK) </td></tr><tr><td valign="top">High</td><td valign="top">Gangguan signifikan pada layanan penting; risiko tinggi terhadap data atau transaksi; kompromi akun privilese; insiden pada pihak ketiga kritikal</td><td valign="top">Credential stuffing dengan banyak akun terdampak, cloud key leak, DDoS pada kanal digital, kebocoran data terbatas tetapi sensitif</td><td valign="top">CISO, TTIS Manager, Legal/ Compliance, Fraud, Vendor Lead</td></tr><tr><td valign="top">Medium</td><td valign="top">Dampak terbatas pada unit/sistem non-kritikal; tidak ada bukti eksfiltrasi luas; pemulihan dapat dilakukan dengan kontrol standar</td><td valign="top">Malware pada endpoint terbatas, phishing pegawai, vulnerability exploited pada sistem pendukung</td><td valign="top">SOC Lead, App/ Infra Owner, Risk</td></tr><tr><td valign="top">Low</td><td valign="top">Peristiwa keamanan atau alert yang belum berdampak material; false positive terkendali; percobaan serangan tertahan</td><td valign="top">Port scanning, blocked malware, phishing gagal</td><td valign="top">SOC/ Service Desk</td></tr></tbody></table>

{% hint style="info" %}
**Rekomendasi:** gunakan severity berdasarkan kombinasi dampak pada _confidentiality_, _integrity_, _availability_, dampak transaksi, dampak nasabah, dampak reputasi, dampak hukum/regulator, serta potensi penyebaran ke entitas lain dalam sektor keuangan.
{% endhint %}

### 6.12 Pelaporan, Eskalasi, dan Koordinasi Eksternal

Pelaporan insiden siber harus dipahami sebagai bagian dari proses penanggulangan dan pemulihan, bukan sekadar pemenuhan administrasi regulasi. Dalam konteks sektor keuangan, satu insiden dapat menimbulkan kewajiban pelaporan kepada lebih dari satu pihak, seperti manajemen internal, regulator sektor, TTIS sektoral atau TTIS nasional, pihak terdampak, mitra ekosistem, dan publik. Oleh karena itu, organisasi perlu memiliki mekanisme pelaporan, eskalasi, dan koordinasi eksternal yang jelas, terdokumentasi, berbasis klasifikasi severity, serta selaras dengan ketentuan OJK, Bank Indonesia, BSSN, dan ketentuan pelindungan data pribadi yang berlaku.

Peraturan BSSN Nomor 1 Tahun 2024 tentang Pengelolaan Insiden Siber memuat pengaturan mengenai Tim Tanggap Insiden Siber, pelaporan insiden siber, penanganan insiden siber, dan pelaksanaan kesiapan terhadap insiden siber. Peraturan tersebut juga menegaskan bahwa insiden siber yang dilaporkan paling sedikit merupakan insiden yang mempunyai risiko tinggi.&#x20;

{% hint style="danger" %}
Dalam insiden siber sektor keuangan, keterlambatan pelaporan dapat memperbesar dampak operasional, reputasi, hukum, dan kepatuhan. Karena itu, organisasi perlu menerapkan prinsip _**single incident record, multiple regulatory outputs.**_ Satu sumber data insiden yang tervalidasi, tetapi dapat digunakan untuk memenuhi berbagai format, kanal, dan tenggat waktu pelaporan kepada otoritas yang berbeda.
{% endhint %}

#### Klasifikasi Jenis Pelaporan Insiden Siber

<table><thead><tr><th width="124.67242431640625" valign="top">Jenis Pelaporan</th><th valign="top">Tujuan</th><th valign="top">Substansi Minimum</th><th valign="top">Stakeholder Utama</th></tr></thead><tbody><tr><td valign="top"><strong>Pelaporan Internal</strong></td><td valign="top">Memberikan informasi cepat kepada manajemen, Direksi, Komite Risiko, Komite TI, Crisis Management Team, dan pemilik layanan agar keputusan taktis dan strategis dapat diambil.</td><td valign="top">Kronologi awal, sistem terdampak, severity, dampak layanan, dampak nasabah, tindakan containment, kebutuhan keputusan, risiko residual, dan status pemulihan.</td><td valign="top">Ketua TTIS/ Incident Commander, CISO atau fungsi keamanan siber.</td></tr><tr><td valign="top"><strong>Pelaporan kepada Regulator Sektor</strong></td><td valign="top">Memenuhi kewajiban pelaporan kepada OJK dan/atau Bank Indonesia sesuai jenis entitas, kegiatan usaha, dan ketentuan sektor.</td><td valign="top">Notifikasi awal, laporan insiden, kronologi, sistem/jaringan terdampak, jenis serangan, dampak, respons awal, rencana pemulihan, tindakan lanjutan, dan narahubung.</td><td valign="top">Compliance/ Regulatory Reporting dengan dukungan TTIS, Legal, Risk, dan pemilik layanan.</td></tr><tr><td valign="top"><strong>Pelaporan kepada TTIS Sektoral/ Nasional</strong></td><td valign="top">Mendukung koordinasi penanganan insiden, berbagi informasi teknis, mitigasi lintas organisasi/ sektor, dan pembelajaran kolektif.</td><td valign="top">Jenis indikasi insiden, sistem/ aset terdampak, indikator teknis yang relevan, rekomendasi mitigasi, kode distribusi informasi, dan hasil pembelajaran pascainsiden.</td><td valign="top">TTIS organisasi sebagai narahubung utama kepada TTIS sektoral / TTIS nasional.</td></tr><tr><td valign="top"><strong>Pelaporan kepada Pihak Terdampak</strong></td><td valign="top">Memberikan informasi kepada pihak yang terdampak langsung, seperti nasabah, peserta, pemegang polis, mitra, vendor, counterparties, atau subjek data pribadi.</td><td valign="top">Dampak yang diketahui, data atau layanan terdampak, tindakan yang telah dilakukan, langkah mitigasi yang perlu dilakukan pihak terdampak, kanal bantuan, dan pembaruan lanjutan.</td><td valign="top">Service Owner bersama Legal, PDP / DPO, Compliance, dan Komunikasi Publik.</td></tr><tr><td valign="top"><strong>Komunikasi Publik</strong></td><td valign="top">Menjaga kepercayaan publik, mengurangi spekulasi, memberikan pesan yang konsisten, dan memastikan komunikasi tidak mengganggu investigasi atau pemulihan.</td><td valign="top">Pernyataan resmi, status layanan, langkah yang dilakukan organisasi, imbauan kepada nasabah/publik, kanal informasi resmi, dan komitmen pemulihan.</td><td valign="top">Direksi/Crisis Management Team dengan Komunikasi Publik, Legal, Compliance, dan TTIS.</td></tr></tbody></table>

#### **Identifikasi Mekanisme Pelaporan kepada OJK**

Untuk industri bank umum, berdasarkan SEOJK 29/SEOJK.03/2022 mengatur bahwa bank menyampaikan informasi insiden siber kepada OJK berupa notifikasi awal dan laporan insiden siber. Notifikasi awal disampaikan paling lama 24 jam setelah insiden siber diketahui, sedangkan laporan insiden siber disampaikan secara daring melalui sistem pelaporan OJK paling lama 5 hari kerja setelah insiden diketahui. SEOJK tersebut juga mengatur prinsip penyelarasan apabila terdapat ketentuan otoritas lain: bila otoritas lain menetapkan jangka waktu lebih cepat, bank menyampaikan notifikasi/laporan kepada OJK pada saat yang bersamaan; bila otoritas lain lebih lama, bank mengikuti jangka waktu OJK.&#x20;

PADK OJK Nomor 1 Tahun 2026 memberikan ketentuan untuk bank umum, dimana bank harus membedakan pelaporan insiden TI nonsiber dan insiden siber; pelaporan insiden siber mengacu pada SEOJK. PADK tersebut juga menegaskan bahwa notifikasi awal insiden TI nonsiber disampaikan paling lama 24 jam setelah diketahui, dan laporan insiden TI disampaikan paling lama 5 hari kerja setelah diketahui.&#x20;

Untuk industri LJKNB, SEOJK 22/SEOJK.05/2021 tentang Penerapan Manajemen Risiko Dalam Penggunaan Teknologi Informasi Oleh Lembaga Jasa Keuangan Nonbank, mengatur pelaporan terkait tindakan tertentu, permohonan persetujuan pusat data/ pusat pemulihan bencana luar negeri, serta laporan kejadian kritis, penyalahgunaan, dan/atau kejahatan dalam penyelenggaraan TI berdasarkan POJK 4/POJK.05/2021.

Untuk industri ITSK, OJK menerbitkan POJK 3 Tahun 2024 dan ketentuan pelaporan lanjutannya; POJK tersebut mengatur penyelenggaraan ITSK, termasuk mekanisme pendaftaran dan pelaporan bagi peserta/penyelenggara ITSK.&#x20;

#### **Identifikasi Mekanisme Pelaporan kepada Bank Indonesia**

Untuk Penyelenggara Sistem Pembayaran, pelaku Pasar Uang dan Pasar Valuta Asing, serta pihak lain yang diatur dan diawasi Bank Indonesia, pelaporan KKS dan insiden siber perlu mengikuti PBI Nomor 2 Tahun 2024, PADG Nomor 24 Tahun 2024, serta petunjuk teknis pelaporan KKS eksternal Bank Indonesia. PBI 2/2024 diterbitkan sebagai pengaturan dan pengawasan KKS agar Penyelenggara mampu membangun KKS melalui kegiatan antisipatif, adaptif, dan proaktif terhadap risiko siber. PADG 24/2024 memperjelas pengaturan operasional penerapan KKS bagi Penyelenggara, termasuk upaya penguatan pengawasan dan kolaborasi dalam pencegahan serta penanganan insiden siber yang berdampak sistemik maupun nonsistemik bagi sistem keuangan. Petunjuk teknis pelaporan KKS eksternal BI mendefinisikan insiden siber sebagai serangan siber yang mengganggu kelancaran bisnis dan/atau layanan operasional Penyelenggara yang memerlukan respons dan/atau pemulihan.&#x20;

#### **Identifikasi Mekanisme Pelaporan kepada TTIS Sektoral dan TTIS Nasional**

Untuk entitas yang termasuk dalam cakupan IIV atau memiliki hubungan dengan mekanisme TTIS sektoral/nasional, pelaporan dan koordinasi insiden mengikuti Peraturan BSSN Nomor 1 Tahun 2024. Peraturan tersebut menempatkan TTIS dalam peran penting untuk menganalisis dan melaporkan insiden, memastikan insiden dikategorikan sesuai kriteria, dan memastikan insiden dilaporkan kepada pihak terkait.  Peraturan BSSN juga menekankan kegiatan isolasi dan mitigasi, pengumpulan dan pemeliharaan bukti, investigasi dan eradikasi penyebab, koordinasi eskalasi, pemulihan sistem/data, strategi komunikasi publik, serta penyampaian informasi penanggulangan dan pemulihan kepada pihak terkait.&#x20;

Peraturan BSSN Nomor 1 Tahun 2024 juga mengatur penyampaian informasi insiden kepada pihak terdampak, paling sedikit memuat jenis indikasi insiden, kode distribusi informasi, sistem dan/atau aset terdampak, serta rekomendasi mitigasi. Selain itu, hasil pembelajaran insiden disampaikan oleh TTIS organisasi kepada TTIS sektoral dengan tembusan kepada TTIS nasional; apabila TTIS sektoral belum terbentuk, hasil pembelajaran disampaikan kepada Kementerian/Lembaga sesuai sektornya dengan tembusan kepada TTIS nasional.&#x20;

#### **Pelaporan kepada Pihak Terdampak dan Komunikasi Publik**

Pelaporan kepada pihak terdampak perlu dibedakan dari komunikasi publik. Pelaporan kepada pihak terdampak ditujukan kepada pihak yang mengalami dampak langsung atau berpotensi terdampak, seperti nasabah, subjek data pribadi, mitra, atau counterparties. Apabila insiden menimbulkan kegagalan pelindungan data pribadi, UU Nomor 27 Tahun 2022 tentang Pelindungan Data Pribadi mewajibkan Pengendali Data Pribadi menyampaikan pemberitahuan tertulis paling lambat 3 x 24 jam kepada subjek data pribadi dan lembaga; pemberitahuan minimal memuat data pribadi yang terungkap, kapan dan bagaimana data pribadi terungkap, serta upaya penanganan dan pemulihan.&#x20;

Komunikasi publik dilakukan apabila insiden berdampak luas, menimbulkan gangguan layanan, menarik perhatian media, memunculkan risiko reputasi, atau terdapat kewajiban pemberitahuan kepada masyarakat. Pesan publik harus disusun secara hati-hati agar tidak mengungkap informasi teknis yang dapat dimanfaatkan pelaku serangan, tidak mengganggu investigasi, tidak bertentangan dengan laporan kepada regulator, dan tetap memberikan kepastian kepada nasabah atau masyarakat mengenai status layanan dan langkah mitigasi yang dilakukan organisasi.

#### **Strategi agar Industri Tetap Memenuhi Seluruh Pengaturan**&#x20;

Organisasi harus memiliki satu catatan utama insiden yang menjadi sumber kebenaran tunggal untuk seluruh kebutuhan pelaporan. Catatan utama ini memuat informasi inti seperti waktu insiden diketahui, kronologi, sistem dan layanan terdampak, jenis serangan atau indikasi insiden, dampak terhadap layanan/nasabah/data, tindakan penanganan, status pemulihan, bukti pendukung, narahubung, serta keputusan manajemen. Dari satu catatan utama tersebut, organisasi kemudian menyusun berbagai keluaran pelaporan sesuai kebutuhan masing-masing pihak, seperti laporan internal kepada Direksi, laporan kepada OJK, laporan kepada Bank Indonesia, laporan kepada BSSN/TTIS sektoral atau nasional, pemberitahuan kepada pihak terdampak, dan komunikasi publik.

> _**Single incident record, Multiple regulatory outputs**_

Pendekatan ini penting karena satu insiden siber di sektor keuangan dapat memicu beberapa kewajiban pelaporan sekaligus, dengan format, terminologi, kanal, dan batas waktu yang berbeda. Dengan menggunakan satu sumber data insiden yang tervalidasi, organisasi dapat menjaga konsistensi informasi antar laporan, mengurangi risiko perbedaan kronologi atau angka dampak, mempercepat penyusunan laporan, serta memastikan setiap pelaporan tetap dapat ditelusuri ke bukti yang sama. Dengan demikian, perbedaan antar laporan terletak pada format dan kebutuhan informasi regulator, bukan pada substansi dasar insidennya.

{% hint style="info" %}
**Contoh penerapan.** Insiden kebocoran data pada layanan mobile banking dicatat dalam satu _incident master record_. Dari catatan yang sama, fungsi TTIS menyusun laporan teknis, fungsi kepatuhan menyusun laporan kepada regulator sektor, fungsi PDP menyiapkan pemberitahuan kepada subjek data pribadi, dan komunikasi publik menyiapkan pernyataan kepada pihak terdampak dan masyarakat. Seluruh keluaran tersebut menggunakan fakta inti yang sama, tetapi disesuaikan dengan format, sensitivitas informasi, dan ketentuan masing-masing penerima laporan.
{% endhint %}

Berikut adalah tabel rekomendasi Strategi agar Industri Tetap Memenuhi Seluruh Pengaturan dalm hal pelaporan keamanan siber.

<table><thead><tr><th width="156.127685546875" valign="top">Strategi</th><th valign="top">Penjelasan</th><th valign="top">Rekomendasi Output Strategi</th></tr></thead><tbody><tr><td valign="top"><strong>Regulatory reporting inventory</strong></td><td valign="top">Organisasi harus memetakan seluruh kewajiban pelaporan insiden berdasarkan status entitas, izin usaha, regulator pengawas, status IIV, jenis layanan, dan jenis data yang diproses.</td><td valign="top">Daftar kewajiban pelaporan kepada OJK, BI, BSSN/TTIS, otoritas PDP, mitra, dan pihak terdampak.</td></tr><tr><td valign="top"><strong>Single incident record</strong></td><td valign="top">Semua laporan harus bersumber dari satu catatan insiden yang tervalidasi, berisi kronologi, waktu diketahui, sistem terdampak, dampak, tindakan, bukti, PIC, dan status pemulihan.</td><td valign="top">Satu repository sumber informasi untuk menghindari perbedaan data antar laporan internal, OJK, BI, BSSN, dan publik.</td></tr><tr><td valign="top"><strong>Fastest-deadline rule</strong></td><td valign="top">Apabila satu insiden wajib dilaporkan kepada beberapa otoritas dengan tenggat berbeda, organisasi menggunakan tenggat paling cepat sebagai dasar eskalasi internal dan persiapan laporan.</td><td valign="top">Kalender pelaporan insiden yang memastikan tidak ada tenggat regulator terlewat.</td></tr><tr><td valign="top"><strong>Multi-regulator notification protocol</strong></td><td valign="top">Protokol ini mengatur kapan laporan disampaikan secara paralel kepada lebih dari satu otoritas, siapa pejabat pengotorisasi, dan bagaimana konsistensi informasi dijaga.</td><td valign="top">Matriks pelaporan lintas regulator dan approval flow untuk insiden mayor/kritis.</td></tr><tr><td valign="top"><strong>Severity matrix terintegrasi</strong></td><td valign="top">Klasifikasi severity internal perlu dipetakan dengan kriteria pelaporan OJK, BI, BSSN, PDP, dan persyaratan kontrak pihak ketiga.</td><td valign="top">Severity matrix yang menunjukkan trigger pelaporan, penerima laporan, tenggat waktu, dan level persetujuan.</td></tr><tr><td valign="top"><strong>Template  &#x26; Format laporan</strong> </td><td valign="top">Organisasi perlu menyiapkan template notifikasi awal, laporan lanjutan, laporan regulator, laporan TTIS, pemberitahuan pihak terdampak, dan holding statement publik.</td><td valign="top">Template siap pakai yang mempercepat pelaporan pada jam-jam awal insiden.</td></tr><tr><td valign="top"><strong>Legal, compliance, dan PDP review gate</strong></td><td valign="top">Setiap laporan eksternal dan komunikasi publik perlu melalui reviu hukum, kepatuhan, dan pelindungan data pribadi tanpa menghambat tenggat pelaporan.</td><td valign="top">Checklist legal/ compliance untuk memastikan laporan akurat, proporsional, dan tidak membuka risiko hukum baru.</td></tr><tr><td valign="top"><strong>Kode distribusi informasi</strong></td><td valign="top">Informasi teknis insiden harus diberi klasifikasi distribusi agar hanya dibagikan kepada pihak yang berwenang dan membutuhkan.</td><td valign="top">Label distribusi informasi, misalnya TLP/ kode distribusi internal, untuk IOC, artefak forensik, dan informasi sensitif.</td></tr><tr><td valign="top"><strong>Vendor and ecosystem reporting clause</strong></td><td valign="top">Kontrak vendor dan mitra kritikal harus mengatur kewajiban notifikasi insiden, akses log, dukungan forensik, SLA eskalasi, kerahasiaan, dan koordinasi pelaporan.</td><td valign="top">Klausul kontrak dan joint incident response procedure dengan vendor kritikal.</td></tr><tr><td valign="top"><strong>Simulasi dan tabletop exercise</strong></td><td valign="top">Organisasi perlu menguji skenario pelaporan lintas otoritas, komunikasi publik, kebocoran data, gangguan layanan, dan insiden yang melibatkan vendor.</td><td valign="top">Hasil simulasi, lesson learned, pembaruan playbook, dan penguatan kesiapan tim.</td></tr></tbody></table>

#### Rekomendasi Alur Eskalasi

Dalam alur eskalasi, waktu “**insiden diketahui**” harus dicatat secara jelas karena menjadi titik awal perhitungan tenggat pelaporan pada beberapa ketentuan. Catatan waktu minimal mencakup waktu alert pertama, waktu validasi sebagai insiden, waktu eskalasi ke TTIS, waktu keputusan severity, waktu notifikasi internal, waktu notifikasi regulator, dan waktu pemulihan layanan. Pencatatan menjadi aktivitas yang penting untuk membuktikan kepatuhan terhadap tenggat pelaporan serta membantu evaluasi efektivitas respons. berikut adalah rekomendasi stepping umum yang dapat dijabarkan dan disesuaikan kembali sesuai dengan kondisi dan pengaturan masing-masing organisasi.

{% stepper %}
{% step %}
**Deteksi / Laporan Awal**
{% endstep %}

{% step %}
**Triage SOC/TTIS**
{% endstep %}

{% step %}
**Klasifikasi Severity**
{% endstep %}

{% step %}
**Aktivasi Incident Commander**
{% endstep %}

{% step %}
**Eskalasi Manajemen**
{% endstep %}

{% step %}
**Penentuan Kewajiban Pelaporan**&#x20;
{% endstep %}

{% step %}
**Notifikasi Awal kepada Otoritas Terkait**
{% endstep %}

{% step %}
**Penanganan dan Pemulihan**
{% endstep %}

{% step %}
**Laporan Lanjutan / Laporan Final**
{% endstep %}

{% step %}
**Komunikasi Pihak Terdampak / Publik**&#x20;
{% endstep %}

{% step %}
**Post-Incident Review & Pembelajaran**
{% endstep %}

{% step %}
**Pembaruan Kontrol dan Playbook**
{% endstep %}
{% endstepper %}

{% hint style="info" %}
Pelaporan insiden siber sektor keuangan harus dikelola sebagai proses lintas fungsi. TTIS menyediakan fakta teknis dan koordinasi respons; compliance memastikan kewajiban regulator terpenuhi; legal dan PDP menjaga kepatuhan hukum; service owner menjelaskan dampak layanan; dan komunikasi publik menjaga pesan kepada pihak terdampak dan publik. Dengan mekanisme yang terintegrasi, organisasi dapat tetap cepat dalam merespons insiden sekaligus patuh terhadap berbagai ketentuan OJK, BI, BSSN, dan pelindungan data pribadi
{% endhint %}

### 6.13 Playbook untuk Industri Sektor Keuangan

Tim Tanggap Insiden Siber (TTIS) perlu memiliki playbook penanganan insiden yang terdokumentasi, diuji, dan diperbarui secara berkala. Playbook berfungsi sebagai panduan operasional agar organisasi dapat merespons insiden secara cepat, terkoordinasi, dan konsisten, terutama pada saat kondisi tekanan tinggi ketika keputusan teknis, bisnis, hukum, kepatuhan, dan komunikasi harus dilakukan dalam waktu terbatas. Dalam konteks sektor keuangan, playbook tidak hanya berisi langkah teknis penanganan insiden, tetapi juga harus mengatur eskalasi internal, pelaporan kepada regulator, koordinasi dengan pihak ketiga, pemberitahuan kepada pihak terdampak, pemulihan layanan kritikal, serta pembelajaran pascainsiden.

Playbook minimum perlu disusun berdasarkan profil risiko organisasi, jenis layanan keuangan yang diselenggarakan, kritikalitas sistem, data yang diproses, model operasional TI, serta ketergantungan terhadap pihak ketiga. Setiap playbook harus memiliki ruang lingkup, kriteria aktivasi, klasifikasi severity, langkah penanganan, kebutuhan bukti, peran dan tanggung jawab, batas waktu eskalasi, indikator pemulihan, serta mekanisme reviu setelah insiden. Dengan demikian, playbook menjadi alat praktis untuk meningkatkan kapabilitas organisasi pada domain **Deteksi**, **Penanggulangan**, dan **Pemulihan**.

{% hint style="success" %}
Playbook yang baik bukan hanya menjawab **“apa yang harus dilakukan secara teknis”**, tetapi juga menjawab **“siapa yang mengambil keputusan”**, **“kapan regulator diberi tahu”**, **“bagaimana layanan dipulihkan”**, **“bagaimana nasabah/pihak terdampak dikomunikasikan”**, dan “**bagaimana organisasi memastikan insiden yang sama tidak terulang”**
{% endhint %}

Setiap playbook TTIS perlu memenuhi beberapa prinsip dasar. Pertama, playbook harus **berbasis skenario yang relevan dengan sektor keuangan,** seperti ransomware, DDoS, kebocoran data, penyalahgunaan kredensial, fraud digital, gangguan sistem pembayaran, dan insiden pihak ketiga. Kedua, playbook harus **terhubung dengan severity matrix** agar organisasi mengetahui kapan insiden dikategorikan minor, major, critical, atau crisis. Ketiga, playbook harus **memiliki pembagian peran yang jelas** antara TTIS, SOC, TI, pemilik layanan, risk, compliance, legal, PDP/DPO, komunikasi korporat, vendor, dan manajemen krisis. Keempat, playbook harus **mengatur bukti yang harus dikumpulkan dan dipelihara**, termasuk log, artefak forensik, tiket insiden, konfigurasi, kronologi, dan keputusan manajemen. Kelima, playbook harus **diuji melalui tabletop exercise, technical drill, atau simulation exercise,** kemudian diperbarui berdasarkan hasil pembelajaran.

Berikut adalah daftar topic playbook yang direkomendasikan dan relevansinya terhadap industri di sektor keuangan

<table><thead><tr><th valign="top">Topic Playbook</th><th valign="top">Skenario yang Dicakup</th><th valign="top">Fokus Respons</th><th valign="top">Subsektor yang Paling Relevan</th></tr></thead><tbody><tr><td valign="top"><strong>Ransomware dan Destructive Malware</strong></td><td valign="top">Enkripsi sistem, penyebaran malware, penghapusan data, gangguan endpoint/server, dan ancaman pemerasan data.</td><td valign="top">Isolasi host, penghentian lateral movement, validasi backup, eradikasi malware, pemulihan sistem, forensik, dan komunikasi krisis.</td><td valign="top">Seluruh sektor, terutama bank, BPR/BPRS, PSP, asuransi, pembiayaan, dan pasar modal.</td></tr><tr><td valign="top"><strong>DDoS dan Gangguan Ketersediaan Layanan Digital</strong></td><td valign="top">Serangan volume, application-layer DDoS, gangguan mobile/internet banking, portal nasabah, API publik, dan kanal transaksi.</td><td valign="top">Aktivasi mitigasi DDoS, koordinasi ISP/cloud/CDN, pengalihan trafik, prioritas layanan kritikal, komunikasi status layanan, dan monitoring stabilitas.</td><td valign="top">Bank umum, PSP/PJP/PIP, ITSK, agregator, aset kripto, pasar modal, dan layanan digital LJKNB.</td></tr><tr><td valign="top"><strong>Kebocoran Data dan Kegagalan Pelindungan Data Pribadi</strong></td><td valign="top">Eksfiltrasi data nasabah, akses tidak sah ke database, publikasi data di dark web, salah konfigurasi cloud/storage, dan kebocoran oleh pihak ketiga.</td><td valign="top">Identifikasi data terdampak, containment akses, forensik, penilaian dampak PDP, pemberitahuan pihak terdampak, pelaporan regulator, dan remediasi kontrol data.</td><td valign="top">Seluruh sektor, terutama entitas dengan data nasabah/peserta besar, agregator, ITSK, asuransi, dana pensiun, dan aset kripto.</td></tr><tr><td valign="top"><strong>Kompromi Kredensial, Account Takeover, dan Privileged Access Abuse</strong></td><td valign="top">Pencurian kredensial, penyalahgunaan akun admin, takeover akun nasabah, akses remote tidak sah, dan compromise token/session.</td><td valign="top">Reset kredensial, revoke session/token, review privileged access, MFA enforcement, analisis log akses, deteksi transaksi abnormal, dan pemulihan akun.</td><td valign="top">Bank, PSP, ITSK, agregator, aset kripto, pembiayaan digital, dan pasar modal online.</td></tr><tr><td valign="top"><strong>Anomali Transaksi, Fraud Digital, dan Abuse pada Kanal Pembayaran</strong></td><td valign="top">Transaksi tidak sah, manipulasi payment logic, abuse API, anomali QRIS/transfer, mismatch debit-credit, dan fraud berbasis kanal digital.</td><td valign="top">Korelasi cyber-fraud, penghentian transaksi mencurigakan, isolasi modul, rekonsiliasi, koordinasi fraud team, pelaporan regulator, dan perbaikan kontrol transaksi.</td><td valign="top">Bank, PSP/PJP/PIP, penyelenggara pembayaran, fintech, agregator, dan aset kripto.</td></tr><tr><td valign="top"><strong>Kompromi Aplikasi, API, dan Kanal Digital</strong></td><td valign="top">Eksploitasi web/mobile/API, bypass otorisasi, injection, broken access control, credential stuffing, dan penyalahgunaan endpoint API.</td><td valign="top">Disable endpoint rentan, apply hotfix/WAF rule, rotate key/token, analisis request log, security testing ulang, dan validasi business logic.</td><td valign="top">Bank digital, mobile banking, PSP, ITSK, agregator, aset kripto, pasar modal online, dan pembiayaan digital.</td></tr><tr><td valign="top"><strong>Phishing, Business Email Compromise, dan Social Engineering</strong></td><td valign="top">Email penipuan, impersonasi eksekutif/vendor, phishing nasabah, penyalahgunaan domain, dan instruksi transaksi palsu.</td><td valign="top">Takedown domain, blokir IOC, reset akun, edukasi pengguna/nasabah, verifikasi transaksi, koordinasi legal, dan preservasi bukti komunikasi.</td><td valign="top">Seluruh sektor, terutama bank, pembiayaan, asuransi, dana pensiun, dan entitas dengan transaksi email-based approval.</td></tr><tr><td valign="top"><strong>Insiden Pihak Ketiga, Cloud, Data Center, dan Supply Chain</strong></td><td valign="top">Gangguan vendor kritikal, breach pada penyedia layanan, compromise update software, cloud misconfiguration, dan kegagalan data center/DRC.</td><td valign="top">Aktivasi joint incident response, permintaan log/bukti, evaluasi SLA, failover/DR, assessment dampak, komunikasi regulator, dan exit/contingency plan.</td><td valign="top">Seluruh sektor, terutama organisasi yang bergantung pada vendor core system, cloud, managed service, payment gateway, dan data center.</td></tr><tr><td valign="top"><strong>Insider Threat dan Penyalahgunaan Akses Internal</strong></td><td valign="top">Eksfiltrasi data oleh pegawai, penyalahgunaan akses privileged, manipulasi data/transaksi, sabotase, dan pelanggaran kebijakan internal.</td><td valign="top">Preservasi bukti, pembatasan akses, investigasi bersama HR/legal, analisis log, kontrol kompensasi, dan tindakan disipliner/hukum sesuai prosedur.</td><td valign="top">Seluruh sektor, terutama entitas dengan akses data/transaksi bernilai tinggi.</td></tr><tr><td valign="top"><strong>Gangguan Sistem Kritikal dan Pemulihan Bencana Siber</strong></td><td valign="top">Gangguan core system, switching, settlement, database, jaringan utama, layanan digital, backup failure, dan kegagalan pemulihan pascainsiden.</td><td valign="top">Aktivasi BCP/DRP, prioritas pemulihan layanan, failover, restore, validasi integritas data, rekonsiliasi transaksi, dan komunikasi status layanan.</td><td valign="top">Bank, BPR/BPRS, PSP, pasar uang/valas, pasar modal, asuransi, pembiayaan, dan dana pensiun.</td></tr></tbody></table>

#### Pengujian dan Pemutakhiran Playbook

Playbook TTIS perlu diuji dan diperbarui secara berkala agar tetap relevan terhadap perubahan ancaman, perubahan arsitektur, perubahan layanan digital, perubahan vendor, serta hasil pembelajaran dari insiden dan simulasi. Pengujian tidak harus selalu berbentuk simulasi besar. Organisasi dapat menggunakan beberapa pendekatan bertahap, mulai dari desk review, walkthrough, tabletop exercise, technical drill, hingga full simulation exercise yang melibatkan fungsi bisnis, TI, risiko, kepatuhan, hukum, komunikasi, vendor, dan manajemen krisis.

<table><thead><tr><th width="145.6785888671875" valign="top">Jenis Pengujian</th><th width="250.635498046875" valign="top">Tujuan</th><th valign="top">Frekuensi yang Disarankan</th></tr></thead><tbody><tr><td valign="top"><strong>Desk Review</strong></td><td valign="top">Memastikan playbook masih sesuai dengan struktur organisasi, kontak, sistem, vendor, dan ketentuan pelaporan terbaru.</td><td valign="top">Minimal semesteran atau setiap ada perubahan signifikan.</td></tr><tr><td valign="top"><strong>Walkthrough</strong></td><td valign="top">Menguji pemahaman tim terhadap alur penanganan, peran, eskalasi, dan bukti yang harus dikumpulkan.</td><td valign="top">Minimal tahunan untuk setiap playbook prioritas.</td></tr><tr><td valign="top"><strong>Tabletop Exercise</strong></td><td valign="top">Menguji koordinasi lintas fungsi dan pengambilan keputusan dalam skenario insiden tertentu.</td><td valign="top">Minimal tahunan, lebih sering untuk layanan kritikal.</td></tr><tr><td valign="top"><strong>Technical Drill</strong></td><td valign="top">Menguji kemampuan teknis seperti isolasi host, restore backup, failover, blokir IOC, rotasi kredensial, atau mitigasi DDoS.</td><td valign="top">Minimal tahunan atau sesuai risiko teknologi.</td></tr><tr><td valign="top"><strong>Full Simulation Exercise</strong></td><td valign="top">Menguji end-to-end response, mulai dari deteksi, eskalasi, penanganan, pemulihan, pelaporan, hingga komunikasi publik.</td><td valign="top">Untuk layanan sangat kritikal, minimal satu kali dalam siklus tahunan atau sesuai profil risiko.</td></tr></tbody></table>

Playbook harus diperbarui apabila terdapat perubahan signifikan yang memengaruhi cara organisasi mendeteksi, menangani, melaporkan, atau memulihkan insiden. Trigger pemutakhiran playbook dapat dipicu oleh hal-hal berikut.

* hasil post-incident review atau lesson learned dari insiden nyata;
* hasil tabletop exercise, technical drill, atau simulasi yang menunjukkan kelemahan prosedur;
* perubahan struktur organisasi, narahubung, RACI matriks, atau decision authority;
* peluncuran layanan digital baru, integrasi API baru, atau perubahan arsitektur besar;
* migrasi cloud, data center, core system, atau penyedia layanan kritikal;
* perubahan kewajiban pelaporan dari OJK, BI, BSSN, atau otoritas lain;
* perubahan kontrak, SLA, atau model dukungan vendor kritikal;
* munculnya ancaman baru, modus fraud baru, atau teknik serangan yang relevan dengan sektor keuangan.

{% hint style="success" %}
Playbook TTIS adalah jembatan antara prosedur dan aksi nyata. Bagi industri sektor keuangan, playbook minimum perlu mencakup skenario yang paling mungkin menimbulkan gangguan layanan, kerugian nasabah, kebocoran data, kewajiban pelaporan, dan dampak reputasi. Playbook yang diuji dan diperbarui berkala dapat membantu organisasi mempercepat respons, memperkuat pemulihan, dan meningkatkan level kematangan & ketahanan siber organisasi.
{% endhint %}

### 6.14 Pengelolaan Bukti Digital ketika Terjadi Insiden

Pengelolaan bukti digital merupakan aspek penting dalam penanganan insiden siber karena bukti yang dikumpulkan selama proses deteksi, analisis, penanggulangan, dan pemulihan dapat digunakan untuk berbagai kebutuhan organisasi. Bukti digital tidak hanya diperlukan untuk kepentingan investigasi teknis, tetapi juga menjadi dasar dalam proses audit, pembelajaran pascainsiden, klaim asuransi siber, pelaporan kepada regulator, pembuktian kepada pihak terdampak, serta kemungkinan proses hukum apabila insiden melibatkan unsur pelanggaran, penyalahgunaan, kejahatan, atau sengketa dengan pihak ketiga. Oleh karena itu, setiap bukti digital harus diperlakukan secara hati-hati, terdokumentasi, terlindungi integritasnya, dan dapat ditelusuri sejak pertama kali ditemukan hingga digunakan dalam proses analisis, pelaporan, atau pembuktian.

Pada sektor keuangan, perlakuan bukti digital menjadi semakin penting karena insiden siber dapat berkaitan dengan transaksi keuangan, data nasabah, sistem pembayaran, hak akses khusus, aplikasi kritikal, layanan pihak ketiga, serta kewajiban pelaporan kepada otoritas. Bukti seperti log sistem, log aplikasi, rekaman aktivitas jaringan, artefak malware, konfigurasi sistem, tiket insiden, hasil forensik, riwayat perubahan, bukti komunikasi, dan data transaksi harus dikelola dengan prinsip _chain of custody_. Prinsip ini memastikan bahwa setiap perpindahan, akses, pemeriksaan, penggandaan, penyimpanan, dan penggunaan bukti tercatat secara lengkap sehingga keaslian, integritas, dan kredibilitas bukti tetap terjaga.

{% hint style="warning" %}
Bukti digital yang tidak dikelola dengan baik dapat kehilangan nilai pembuktiannya, menimbulkan keraguan dalam audit atau investigasi, serta melemahkan posisi organisasi dalam proses pelaporan kepada regulator, klaim asuransi, maupun proses hukum lanjutan. Karena itu, TTIS perlu memiliki prosedur pengumpulan, pelabelan, penyimpanan, akses, pemeliharaan, dan dokumentasi bukti digital yang baku dan diuji secara berkala.
{% endhint %}

Berikut adalah tabel kelompok dan contoh bukti digital yang umum ada pada insiden di sektor keuang, serta perlakuan minimum yang perlu diperhatikan organisasi. Perlakuan mininum seperti akuisisi barang bukti digital membutuhkan keterampilan dan keahlian khusus, sehingga organisasi perlu mengalokasikan resources untuk SDM nya agar dapat dilatih dan/atau disertifikasi, sehingga bukti digital dapat dijamin keabsahanya sejak awal.

<table><thead><tr><th width="151.84539794921875" valign="top">Bukti</th><th valign="top">Contoh</th><th valign="top">Perlakuan Minimum</th></tr></thead><tbody><tr><td valign="top">Log keamanan</td><td valign="top">SIEM, EDR, NDR, WAF, firewall, IAM, VPN, email gateway</td><td valign="top">Ekspor dengan timestamp, hash, penyimpanan aman, akses terbatas</td></tr><tr><td valign="top">Bukti sistem</td><td valign="top">Disk image, memory dump, snapshot VM/cloud, konfigurasi</td><td valign="top">Akuisisi forensik, dokumentasi alat, hash, chain of custody</td></tr><tr><td valign="top">Bukti aplikasi</td><td valign="top">Application log, API gateway log, database audit trail</td><td valign="top">Preservasi sebelum rotasi log, korelasi dengan user/session</td></tr><tr><td valign="top">Bukti transaksi</td><td valign="top">Payment logs, transaction journal, fraud case, settlement file</td><td valign="top">Rekonsiliasi, legal hold, perlindungan data nasabah</td></tr><tr><td valign="top">Bukti komunikasi</td><td valign="top">Email phishing, tiket, chat war room, instruksi vendor</td><td valign="top">Arsipkan sesuai klasifikasi dan kebijakan retensi</td></tr><tr><td valign="top">Bukti pihak ketiga</td><td valign="top">Vendor report, cloud audit log, CDN/DDoS report</td><td valign="top">Validasi integritas, kaitkan dengan SLA/kontrak</td></tr></tbody></table>

{% hint style="danger" %}
**Basic Rules:** jangan melakukan perubahan pada sistem terdampak sebelum bukti kritikal diamankan, kecuali tindakan segera yang diperlukan untuk mencegah dampak yang lebih besar. Setiap tindakan darurat harus dicatat dalam timeline insiden.
{% endhint %}

### 6.15 Komunikasi Insiden dan Kode Distribusi Informasi

Informasi insiden siber sering kali sensitif karena dapat berisi celah keamanan, IoC, data nasabah, taktik penyerang, dan kelemahan kontrol. TTIS perlu menetapkan klasifikasi distribusi informasi. Secara praktis, organisasi dapat mengadopsi TLP 2.0 untuk melengkapi kode distribusi informasi yang diwajibkan dalam ketentuan nasional.

<table><thead><tr><th width="188.74505615234375">Label</th><th>Penggunaan Praktis</th></tr></thead><tbody><tr><td><mark style="color:red;"><strong>TLP:RED</strong></mark></td><td>Hanya untuk penerima tertentu di war room/komite krisis. Contoh: detail kunci privat bocor, bukti data nasabah, strategi negosiasi krisis.</td></tr><tr><td><mark style="color:$warning;background-color:orange;"><strong>TLP:AMBER+STRICT</strong></mark></td><td>Boleh dibagikan secara need-to-know hanya dalam organisasi. Contoh: detail teknis insiden, sistem rentan, akun privilese terdampak.</td></tr><tr><td><mark style="color:orange;"><strong>TLP:AMBER</strong></mark></td><td>Boleh dibagikan need-to-know dalam organisasi dan pihak yang perlu membantu seperti vendor/mitra terikat NDA.</td></tr><tr><td><mark style="color:green;"><strong>TLP:GREEN</strong></mark></td><td>Boleh dibagikan dalam komunitas tepercaya untuk pencegahan, misalnya IoC tanpa data sensitif.</td></tr><tr><td><strong>TLP:CLEAR</strong></td><td>Dapat dipublikasikan, misalnya advisory umum tanpa detail eksploitasi sensitif.</td></tr></tbody></table>

### 6.16 Capaian Terukur TTIS

Capaian terukur TTIS diperlukan untuk memastikan bahwa fungsi penanggulangan dan pemulihan insiden tidak hanya tersedia secara formal, tetapi benar-benar berjalan efektif, dapat diuji, dan memberikan kontribusi nyata terhadap peningkatan ketahanan siber organisasi. Pengukuran capaian TTIS perlu mencakup aspek tata kelola, kesiapan personel, kecepatan deteksi dan eskalasi, efektivitas penanganan, kemampuan pemulihan, kualitas pelaporan, pengelolaan bukti digital, koordinasi pihak ketiga, serta pembelajaran pascainsiden.

Pada sektor keuangan, indikator capaian TTIS harus dikaitkan dengan perlindungan layanan kritikal, transaksi keuangan, data nasabah, kewajiban pelaporan regulator, serta keberlangsungan operasional. Oleh karena itu, ukuran keberhasilan TTIS tidak hanya dilihat dari jumlah insiden yang ditangani, tetapi juga dari seberapa cepat insiden terdeteksi, seberapa akurat klasifikasinya, seberapa cepat layanan dipulihkan, seberapa lengkap bukti dikumpulkan, dan seberapa efektif organisasi mencegah insiden serupa berulang kembali.

#### **Rekomendasi Capaian KPI TTIS**

<table><thead><tr><th width="163.49609375" valign="top">Indikator</th><th valign="top">Definisi</th><th valign="top">Arah Target</th></tr></thead><tbody><tr><td valign="top"><strong>MTTD - Mean Time to Detect</strong></td><td valign="top">Rata-rata waktu dari awal indikasi insiden sampai insiden terdeteksi atau tervalidasi.</td><td valign="top">Semakin pendek semakin baik.</td></tr><tr><td valign="top"><strong>MTTA - Mean Time to Acknowledge</strong></td><td valign="top">Rata-rata waktu dari alert diterima sampai alert diakui dan mulai ditangani oleh tim yang berwenang.</td><td valign="top">Semakin pendek semakin baik.</td></tr><tr><td valign="top"><strong>MTTC - Mean Time to Contain</strong></td><td valign="top">Rata-rata waktu dari insiden tervalidasi sampai dampak berhasil diisolasi atau dikendalikan.</td><td valign="top">Semakin pendek semakin baik.</td></tr><tr><td valign="top"><strong>MTTR - Mean Time to Recover/Resolve</strong></td><td valign="top">Rata-rata waktu sampai layanan pulih atau insiden dinyatakan selesai secara operasional.</td><td valign="top">Harus selaras dengan RTO/RPO dan prioritas layanan kritikal.</td></tr><tr><td valign="top"><strong>Persentase insiden sesuai SLA eskalasi</strong></td><td valign="top">Proporsi insiden yang dieskalasikan sesuai batas waktu severity matrix.</td><td valign="top">Semakin tinggi semakin baik.</td></tr><tr><td valign="top"><strong>Persentase laporan regulator tepat waktu</strong></td><td valign="top">Proporsi laporan/notifikasi insiden yang disampaikan sesuai batas waktu regulator.</td><td valign="top">Target ideal 100%.</td></tr><tr><td valign="top"><strong>Persentase playbook yang diuji</strong></td><td valign="top">Proporsi playbook prioritas yang telah diuji melalui walkthrough, tabletop, drill, atau simulasi.</td><td valign="top">Meningkat secara bertahap sesuai prioritas risiko.</td></tr><tr><td valign="top"><strong>Persentase remediasi pascainsiden yang closed</strong></td><td valign="top">Proporsi action item dari post-incident review yang selesai sesuai target waktu.</td><td valign="top">Semakin tinggi semakin baik.</td></tr><tr><td valign="top"><strong>Jumlah insiden berulang</strong></td><td valign="top">Jumlah insiden dengan pola, akar masalah, atau kontrol gagal yang sama dalam periode tertentu.</td><td valign="top">Semakin rendah semakin baik.</td></tr><tr><td valign="top"><strong>Rasio false positive alert kritikal</strong></td><td valign="top">Proporsi alert kritikal yang setelah triage tidak terbukti sebagai insiden atau peristiwa relevan.</td><td valign="top">Dikendalikan agar SOC/TTIS tidak mengalami alert fatigue.</td></tr></tbody></table>

{% hint style="success" %}
TTIS yang efektif harus dapat diukur. Indikator seperti MTTD, MTTC, MTTR, ketepatan pelaporan regulator, keberhasilan pemulihan, kualitas bukti digital, dan penyelesaian remediasi pascainsiden membantu organisasi menilai apakah kapabilitas penanggulangan dan pemulihan benar-benar meningkat dari waktu ke waktu.
{% endhint %}

***

