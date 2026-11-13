# programlama-dili-ogret

Herhangi bir programlama dilini veya sorgu dilini sıfırdan ileri seviyeye öğreten Claude skill'i. Müfredat, ders, alıştırma ve quiz üretir. Dile bağlı olmayan tek bir eğitim taslağı kullanır.

## Hızlı bilgi
- Dil / altyapı: Markdown (YAML ön bilgili `SKILL.md`)
- Ana dosya: `SKILL.md`; ayrıntılar `references/`, şablonlar `assets/` klasöründe; testler `evals/` klasöründe
- Mimari ve işleyiş: [MIMARI.md](MIMARI.md)
- Planlar: [plan/](plan/)

## Değişiklik Günlüğü

### 13.11.2026 — Skill araştırmaya dayalı olarak yeniden yapılandırıldı (B mimarisi)
**Plan:** plan/12_11_2026_1.md (tamamlandı; 09_11_2026_1'in yerine geçti)
**Değişen dosyalar:**
- `SKILL.md`: yeniden yazıldı (342 → 189 satır). Tek açıklama, 8 adımlı iş akışı, `|` tablolar, yapay zekâ öğretmen kuralları, doğrulama döngüsü, 3 örnek.
- `references/` (5 dosya), `assets/` (3 şablon), `evals/evals.json` (5 senaryo): oluşturuldu.
- `MIMARI.md`: yeniden yazıldı. `plan/09_11_2026_1.md`: durumu güncellendi.
**Alınan kararlar:**
- K1–K5 önerildiği gibi uygulandı: B mimarisi; profil tablosu kurulum dosyasına taşındı; Bölüm 6 eklendi; ilerleme kaydı eklendi; evals eklendi.
- SQL araç tablosu ve C++ "Derinleşmek için" tablosu kaldırıldı. Bu bilgiler artık araştırma çıktısından gelir.
**Açık kalan işler:**
- Yeni zip'in claude.ai'ye yüklenmesi. Komut, üst klasörden: `zip -r programlama-dili-ogret.zip programlama-dili-ogret -x 'programlama-dili-ogret/README.md' 'programlama-dili-ogret/MIMARI.md' 'programlama-dili-ogret/plan/*' 'programlama-dili-ogret/arastirma/*' 'programlama-dili-ogret/evals/*' '*/.DS_Store'`
- evals'ın çalıştırılması.
- Kurulum kuralının tek konuluk ders isteklerindeki davranışı (karar bekliyor; MIMARI §6).

### 12.11.2026 — "Her dil, baştan sona" tasarım araştırması
**Plan:** plan/12_11_2026_1.md (onay bekliyor; 09_11_2026_1'i içerir ve genişletir)
**Değişen dosyalar:**
- `arastirma/12_11_2026_1.md`: oluşturuldu. 29 kaynaklı rapor: dil aileleri, öğretim yöntemleri, müfredat çerçeveleri, skill yazım kuralları.
- `plan/12_11_2026_1.md`: oluşturuldu.
- `MIMARI.md`: `arastirma/` klasörü eklendi.
**Alınan kararlar:**
- Araştırma raporları `arastirma/GG_AA_YYYY_N.md` biçiminde tutulur ve zip'e girmez.
**Açık kalan işler:**
- Plan 12_11_2026_1'in onayı ve K1–K5 kararları (mimari, profil tablosu, Bölüm 6, ilerleme kaydı, evals).

### 09.11.2026 — Kayıt düzeni kuruldu
**Plan:** — (ilk kurulum). Açık plan: `plan/09_11_2026_1.md` (onay bekliyor)
**Değişen dosyalar:**
- `README.md`, `MIMARI.md` — oluşturuldu (ilk tam analiz sonucu)
**Alınan kararlar:**
- Proje klasörü `skiller/programlama-dili-ogret/`. Kullanıcı kararı; kayıtlar repo kökünde değil burada tutulur.
- Skill hiçbir dile bağlı olmayacak; her dil için internetten araştırma yapıp kaynakçalı akademik program hazırlayacak (plan 09_11_2026_1).
- Dil bazlı derleyici tablosu kalacak (kullanıcı kararı).
**Açık kalan işler:**
- Plan 09_11_2026_1'in onayı.
- 8 dillik dil profili tablosu kalsın mı? (kullanıcının kararı bekleniyor)

### 08.11.2026 — Skill eklendi
**Plan:** — (kayıt düzeni öncesi, commit `de66864`)
**Değişen dosyalar:**
- `SKILL.md` — eklendi
