# Kod haritası — Tablet Helper

> Güncellendi: 2026-09-21. Kanıt: TabletHelper.cpp, config/game kaynakları, README ve `.vcxproj`; oyun içi çalışma gözlenmedi.

## Giriş ve akış

Windows x64/C++20 PoeFixer overlay/item DLL; `TabletHelper.sln` / `TabletHelper.vcxproj`, MSVC v145, SDK C ABI v6. `TabletHelper.cpp` ayarları yükler, açık item pencerelerini tarar ve vurguları çizer. Kaynak/README sürümü 1.4.1.

| Yol | Görev |
|---|---|
| `config/Settings.h` | Filtre eşikleri, renkler, scan aralığı ve crash-safe JSON |
| `config/tablet_mod_ranges.json` | Bonus aralıkları ve veri tabanlı mod sınırları |
| `game/TabletScanner.h` | Açık envanterleri ve Precursor Tablet item'larını toplama |
| `game/TabletMatch.h` | Tablet bonus/kullanım/isim eşleşmeleri |
| `game/TabletRanges.h` | JSON aralıklarının yüklenmesi ve varsayılanlar |
| `game/HighlightRenderer.h` | Eşya dikdörtgenleri, rozet ve renk çizimi |
| `game/PanelDetector.h` | Oyuncu/özel panel ayrımı |

## Çalışma ve veri

- `DrawUI` foreground/oyun/panel koşullarında tarama sonucu tabletleri vurgular; SDK envanter verisi ve item mod okumaları kullanılır. Tablet türleri artık Expedition dahil 8 türdür.
- Kalıcı ayar `config/settings.json`; bonus veri dosyası plugin `config/tablet_mod_ranges.json` içindedir. Harici ağ/DB yoktur.
- Vendored `sdk/`, `imgui/` ve `third_party/json.hpp` değiştirilmez.

## Derleme ve kurulum

```powershell
& 'C:/Program Files/Microsoft Visual Studio/18/Enterprise/MSBuild/Current/Bin/MSBuild.exe' TabletHelper.sln -p:Configuration=Release -p:Platform=x64 -nologo -v:minimal -m
```

Çıktı `bin/Release/TabletHelper.dll`; kurulum `D:/POE2/fixer/Plugins/TabletHelper/TabletHelper.dll` ve gerekli `config/tablet_mod_ranges.json`. Çalışan host için ortak AGENTS.md kapat → kopyala → yönetici olarak yeniden başlat akışı uygulanır. Otomatik test/linter/CI görülmedi.

## Doğrulanmamış noktalar

Tablet mod alanlarının güncel host anlamı ve pencereli koordinatlar oyun içinde doğrulanmadı. Depo başlangıçta yerel `TabletHelper.cpp` değişikliği taşıyordu; bu yenilemede korunmuştur.
