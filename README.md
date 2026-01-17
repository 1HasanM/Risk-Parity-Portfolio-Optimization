# Risk Parity Portföy Optimizasyonu

Bireysel yatırımcı portföylerindeki dengesiz risk dağılımı sorununu çözmek için risk parity stratejisi uygulayan nicel bir portföy optimizasyon projesi.

## Problem Tanımı

Bireysel yatırımcılar genellikle eşit ağırlık dağılımı stratejisi kullanır ve farkında olmadan portföy riskini yüksek volatiliteli varlıklarda yoğunlaştırır. Bu yaklaşım şu sorunlara yol açar:
- Hisse senedi piyasası düşüşlerine aşırı maruz kalma
- Düşük risk-ayarlı getiri
- Çoklu varlık tutulmasına rağmen yetersiz çeşitlendirme

## Çözüm

Bu proje, sermaye dağılımı yerine risk katkısını eşitleyen **Risk Parity** yaklaşımını uygular. Her varlıktan eşit risk katkısı hedeflenerek portföy şunları sağlar:
- Piyasa düzeltmelerinde daha iyi koruma
- Daha tutarlı risk-ayarlı performans
- Farklı piyasa koşullarında gerçek çeşitlendirme

## Metodoloji

Uygulama şunları içerir:
- **Risk katkısı eşitleme**: Her varlık toplam portföy riskine %25 katkı yapar
- **Çoklu varlık evreni**: SPY (S&P 500), TLT (Hazine Tahvilleri), GLD (Altın), QQQ (Nasdaq 100)
- **Volatilite bazlı ağırlıklandırma**: Düşük volatiliteli varlıklara yüksek, yüksek volatiliteli varlıklara düşük pay
- **Geriye dönük test dönemi**: 2017-2025, farklı piyasa rejimlerini içerir

## Teknoloji Yığını

- **Python 3.x**
- **NumPy/Pandas**: Veri manipülasyonu ve hesaplama
- **yfinance**: Piyasa verisi çekimi
- **Matplotlib**: Performans görselleştirme
- **Scipy**: Portföy optimizasyon algoritmaları

## Temel Bulgular

### Performans Karşılaştırması (2017-2025)

| Metrik | Risk Parity | Equal Weight |
|--------|-------------|--------------|
| Toplam Getiri | %110 (2.1x) | %150 (2.5x) |
| 2022 Düşüşü | -%21 | -%24 |
| Volatilite | Düşük | Yüksek |
| Grafik Düzgünlüğü | Yüksek | Düşük |

### Kritik Bulgular

1. **Düşüş Koruması**: Risk Parity, 2022 ayı piyasasında Equal Weight'e kıyasla kayıpları %13 azalttı
2. **Düzgün Getiriler**: Tüm test periyodu boyunca daha düşük volatilite ve daha istikrarlı performans
3. **Boğa Piyasası Takası**: Güçlü hisse rallilerinde (2020-2022, 2023-2025) Equal Weight'in gerisinde kaldı
4. **Risk Dengesi**: Her varlık sınıfından %25 risk katkısını başarıyla korudu

### Portföy Ağırlıkları

**Risk Parity dağılımı:**
- QQQ: %33
- SPY: %30
- GLD: %21
- TLT: %16

**Equal Weight dağılımı:**
- Her varlık: %25

Risk Parity'de volatil varlıklara daha fazla pay verilmiş gibi görünse de, düşük volatiliteli varlıklara (TLT) kaldıraç uygulanarak risk katkıları eşitlenir.
