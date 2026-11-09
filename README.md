# skiller

Claude için yazılmış skill'lerin (SKILL.md dosyaları) toplandığı depo. Her skill kendi klasöründe durur ve claude.ai / Claude Code'a yüklenerek kullanılır. Şu an tek skill var: `programlama-dili-ogret`.

## Hızlı bilgi
- Dil / altyapı: Markdown (YAML ön bilgili SKILL.md), git
- Ana dosyalar: `programlama-dili-ogret/SKILL.md`
- Mimari ve işleyiş: [MIMARI.md](MIMARI.md)
- Planlar: [plan/](plan/)

## Değişiklik Günlüğü

### 09.11.2026 — Kayıt düzeni kuruldu
**Plan:** — (ilk kurulum, plan gerekmez)
**Değişen dosyalar:**
- `README.md` — oluşturuldu
- `MIMARI.md` — oluşturuldu (ilk tam analiz sonucu)
**Alınan kararlar:**
- Proje dosyalarına dokunulmadı; analizde bulunan sorunlar MIMARI.md §6'ya yazıldı.
**Açık kalan işler:**
- Kökteki kopya `programlama-dili-ogret-SKILL.md` (klasördekiyle birebir aynı) silinsin mi?
- `.DS_Store` git'ten çıkarılıp `.gitignore` eklensin mi?
- SKILL.md biçim ve tutarlılık düzeltmeleri (MIMARI.md §6).

### 08.11.2026 — programlama-dili-ogret skill eklendi
**Plan:** — (kayıt düzeni öncesi, commit `de66864`)
**Değişen dosyalar:**
- `programlama-dili-ogret/SKILL.md` — eklendi
- `programlama-dili-ogret-SKILL.md` — eklendi (aynı içerik)
- `.DS_Store` — eklendi
