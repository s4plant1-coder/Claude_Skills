---
name: "proje"
description: "sadece klasörler için geçerli"
---


# Proje Kayıt Düzeni

Amaç: Projede yapılan her şeyin kayıtlı, geriye dönük izlenebilir ve kullanıcı onaylı olması.
Her zaman Türkçe yaz.

## 0. Oturum başında (her seferinde)

1. Çalışılan proje klasörünü belirle. Bağlı bir proje klasörü yoksa kullanıcıya söyle: kayıtların kalıcı olması için görevin bilgisayardaki proje klasörüne bağlanması gerekir.
2. Proje kökünde şunları kontrol et:
   - `README.md`
   - `MIMARI.md`
   - `plan/` klasörü
3. Varsa: aşağıdaki **"Az okuma (token tasarrufu)"** kuralına göre yalnızca README.md'nin son günlük kayıtlarını, MIMARI.md'yi ve `plan/` içindeki tamamlanmamış planları oku. Kullanıcıya kısaca "En son şunlar yapılmıştı, açık kalan işler şunlar" diye özetle.
   - Projede eski adla `TASARIM.md` varsa kullanıcıya sor; onay verirse `MIMARI.md` olarak yeniden adlandır.
   - `plan/` içinde adlandırma kuralına uymayan dosyalar varsa (ör. `YAPILACAKLAR.md`, `2026-10-26_konu.md`) kullanıcıya listele; onay verirse içindeki tarihe göre (tarih yoksa dosyanın oluşturulma tarihine göre) `GG_AA_YYYY_N.md` biçiminde yeniden adlandır.
4. Yoksa: kullanıcıya oluşturacağını söyle, aşağıdaki şablonlarla oluştur. (Bu kayıt dosyalarını oluşturmak için ayrıca izin gerekmez; proje kodunu değiştirmek için gerekir.) Tüm projeyi baştan inceleme yalnızca bu ilk kurulumda yapılır.

## Az okuma (token tasarrufu) — ZORUNLU

Amaç: Projeyi her oturumda baştan analiz etmemek; kayıt dosyalarını projenin "hafızası" olarak kullanmak.

**Oturum başında yalnızca şunları oku:**
1. `MIMARI.md` → projenin yapısı, dosyaların görevleri, veri ve hesap kuralları için TEK kaynak. Hangi işin hangi dosyada olduğunu "Hızlı yön bulma" tablosundan bul.
2. `README.md` → yalnızca "Hızlı bilgi" ve "Değişiklik Günlüğü"nün **son 3 kaydı**.
3. `plan/` → yalnızca içinde `- [ ]` (tamamlanmamış madde) olan planlar. Durumu "Tamamlandı" olan eski planları okuma; dosya listesine bakmak yeterli.

**Kaynak kod okuma kuralları:**
- Tüm projeyi, tüm klasörleri veya büyük dosyaların tamamını OKUMA.
- Hangi dosyalara bakılacağını önce MIMARI.md'den belirle; yalnızca o işle ilgili dosyaları oku.
- Büyük dosyalarda önce ara (`grep` / `rg` / `Select-String`), sonra yalnızca ilgili satır aralığını oku.
- Plan yazıldıktan sonra yalnızca planın "Neyi değiştirecek?" tablosundaki dosya/bölümlere dokun ve onları oku.
- Bir dosyayı oturum içinde bir kez okuduysan, değişmediyse tekrar baştan okuma.

**Tam proje taraması yalnızca şu durumlarda yapılır:**
- İlk kurulum (README / MIMARI yokken),
- Kullanıcı açıkça isterse ("projeyi baştan incele"),
- MIMARI.md'nin kodla uyuşmadığı görülürse → önce kullanıcıya söyle, onay alınca yalnızca uyuşmayan bölümü inceleyip MIMARI.md'yi düzelt.

**Hafızayı güncel tut:** Bu düzenin çalışması MIMARI.md'nin doğru olmasına bağlıdır. Her iş sonunda yapı, dosya görevi, akış, tablo/alan veya hesap kuralı değiştiyse MIMARI.md'yi mutlaka güncelle. README günlüğü kısa ve öz olsun (her kayıt en fazla ~10 satır).

## 1. Plan yaz → onay al

Herhangi bir kod/dosya değişikliğinden ÖNCE:

1. `plan/` klasöründe aşağıdaki **adlandırma kuralına** göre yeni bir plan dosyası oluştur ve aşağıdaki plan şablonuyla doldur.
2. Planda şu iki bilgi ZORUNLUDUR; eksikse plan tamamlanmış sayılmaz, onaya sunma:
   - **Neden yapılıyor:** Kullanıcının isteği, mevcut durum / sorun, değişiklik yapılmazsa ne olur.
   - **Neyi değiştirecek:** Her dosya için hangi bölüm / fonksiyon / sorgu değişecek; **şu anki hâli → yeni hâli**; kullanıcının ekranda / çıktıda göreceği fark.
3. Yapılacaklar listesindeki **her madde** de kendi "Neden" ve "Ne değişecek" satırını taşır. Sadece "Adım 1: X'i düzenle" gibi gerekçesiz madde yazma.
4. Planı kullanıcıya göster ve AÇIK ONAY bekle. Onay gelmeden proje dosyalarına dokunma.
5. Kullanıcı planı değiştirirse dosyayı güncelle, tekrar onay al.

### Plan dosyası adlandırma kuralı (ZORUNLU)

- Biçim: `plan/GG_AA_YYYY_N.md`
  - `GG_AA_YYYY` = bugünün tarihi (gün_ay_yıl, iki haneli gün ve ay), ör. `26_10_2026`
  - `N` = o günün kaçıncı planı olduğu: 1, 2, 3 …
- `N`'yi bulmak için: `plan/` içinde bugünün tarihiyle başlayan dosyaları say, en büyük numaranın bir fazlasını kullan. O gün hiç plan yoksa `1`.
  - Örnek: `26_10_2026_1.md`, `26_10_2026_2.md`; ertesi gün yeniden `27_10_2026_1.md`.
- Tarihi tahmin etme; sistem tarihini kullan (Windows PowerShell: `Get-Date -Format dd_MM_yyyy`, Linux/macOS: `date +%d_%m_%Y`).
- Var olan bir plan dosyasının üzerine yazma; her yeni iş = yeni dosya. Aynı işe devam ediliyorsa mevcut planı güncelle.
- `YAPILACAKLAR.md`, `todo.md`, `plan.md` gibi tarihsiz / genel adlar KULLANMA.
- Planın konusu dosya adında değil, dosyanın ilk satırındaki başlıkta yazar (`# Plan 26_10_2026_2: <konu>`).

## 2. Uygula

- Yalnızca plandaki işleri yap. İstenmeyen kod, tasarım veya davranış değişikliği yapma.
- Değiştirmeden önce dosyanın yedeğini al veya değişikliği diff olarak göster.
- Her madde bittikçe plan dosyasında `- [ ]` → `- [x]` yap.
- Plan dışına çıkmak gerekirse dur: önce planı güncelle, kullanıcıya sor.
- Mümkünse doğrula (ör. PHP için `php -l`, JS için söz dizimi kontrolü). Test edilemeyenleri not et.

## 3. Kapat: günlük + mimari + commit mesajı

İş bittiğinde sırasıyla:

1. Plan dosyasının sonundaki "Sonuç" bölümünü doldur.
2. `README.md` → "Değişiklik Günlüğü" bölümünün EN ÜSTÜNE tarihli kayıt ekle (şablon aşağıda); kayıtta ilgili plan dosyasının adını belirt. Eski kayıtları asla silme veya değiştirme.
3. Yapı, akış, dosya görevi veya veritabanı kullanımı değiştiyse `MIMARI.md`'yi güncelle.
4. Kullanıcıya commit mesajı ver (şablon aşağıda). Commit'i KULLANICI atar.
5. Son mesajda: ne değişti, neyi test edemedin, kullanıcının neyi kontrol etmesi gerekiyor.

## Kesin kurallar (izinsiz yapılmaz)

- `git commit`, `push`, `merge`, `rebase`, branch oluşturma/silme → ASLA izinsiz.
- Dosya silme, taşıma, yeniden adlandırma → önce sor.
- Proje klasörü dışındaki bir klasöre erişim → önce nedenini söyle, izin iste.
- İnternetten dosya indirme, paket kurma, dış servise/veritabanına bağlanma → önce sor.
- Var olan proje dosyasının üzerine yazma → yalnızca onaylı plan kapsamında.
- Bilgi veya dosya eksikse tahmin etme, sor.

## Şablonlar

### README.md

```markdown
# <Proje adı>

<Projenin 2-3 cümlelik tanımı: ne işe yarar, kim kullanır.>

## Hızlı bilgi
- Dil / altyapı: 
- Ana dosyalar: 
- Mimari ve işleyiş: [MIMARI.md](MIMARI.md)
- Planlar: [plan/](plan/)

## Değişiklik Günlüğü

### GG.AA.YYYY — <kısa başlık>
**Plan:** plan/GG_AA_YYYY_N.md
**Değişen dosyalar:**
- `dosya.php` — ne değişti
**Alınan kararlar:**
- Karar — nedeni
**Açık kalan işler:**
- ...
```

### MIMARI.md

```markdown
# <Proje adı> — Mimari ve İşleyiş

## 1. Genel bakış
Projenin amacı ve kapsamı.

## 2. Mimari
(Mermaid diyagramı: dosyalar/modüller ve birbirleriyle ilişkisi)

## 3. Dosyalar ve görevleri
| Dosya | Görevi | Kimden çağrılır | Neyi çağırır |
|---|---|---|---|

## 4. Ana akışlar / algoritmalar
Her önemli işlem için adım adım anlatım + Mermaid akış şeması (flowchart / sequenceDiagram).

## 5. Veri
Kullanılan tablolar, önemli alanlar, alanların anlamı ve hesap kuralları
(ör. "Boşta = cekiListesiID = 0 AND rezerveProjeID = 0").

## 6. Bilinen kısıtlar ve notlar

## 7. Hızlı yön bulma (hangi iş → nereye bakılır)
| Konu / ekran | Dosya | Fonksiyon / bölüm (yaklaşık satır) |
|---|---|---|
| ör. Stok özet kartları | `lib/stok_islemleri/stok_ozet.php` | ana SQL (~90), kartlar (~380) |
```

### plan/GG_AA_YYYY_N.md

```markdown
# Plan GG_AA_YYYY_N: <kısa konu>
Tarih: GG.AA.YYYY
Günün planı: N
Durum: Onay bekliyor | Onaylandı | Tamamlandı

## 1. Neden yapılıyor?
- **İstek:** <Kullanıcının istediği, kendi ifadesine yakın.>
- **Mevcut durum / sorun:** <Şu an nasıl çalışıyor, neden yetersiz veya hatalı.>
- **Yapılmazsa:** <Sorun devam ederse ne olur.>

## 2. Neyi değiştirecek?
| Dosya | Bölüm / fonksiyon / sorgu | Şu anki hâli | Yeni hâli |
|---|---|---|---|
| `dosya.php` | `fonksiyon_adi()` / satır ~120 | ... | ... |

**Kullanıcının göreceği fark:** <Ekranda / Excel'de / çıktıda neyin değişeceği.>
**Değişmeyecekler:** <Bilerek dokunulmayan, aynı kalacak şeyler.>

## 3. Yapılacaklar
- [ ] **<Adım 1 başlığı>**
  - Neden: <bu adım neden gerekli>
  - Ne değişecek: `dosya.php` → <bölüm>: <eski> → <yeni>
- [ ] **<Adım 2 başlığı>**
  - Neden: ...
  - Ne değişecek: ...
- [ ] **Doğrulama** — Neden: hatasız çalıştığından emin olmak. Ne: `php -l` / test / ekran kontrolü
- [ ] **Kayıtlar** — README günlüğü ve (gerekirse) MIMARI.md güncellemesi

## 4. Riskler / dikkat edilecekler
- ...

## 5. Sonuç
<İş bitince: ne yapıldı, ne test edilemedi, kullanıcının kontrol etmesi gerekenler.>
```

#### Örnek (doldurulmuş plan maddesi)

```markdown
- [x] **Paket sayısında boş paketleri sayma**
  - Neden: "1.641 modül / 1.753 paket" kafa karıştırıyor; modülü 0 olan boş paket kayıtları da sayılıyor.
  - Ne değişecek: `stok_ozet.php` → ana SQL, `b_paket` / `r_paket`:
    `SUM(CASE WHEN rezerveProjeID = 0 THEN 1 END)` → `SUM(CASE WHEN rezerveProjeID = 0 AND modulSayisi <> 0 THEN 1 END)`.
    Modül sayıları değişmez; yalnızca "… paket" yazıları düşer.
```

### Commit mesajı

```
<Kısa özet, en fazla ~60 karakter>

- <değişiklik 1> (neden: ...)
- <değişiklik 2> (neden: ...)

Plan: plan/GG_AA_YYYY_N.md
```
