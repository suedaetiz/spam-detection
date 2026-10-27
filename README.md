# SMS Spam Tespiti – Derin Öğrenme Projesi

Bu proje, SMS mesajlarını **spam** ve **normal (ham)** olarak sınıflandırmak için klasik bir makine öğrenmesi yöntemi ile iki derin öğrenme yaklaşımını karşılaştırır.

## Ekip

| Kişi | Sorumluluk |
|---|---|
| Kişi A | Veri, EDA, ön işleme, TF-IDF + Lojistik Regresyon (baseline) |
| Kişi B | Embedding + BiLSTM / 1D-CNN |
| Kişi C | DistilBERT fine-tuning |

## Veri seti

**Super SMS Dataset** (Salman, Ikram ve Kaafar, 2024)

- Kaynak: https://github.com/smspamresearch/spstudy (`Data/super_sms_dataset.csv`)
- Sütunlar: `SMSes` (mesaj metni), `Labels` (0 = normal, 1 = spam)

Veri dosyası repoya eklenmez; notebook'lar veriyi doğrudan kaynaktan indirir.

## Klasör yapısı

```
spam-detection/
├── data/
│   ├── raw/          # indirilen ham veri (git'e eklenmez)
│   └── processed/    # train / val / test bölünmüş veriler
├── notebooks/        # Colab notebook'ları
├── src/              # ortak Python fonksiyonları
├── results/
│   ├── figures/      # grafikler
│   └── tables/       # metrik tabloları
├── requirements.txt
└── README.md
```

## Kurulum ve çalıştırma

```bash
git clone https://github.com/<kullanici-adi>/spam-detection.git
cd spam-detection
pip install -r requirements.txt
```

Notebook'ları sırasıyla çalıştırın:

1. `notebooks/01_eda.ipynb` – veri yükleme, keşifsel analiz, train/val/test bölme
2. `notebooks/02_baseline.ipynb` – TF-IDF + Lojistik Regresyon
3. `notebooks/03_bilstm.ipynb` – BiLSTM / CNN
4. `notebooks/04_distilbert.ipynb` – DistilBERT

## Kaynak

Salman, M., Ikram, M., & Kaafar, M. A. (2024). Investigating Evasive Techniques in SMS Spam Filtering: A Comparative Analysis of Machine Learning Models. *IEEE Access*, 12, 24306–24324. https://doi.org/10.1109/ACCESS.2024.3364671
