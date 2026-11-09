# Kayıp Fonksiyonu Seçiminin Regresyon Performansına Etkisi: Enerji Tüketimi Tahmini

Celal Bayar Üniversitesi, Yapay Sinir Ağları Dersi kitap bölümü ödevi.

## Veri seti
UCI Appliances Energy Prediction (Candanedo vd., 2017).
https://archive.ics.uci.edu/dataset/374/appliances+energy+prediction
Dosya `data/energydata_complete.csv` konumundadır.

## Kurulum
Python 3.12 gerekir.

    py -3.12 -m venv .venv
    .venv\Scripts\activate
    pip install -r requirements.txt

## Çalıştırma
1. VS Code ile `notebooks/01_veri_kesfi.ipynb` dosyasını aç.
2. Çekirdek olarak `.venv` seç.
3. Run All ile tüm hücreleri çalıştır (CPU'da yaklaşık 10-15 dakika).

Tüm deneylerde rastgelelik tohumu (seed) 42-46 aralığında sabitlenmiştir.
Şekiller `figures/` klasörüne 300 DPI olarak kaydedilir.

## Klasör yapısı
- `data/`: ham veri
- `notebooks/`: deney defteri
- `figures/`: şekiller ve tablo çıktıları (CSV)
- `requirements.txt`: kütüphane sürümleri