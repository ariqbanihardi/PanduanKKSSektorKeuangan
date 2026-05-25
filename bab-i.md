---
description: >-
  Bab penjelasan umum terkait dokumen panduan Ketahanan dan Keamanan Siber (KKS)
  untuk Sektor Keuangan di Indonesia
---

# Bab I

## Pendahuluan

Penyusunan dokumen Panduan Ketahanan dan Keamanan Siber (KKS) untuk Sektor Keuangan di Indonesia menggunakan pendekatan kerangka regulasi yang ada khususnya di Sektor Keuangan Indonesia sehingga dapat menjadi panduan organisasi dalam meningkatkan keamanan dan ketahanan siber organisasi secara terukur.

Aspek dasar yang dibahas dalam dokumen ini terkait dengan penguatan aspek _people_, _process_, dan _technology_ dengan domain standar dari **Instrumen Penilaian Kematangan Keamanan Siber (IKAS)** yaitu Identifikasi, Deteksi, Proteksi, Penanggulangan dan Pemulihan. Target ideal dalam pemanfaatan panduan ini adalah peningkatan KKS organisasi untuk mencapai nilai/level ideal IKAS untuk keseluruhan domain.

KKS · IKAS · Sektor Keuangan

{% hint style="warning" %}
**Disclaimer**

Dokumen panduan ini tidak menggantikan ketentuan regulator dan perlu disesuaikan dengan jenis lembaga, klasifikasi sistem elektronik dan status IIV, ketentuan pengatur dan pengawas sektor keuangan OJK/BI yang berlaku saat ini, serta kebijakan internal masing-masing organisasi.
{% endhint %}

***

## Ringkasan Eksekutif

{% hint style="info" icon="briefcase" %}
Panduan ini membantu organisasi di sektor keuangan Indonesia untuk dapat menerapkan, menilai, dan meningkatkan **Ketahanan dan Keamanan Siber (KKS)** secara terstruktur dengan menggunakan **IKAS (Instrumen Penilaian Kematangan Keamanan Siber)** sebagai baseline pengukuran kematangan, kemudian memperkaya interpretasinya dengan konteks industri sektor keuangan yang ada di Indonesia seperti perbankan, BPR/BPRS, penyelenggara sistem pembayaran, pasar uang dan valuta asing, pembiayaan, asuransi, dana pensiun, penjaminan, pasar modal, agregator jasa keuangan, dan inovasi teknologi sektor keuangan. Pesan utama yang ingin disampaikan melalui dokumen ini adalah

<p align="center"><mark style="color:red;"><strong>"Penguatan KKS di sektor keuangan tidak cukup berhenti pada pemenuhan dokumen kepatuhan saja, tetapi harus dibuktikan dengan resiliensi yang teruji"</strong></mark></p>

Hasil penilaian kematangan keamanan siber perlu diubah menjadi _risk-based roadmap_ yang menjadi referensi untuk membantu mengurangi risiko gangguan layanan kritikal, kebocoran data nasabah, fraud digital, gangguan sistem pembayaran, gangguan layanan digital, serta risiko pihak ketiga yang ada pada organisasi. Panduan ini juga menambahkan Bab khusus terkait Tim Tanggap Insiden Siber (TTIS) sebagai tim atau unit resmi organisasi yang bertugas mencegah, mengelola, dan menanggulangi gangguan serta serangan keamanan siber dari organisasi. TTIS Organisasi yang terdaftar resmi terhubung dengan ekosistem TTIS sesuai dengan pengaturan, dan menjadi bagian dari upaya pemerintah dalam meningkatkan ketahanan dan keamanan siber secara nasional.

Panduan ini tidak dimaksudkan untuk menggantikan ketentuan regulator sektor atau otoritas yang berwenang. Panduan ini berfungsi sebagai acuan penyelarasan agar organisasi sektor keuangan dapat menerapkan pengukuran, pelaporan & kepatuhan, peningkatan kematangan, dan pengelolaan insiden siber secara konsisten, proporsional, dan berbasis risiko.
{% endhint %}

***

## 1.1 Tujuan Utama

Panduan KKS untuk Sektor Keuangan di Indonesia memiliki beberapa tujuan utama, yaitu:

1. Memberikan acuan praktis bagi lembaga sektor keuangan di Indonesia dalam melakukan penilaian kematangan KKS secara mandiri.
2. Menyelaraskan pendekatan IKAS dengan konteks operasional sektor keuangan yang memiliki ketergantungan tinggi pada layanan yang terdigitalisasi, pengelolaan data nasabah, ekosistem sistem pembayaran, dan pihak ketiga.
3. Menjadikan hasil penilaian sebagai dasar penyusunan rencana aksi, prioritas investasi keamanan, perbaikan kontrol, dan pelaporan kepada manajemen/regulator sesuai kewajiban yang diamanatkan dalam pengaturan.
4. Mendorong perubahan orientasi dari sekadar kepatuhan dokumen menuju ketahanan operasional, kemampuan identifikasi, deteksi, proteksi, respons, pemulihan, hingga pembelajaran pasca-insiden.

## 1.2 Ruang Lingkup Entitas Pengguna Panduan

Panduan KKS untuk Sektor Keuangan di Indonesia dapat digunakan oleh berbagai pelaku industri di sektor keuangan seperti:

* Bank umum konvensional dan syariah.
* Bank Perekonomian Rakyat dan Bank Perekonomian Rakyat Syariah.
* Penyelenggara jasa pembayaran, penyelenggara infrastruktur pembayaran, peserta infrastruktur pembayaran, dan penyelenggara penunjang.
* Pelaku pasar uang dan pasar valuta asing yang menggunakan sistem elektronik kritikal.
* Lembaga jasa keuangan non-bank, termasuk pembiayaan, modal ventura, asuransi, reasuransi, penjaminan, dana pensiun, dan lembaga keuangan mikro.
* Penyelenggara inovasi teknologi sektor keuangan, aset keuangan digital, agregator jasa keuangan, dan entitas lain yang memproses data/layanan keuangan digital.
* Penyelenggara penunjang seperti Pihak ketiga kritikal yang menyediakan data center, cloud, core system, switching, payment gateway, managed SOC, aplikasi digital, jaringan komunikasi, atau layanan TI lainnya.

## 1.3 Ruang Lingkup Sistem dan Layanan Kritikal

Penilaian KKS di sektor keuangan perlu mendefinisikan cakupan sistem elektronik dan proses bisnis kritikal yang berdampak pada kerahasiaan, integritas, ketersediaan, keaslian, akuntabilitas, dan keandalan layanan. Beberapa lingkup Sistem dan Layanan Kritikal di sektor keuangan yang dapat diidentifikasi antara lain:

* Core banking/core insurance/core financing.
* Mobile banking, internet banking, super-app, digital onboarding, dan kanal layanan nasabah.
* ATM, CRM, EDC/POS, QRIS, payment gateway, host-to-host system, switching, BI-FAST, RTGS/SKNBI, kartu, dan kanal pembayaran lain.
* Treasury, pasar uang, pasar valas, trading, settlement, custody, dan sistem rekonsiliasi.
* Data warehouse, data lake, customer analytics, fraud monitoring, AML/CFT supporting systems.
* API/open finance, integrasi dengan fintech, merchant, aggregator, cloud, dan pihak ketiga.
* DRC, backup platform, SOC/SIEM, IAM/PAM, vulnerability management, dan sistem keamanan pendukung lainnya.

## 1.4 Prinsip Pemanfaatan Panduan

{% hint style="success" %}
**Prinsip dasar:** Dasar penilaian yang baik adalah pembuktian. Angka yang diberikan tanpa bukti tidak akan mencerminkan kapabilitas keamanan yang sebenarnya.
{% endhint %}

1. _**Risk-based**_ - prioritas kontrol mengikuti kritikalitas sistem dan nilai dampak risikonya, data yang disimpan dan diproses, dan eksposur ancaman.
2. _**Evidence-based**_ - setiap indeks nilai harus didukung dengan bukti seperti dokumen, laporan, notulen, hasil audit, log, konfigurasi, atau bukti teknis terkait lainnya.
3. _**Proportionate**_ - penerapan kontrol mempertimbangkan skala, kompleksitas, model bisnis, dan keterhubungan antar sistem.
4. _**End-to-end resilience**_ - penilaian tidak hanya melihat pencegahan, tetapi juga kemampuan pada aspek deteksi, respons dan pemulihan, serta pembelajaran.
5. _**Third-party aware**_ - ketahanan lembaga keuangan juga bergantung pada ketahanan pihak ketiga, vendor, penyedia cloud, jaringan, data center, dan mitra ekosistem.
6. _**Continuous improvement**_ - hasil penilaian harus diterjemahkan menjadi rencana aksi, pemantauan, review, dan perbaikan berkala.

## 1.5 Cara Menggunakan Panduan

Panduan ini digunakan secara bertahap agar hasil pengukuran KKS dapat diterjemahkan menjadi keputusan manajemen dan peningkatan kapabilitas yang nyata. Secara umum, tahapan penggunaan panduan ini bagi organisasi adalah sebagai berikut.

{% stepper %}
{% step %}
Organisasi perlu melakukan **Pemetaan ruang lingkup,** memahami ruang lingkup entitas, sistem, layanan kritikal, data, dan pihak ketiga yang menjadi objek penilaian. Penentuan ini akan membantu organisasi untuk menentukan layanan, sistem, data, unit, lokasi, dan pihak ketiga kritikal.&#x20;
{% endstep %}

{% step %}
Organisasi melakukan **Pemetaan regulasi** untuk memetakan kewajiban regulasi yang harus dipenuhi, mengidentifikasi kewajiban BSSN, OJK, BI, dan otoritas lain sesuai subsektor, dan menempatkan IKAS sebagai instrumen pengukuran kematangan yang berbasis bukti.
{% endstep %}

{% step %}
Organisasi melakukan **Penilaian IKAS** secara mandiri berbasis bukti untuk menentukan gap prioritas. Kemudian menyusun laporan internal, dan menyiapkan pelaporan kepada regulator atau otoritas sesuai ketentuan.&#x20;
{% endstep %}

{% step %}
Organisasi menyusun **Peta Jalan Peningkatan /** **Roadmap KKS** berdasarkan kesenjangan kematangan, profil risiko, dan prioritas layanan kritikal. Fokus Roadmap adalah mengubah gap menjadi rencana aksi berbasis risiko.
{% endstep %}

{% step %}
Organisasi **Memperkuat TTIS** sebagai fungsi operasional untuk mendeteksi, menangani, memulihkan, melaporkan, dan mengambil pembelajaran dari insiden siber. Fokus penguatan TTIS untuk membangun kapabilitas respons insiden dan koordinasi eksternal.
{% endstep %}
{% endstepper %}

## Ringkasan Implikasi bagi Industri Sektor Keuangan

<table><thead><tr><th width="173.998291015625" valign="top">Area</th><th valign="top">Implikasi Praktis</th></tr></thead><tbody><tr><td valign="top"><strong>Tata kelola</strong></td><td valign="top">Direksi dan komite terkait perlu menjadikan hasil KKS sebagai dasar pengambilan keputusan risiko, investasi keamanan, dan prioritas transformasi digital.</td></tr><tr><td valign="top"><strong>Kepatuhan</strong></td><td valign="top">Organisasi perlu menyelaraskan kewajiban kepada BSSN, OJK, BI, dan otoritas lain sesuai izin usaha, status IIV, dan karakteristik layanan.</td></tr><tr><td valign="top"><strong>Operasional</strong></td><td valign="top">Unit TI, keamanan siber, risiko, kepatuhan, legal, pelindungan data pribadi, komunikasi, dan TTIS perlu bekerja lintas fungsi.</td></tr><tr><td valign="top"><strong>Ketahanan</strong></td><td valign="top">Penilaian IKAS harus menghasilkan rencana peningkatan yang dapat diuji melalui simulasi, audit, pemulihan, dan pembelajaran pascainsiden.</td></tr></tbody></table>

***
