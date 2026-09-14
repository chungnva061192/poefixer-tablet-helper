# Proje hafızası — Tablet Helper

> Güncellendi: 2026-09-15. Repository-owned context; secret içermez.

## Mevcut durum

- Kaynak ve README sürümü 1.4.0; Expedition Tablet desteği eklendi (8 tür, Expedition bonus kataloğu ve 0.5.5 aralıkları). GitHub release yayımlandı: https://github.com/omrfarukarpa/poefixer-tablet-helper/releases/tag/v1.4.0.
- Depoda bağlam yenilemesi öncesinden gelen yerel `TabletHelper.cpp` değişikliği vardır; korunuyor, işlevi bu görevde yeniden değerlendirilmedi.

## Onaylı kararlar ve sonuçlar

- JSON bonus aralıkları `config/tablet_mod_ranges.json` ile DLL'den ayrı taşınır; dağıtımda bu dosya birlikte tutulur.
- Expedition türünün iç mod aileleri `TowerExpeditionExplosionRadius`, `TowerExpeditionLogbookIncrease`, `TowerExpeditionRunicMonsters`, `TowerExpeditionIncreasedVerisium`, `TowerExpeditionUnearthedRares`, `TowerExpeditionAdditionalSentinels`, `TowerExpeditionIncreasedMonsterRarity`, `TowerExpeditionFrozenBosses`, `TowerExpeditionBuriedStrongboxes`, `TowerExpeditionVaalRemnants`, `TowerExpeditionChanceForVerisiumRemnant`, `TowerExpeditionChanceForTwinnedElites` ve `TowerExpedition2RunicModPassoverChance` olarak kataloglandı. Benzersiz mod kimlikleri oyun içi debug dump ile ayrıca doğrulanmalıdır.
- Kullanım/filtre alanları kullanıcı ayarlarında kalıcıdır. Boş sayı alanlarının 0'a sıfırlanması ortak UI kuralıdır.

## Riskler ve bekleyenler

- 1.4.0 Release x64 derlemesi hatasız tamamlandı; DLL SHA-256 `EFC8AF75022F9D6E3D031BBE7228B711FC7CD1FF57780F10BF79D6023415D611` ile yerel PoeFixer kurulumuna ve GitHub release varlığına kopyalandı. GitHub release yayımlandı: https://github.com/omrfarukarpa/poefixer-tablet-helper/releases/tag/v1.4.0. Expedition mod kimliklerinin canlı `ReadItemMods` çıktısı ve özel/guild sekme rect'leri oyun içinde doğrulanmadı.
- Otomatik test çalıştırılmadı; yayın öncesi temiz derleme ve veri dosyası kontrolü gerekir.
