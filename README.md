# Kayıp Fonksiyonu Seçiminin Regresyon Performansına Etkisi: Enerji Tüketimi Tahmini

Celal Bayar Üniversitesi, Yapay Sinir Ağları dersi kitap bölümü ödevi.
Yazarlar: S. Arabacı, A. E. Akdeniz.

Aynı çok katmanlı algılayıcı (27-128-64-32-1), aynı optimizör (Adam) ve aynı kronolojik veri bölmesi (%70/%15/%15)
altında yalnızca kayıp fonksiyonu (MSE, MAE, Huber, log-cosh) değiştirilerek regresyon performansı karşılaştırılmıştır.
Her konfigürasyon 5 rastgele tohumla (42-46) tekrarlanmıştır.

## Ana sonuçlar (test kümesi, 5 tohum, ortalama ± std)
| Kayıp | RMSE (Wh) | MAE (Wh) | R² |
|---|---|---|---|
| MSE | 91,86 ± 5,92 | 58,75 ± 9,00 | -0,03 ± 0,13 |
| MAE | 85,48 ± 0,74 | 42,42 ± 1,27 | 0,12 ± 0,02 |
| Huber (δ=1) | 88,29 ± 2,57 | 51,50 ± 6,19 | 0,06 ± 0,05 |
| Log-cosh | 88,98 ± 3,49 | 52,89 ± 7,96 | 0,04 ± 0,07 |

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
- `notebooks/`: deney defteri (tüm deneyler, şekiller ve tablolar)
- `figures/`: şekiller (G1-G7) ve tablo çıktıları (CSV)
- `kaynakca.bib`: kaynakça (BibTeX)
- `requirements.txt`: kütüphane sürümleri (UTF-8)
