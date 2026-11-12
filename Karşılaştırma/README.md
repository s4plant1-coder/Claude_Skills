# Karşılaştırmalı Araştırma Skill'i (`karsilastirmali-arastirma`)

Herhangi bir konuda seçenekleri web'de araştırıp kaynaklı bir karşılaştırma raporu üreten Claude skill'i. Hedef: aranan şeyin varyasyonlarını, yakın alternatiflerini ve rakiplerini en ince ayrıntısına kadar karşılaştırmak; fiyat, ayırıcı özellik, avantaj/dezavantaj ve senaryoya göre öneri vermek. Kullanıcı ürün, yazılım, hizmet, kurs, araç veya yöntem seçerken kullanır.

## Hızlı bilgi
- Dil / altyapı: Claude Agent Skill — YAML frontmatter + Markdown talimatlar. claude.ai'ye yüklenip `anthropic-skills:karsilastirmali-arastirma` adıyla kullanılıyor.
- Ana dosyalar: `SKILL.md` (henüz bu klasörde yok; plan 12_11_2026_1 onaylanınca eklenecek)
- Mimari ve işleyiş: [MIMARI.md](MIMARI.md)
- Planlar: [plan/](plan/)
- Not: Bu klasördeki `SKILL.md` değişince claude.ai'deki yüklü sürüm kendiliğinden güncellenmez; yüklemeyi kullanıcı yapar.

## Değişiklik Günlüğü

### 12.11.2026 — Proje kayıtları kuruldu
**Plan:** — (ilk kurulum; kayıt dosyaları plansız oluşturulur)
**Değişen dosyalar:**
- `README.md` — oluşturuldu
- `MIMARI.md` — oluşturuldu; claude.ai'de yüklü mevcut sürümün yapısı ve bilinen eksikleri yazıldı
- `plan/12_11_2026_1.md` — skill'i varyasyon, rakip ve derinlik desteğiyle geliştirme planı (onay bekliyor)
**Alınan kararlar:**
- Kayıtlar repo kökünde değil `Karşılaştırma/` klasöründe tutulur — her skill klasörü ayrı bir proje.
- Skill'e sabit site listesi yazılmaz; bölgeye özgü kaynaklar her seferinde aramayla bulunur — skill'lerin genel ve araştırmacı olması ilkesi.
**Açık kalan işler:**
- Plan 12_11_2026_1 onay bekliyor.
- Orijinal biçimli `SKILL.md` dosyası henüz klasörde yok.
