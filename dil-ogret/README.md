# dil-ogret

Dünyadaki herhangi bir insan dilini öğreten Claude skill'i. Kapsam: yaygın yaşayan diller, az konuşulan ve tehlike altındaki diller, klasik ve ölü diller, yapay diller, işaret dilleri. Skill hiçbir dile bağlı değildir. Her dili önce beş kaynak türünden araştırır, sonra CEFR seviyelerine (Pre-A1–C2) dayanan, kaynakçalı bir program, ders ve alıştırma hazırlar.

## Hızlı bilgi
- Dil / altyapı: Markdown (YAML ön bilgili SKILL.md), git
- Ana dosyalar: `SKILL.md` (claude.ai / Claude Code'a yüklenecek tek dosya)
- Mimari ve işleyiş: [MIMARI.md](MIMARI.md)
- Planlar: [plan/](plan/)
- Kardeş skill: `../programlama-dili-ogret/` (programlama dilleri). İki skill'in tetikleme ayrımı MIMARI.md §2'dedir.

## Değişiklik Günlüğü

### 09.11.2026 — dil-ogret skill'i oluşturuldu
**Plan:** plan/09_11_2026_1.md
**Değişen dosyalar:**
- `SKILL.md`: oluşturuldu (330 satır, 12 bölüm)
- `README.md`, `MIMARI.md`, `plan/`: kayıt düzeni kuruldu (kökten taşındı)
**Alınan kararlar:**
- Dile özgü sabit bilgi tutulmaz. Her dil beş kaynak türünden araştırılır. Neden: kullanıcının kalıcı kuralı ve Claude'un az kaynaklı dillerdeki hata riski.
- Seviye sistemi CEFR, Pre-A1–C2. Neden: 2020 Companion Volume'da "A0" yok, Pre-A1 var.
- Öğretim ilkeleri meta-analizlere dayanır, kaynakları SKILL.md §5'te "Dayanak" sütunundadır.
- Konum `dil-ogret/` (Karar A). Neden: depodaki `<ad>/SKILL.md` düzeni.
**Açık kalan işler:**
- Kullanıcı silecek:
  - `rm ../plan/09_11_2026_2.md`
  - `rm -r ../DiL-Egitimi`
- claude.ai'ye yükleyip 3 test istemiyle denemek (plan §5).
