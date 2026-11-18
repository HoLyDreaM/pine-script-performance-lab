# Pine Script Performance Lab

**Proje kökü:** `pine-script-performance-lab/` (`d:\SoftWare\pine-script-performance-lab`)

TradingView Pine Script **v6** için performans ölçümü ve optimizasyon örneği.

## Dosyalar

| Dosya | Açıklama |
|-------|----------|
| `pine-script-performance-lab.pine` | Optimize edilmiş gösterge — kapsam, yerleşik fonksiyon, döngü/array, birleşik request, kontrollü çizim |
| `examples/before-heavy.pine` | Anti-örnek — Profiler karşılaştırması için pahalı kalıplar |

## 7 adım → kod

| Adım | Uygulama |
|------|----------|
| 1 Profiler ile başla | TradingView Pine Editor → Profiler; iki scripti aynı sembol/TF’de karşılaştırın |
| 2 Geçmişi sınırla | `calc_bars_count` + `request.security(..., calc_bars_count=...)` |
| 3 Yerleşik fonksiyon | `ta.sma`, `ta.atr`, `ta.highest` / `ta.lowest` |
| 4 Döngüyü daralt | Sabit üst sınır + erken `break` |
| 5 Array yaşam döngüsü | Sabit uzunluklu pencere (`push` + `shift`) |
| 6 request birleştir | Tek `request.security` ile tuple (`[htfClose, htfMa]`) |
| 7 Çizimi sınırla | `label` / `table` güncellemesi yalnız `barstate.islast` |

## Kurulum

1. TradingView → Pine Editor
2. `pine-script-performance-lab.pine` içeriğini yapıştırın → **Add to chart**
3. (İsteğe bağlı) `examples/before-heavy.pine` dosyasını ayrı bir panele ekleyin
4. Pine Editor → **Profiler** ile süre ve çağrı sayılarını karşılaştırın

## Not

Bu örnek eğitim amaçlıdır. Profiler kendi ölçüm ek yükünü de oluşturur; sonuçları mutlak kronometre değil, darboğaz sıralaması olarak okuyun. Optimizasyon sonrası çıktının (plot / alarm) aynı kaldığını doğrulayın.

## İlgili Makale

### Pine Script v6 Performans Optimizasyonu: 7 Etkili Adım

https://www.mehmet-ozdemir.com.tr/pine-script-v6-performans-optimizasyonu/

## Yazar

Mehmet Özdemir

Web Sitesi: https://www.mehmet-ozdemir.com.tr/

## Lisans

MIT
