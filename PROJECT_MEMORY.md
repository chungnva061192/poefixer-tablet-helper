# Proje hafızası — Tablet Helper

> Güncellendi: 2026-09-21. Repository-owned context; secret içermez.

## Mevcut durum

- Kaynak ve README sürümü 1.4.1; Expedition tablet "Surpassing chance" mod etiketleri oyun içi metinlerle eşitlendi (`TowerExpeditionChanceForVerisiumRemnant` ve `TowerExpeditionChanceForTwinnedElites`). Kullanıcılar artık arama kutusuna `surpassing` yazarak bu modları bulup filtreleyebiliyor.
- GitHub release yayımlandı: https://github.com/omrfarukarpa/poefixer-tablet-helper/releases/tag/v1.4.1.

## Onaylı kararlar ve sonuçlar

- JSON bonus aralıkları `config/tablet_mod_ranges.json` ile DLL'den ayrı taşınır; dağıtımda bu dosya birlikte tutulur.
- Expedition türünün iç mod aileleri `TowerExpeditionExplosionRadius`, `TowerExpeditionLogbookIncrease`, `TowerExpeditionRunicMonsters`, `TowerExpeditionIncreasedVerisium`, `TowerExpeditionUnearthedRares`, `TowerExpeditionAdditionalSentinels`, `TowerExpeditionIncreasedMonsterRarity`, `TowerExpeditionFrozenBosses`, `TowerExpeditionBuriedStrongboxes`, `TowerExpeditionVaalRemnants`, `TowerExpeditionChanceForVerisiumRemnant`, `TowerExpeditionChanceForTwinnedElites` ve `TowerExpedition2RunicModPassoverChance` olarak kataloglandı. Benzersiz mod kimlikleri oyun içi debug dump ile ayrıca doğrulanmalıdır.
- Kullanım/filtre alanları kullanıcı ayarlarında kalıcıdır. Boş sayı alanlarının 0'a sıfırlanması ortak UI kuralıdır.

## Riskler ve bekleyenler

- 1.4.1 Release x64 derlemesi hatasız tamamlandı; DLL SHA-256 `6516B73B558FBEE16FA39813973B4B0738D5C252A5B2D68A7C038C3CEC5AB10B` ile yerel PoeFixer kurulumuna (`D:\POE2\fixer\Plugins\TabletHelper`) ve GitHub release varlığına kopyalandı.
- Otomatik test çalıştırılmadı; yayın öncesi temiz derleme ve veri dosyası kontrolü gerekir.
