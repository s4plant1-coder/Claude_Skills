# Araştırma protokolü

Bu dosya iş akışının 3. adımında okunur. Amaç, dil hakkında verilen her bilgiyi güncel kaynaklara dayandırmak ve kaynakçayla göstermektir. Skill hiçbir dile bağlı değildir. Sabit tablolar yalnızca başlangıç örneğidir, asıl bilgi araştırmadan gelir.

## İçindekiler
1. Ne zaman, ne kadar
2. Kaynak türleri
3. Arama kalıpları
4. Kaynak değerlendirme
5. Az kaynaklı, tarihsel ve ezoterik diller
6. Resmi referansın içindekilerini çıkarma
7. Kod doğrulama döngüsü
8. Araştırma çıktısı ve kaynak gösterme

## 1. Ne zaman, ne kadar

| Durum | Araştırma |
|---|---|
| Konuşmada bu dil için ilk kez müfredat isteniyor | Tam araştırma, resmi referansın içindekiler tablosu dahil (§6) |
| Konuşmada bu dil ilk kez bir ders, alıştırma veya quiz için geçiyor | Tam araştırma, ama içindekiler tablosu çıkarılmaz. Kullanıcıya kısa çıktı verilir (araştırma çıktısı şablonundaki not). |
| Aynı dilde yeni bir konu için ders, alıştırma veya quiz isteniyor | Yalnızca o konuya odaklı araştırma: resmi belgenin ilgili bölümü, o konudaki sık hatalar, akademik kaynaklardaki anlatım sırası |
| Kullanıcı bir ilerleme kaydı getirdi ve kayıtta kaynakça var | Tam araştırma tekrarlanmaz. Yalnızca sürüm değişikliği ve yeni konu kontrol edilir. |
| Web erişimi yok | Kullanıcıya açıkça söylenir. Genel bilgiyle devam edilir, doğrulanmamış her bilgi "doğrulanmadı" diye işaretlenir. |

**Kaynak zenginliğine göre derinlik.** Dil modellerinin bilgisi, eğitim verisinde az bulunan dillerde belirgin biçimde zayıftır. Bu yüzden araştırmanın derinliği dilin kaynak zenginliğine göre ayarlanır:

| Kaynak zenginliği | Belirtisi | Araştırma |
|---|---|---|
| Yüksek | Kapsamlı resmi belge, çok sayıda kitap ve ders, yapılandırılmış öğrenme yolları | Asgari kaynak sayısı yeterli. Topluluk kaynağı bol olduğu için seçici olunur. |
| Orta | Resmi belge var, öğretici ve ders az | Birincil kaynağa ağırlık verilir. Akademik ve topluluk kaynağı ne bulunursa kullanılır. |
| Düşük | Dağınık veya arşivlenmiş belgeler, az örnek kod | Bölüm 5 uygulanır. Her iddia bir kaynağa bağlanır. Örnekler mutlaka çalıştırılarak doğrulanır. |

## 2. Kaynak türleri

Tam araştırmada dört ana türün her biri taranır. Asgari olarak 3 birincil, 2 akademik ve 2 topluluk kaynağı incelenir. Bu sayıya ulaşılamazsa eksik tür kaynakçada belirtilir.

| Tür | Örnek kaynaklar | Ne için kullanılır | Dikkat |
|---|---|---|---|
| Birincil | Spesifikasyon veya standart (ISO, ECMA, IEC), resmi belge ve öğretici, sürüm notları, resmi stil rehberi, dil geliştirme önerileri (PEP, RFC, JEP, TC39 vb.) | Doğru söz dizimi, güncel kararlı sürüm, resmi terimler, kapsam matrisi | Eski sürüm belgesi yanıltabilir |
| Akademik | Üniversite ders izlenceleri (syllabus), ders notları, ders kitapları, dilin tasarım makaleleri, HOPL konferans makaleleri | Konu sırası, formal temel, tasarım gerekçesi | Ders izlencesi belirli bir dönemin sürümüne ait olabilir |
| Topluluk | Exercism dil müfredatı, Rosetta Code, "Learn X in Y minutes", yaygın kitaplar, soru-cevap siteleri, "gotchas" listeleri | Sık hatalar, deyimsel (idiomatic) kullanım, gerçek kullanım alanları | Tek tek yorumlar genellenemez |
| Ekosistem | Derleyici veya yorumlayıcı (resmi ve yaygın alternatifler), paket yöneticisi, test aracı, biçimlendirici, statik analiz, hata ayıklayıcı, çevrimiçi deneme ortamı | Araç tablosu, kurulum, derleyici tablosunun doğrulanması | Araç adları ve kurulum yolları sık değişir |
| Az kaynaklı ve tarihsel | HOPL, PLDB, arşivlenmiş kılavuzlar, esolangs wiki, benzeticiler, açık kaynak yorumlayıcıların belgeleri | Bölüm 5'teki durumlar | Kaynağın az olduğu açıkça söylenir |

"İnternetteki tüm kaynaklar" tek tek okunamaz. Bunun yerine her tür sistematik olarak taranır ve neye bakıldığı kaynakçada gösterilir. Kullanıcıya da bu şekilde anlatılır.

## 3. Arama kalıpları

`<dil>` yerine dilin adı, `<bildiği>` yerine öğrencinin bildiği dil yazılır. Aramalar İngilizce ve Türkçe yapılır. Türkçe arama, terimlerin yerleşik Türkçe karşılıklarını bulmak için de kullanılır.

- **Birincil:** `<dil> language specification`, `<dil> reference manual`, `<dil> official tutorial`, `<dil> release notes`, `<dil> style guide`, `<dil> enhancement proposals`
- **Akademik:** `<dil> course syllabus`, `<dil> lecture notes`, `<dil> textbook`, `<dil> design rationale paper`, `history of <dil> HOPL`
- **Topluluk:** `<dil> gotchas`, `<dil> common beginner mistakes`, `<dil> pitfalls`, `exercism <dil>`, `learn x in y minutes <dil>`, `rosetta code <dil>`
- **Ekosistem:** `<dil> install`, `<dil> package manager`, `<dil> testing framework`, `<dil> formatter linter`, `<dil> debugger`, `<dil> online playground`
- **Transfer** (öğrenci başka dil biliyorsa): `<bildiği> to <dil> differences`, `<dil> for <bildiği> programmers`, `<bildiği> developers learning <dil> pitfalls`
- **Türkçe:** `<dil> dersleri`, `<dil> türkçe kaynak`, `<kavram> türkçe karşılığı`

## 4. Kaynak değerlendirme

- Her kaynak için şunlar not edilir: türü, yayın veya güncelleme tarihi, anlattığı sürüm ve güvenilirlik düzeyi (resmi, hakemli, uzman, topluluk).
- Birincil kaynakla çelişen bilgi kullanılmaz. Çelişki araştırma çıktısının "Belirsizlikler" bölümüne yazılır.
- Eski sürüme ait bilgi "eski sürüm" diye işaretlenir.
- Bir sık hata iddiası resmi belgede veya en az iki bağımsız kaynakta geçmelidir. Tek bir forum yorumu genellenmez.
- Kaynağı belirsiz kopya siteler kaynak sayılmaz.
- **Popülerlik endeksleri farklı şeyler ölçer:**
  - TIOBE: arama motoru sonuç sayısı
  - PYPL: Google'da öğretici aranma sıklığı
  - RedMonk: GitHub ve Stack Overflow etiketleri
  - IEEE Spectrum: birden çok kaynağın ağırlıklı birleşimi

  Bu endeksler "en iyi dil" kanıtı olarak değil, yalnızca ekosistemin canlılığı için bir sinyal olarak kullanılır.

## 5. Az kaynaklı, tarihsel ve ezoterik diller

- **Kaynaklar:** HOPL (hopl.info), PLDB (pldb.io), arşivlenmiş kılavuzlar (archive.org, bitsavers.org), esolangs wiki, üniversite arşivleri, benzeticilerin ve açık kaynak yorumlayıcıların belgeleri.
- **Lehçe seçimi:** Öğretilecek lehçe ve sürüm baştan seçilir. Gerekçesi söylenir; çoğu zaman bu gerekçe çalıştırılabilir bir uygulamanın bulunmasıdır.
- **Dürüstlük:** Kaynakların az olduğu kullanıcıya baştan söylenir. Doğrulanamayan bilgi işaretlenir. Kendi bilgine, yaygın dillere göre daha az güvenilir.
- **Doğrulama:** Örnekler mutlaka bir yorumlayıcı veya benzeticide çalıştırılır. Çalıştırılamıyorsa bu açıkça belirtilir.
- **Tarihsel dillerde** günümüzdeki kullanım ve bakım bağlamı da verilir: hangi sektörde yaşıyor, kod nasıl modernleştiriliyor.

## 6. Resmi referansın içindekilerini çıkarma

Bu, kapsam matrisinin dayanağıdır. Matrisin nasıl kurulacağı müfredat dosyasındadır.

1. Dilin resmi referansı belirlenir. Bu bir standart (ISO, ECMA, IEC), bir spesifikasyon (ör. Go Specification, Java Language Specification) ya da bir dil başvuru kılavuzu (ör. Python Language Reference) olabilir. Standart yoksa ana uygulamanın başvuru kılavuzu kullanılır ve bu belirtilir.
2. Standart ücretliyse son taslak sürümü veya yaygın kabul gören bir topluluk referansı kullanılır (ör. C++ için standart taslakları ve cppreference). Bu durum da belirtilir.
3. Referansın ve standart kütüphane dizininin bölüm başlıkları, genellikle ikinci düzeye kadar, listelenir.
4. Liste araştırma çıktısının "Kapsam matrisi özeti" bölümüne aktarılır.

## 7. Kod doğrulama döngüsü

- **Claude Code'da** örnekler yerel makinede çalıştırılır. Gerekli araç kurulu değilse kurulum için önce kullanıcının onayı alınır.
- **claude.ai'de** kod çalıştırma ortamı varsa örnekler orada çalıştırılır. Ortamda derleyici yoksa ve kurulamıyorsa örnek işaretlenir.
- **Döngü:** çalıştır → gerçek çıktıyı beklenen çıktıyla karşılaştır → fark varsa örneği veya açıklamayı düzelt → tekrar çalıştır.
- Çıktı uydurulmaz. Yazılan çıktı ya gerçek bir çalıştırmadan gelir ya da "beklenen çıktı (çalıştırılarak doğrulanmadı)" diye etiketlenir.
- Çalıştırmada kullanılan derleyici veya yorumlayıcının sürümü not edilir.
- **Grafik veya donanım ortamlarında** (PLC, blok dilleri, FPGA) doğrulama, varsa metin karşılığıyla ya da bir benzeticiyle yapılır. İkisi de yoksa örnek işaretlenir.

## 8. Araştırma çıktısı ve kaynak gösterme

- Araştırma çıktısı, araştırma çıktısı şablonuyla (`assets/arastirma-ciktisi-sablonu.md`) müfredattan önce kullanıcıya verilir.
- Kaynakça numaralıdır. Müfredat ve derslerde bilgi, dayandığı kaynağa `[1]`, `[4]` gibi numaralarla bağlanır.
- Numaralar konuşma boyunca ve ilerleme kaydında sabit kalır. Yeni bulunan kaynak bir sonraki numarayı alır.
- Odaklı araştırmada yalnızca yeni kaynaklar kaynakçaya eklenir. Kaynakçanın tamamı yeniden yazılmaz.
- Konuya odaklı derslerde araştırma özeti birkaç satırla sınırlı tutulur: hangi kaynağa bakıldı, ne doğrulandı.
