# 🔍 Botnet C&C Altyapısının Sosyal Ağ Analizi Yöntemleriyle Tespiti

## 📋 Proje Özeti

Bu çalışmada, botnet ağlarının komuta-kontrol (C&C) altyapısının **sosyal ağ analizi** yöntemleriyle tespit edilebilirliği araştırılmıştır. **CTU-13** veri setinin 6. senaryosu (DonBot ailesi) üzerinde uygulamalı analiz gerçekleştirilmiştir.

### Temel Bulgular

| Metrik | Değer |
|--------|-------|
| Toplam Düğüm | 8.701 |
| Toplam Kenar | 9.618 |
| Modularite Skoru | 0,8011 |
| Botnet Topluluğu Saflığı | %99,9 |
| Hedefli vs Rastgele Saldırı Farkı | ~104 kat |

- **Bot Makinesi:** `147.32.84.165` (DonBot — out-degree analizi ile tespit)
- **C&C Sunucusu:** `91.212.135.158` (hedef profil analizi ile tespit)
- Albert-Barabási (2000) teoremi ampirik olarak doğrulanmıştır.

## 📁 Proje Yapısı

```
├── Botnet_C2_Sosyal_Ag_Analizi.ipynb   # Jupyter Notebook (tüm analiz kodu)
├── Botnet_C2_Sosyal_Ag_Analizi_Raporu.pdf  # Proje raporu
├── Botnet_C2_Sunum.pptx               # Sunum dosyası
├── veri_seti.txt                       # Veri seti bilgileri ve indirme bağlantısı
├── gorseller/                          # Analiz görselleri
│   ├── derece_dagilimi.png
│   ├── senaryo_bar.png
│   ├── senaryo_karsilastirma.png
│   ├── botnet_interaktif.html
│   └── gorsel_1_bot_etrafi_interaktif.html
└── README.md
```

## 🛠️ Kullanılan Teknolojiler

- **Python 3** — Ana programlama dili
- **NetworkX** — Graf modelleme ve analiz
- **python-louvain** — Topluluk tespiti (Louvain algoritması)
- **Matplotlib** — Statik görselleştirme
- **PyVis** — İnteraktif ağ görselleştirme
- **Pandas** — Veri ön işleme
- **Google Colab** — Çalışma ortamı

## 📊 Veri Seti

**CTU-13 Senaryo 6 (Capture-47) — DonBot**

- Kaynak: [Stratosphere Research Lab (Çek Teknik Üniversitesi)](https://www.stratosphereips.org/datasets-ctu13)
- İndirme: [capture20110816.binetflow](https://mcfp.felk.cvut.cz/publicDatasets/CTU-Malware-Capture-Botnet-47/capture20110816.binetflow.2format)
- Toplam akış: 558.919 | Botnet etiketli: 4.630 | Normal: 7.493

## 🔬 Uygulanan Analizler

1. **Temel Ağ Ölçütleri** — Yoğunluk, derece dağılımı, çap, kümeleme katsayısı
2. **Merkezilik Analizi** — Derece, ara-değerlik, yakınlık, özvektör, PageRank
3. **Topluluk Tespiti** — Louvain algoritması ile modularite optimizasyonu
4. **Dayanıklılık Analizi** — 8 farklı hedefli/rastgele saldırı senaryosu
5. **C&C Tespiti** — Bot hedef profil analizi ile komuta sunucusu belirleme

## 📚 Kaynakça

- Albert, R., & Barabási, A.-L. (2000). Error and attack tolerance of complex networks. *Nature*, 406, 378–382.
- Barabási, A.-L., & Albert, R. (1999). Emergence of scaling in random networks. *Science*, 286, 509–512.
- Blondel, V. D. et al. (2008). Fast unfolding of communities in large networks. *JSTAT*, P10008.
- García, S. et al. (2014). An empirical comparison of botnet detection methods. *Computers & Security*, 45, 100–123.

## 📄 Lisans

Bu proje akademik amaçlı hazırlanmıştır. CTU-13 veri seti Stratosphere Research Lab tarafından kamuya açık olarak yayımlanmıştır.
