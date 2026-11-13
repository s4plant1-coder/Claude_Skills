# proje (skill)

Claude için proje başlatma ve kayıt skill'i. Bir proje klasöründe çalışmaya başlarken veya yeni bir proje oluştururken çalışır. Her projede aynı kayıt düzenini (README.md, MIMARI.md, plan/) kurar ve her değişikliği "plan yaz → onay al → uygula → kaydet" akışıyla yürütür. Hedef: kullanıcının bütün projelerinin aynı mimaride olması.

## Hızlı bilgi
- Dil / altyapı: Claude Agent Skill. Markdown biçiminde, YAML ön bilgili `SKILL.md`
- Ana dosyalar: `SKILL.md`
- Mimari ve işleyiş: [MIMARI.md](MIMARI.md)
- Planlar: [plan/](plan/)
- Yüklü kopya: claude.ai'den senkronize gelen `~/.claude/skills/synced/…/proje/SKILL.md`. Bu klasördeki değişiklikler claude.ai'ye yeniden yüklenince etkinleşir.

## Değişiklik Günlüğü

### 13.11.2026 — Standart proje iskeleti ve yeni proje kurulumu
**Plan:** plan/12_11_2026_1.md
**Değişen dosyalar:**
- `SKILL.md` — yeni `description` ve başlık; "Standart proje iskeleti" bölümü (●/○ ağaç, proje türü profilleri, iskelet kuralları); §0'a 0.A Yeni proje kurulumu ve 0.B Uyum kontrolü; MIMARI şablonuna klasör düzeni ve sapma tablosu (212 → 301 satır)
- `MIMARI.md` — akış, veri kuralları, kısıtlar ve satır numaraları yeni sürüme göre güncellendi
**Alınan kararlar:**
- Klasör ve yeni dosya adları İngilizce; kayıt katmanı adları (README.md, MIMARI.md, plan/) değişmez — var olan projeler uyumlu kalsın
- Var olan projelerde sapmalar yalnızca raporlanır, taşıma yapılmaz
**Açık kalan işler:**
- `SKILL.md`'yi claude.ai'ye yeniden yüklemek; sonraki plan önerileri (MIMARI §6)

### 12.11.2026 — Klasör proje düzenine açıldı
**Plan:** — (ilk kurulum, yalnızca kayıt dosyaları)
**Değişen dosyalar:**
- `SKILL.md` — kullanıcının verdiği mevcut içerik birebir kaydedildi (başlangıç sürümü, 212 satır)
- `README.md`, `MIMARI.md`, `plan/` — oluşturuldu
**Alınan kararlar:**
- Kayıtlar repo kökünde değil, `Proje/` klasöründe tutulur. Neden: her skill ayrı bir çalışma.
**Açık kalan işler:**
- `plan/12_11_2026_1.md`: standart proje iskeleti (onay bekliyor)
