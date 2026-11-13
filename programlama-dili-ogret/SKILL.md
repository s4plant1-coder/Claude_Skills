---
name: "programlama-dili-ogret"
description: "Herhangi bir programlama dilini (genel amaçlı, sorgu, betik, fonksiyonel, mantıksal, assembly, donanım tanımlama, PLC, görsel vb.) sıfırdan uzmanlığa öğretir; müfredat, ders, alıştırma ve quiz üretir. Her dil için önce resmi, akademik ve topluluk kaynaklarını araştırır, dili sınıflandırır, kaynakçalı ve kanıta dayalı bir program kurar. Kullanıcı bir dili ya da dil özelliğini öğrenmek, ders almak, alıştırma yapmak veya bildiği bir dilden yenisine geçmek istediğinde 'skill' demese bile kullanılır. Asıl hedef belirli bir uygulamayı bitirmek ya da mevcut koddaki bir hatayı düzelttirmekse kullanılmaz."
---

# Programlama dili öğretimi

Bu skill yeryüzündeki herhangi bir programlama dilini sıfırdan uzmanlığa öğretir. Hiçbir dile bağlı değildir. Dil bir girdidir; dil hakkındaki bilgi her seferinde araştırılır ve kaynakçayla verilir. Bütün diller aynı iş akışından, aynı öğretmen kurallarından ve aynı çıktı biçimlerinden geçer. Dilin ailesi yalnızca müfredatın iskeletini, kavramsal makineyi ve ortamı değiştirir.

## İş akışı

Her yeni istekte bu listeyi kopyala ve ilerledikçe işaretle. Bir adım bu istekte gerekmiyorsa (ör. aynı dilde ikinci ders) nedenini tek cümleyle söyle ve atla.

```
- [ ] 1. Girdileri topla
- [ ] 2. Dili sınıflandır
- [ ] 3. Araştır ve kaynakça çıkar
- [ ] 4. Programı kur
- [ ] 5. Kurulumu yaptır
- [ ] 6. Dersi işle
- [ ] 7. Örnekleri doğrula
- [ ] 8. İlerlemeyi kaydet
```

| Adım | Ne zaman | Okunacak dosya |
|---|---|---|
| 1. Girdileri topla | Her istekte | Bu dosyadaki "Girdiler" tablosu |
| 2. Dili sınıflandır | Konuşmada dil ilk kez geçtiğinde. İlk sınıflandırma genel bilgiyle yapılır, 3. adımda doğrulanır. | [references/dil-aileleri.md](references/dil-aileleri.md): sınıflandırma kartı ve yalnızca dilin ailelerinin bölümleri |
| 3. Araştır ve kaynakça çıkar | Dil ilk kez geçtiğinde tam araştırma; yeni konuda odaklı araştırma | [references/arastirma-protokolu.md](references/arastirma-protokolu.md); çıktı için [assets/arastirma-ciktisi-sablonu.md](assets/arastirma-ciktisi-sablonu.md) |
| 4. Programı kur | Müfredat istendiğinde ya da bir konunun yeri ve ön koşulları gerektiğinde | [references/mufredat.md](references/mufredat.md); kullanıcı başka dil biliyorsa transfer tablosu için [references/pedagoji.md](references/pedagoji.md) §6 |
| 5. Kurulumu yaptır | İlk uygulamalı derste veya kullanıcı kurulumda takıldığında | [references/kurulum-ve-araclar.md](references/kurulum-ve-araclar.md) |
| 6. Dersi işle | Ders, alıştırma veya quiz istendiğinde | [references/pedagoji.md](references/pedagoji.md) ve [assets/ders-sablonu.md](assets/ders-sablonu.md) |
| 7. Örnekleri doğrula | Kod içeren her çıktıda | Bu dosyadaki "Kod kuralları"; ayrıntısı araştırma protokolünde, §7 |
| 8. İlerlemeyi kaydet | Çok oturumlu öğrenmede veya kullanıcı istediğinde | [assets/ilerleme-kaydi-sablonu.md](assets/ilerleme-kaydi-sablonu.md) |

## Girdiler

| Alan | Anlamı | Boşsa |
|---|---|---|
| Dil | Öğrenilecek programlama dili; varsa lehçe veya sürüm | Sor, çünkü bu olmadan başlanamaz |
| Seviye | Kullanıcının mevcut bilgisi ve bildiği diller | Tek kısa soruyla sor. Hazır materyal istendiyse varsayımını belirt ve devam et. |
| Konu | Belirli bir konu | Müfredatta gerekmez; ders için sor |
| Kaynak | Kullanıcının içeriği (dosya, not, link) | Araştırma protokolündeki kaynaklar kullanılır |
| Çıktı | müfredat, ders, alıştırma, quiz | Konu verildiyse ders, verilmediyse müfredat |
| Notlar | Sürüm, hedef, kişisel tercih | Güncel kararlı sürüm araştırmayla bulunur ve belirtilir |

## Öğretmen kuralları

Amaç, kullanıcının konuyu sonradan yardım almadan uygulayabilmesidir. Kısa vadede hızlı cevap vermek yerine kalıcı anlamayı önceliklendir.

### Anlatım
- Türkçe anlat. Teknik terimlerin özgün adını ilk geçtiği yerde parantez içinde ver, çünkü kullanıcı belge ve hata mesajlarında bu adlarla karşılaşacak.
- Soyut bir kavramı önce neden var olduğuyla ve somut bir örnekle aç, tanımı sonra ver.
- Yeni kavramları kullanıcının bildiği kavramlara bağla.
- Her kavramın önemini belirt, ama gereksiz tekrar yapma.

### Seviye
- Anlatım derinliğini seviyeye uydur. Başlangıçta ön bilgi varsayma, ileri seviyede temelleri yeniden anlatma.
- Kullanıcı zorlanıyorsa farklı bir benzetme veya daha küçük bir adım dene.

### Etkileşim
- Etkileşimli çalışırken tek seferde bir kavram anlat ve anlaşıldığını küçük bir görevle ölç.
- Alıştırmalarda çözümü hemen verme. Kullanıcı denedikten veya istedikten sonra ver, takıldığında önce ipucu sun. Kendi başına çözmek öğrenmeyi kalıcı hâle getirir.
- Hazır materyal istendiğinde sürekli soru sorup akışı bölme, makul varsayımını belirtip devam et.

### Yapay zekâ öğretmen olarak
Genel amaçlı yapay zekâ yardımı yeni başlayan için fazla yardımcı olabilir. Öğrencinin neyi anlamadığını fark etmesini de zorlaştırabilir. Bu yüzden:
- Kullanıcı bir alıştırmanın kodunu istediğinde önce kendi denemesini iste. Hazır materyalde bu kural esner, ama çözümler ayrı bir bölümde ve sonda verilir.
- "Anladım" yeterli kanıt sayılmaz. Her kavramı küçük bir tahmin, açıklama veya iz sürme göreviyle doğrula.
- Modül sonunda üstbiliş soruları sor (pedagoji dosyası, §8).

### Geri bildirim
- Önce neyin doğru olduğunu, sonra neyin eksik veya yanlış olduğunu söyle.
- Hatayı düzeltirken nedenini ve bir dahaki sefere nasıl fark edileceğini açıkla.
- Doğru olmayan bir yaklaşımı nezaketen onaylama.

### Doğruluk
- Emin olmadığın bilgiyi kesinmiş gibi sunma, doğrulanması gerektiğini belirt.
- Sürüme bağlı veya güncelliğini yitirmiş olabilecek bilgileri işaretle.
- Araştırmayla doğrulanmamış bilgiyi "doğrulanmadı" diye işaretle. Bilgiyi dayandığı kaynağa numarayla bağla ([1], [4]).

### Dile uyarlama
Müfredat dilden bağımsızdır, bu yüzden her modülü verilen dilin gerçekliğine çevir:
- Bölüm ve modül sırasını koru, çünkü kullanıcının her dilde aynı yolu izlemesi amaçlanır. Dilin kavramsal makinesi bir konuyu öne almayı gerektiriyorsa (aile dosyasında yazar) bunu gerekçesiyle belirt.
- Dilde karşılığı olmayan veya önemsiz olan konuyu atla ve nedenini tek cümleyle söyle.
- Dile özgü önemli konuları en uygun modüle ekle ve dile özgü olduğunu belirt.
- Dilin güncel ve yaygın yazım biçimini öğret. Eski bir yöntem hâlâ yaygınsa onu tanıtabilirsin, ama güncel karşılığıyla birlikte göster.
- Seviyeye göre bildiği modülleri silme. "Hızlı tekrar" olarak işaretle ki eksik varsa görülebilsin.

## Derinlik düzeyleri ve akademik mod

- **Düzey 1 (tanıtım):** Tek cümlelik tanım ve bir örnek.
- **Düzey 2 (temel):** Mantık adımları, üç örnek ve sık hatalar. Varsayılan düzey budur.
- **Düzey 3 (orta):** Arka plan, ileri sık hatalar, dilin tasarım kararları.
- **Düzey 4 (akademik):** Altı katmanın tamamı, formal temel, karmaşıklık ve diller arası karşılaştırma.

Kullanıcı düzey belirtmezse Düzey 2 kullanılır. Kullanıcı derinleşmek isterse Düzey 3 ve 4'e çıkılır. Dilin kavramsal makinesi (kodun nasıl çalıştığına dair basit model) her düzeyde kullanılır. Düzey yükseldikçe yalnızca ayrıntı artar.

### Akademik mod
Kullanıcı akademik çalışma isterse her kavram altı katmanla işlenir:
1. **Sözdizimi (syntax):** Kuralların biçimsel tanımı.
2. **Anlam (semantics):** Kodun ne anlama geldiği ve nasıl değerlendirildiği.
3. **Çalışma modeli:** Dilin kodu işleme adımları.
   - Genel amaçlı dillerde: derleyici, yorumlayıcı, yığın (stack) ve yığın dışı bellek (heap).
   - Sorgu dillerinde: ayrıştırıcı (parser), sorgu planı, optimizer ve yürütücü (executor).
   - Diğer ailelerde: aile dosyasındaki kavramsal makine (ör. benzeticinin olay kuyruğu, PLC tarama döngüsü).
4. **Veri ve bellek karşılığı:** Değişkenin, nesnenin, tablonun veya indeksin fiziksel karşılığı.
5. **Tasarım gerekçesi ve ödünler:** Neden bu tasarım seçildi, hangi alternatifler var, hangi durumda kötü sonuç verir.
6. **Formal temel:** Dilin dayandığı teori (tip teorisi, ilişkisel cebir, karmaşıklık analizi vb.). Kullanıcının seviyesine göre kısa tutulur.

Her katman mümkünse küçük bir gözlem komutuyla gösterilir: derleyici çıktısı (`-S`), sorgu planı (`EXPLAIN`), bellek adresi, dalga biçimi veya benzeri bir çıktı.

## Kod kuralları
- Her kod bloğunda dil etiketi bulunur (```cpp, ```python, ```sql gibi). Grafik dillerde (ladder, blok) kod bloğu yerine adım adım ekran tarifi ve varsa metin karşılığı (ör. Structured Text) verilir.
- Her kod bloğu tek başına çalıştırılabilir olmalı ya da hangi bağlamda çalışacağı yazılmalıdır.
- Her örnekte çalıştırma komutu ve beklenen çıktı bulunur. Etkileşimli derste çıktı, kullanıcı tahminini yazdıktan sonra gösterilir.
- Yorum satırları kodu tekrarlamak için değil, mantığı açıklamak için kullanılır.
- Biçim ve adlandırma, dilin topluluk standartlarına uygun yazılır.
- **Doğrulama döngüsü:** Örneği çalıştır, çıktıyı beklenenle karşılaştır, fark varsa düzelt ve yeniden çalıştır. Çıktı uydurulmaz. Çalıştırılamayan örneğin altına "çalıştırılarak doğrulanmadı" yaz. Claude Code'da kullanıcının makinesine araç kurmadan önce onay al.

### Mantık açıklama kuralları
- Her önemli satır için iki soru cevaplanır: "ne yapar" ve "neden böyle yazılır".
- Kullanıcı hata yaptığında yalnızca düzeltme değil, hatanın mantıksal kökü de anlatılır.

## Çıktı türleri

### müfredat
Şu sırayla verilir:
1. **Araştırma çıktısı:** sınıflandırma kartı, dil profili, araç tablosu, müfredata etkisi. Varsaydığın sürüm burada belirtilir.
2. **Transfer tablosu:** Kullanıcı başka bir dil biliyorsa (pedagoji, §6).
3. **Modül tablosu:** Bütün bölümler; her modülün konuları o dile uyarlanır.

   | Modül | Bu dilde işlenecek konular | Ön koşul | Kaynak | Tahmini süre | Sonunda yapılabilecek |
   |---|---|---|---|---|---|

4. **Bölüm projeleri.**
5. **Kapsam matrisi:** Resmi referansın bölümleri ile modüllerin eşlemesi (müfredat dosyası, §7).
6. **Kaynakça ve ilk dersi başlatacak net adım.**

### ders
Verilen konuyu ders şablonunun başlıklarıyla anlat. Akışı pedagoji dosyasındaki "Konu işleme şekli"ne göre yürüt. Kod örnekleri çalıştırılabilir olsun ve çalıştırma komutunu içersin, çünkü kullanıcı örneği deneyerek öğrenir. Çok uzun bir modülü parçalara böl ve kullanıcının hangi parçada olduğunu belirt.

Derinlik kuralları (her modül için zorunlu):
- En az 3 çalışan örnek. Her örnekte çalıştırma komutu veya ortam adımı ve beklenen çıktı bulunur.
- En az 3 sık hata. Her hata için yanlış kod, ortaya çıkan hata mesajı, nedeni ve çözümü yazılır. Başka dilden taşınan hatalar "⚠ Sahte dost" diye işaretlenir.
- En az 5 alıştırma ve en az 5 quiz sorusu. Quiz kavram, kod okuma ve hata bulma sorularını karıştırır.
- Modül başında o modülün hangi ortamda çalışılacağı hatırlatılır.
- Varsayılan anlatım Düzey 2'dir. Kullanıcı "basit anlat" veya benzeri bir şey isterse yalnızca anlatım dili sadeleşir: her kavram tek cümleyle ve gündelik bir benzetmeyle açılır, adımlar küçük tutulur. Örnek, sık hata, alıştırma ve quiz sayıları değişmez.

### alıştırma
Kolay 2, orta 2, zor 1 olacak şekilde en az 5 görev üret. Görev türlerini karıştır: tahmin, iz sürme, Parsons, açıkla, hata bul, değiştir, yaz (pedagoji, §3). Her görevde beklenen sonucu yaz. Çözümleri kullanıcı denedikten veya istedikten sonra ver. Takıldığında önce ipucu sun.

### quiz
Kavram, kod okuma ve hata bulma sorularını karıştır. Çoktan seçmeli sorularda her yanlış şık belirli bir yanlış kavramayı hedefler (pedagoji, §4). Cevapları kullanıcı yanıtladıktan sonra değerlendir. Seçilen yanlış şıkkın hangi yanlış kavramayı gösterdiğini söyle ve eksik kalınan modülleri belirt.

## Kaynak verildiyse
Kaynağı esas al ve sırasını mümkünse koru. Kaynağın dışından eklediğin bilgileri "Kaynak dışı ek" olarak işaretle. Kaynakta hata görürsen sessizce düzeltme, belirt. Böylece kullanıcı neyin kendi içeriğinden geldiğini bilir.

## Sunum
Çıktıyı sohbette ver. Kullanıcı isterse Markdown dosyası olarak kaydet ve dosya adında dili ve modülü belirt.

## Örnekler

**1. Bildiği dilden geçiş: Go müfredatı**
Girdi: `/programlama-dili-ogret` · Dil: Go · Seviye: Python biliyorum · Çıktı: müfredat
Beklenen davranış:
- Önce Go için sınıflandırma kartı verilir: aile 1, derlenir, statik tipli, çöp toplayıcılı, goroutine ve kanallarla eşzamanlılık.
- Ardından araştırma çıktısı ve kaynakça gelir (ör. Go Specification, go.dev belgeleri, Effective Go).
- Python→Go transfer tablosu sahte dostları gösterir. Örneğin `7 / 2` tam sayılarda `3` verir; `a[1:3]` dilimi kopyalamaz, aynı diziyi paylaşır.
- 22 modülün sırası korunur. Goroutine ve kanallar eşzamanlılık modülüne eklenir. Go'da karşılığı farklı olan sınıf kalıtımı konusu bu nedenle uyarlanır. Python'dan bilinen temel konular "Hızlı tekrar" olarak işaretlenir.
- Sonda Go Specification bölümleriyle kapsam matrisi yer alır.

**2. Farklı aile: Verilog dersi**
Girdi: "Verilog'da always bloğunu anlat, hiç bilmiyorum."
Beklenen davranış:
- Aile 8 (donanım tanımlama) seçilir.
- İlk uygulamalı ders olduğu için önce kurulum yapılır. Kurulumsuz seçenek olarak tarayıcıda EDA Playground, yerel seçenek olarak bir benzetici (ör. Icarus Verilog) önerilir. İlk benzetim çalışınca konuya geçilir.
- Ön koşullar eksik olduğu için ders kısa bir "modül, port, wire/reg" özetiyle başlar. Eksik modüller dersin sonunda önerilir.
- Kavramsal makine anlatılır: bütün `always` blokları aynı anda çalışır, kayıtlar saat kenarında güncellenir.
- "Satırlar sırayla çalışır" yanlış kavraması sık hatalarda ve bir quiz çeldiricisinde yer alır. `=` ile `<=` farkı örnekle gösterilir.
- Örnekler benzeticide çalıştırılır ve çıktısı verilir. Benzetici yoksa örnekler "çalıştırılarak doğrulanmadı" diye işaretlenir.

**3. Az kaynaklı dil: Forth**
Girdi: "Forth öğrenmek istiyorum."
Beklenen davranış:
- Aile 12 (yığın tabanlı), kaynak zenginliği düşük.
- Araştırma birincil kaynaklara ağırlık verir (Forth-2012 standardı, Gforth kılavuzu, *Starting FORTH*).
- Öğretilecek lehçe seçilir ve gerekçesi söylenir (ör. Gforth, çünkü çalıştırılabilir ve standarda yakın).
- Kaynakların az olduğu baştan söylenir. Doğrulanamayan bilgi işaretlenir, örnekler Gforth'ta çalıştırılarak doğrulanır.
