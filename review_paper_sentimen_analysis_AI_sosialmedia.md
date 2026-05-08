# Review Paper: Validitas AI dalam Sentiment Analysis Media Sosial
## Tantangan Noise, Bot, dan Buzzer terhadap Relevansi Analisis Sentimen Publik

---

> **Disusun oleh:** Haryanto, Mahasiswa S2 Magister Teknik Informatika, UNPAM  
> **Mata Kuliah:** Advanced Intelligent System (AIS)  
> **Tujuan:** Bahan kajian literatur untuk analisis kebijakan publik berbasis AI  
> **Versi:** 1.0 | 8 Mei 2026

---

## Daftar Isi

1. [Abstrak](#abstrak)
2. [Pendahuluan](#pendahuluan)
3. [Paper Kajian Utama](#paper-kajian-utama)
4. [Temuan Kritis dari Literatur](#temuan-kritis-dari-literatur)
5. [Analisis Sintesis: Validitas di Tengah Gangguan](#analisis-sintesis)
6. [Implikasi untuk Analis Kebijakan Publik](#implikasi-kebijakan)
7. [Rekomendasi Framework Penggunaan AI](#rekomendasi-framework)
8. [Kesimpulan](#kesimpulan)
9. [Daftar Referensi](#referensi)

---

## 1. Abstrak <a name="abstrak"></a>

Review ini disusun atas pertanyaan dalam benak dan hasil diskusi dengan dosen, Bpk. Dr. Arya, "apakah penggunaan AI dalam Sentiment Analysis terutama di sosial media masih relevan di tengah maraknya buzzer?". Sentiment analysis berbasis kecerdasan buatan (AI) dari data media sosial telah berkembang pesat sebagai metode pengukuran opini publik. Namun demikian, pertanyaan mendasar terus mengemuka: apakah sentimen yang diukur AI dari media sosial benar-benar mencerminkan opini publik yang autentik, ataukah sekadar artefak dari noise digital, akun bot, dan operasi buzzer yang terkoordinasi? Review paper ini mengkaji tiga kelompok literatur ilmiah bereputasi tinggi (Q1/Q2) yang secara langsung mengangkat persoalan ini: (1) validasi makroskopi sentimen media sosial terhadap survei nyata, (2) dampak bot/buzzer terhadap distorsi sentimen, dan (3) evaluasi perbandingan metode AI untuk analisis sentimen kebijakan publik. Temuan menunjukkan bahwa AI untuk sentiment analysis *tetap relevan* jika diterapkan dengan metodologi yang tepat, namun memerlukan lapisan validasi, deteksi bot, dan triangulasi lintas sumber. Review ini memberikan rekomendasi praktis bagi calon fungsional analis kebijakan yang ingin memanfaatkan AI sebagai alat bantu pengukuran sentimen publik.

**Kata kunci:** Sentiment Analysis, AI, Media Sosial, Bot, Buzzer, Validitas, Kebijakan Publik, NLP, LLM

---

## 2. Pendahuluan <a name="pendahuluan"></a>

### 2.1 Latar Belakang

Media sosial telah menjadi ruang utama ekspresi opini publik. Setiap hari, ratusan juta pengguna meninggalkan jejak digital berupa cuitan, komentar, dan unggahan yang mengandung sentimen terhadap beragam isu — termasuk kebijakan pemerintah. Bagi para analis kebijakan publik, kemampuan membaca sentimen ini secara real-time dan masif merupakan peluang yang sangat besar, yang sebelumnya tidak tersedia melalui metode survei konvensional.

Perkembangan metode Natural Language Processing (NLP) berbasis deep learning — mulai dari VADER, BERT, RoBERTa, hingga Large Language Models (LLM) seperti GPT dan Llama — semakin memperkuat kemampuan AI dalam mengklasifikasikan teks bermuatan emosi secara otomatis. Namun, validitas output AI ini menghadapi tantangan serius yang tidak bisa diabaikan:

**Tantangan utama yang perlu dikritisi:**

- **Noise data** — Slang, sarkasme, kode budaya lokal, dan bahasa campuran (code-switching) sering salah ditafsirkan oleh model AI.
- **Bot dan akun otomatis** — Akun-akun non-manusia ini dapat menghasilkan volume posting yang besar dan mendistorsi distribusi sentimen.
- **Buzzer terkoordinasi (Astroturfing)** — Operasi terkoordinasi untuk menyimulasikan gerakan akar rumput yang palsu, sangat relevan dalam konteks politik Indonesia.
- **Sampling bias** — Pengguna media sosial tidak representatif untuk seluruh populasi. Kelompok diam (silent majority) tidak terekam.
- **Platform effect** — Norma komunitas dan algoritma platform membentuk cara orang mengekspresikan diri, bukan sekadar cermin opini alami.

### 2.2 Pernyataan Masalah

Apakah AI untuk sentiment analysis dari media sosial masih relevan sebagai alat ukur sentimen publik, khususnya untuk keperluan analisis kebijakan, mengingat keberadaan bot, buzzer, dan noise yang sistematis?

### 2.3 Tujuan Review

Review ini bertujuan untuk:
1. Mengidentifikasi paper-paper berkualitas tinggi yang mengangkat validitas AI sentiment analysis.
2. Mensintesis temuan-temuan kunci dari literatur tersebut.
3. Memberikan rekomendasi praktis bagi analis kebijakan yang ingin menggunakan AI.

---

## 3. Paper Kajian Utama <a name="paper-kajian-utama"></a>

### 📄 Paper 1 (Q1 — Nature / Scientific Reports)

**Judul:** *Validating Daily Social Media Macroscopes of Emotions*

| Atribut | Detail |
|---|---|
| **Penulis** | Max Pellert, Hannah Metzler, Michael Matzenberger, David Garcia |
| **Jurnal** | Scientific Reports (Nature Portfolio) |
| **Kuartil** | **Q1** (Scopus & WoS) |
| **Tahun** | 2022 |
| **DOI** | [10.1038/s41598-022-14579-y](https://doi.org/10.1038/s41598-022-14579-y) |
| **Link** | https://www.nature.com/articles/s41598-022-14579-y |

**Latar Belakang Penelitian:**
Paper ini merupakan salah satu upaya validasi paling sistematis terhadap penggunaan sentimen media sosial sebagai cerminan emosi publik. Para peneliti dari Medical University of Vienna dan Complexity Science Hub Vienna bertanya: apakah agregat sentimen media sosial benar-benar berkorelasi dengan laporan mood nyata dari manusia?

**Metodologi:**
Peneliti melakukan survei skala besar di platform berita online Austria (*Der Standard*), mengumpulkan self-report suasana hati harian dari penggunanya, kemudian membandingkannya dengan hasil agregasi sentiment analysis dari diskusi pengguna di platform yang sama. Studi ini direplikasi menggunakan data Twitter.

**Temuan Kritis:**
- Terdapat **korelasi kuat** antara hasil text analysis dengan tingkat mood yang dilaporkan sendiri (self-reported mood).
- Korelasi juga ditemukan pada perubahan antar-hari (*inter-day changes*) dari kedua pengukuran.
- Kombinasi metode **supervised deep learning + unsupervised dictionary-based** memberikan kesepakatan tertinggi dengan data survei.
- Noise pada level individual memang ada, namun **ketika diagregasi** dari ribuan posting per hari, sinyal sentimen menjadi valid dan kuat.

**Kutipan Penting:**
> *"Aggregates of social media text analysis can serve as macroscopes which combine measurements that may be noisy at the level of individuals or posts, but, when aggregated across thousands of posts per day, can provide a valid signal."* — Pellert et al. (2022)

**Ancaman Validitas yang Diakui:**
- Measurement error pada tools sentiment analysis
- Perilaku performatif pengguna (orang berperilaku berbeda di media sosial vs kenyataan)
- Sampling bias (pengguna yang membuat konten vs. pengguna diam)

---

### 📄 Paper 2 (Q1 — Nature / Scientific Reports)

**Judul:** *Social Bots Spoil Activist Sentiment Without Eroding Engagement*

| Atribut | Detail |
|---|---|
| **Penulis** | Linda Li, Orsolya Vásárhelyi, Balázs Vedres |
| **Afiliasi** | LSE, Oxford Internet Institute, CEU Democracy Institute |
| **Jurnal** | Scientific Reports (Nature Portfolio) |
| **Kuartil** | **Q1** (Scopus & WoS) |
| **Tahun** | 2024 |
| **DOI** | [10.1038/s41598-024-74032-0](https://doi.org/10.1038/s41598-024-74032-0) |
| **Link** | https://www.nature.com/articles/s41598-024-74032-0 |

**Latar Belakang Penelitian:**
Paper ini secara langsung mengukur **dampak kausal** interaksi bot terhadap sentimen manusia nyata. Studi ini menganalisis gerakan protes Extinction Rebellion tahun 2019 di Twitter, sebuah kasus empiris yang kaya karena melibatkan protes nyata (human signal) yang dicampuri oleh bot.

**Metodologi:**
Menggunakan pendekatan *matched comparison* — membandingkan riwayat komunikasi pengguna yang berinteraksi dengan bot versus pengguna yang tidak berinteraksi dengan bot (matched users). Pendekatan ini memungkinkan estimasi dampak kausal.

**Temuan Kritis:**
- Bot **sangat aktif** di media sosial dan secara signifikan mempengaruhi wacana online.
- Terdapat **dampak negatif yang konsisten** dari pertemuan dengan bot terhadap sentimen selanjutnya dari pengguna manusia.
- Dampak paling kuat terjadi pada pengguna dengan **stance yang awalnya mendukung atau netral** — artinya bot paling efektif mengubah sentimen kelompok yang belum memiliki pendirian kuat.
- Bot **astroturfing** (jenis bot untuk mensimulasikan gerakan akar rumput palsu) justru memicu **peningkatan komunikasi** manusia, sementara jenis bot lain justru menekan keterlibatan.
- Meskipun dampak per-interaksi terlihat kecil, **efek kumulatif sangat besar** karena volume komunikasi bot yang masif.

**Implikasi Kritis:**
Bot tidak hanya menambah noise pada data sentimen — mereka secara aktif **mengubah** sentimen manusia nyata. Ini berarti dampak bot berlapis dua: (1) data sentimen yang terukur terdistorsi oleh posting bot, dan (2) sentimen manusia nyata pun ikut berubah akibat paparan bot.

---

### 📄 Paper 3 (Q2 — JMIR Formative Research)

**Judul:** *Public Health Discussions on Social Media: Evaluating Automated Sentiment Analysis Methods*

| Atribut | Detail |
|---|---|
| **Penulis** | Lisa M. Gandy, Lana V. Ivanitskaya, Leeza L. Bacon, Rodina Bizri-Baryak |
| **Jurnal** | JMIR Formative Research |
| **Kuartil** | **Q2** (Scopus) |
| **Tahun** | 2025 |
| **DOI** | [10.2196/57395](https://doi.org/10.2196/57395) |
| **Link** | https://formative.jmir.org/2025/1/e57395 |

**Latar Belakang Penelitian:**
Paper ini melakukan evaluasi **komparatif** terhadap berbagai metode automated sentiment analysis yang populer — VADER, LIWC-22, dan ChatGPT 4.0 — untuk menilai performa masing-masing dalam konteks diskusi kesehatan publik di media sosial (data YouTube).

**Metodologi:**
Mengevaluasi performa tools berdasarkan metrik: accuracy, specificity, precision, sensitivity, F1-score, dan Matthews Correlation Coefficient (MCC). Dataset yang digunakan adalah komentar YouTube terkait diskusi opioid.

**Temuan Kritis:**
- **Tidak ada model tunggal yang superior** dalam semua metrik — setiap metode memiliki keunggulan dan kelemahan spesifik.
- F1-score untuk NLP tools berkisar antara 0.34–0.38, dan sangat rendah (0.13) untuk ChatGPT 4.0.
- **ChatGPT 4.0** menunjukkan performa mengecewakan — F1-score lebih rendah dari tools tradisional untuk dataset yang tidak seimbang (imbalanced).
- **VADER** direkomendasikan untuk dataset yang tidak memerlukan biaya (cost-free), dengan performa diskriminasi terbaik — dan semakin baik ketika komentar memiliki minimal 100 karakter.
- **LIWC-22** direkomendasikan untuk estimasi prevalensi komentar negatif.
- Dataset yang tidak seimbang (lebih banyak sentimen tertentu) menjadi tantangan signifikan bagi semua model.

**Relevansi untuk Kebijakan:**
Dalam konteks kebijakan publik, di mana data media sosial sangat tidak seimbang (satu isu dapat memiliki dominasi sentimen negatif atau positif yang ekstrem), temuan ini sangat relevan. Pilihan metode harus disesuaikan dengan karakteristik data dan tujuan analisis.

---

### 📄 Paper 4 (Q1 — Systematic Review, Frontiers in Public Health)

**Judul:** *Sentiment Analysis in Public Health: A Systematic Review of the Current State, Challenges, and Future Directions*

| Atribut | Detail |
|---|---|
| **Penulis** | Ismael Villanueva-Miranda, Yang Xie, Guanghua Xiao |
| **Afiliasi** | University of Texas Southwestern Medical Center |
| **Jurnal** | Frontiers in Public Health |
| **Kuartil** | **Q1** (Scopus) |
| **Tahun** | 2025 |
| **DOI** | [10.3389/fpubh.2025.1609749](https://doi.org/10.3389/fpubh.2025.1609749) |

**Latar Belakang:**
Systematic review ini merangkum studi sentiment analysis dalam domain kesehatan publik yang diterbitkan antara 2020–2025, memberikan gambaran komprehensif tentang praktik, tantangan, dan arah ke depan.

**Temuan Kritis:**
- Platform media sosial (terutama Twitter/X) menghadirkan tantangan serius terkait **kualitas data, noise, representativitas,** dan kekhawatiran etis.
- Penerapan AI untuk analisis sentimen yang andal dan etis memerlukan: **validasi yang ketat, interpretabilitas model yang lebih baik, dan framework etika yang jelas**.
- LLM menunjukkan potensi besar tetapi juga membawa risiko baru dalam hal bias dan interpretabilitas.

---

## 4. Temuan Kritis dari Literatur <a name="temuan-kritis-dari-literatur"></a>

### 4.1 Relevansi AI Sentiment Analysis: Masih Valid, Tapi Bersyarat

Berdasarkan sintesis dari keempat paper di atas, dapat disimpulkan bahwa AI untuk sentiment analysis dari media sosial **masih relevan**, namun keberlanjutannya sangat bergantung pada pemenuhan sejumlah syarat metodologis.

**Argumen PRO relevansi:**
- Pellert et al. (2022) membuktikan bahwa agregat sentimen media sosial berkorelasi kuat dengan self-reported mood masyarakat dalam survei tradisional.
- Ketika data diagregasi dalam volume besar (ribuan posting per hari), noise individual teredam dan sinyal sentimen makro menjadi valid.
- Metode AI modern (BERT-based, LLM) telah melampaui metode lexicon konvensional dalam menangkap nuansa bahasa.

**Argumen KONTRA atau peringatan:**
- Li et al. (2024) menunjukkan bahwa bot secara aktif mendistorsi sentimen — tidak hanya menambah noise, tetapi mengubah sentimen manusia nyata.
- Gandy et al. (2025) membuktikan bahwa tidak ada model AI tunggal yang sempurna; bahkan LLM mutakhir seperti GPT-4 dapat berkinerja buruk pada dataset yang tidak seimbang.
- Sampling bias tetap menjadi masalah fundamental: pengguna media sosial tidak merepresentasikan populasi umum.

### 4.2 Anatomi Gangguan: Bot vs. Buzzer vs. Noise Alami

Penting untuk membedakan jenis gangguan yang berbeda-beda:

| Jenis Gangguan | Karakteristik | Dampak pada Sentimen | Solusi |
|---|---|---|---|
| **Noise Alami** | Sarkasme, slang, kode budaya | Salah klasifikasi individual | Model kontekstual (BERT, LLM) |
| **Bot Spam** | Volume tinggi, konten repetitif | Distorsi distribusi sentimen | Bot detection tools (Botometer, dll.) |
| **Bot Astroturfing** | Menyamar sebagai manusia, terkoordinasi | Mempengaruhi sentimen manusia nyata | Graph analysis, behavioral fingerprinting |
| **Buzzer Manusia** | Manusia nyata, dibayar, terkoordinasi | Paling sulit dideteksi | Network analysis, koordinasi pola waktu |

### 4.3 Fenomena Buzzer Indonesia: Tantangan Tambahan

Dalam konteks Indonesia, tantangan *buzzer* memiliki dimensi unik yang belum banyak dikaji dalam literatur global:

- **Buzzer manusia** (bukan bot) lebih sulit dideteksi karena akun-akunnya memiliki perilaku yang tidak bisa dibedakan dari pengguna organik biasa.
- Platform seperti Twitter/X dan Facebook digunakan secara intensif untuk membentuk narasi kebijakan, terutama menjelang pemilu atau saat kebijakan kontroversial diluncurkan.
- Bahasa campuran Indonesia (Bahasa Indonesia, Jawa, Sunda, slang internet) membuat model NLP generik performanya menurun.

### 4.4 LLM vs. Model Tradisional: Mana yang Lebih Baik?

Salah satu pertanyaan praktis yang krusial bagi analis kebijakan adalah: apakah menggunakan LLM (GPT, Claude) lebih baik daripada model tradisional seperti VADER atau IndoBERT?

Berdasarkan literatur:

- **LLM** unggul dalam menangkap nuansa, sarkasme, dan konteks — terutama dalam teks yang panjang dan kaya konteks.
- **LLM** berkinerja buruk pada dataset tidak seimbang dan data pendek/informal (Gandy et al., 2025).
- **VADER** tetap relevan untuk analisis cepat, terutama jika teks cukup panjang (>100 karakter).
- **BERT/IndoBERT** adalah pilihan terbaik untuk Bahasa Indonesia karena telah di-*pretrain* pada korpus bahasa tersebut.
- Kombinasi metode (ensemble) menghasilkan performa lebih baik dan lebih robust.

---

## 5. Analisis Sintesis: Validitas di Tengah Gangguan <a name="analisis-sintesis"></a>

### 5.1 Model Konseptual Validitas Berlapis

Berdasarkan kajian literatur, penulis mengusulkan model konseptual **"Validitas Berlapis"** untuk memahami di mana dan bagaimana validitas AI sentiment analysis dapat dipertahankan:

```
LEVEL VALIDITAS SENTIMEN AI MEDIA SOSIAL

┌─────────────────────────────────────────────────────────────┐
│  LAYER 1: Validitas Lingustik                               │
│  → Apakah model AI memahami bahasa dengan benar?           │
│  → Tantangan: Sarkasme, slang, code-switching               │
│  → Solusi: Model kontekstual (IndoBERT, LLM fine-tuned)     │
├─────────────────────────────────────────────────────────────┤
│  LAYER 2: Validitas Data                                    │
│  → Apakah data bersih dari akun non-organik?               │
│  → Tantangan: Bot, buzzer, spam accounts                    │
│  → Solusi: Bot detection, network analysis, pre-filtering   │
├─────────────────────────────────────────────────────────────┤
│  LAYER 3: Validitas Representasi                            │
│  → Apakah data merepresentasikan populasi target?          │
│  → Tantangan: Sampling bias, digital divide                 │
│  → Solusi: Triangulasi dengan survei, weighting            │
├─────────────────────────────────────────────────────────────┤
│  LAYER 4: Validitas Interpretasi                            │
│  → Apakah sentimen online = sentimen nyata?                │
│  → Tantangan: Platform effects, performativity              │
│  → Solusi: Mixed-methods, expert validation                 │
└─────────────────────────────────────────────────────────────┘
```

### 5.2 Kondisi di Mana Sentimen AI Tetap Valid

Berdasarkan temuan Pellert et al. (2022), sentimen media sosial yang dianalisis AI memiliki validitas yang baik **ketika:**

1. **Volume data besar** — minimal ribuan posting per hari per topik.
2. **Analisis dilakukan di level agregat** — bukan per-individu.
3. **Konteks diskursif homogen** — komunitas dengan norma bahasa yang relatif konsisten.
4. **Jendela waktu pendek** — perubahan sentimen jangka pendek (harian) lebih akurat dari tren jangka panjang yang bisa dipengaruhi perubahan demografis pengguna.

### 5.3 Kondisi di Mana Validitas Melemah

Validitas melemah secara signifikan ketika:

1. **Isu sangat politis** — astroturfing dan buzzer lebih intensif.
2. **Topik baru atau viral** — data tidak seimbang, model belum terlatih untuk konteks spesifik.
3. **Bahasa lokal/daerah** — model generik gagal menangkap nuansa.
4. **Kampanye koordinasi** — pola distribusi posting tidak organik.

---

## 6. Implikasi untuk Analis Kebijakan Publik <a name="implikasi-kebijakan"></a>

### 6.1 Positioning AI sebagai Alat Bantu, Bukan Pengganti

Literatur secara konsisten menunjukkan bahwa AI sentiment analysis **paling efektif digunakan sebagai:**

- **Sistem peringatan dini (early warning)** — mendeteksi pergeseran sentimen publik sebelum krisis komunikasi kebijakan terjadi.
- **Pemantauan tren jangka pendek** — tracking sentimen harian/mingguan terhadap kebijakan yang sedang berjalan.
- **Complementary tool** — melengkapi survei konvensional, bukan menggantikannya.

**Yang tidak boleh dilakukan:**
- Mengklaim bahwa "87% publik mendukung kebijakan X" berdasarkan sentiment analysis media sosial tanpa validasi lebih lanjut.
- Mengabaikan lapisan bot filtering sebelum analisis.
- Menggunakan model AI generik untuk analisis bahasa Indonesia tanpa fine-tuning.

### 6.2 Studi Kasus Relevan: Analisis Kebijakan

**Contoh Kasus Aplikasi di Indonesia:**

| Skenario Kebijakan | Pertanyaan Analisis | Metode Direkomendasikan |
|---|---|---|
| Kenaikan BBM | Bagaimana tren sentimen 7 hari pasca pengumuman? | IndoBERT + bot filter + time-series |
| Kebijakan UMP baru | Kelompok mana yang paling banyak bereaksi negatif? | ABSA (Aspect-Based) + network analysis |
| RUU kontroversial | Apakah ada koordinasi posting yang terdeteksi? | Bot detection + koordinasi temporal |
| Kebijakan sosial baru | Perbandingan sentimen urban vs. rural? | Geo-tagged analysis + demographic proxy |

### 6.3 Framework Kerja untuk Analis Kebijakan Berbasis AI

Berikut adalah langkah-langkah yang direkomendasikan untuk analis kebijakan yang menggunakan AI sentiment analysis:

```
ALUR KERJA ANALISIS SENTIMEN KEBIJAKAN

1. PENGUMPULAN DATA
   └─ Tentukan platform (Twitter/X, Facebook, TikTok, berita online)
   └─ Tentukan kata kunci + hashtag relevan
   └─ Tentukan jendela waktu analisis

2. PRE-PROCESSING & FILTERING
   └─ Bersihkan duplikat, spam, dan konten tidak relevan
   └─ Deteksi dan isolasi akun bot (gunakan Botometer atau similar)
   └─ Tandai akun dengan pola koordinasi mencurigakan

3. ANALISIS SENTIMEN
   └─ Gunakan model yang sesuai bahasa (IndoBERT untuk Bahasa Indonesia)
   └─ Pertimbangkan ensemble method (gabungan beberapa model)
   └─ Lakukan analisis aspek (ABSA) untuk sentimen yang lebih granular

4. VALIDASI
   └─ Bandingkan dengan survei atau polling konvensional jika tersedia
   └─ Lakukan human annotation pada sampel acak (spot check)
   └─ Periksa koherensi dengan laporan media mainstream

5. INTERPRETASI & KONTEKSTUALISASI
   └─ Pertimbangkan konteks politik/sosial saat analisis
   └─ Identifikasi kemungkinan operasi buzzer
   └─ Sajikan sebagai sinyal, bukan kebenaran tunggal

6. PELAPORAN
   └─ Cantumkan limitasi metodologi secara eksplisit
   └─ Sertakan confidence interval atau margin of uncertainty
   └─ Rekomendasikan tindak lanjut triangulasi
```

---

## 7. Rekomendasi Framework Penggunaan AI <a name="rekomendasi-framework"></a>

### 7.1 Stack Teknologi yang Direkomendasikan

Berdasarkan kajian literatur dan kebutuhan konteks Indonesia:

```python
# Contoh Stack untuk Analisis Kebijakan Indonesia

# 1. Pengumpulan Data
- Twitter API v2 / Scraping (Snscrape, Apify)
- Facebook Graph API
- Portal berita online scraper

# 2. Bot Detection
- Botometer API (untuk Twitter)
- Analisis pola temporal posting
- Network centrality analysis (Gephi, NetworkX)

# 3. Preprocessing NLP Bahasa Indonesia
- Sastrawi (stemming Bahasa Indonesia)
- PySastrawi + NLTK kombinasi
- Hapus stopwords bahasa Indonesia

# 4. Model Sentiment Analysis
- IndoBERT (fine-tuned untuk Bahasa Indonesia)
- IndoBERTweet (khusus untuk teks Twitter berbahasa Indonesia)
- VADER (untuk analisis cepat + teks >100 karakter)
- Ensemble: IndoBERT + VADER untuk robustness

# 5. Validasi & Visualisasi
- Manual annotation (10-15% sampel)
- Cohen's Kappa untuk inter-rater reliability
- Dashboard dengan Streamlit / Tableau
```

### 7.2 Tools Spesifik untuk Konteks Indonesia

| Kebutuhan | Tool Rekomendasi | Alasan |
|---|---|---|
| Sentiment Analysis BI | IndoBERT / IndoBERTweet | Pre-trained pada korpus Indonesia |
| Bot Detection | Botometer + custom rules | Efektif untuk Twitter/X |
| Topik Modeling | LDA / BERTopic | Menemukan tema dominan |
| Network Analysis | Gephi / NetworkX | Deteksi koordinasi buzzer |
| Dashboard | Streamlit / Grafana | Visualisasi real-time |
| LLM Analysis | GPT-4 / Claude (untuk teks panjang) | Nuansa dan konteks mendalam |

### 7.3 Indikator Kualitas Analisis

Analis kebijakan harus melaporkan indikator berikut untuk menjamin transparansi:

- **Bot ratio** — persentase akun yang teridentifikasi sebagai bot/mencurigakan dalam dataset.
- **Model accuracy** — F1-score pada validation set yang diannotasi manusia.
- **Coverage** — persentase populasi yang terrepresentasikan vs. populasi target.
- **Temporal coherence** — apakah tren sentimen konsisten dengan peristiwa nyata.
- **Cross-platform consistency** — apakah sentimen konsisten di berbagai platform.

---

## 8. Kesimpulan <a name="kesimpulan"></a>

Review paper ini menjawab pertanyaan utama dengan nuansa: **AI untuk sentiment analysis media sosial masih relevan, tetapi tidak bisa digunakan secara naif.**

**Tiga Prinsip Utama:**

1. **Prinsip Agregasi** (dari Pellert et al., 2022): Noise individual menjadi sinyal valid ketika diagregasi dalam volume besar. Jangan menganalisis opini per-individu; fokus pada tren populasi.

2. **Prinsip Kontaminasi** (dari Li et al., 2024): Bot dan buzzer bukan sekadar noise tambahan — mereka secara aktif mengubah sentimen manusia nyata. Filtering bot bukan opsional, melainkan **wajib**.

3. **Prinsip Komplementaritas** (dari Gandy et al., 2025; Villanueva-Miranda et al., 2025): Tidak ada model AI tunggal yang superior untuk semua konteks. Gunakan pendekatan ensemble dan selalu triangulasi dengan sumber data lain.

**Bagi calon fungsional analis kebijakan:**

Peluang penggunaan AI untuk analisis sentimen kebijakan publik sangat besar dan nyata. Dengan metodologi yang tepat — bot filtering, model bahasa yang sesuai (IndoBERT untuk Indonesia), validasi berlapis, dan presentasi hasil yang jujur tentang keterbatasannya — AI dapat menjadi alat analisis kebijakan yang powerful, efisien, dan responsif terhadap dinamika opini publik yang bergerak cepat.

Tantangan buzzer dan bot di Indonesia bukan alasan untuk tidak menggunakan sentiment analysis, melainkan alasan untuk **menggunakannya dengan lebih cerdas dan hati-hati**.

---

## 9. Daftar Referensi <a name="referensi"></a>

### Paper Primer yang Dikaji

1. **Pellert, M., Metzler, H., Matzenberger, M., & Garcia, D.** (2022). Validating daily social media macroscopes of emotions. *Scientific Reports*, 12(1), 11236.  
   DOI: [10.1038/s41598-022-14579-y](https://doi.org/10.1038/s41598-022-14579-y)  
   Link: https://www.nature.com/articles/s41598-022-14579-y  
   **[Q1 — Nature Portfolio / Scientific Reports]**

2. **Li, L., Vásárhelyi, O., & Vedres, B.** (2024). Social bots spoil activist sentiment without eroding engagement. *Scientific Reports*, 14(1), 27005.  
   DOI: [10.1038/s41598-024-74032-0](https://doi.org/10.1038/s41598-024-74032-0)  
   Link: https://www.nature.com/articles/s41598-024-74032-0  
   **[Q1 — Nature Portfolio / Scientific Reports]**

3. **Gandy, L.M., Ivanitskaya, L.V., Bacon, L.L., & Bizri-Baryak, R.** (2025). Public health discussions on social media: Evaluating automated sentiment analysis methods. *JMIR Formative Research*, 9, e57395.  
   DOI: [10.2196/57395](https://doi.org/10.2196/57395)  
   Link: https://formative.jmir.org/2025/1/e57395  
   **[Q2 — JMIR Formative Research]**

4. **Villanueva-Miranda, I., Xie, Y., & Xiao, G.** (2025). Sentiment analysis in public health: A systematic review of the current state, challenges, and future directions. *Frontiers in Public Health*, 13, 1609749.  
   DOI: [10.3389/fpubh.2025.1609749](https://doi.org/10.3389/fpubh.2025.1609749)  
   **[Q1 — Frontiers in Public Health]**

### Referensi Pendukung

5. **Shi, W., et al.** (2020). Social bots' sentiment engagement in health emergencies: A topic-based analysis of the COVID-19 pandemic discussions on Twitter. *International Journal of Environmental Research and Public Health*, 17(22), 8701.  
   DOI: [10.3390/ijerph17228701](https://doi.org/10.3390/ijerph17228701)

6. **Yang, Y., et al.** (2023). Sentiment analysis of tweets on menu labeling regulations in the US. *Nutrients*, 15(19), 4269.  
   DOI: [10.3390/nu15194269](https://doi.org/10.3390/nu15194269)

7. **Beatson, O., Gibson, R., Cantijoch Cunill, M., & Elliot, M.** (2023). Automation on Twitter: Measuring the effectiveness of approaches to bot detection. *Social Science Computer Review*.  
   DOI: [10.1177/08944393211034991](https://doi.org/10.1177/08944393211034991)

8. **Liu, A., & Sun, M.** (2023). From voices to validity: Leveraging large language models (LLMs) for textual analysis of policy stakeholder interviews. *arXiv preprint*.  
   Link: https://arxiv.org/pdf/2312.01202

---

## Appendix: Glosarium Istilah Teknis

| Istilah | Definisi |
|---|---|
| **Sentiment Analysis** | Proses komputasi untuk mengidentifikasi dan mengekstrak opini/emosi dari teks |
| **NLP** | Natural Language Processing — bidang AI yang memproses bahasa manusia |
| **Bot** | Akun otomatis yang dioperasikan oleh perangkat lunak, bukan manusia |
| **Buzzer** | Individu atau jaringan yang dibayar untuk menyebarkan narasi tertentu |
| **Astroturfing** | Simulasi gerakan akar rumput yang seolah organik padahal terkoordinasi |
| **BERT** | Bidirectional Encoder Representations from Transformers — model NLP dari Google |
| **IndoBERT** | Versi BERT yang dilatih khusus pada korpus Bahasa Indonesia |
| **VADER** | Valence Aware Dictionary for Sentiment Reasoning — model lexicon-based populer |
| **LLM** | Large Language Model — model bahasa berukuran besar seperti GPT, Claude, Llama |
| **ABSA** | Aspect-Based Sentiment Analysis — analisis sentimen per aspek/entitas |
| **F1-Score** | Harmonic mean dari precision dan recall — metrik evaluasi model |
| **MCC** | Matthews Correlation Coefficient — metrik evaluasi untuk dataset tidak seimbang |
| **Ensemble** | Kombinasi beberapa model untuk hasil yang lebih robust |
| **Sampling Bias** | Ketika sampel tidak merepresentasikan populasi target |
| **Macroscope** | Pengukuran agregat tingkat populasi (lawan dari mikroskop individual) |

---

*Review paper ini disusun untuk keperluan akademis dalam mata kuliah Advanced Intelligent System (AIS), Program S2 Magister Teknik Informatika, UNPAM. Seluruh referensi dapat diverifikasi melalui tautan DOI yang disertakan.*

*Repository GitHub: Silakan tambahkan link repository Anda di sini.*

---
**© 2026 | Dokumen ini bersifat open-access untuk keperluan akademis**
