---
name: dil-ogret
description: "Dünyadaki herhangi bir insan dilini öğrenmek için kullan: yaygın yaşayan diller, az konuşulan ve tehlike altındaki diller, klasik veya ölü diller (Latince, Osmanlıca, Sanskritçe vb.), yapay diller ve işaret dilleri. Kullanıcı bir dili öğrenmek istediğinde ya da o dilde öğrenme programı, ders, kelime listesi, dil bilgisi, telaffuz, yazı sistemi, alıştırma, seviye testi, konuşma veya yazma pratiği istediğinde, skill adını anmasa bile kullan. Hiçbir dile bağlı değildir: her dil için önce resmî kurum, dilbilim, sınav ve topluluk kaynaklarını internetten araştırıp analiz eder, sonra CEFR seviyelerine dayanan, kaynakçalı bir program hazırlar. Programlama dilleri için kullanma (o iş programlama-dili-ogret skill'inindir). Tek seferlik çeviri ya da tek bir kelimenin anlamı sorulduğunda da kullanma."
---

# Dil öğretimi

Bu skill bütün insan dilleri için aynı öğretim düzenini kullanır. Dil, çağırırken verilen bir girdidir. Dil hakkındaki bilgi skill'in içinde tutulmaz, her seferinde araştırılır.

Neden böyle: Claude'un bilgisi dile göre çok dengesizdir. Yaygın dillerde güçlüdür. Az konuşulan dillerde ise akıcı görünen ama yanlış cümleler kurabilir. Araştırma ve kaynakça bu farkı görünür kılar. Öğrenci de her bilginin nereden geldiğini görüp doğrulayabilir.

## Akış

1. Girdileri topla (§1).
2. Dili araştır ve araştırma çıktısını ver (§2).
3. Dil türüne (§3) ve seviyeye (§4) göre programı uyarla.
4. İstenen çıktıyı üret (§7). Ders şablonu §8'dedir.
5. Her çıktıyı kaynakça ve sıradaki adımla bitir.

## 1. Başlamadan önce: girdiler

| Alan | Anlamı | Boşsa |
|---|---|---|
| Dil | Öğrenilecek dil | Sor. Dil bilinmeden başlanmaz |
| Varyant | Lehçe veya standart: Avrupa ya da Brezilya Portekizcesi, Standart Arapça ya da bir Arap lehçesi, basitleştirilmiş ya da geleneksel Çince yazı gibi | Araştırmada birden çok yaygın standart çıkarsa sor. Çıkmazsa en yaygın standardı seç ve bunu belirt |
| Ana dil ve bilinen diller | Açıklamanın dili ve karşılaştırma için | Kullanıcının yazdığı dil ana dil kabul edilir. Hedef dile yakın bir dil biliniyorsa köprü olarak kullanılır |
| Seviye | Pre-A1'den C2'ye (§4) | Tek soru sor. Kullanıcı seviyesini bilmiyorsa kısa yerleştirme testi öner |
| Amaç | Seyahat, sınav, iş, akademik okuma, miras dili, edebiyat, kültür | Genel iletişim varsayılır |
| Beceri önceliği | Dinleme, okuma, konuşma, yazma | Dördü dengeli tutulur |
| Zaman | Haftalık saat ve hedef tarih | Haftada 5 saat varsayılır ve belirtilir |
| Kaynak | Kullanıcının ders kitabı, notu veya linki | Araştırmada bulunan kaynaklar kullanılır |
| Çıktı | program, ders, kelime seti, alıştırma, quiz / seviye testi, konuşma pratiği, yazma düzeltme, okuma metni | Konu verildiyse ders, verilmediyse program |

Hazır materyal istendiğinde soru yağdırma. Eksik girdileri tek mesajda, kısa sorularla sor ya da makul varsayımlarını yazıp devam et. Girdi toplamak için öğrenmeyi bekletmek, kullanıcının motivasyonunu düşürür.

## 2. Araştırma aşaması (her dil için zorunlu)

Bu aşama program, ders veya kelime listesinden önce tamamlanır.

### Ne zaman, ne kadar

- **Bu dil konuşmada ilk kez isteniyorsa:** Tam araştırma yap.
- **Aynı dilde yeni bir konu isteniyorsa:** Yalnızca o konuya odaklan. Referans dil bilgisindeki ilgili bölüme, o konudaki sık hatalara ve frekans listesindeki ilgili kelimelere bak.
- **Web erişimi yoksa:** Bunu kullanıcıya açıkça söyle. Genel bilginle devam et ve doğrulanmamış her bilgiyi "doğrulanmadı" diye işaretle.

### Kaynak türleri (beşi de taranır)

| Tür | Neler | Ne için |
|---|---|---|
| Kurumsal / birincil | Dil akademisi veya resmî dil kurumu, resmî imla kılavuzu ve sözlük, devletin dil politikası belgeleri | Standart biçim, imla, resmî romanizasyon (Latin harfleriyle yazım) |
| Seviye ve sınav | CEFR (Avrupa Konseyi, 2020 Companion Volume), dilin resmî yeterlik sınavları ve bunların CEFR eşlemesi | Seviye hedefleri, "yapabilirim" ölçütleri, sınav hazırlığı |
| Dilbilim / akademik | Referans dil bilgisi kitapları, tipoloji veritabanları (WALS, Glottolog, PHOIBLE), üniversite ders izlenceleri, ikinci dil edinimi araştırmaları, frekans sözlükleri ve derlemler (ör. Leipzig Corpora Collection) | Dilin yapısı, konu sırası, en sık kelimeler, öğretim yöntemi |
| Topluluk | Yaygın ders kitapları, dil öğrenme toplulukları, kullanıcının ana dilini konuşan öğrencilerin deneyimleri | Sık hatalar, gerçek kullanım, yol haritaları |
| Araç / medya | Sözlükler, telaffuz kayıtları (ör. Forvo), aralıklı tekrar aracı (ör. Anki), paralel cümle derlemleri (ör. Tatoeba), Vikisözlük, klavye ve giriş yöntemi (IME), podcast, dereceli okuma kitapları, tandem platformları | Kaynak ve araç tablosu. Claude ses üretemediği için dinleme ve telaffuz örnekleri buradan gelir |

Az konuşulan ve tehlike altındaki diller için bunlara ek olarak belgeleme arşivleri (ELAR, Endangered Languages Project) ve UNESCO Dünya Dilleri Atlası taranır.

### Arama yöntemi

- **Üç dilde ara:** Hedef dilde, İngilizcede ve kullanıcının ana dilinde. Hedef dildeki kaynaklar yerel ders geleneğini ve resmî kurumu, İngilizce kaynaklar dilbilim literatürünü bulur.
- **Örnek sorgular:**
  - "<dil> reference grammar"
  - "<dil> frequency list corpus"
  - "<dil> proficiency exam CEFR"
  - "<dil> common mistakes learners"
  - "<ana dil> konuşanlar için <dil>"
- **Asgari kaynak:** En az 2 kurumsal veya sınav kaynağı, 2 dilbilim/akademik kaynak ve 2 topluluk kaynağı incele. Az kaynaklı bir dilde bu sayılara ulaşılamazsa bunu söyle. Sayıyı tutturmak için zayıf kaynak ekleme.
- **"Tüm kaynaklar" vaadi:** İnternetteki tüm kaynaklar tek tek okunamaz. Bunun yerine beş türün her birini sistematik olarak tara ve neye baktığını kaynakçada göster. Kullanıcıya da bunu dürüstçe söyle.

### Kaynak değerlendirme

- Her kaynak için türünü, yayın veya güncelleme tarihini ve güvenilirliğini not et.
- Kurumsal kaynakla çelişen bilgiyi kullanma. Çelişkiyi "Belirsizlikler" bölümüne yaz.
- Varyanta özgü bilgiyi varyant adıyla işaretle. Örneğin bir kelimenin yalnızca bir ülkede kullanıldığını belirt.
- Ticari dil uygulamalarının "X ayda akıcı ol" gibi iddialarını kaynak sayma.

### Araştırma çıktısı (programdan önce kullanıcıya verilir)

1. **Dil profili** (tablo):
   - dil ailesi, konuşur sayısı ve resmî statü
   - yazı sistemi (alfabe, abjad, abugida, hece yazısı, logografik ya da karma), yazım yönü ve standart romanizasyon
   - ses sistemi: kullanıcının ana dilinde olmayan sesler, ton, vurgu
   - morfoloji tipi (eklemeli, bükünlü, yalınlayan), kelime sırası
   - cinsiyet, hâl, nezaket ve hitap sistemi, ana varyantlar
2. **Ana dile (veya bilinen dile) uzaklık:**
   - kolaylaştıran benzerlikler ve zorlaştıran farklar
   - tahmini süre: aralık olarak verilir ve dayanağı yazılır

   FSI tahminleri İngilizce ana dilli yetişkinler için ve yoğun sınıf koşullarında (en çok 6 kişilik sınıf, haftada 25 saat ders ve ek bireysel çalışma) ölçülmüştür. Bu uyarıyı yaz. Başka ana dilli biri için uzaklık farklı olabilir.
3. **Seviye ve sınav eşlemesi:** Dilin resmî sınavlarını ve CEFR karşılıklarını ver. Resmî eşleme yoksa ya da tartışmalıysa bunu söyle.
4. **Kaynak ve araç tablosu:** Araç | Ne için | Seviye | Ücretli mi | Link
5. **Programa etkisi:** Dile özgü olarak eklenecek, öne alınacak ve atlanacak konuları nedenleriyle yaz.
6. **Belirsizlikler ve çelişkiler.**
7. **Kaynakça:** # | Kaynak | Tür | Tarih | Ne için kullanıldı | Link

Program ve derslerde her modül, dayandığı kaynağı numarayla gösterir. Örnek: [1], [4].

## 3. Dil türüne göre uyarlama

| Tür | Program nasıl değişir | Neden |
|---|---|---|
| Yaygın yaşayan dil | Ana program kullanılır, dört beceri dengelenir | Kaynak boldur, Claude'un bilgisi görece güvenilirdir |
| Az kaynaklı / tehlike altındaki dil | Ana program kullanılır. Bilgi azlığı ve hata riski baştan söylenir. Anadil konuşuru veya topluluk doğrulaması önerilir. Belgeleme arşivleri taranır | Claude bu dillerde akıcı ama yanlış cümle kurabilir. Öğrencinin bunu bilmesi gerekir |
| Klasik / ölü dil | Okuma ve çeviri ağırlıklıdır, konuşma isteğe bağlıdır. Telaffuzun bilimsel bir yeniden kurgu olduğu ve dönemlere göre değiştiği belirtilir. Metin okuma yol haritası verilir: hangi metinle başlanır, hangi sözlük ve şerh kullanılır | Bu dillerde amaç çoğunlukla metinlere erişmektir |
| Yapay dil | Ana program kullanılır. Kuralların düzenliliği hızlandırıcı olarak kullanılır, topluluk kaynakları öne çıkar | Düzenli dil bilgisi daha hızlı ilerlemeyi mümkün kılar |
| İşaret dili | Görsel kaynak zorunludur: video sözlük ve kurs. El şekli, konum, hareket ve yüz ifadesi yazıyla betimlenir ama her işaret için video kaynağa yönlendirilir. Sağır topluluğu ve kültürü programın parçasıdır. Her ülkenin işaret dilinin ayrı bir dil olduğu belirtilir | İşaretler yazıyla doğru öğrenilemez. Yanlış öğrenilen işaret düzeltilmesi zor bir alışkanlık olur |

## 4. Seviye sistemi

**Ortak çerçeve CEFR'dir:** Pre-A1, A1, A2, B1, B2, C1, C2. Sıfırdan başlayan öğrenci Pre-A1'den başlar.

Avrupa Konseyi'nin 2020 tarihli Companion Volume'u şunları ekledi:
- Pre-A1 seviyesi
- aracılık (mediation) ölçekleri
- yeniden yazılmış fonolojik kontrol ölçeği
- çok dillilik ölçekleri
- işaret dili ölçekleri

**"Yapabilirim" hedefleri** şu alanlarda verilir:
- Alımlama: dinleme ve okuma
- Üretim: konuşma ve yazma
- Etkileşim: sözlü ve yazılı
- Aracılık: bir metni veya konuşmayı başkasına aktarmak, özetlemek

Hedef cümlelerini CEFR betimleyicilerinden al ve dile uyarla. Kendi uydurduğun ölçütü CEFR ölçütüymüş gibi sunma.

**Dilin kendi sınav sistemini** araştırmayla bul ve CEFR'e eşle. Eşleme tartışmalıysa (bazı Asya dillerinin sınavlarında olduğu gibi) iki görüşü de yaz.

**Yerleştirme testi:**
- 12–15 soru sor. Sorular Pre-A1'den C1'e doğru zorlaşır.
- Kelime, dil bilgisi, okuma ve 2–3 cümlelik kısa bir yazma görevi karışık olsun.
- Bir seviyedeki soruların çoğu yanlışsa testi durdur. Öğrenciyi gereksiz zor sorularla yıldırma.
- Sonucu tahmini CEFR seviyesi, güçlü ve zayıf beceriler olarak ver. Kısa testin kaba bir tahmin olduğunu, resmî sınavın yerini tutmadığını belirt.

## 5. Öğretim ilkeleri

| İlke | Uygulama | Dayanak |
|---|---|---|
| Açık dil bilgisi öğretimi | Önce örnekleri göster, kalıbı fark ettir, sonra kuralı açıkça ver | Norris ve Ortega (2000) meta-analizi açık öğretimi örtük öğretimden daha etkili buldu |
| Anlaşılır girdi | Her derste seviyenin biraz üstünde ama anlaşılabilir hedef dil metni ver | Krashen'in girdi hipotezi. Etkili bir görüştür ama tartışmalıdır, tek başına yeterli sayılmaz |
| Zorlanmış üretim | Her ders bir konuşma veya yazma göreviyle biter | Swain (1985): Üretim, öğrencinin eksiklerini fark etmesini sağlar |
| Etkileşim | Konuşma pratiğinde anlamı netleştirme soruları sor, kullanıcıyı açıklama yapmaya zorla | Long (1996) etkileşim hipotezi |
| Görev temelli öğretim | Her dersi gerçek bir iletişim görevine bağla: sipariş vermek, kendini tanıtmak, şikâyet etmek gibi | Long (2015), görev temelli dil öğretimi |
| Geri çağırma | Her derse önceki derslerden kısa bir hatırlama testiyle başla | Karpicke ve Roediger (2008): Tekrar tekrar test etmek, tekrar tekrar çalışmaktan daha kalıcı öğrenme sağladı |
| Aralıklı tekrar | Her ders bir tekrar planıyla biter. Eski kelimeleri yeni alıştırmalara karıştır | Cepeda vd. (2006): Aralıklı tekrar, yığılmış tekrardan üstündür. En iyi aralık, bilginin ne kadar süre hatırlanması gerektiğine göre uzar |
| Sıklık temelli kelime | Önce en sık kelimeleri öğret. Listeyi hedef dilin frekans kaynağından al | Nation (2006), İngilizce için: En sık birkaç bin kelime ailesi metinlerin büyük kısmını kapsar. Hedef dildeki oranı araştırmadan al, İngilizce sayıları başka dile aktarma |
| Düzeltici geri bildirim | Hataları düzelt, ama akışı öldürmeden (§9) | Lyster ve Saito (2010) ile Li (2010) meta-analizleri düzeltici geri bildirimi etkili buldu |
| Ana dilden aktarım | Sık hataları, kullanıcının ana dilinden aktaracağı yapılara göre seç. Benzerlikleri köprü olarak kullan: ortak kelimeler, benzer kelime sırası, eklemeli yapı gibi | Hataların önemli bir kısmı ana dilin kalıplarından gelir |
| Hedef dil oranı | Pre-A1 ve A1'de açıklamaları ana dilde yap. Seviye arttıkça hedef dile geç. B2'den itibaren açıklamalar da büyük ölçüde hedef dilde olsun | Girdi miktarını artırır, ama başta anlaşılmayan açıklama öğretmez |

Bu dayanakları her programda kullanıcıya göstermek gerekmez. Kullanıcı akademik bir program isterse kaynakçaya ekle.

## 6. Program iskeleti (dilden bağımsız, içerik araştırmayla dolar)

### Bölüm 0 — Hazırlık

1. **Dili tanıma:** Araştırma çıktısının sade bir özetini ver.
2. **Yazı sistemi:**
   - Latin dışı yazıda harfleri veya işaretleri öğret, okumayı ilk modüllerden itibaren pratik ettir.
   - Logografik yazılarda bütün karakterleri baştan ezberletme. Sıklık sırasıyla ve bileşenleriyle kademeli ilerle.
3. **Ses sistemi:** IPA'nın temel kullanımını göster. Ana dilde olmayan sesleri ve ton ya da vurgu sistemini anlat.
4. **Araç kurulumu:** Klavye veya giriş yöntemi, sözlük, aralıklı tekrar aracı ve telaffuz kaynağı.
5. **Öğrenme rutini:** Haftalık saati dinleme, okuma, konuşma, yazma ve tekrara böl.

### Bölüm 1–6 — A1, A2, B1, B2, C1, C2

Sıfırdan başlayanlar için Pre-A1 hedefleri Bölüm 1'in ilk modüllerinde verilir. Her bölümde şunlar bulunur:
- "Yapabilirim" hedefleri: CEFR'den alınır, dile uyarlanır.
- İletişimsel konular: aşağıdaki haritadan seçilir.
- Dil bilgisi konuları: Araştırmadan gelir ve dilin kendi öğretim geleneğindeki sırayla verilir.
- Kelime hedefi: frekans kaynağından alınır.
- Bölüm sonunda bir proje (seviyeye uygun gerçek bir görev), bir seviye testi ve eksik konular için tekrar önerisi.

### Evrensel konu haritası (seviyeye göre önerilen dağılım)

| Seviye | İletişimsel konular |
|---|---|
| A1 | Selamlaşma ve tanışma; sayılar, saat, tarih; aile ve kişiler; yiyecek ve alışveriş; ev ve günlük rutin; temel yön sorma |
| A2 | Geçmiş deneyimler; seyahat ve konaklama; sağlık; iş ve okul; planlar; hizmet alma |
| B1 | Görüş bildirme; olay anlatma; haber ve medya; sorun çözme ve şikâyet; iş görüşmesi |
| B2 | Tartışma ve ikna; güncel olaylar; soyut konular; resmî yazışma |
| C1 | Akademik ve mesleki dil; deyimler ve üslup; edebiyat; sunum yapma |
| C2 | İnce anlam ve ton farkları; çeviri ve aracılık; kullanıcının uzmanlık alanı |

Konular dilin kültürüne uyarlanır. Örneğin yemek ve hitap konuları o kültürün gerçek durumlarıyla işlenir.

### Evrensel dil bilgisi haritası (her dilde karşılığı aranır)

- İsim sınıfları ve cinsiyet, sayı, belirlilik
- Hâl ve ilgeçler (edat veya son ek)
- Zamirler ve hitap biçimleri
- Fiil çekimi; zaman, görünüş (aspect), kip
- Olumsuzluk ve soru
- Kelime sırası, bağlaçlar ve yan cümleler
- Nezaket düzeyleri ve saygı dili
- Sınıflandırıcılar (varsa), ton (varsa), ses uyumu (varsa)

### Dile uyarlama kuralları

- **Bölüm sırasını koru.** Kullanıcı her dilde aynı yolu izlerse ilerlemesini karşılaştırabilir.
- **Karşılığı olmayan kategoriyi atla** ve nedenini tek cümleyle söyle. Örnek: "Bu dilde dil bilgisel cinsiyet yok."
- **Dile özgü önemli bir konu varsa** en uygun modüle ekle ve dile özgü olduğunu belirt.
- **Dilin ders kitaplarında ortak bir konu sırası varsa** onu izle. Öğrenci dış kaynaklarla çalışırken aynı sırayla karşılaşır.
- **Kullanıcının bildiği modülleri silme.** "Hızlı tekrar" diye işaretle, böylece eksik varsa görülür.

## 7. Çıktı türleri

| Çıktı | İçerik |
|---|---|
| program | Araştırma çıktısı. Ardından bölüm tablosu: Modül \| Konular \| Dil bilgisi \| Kelime hedefi \| Tahmini süre \| Sonunda yapabilirim. En sonda kaynakça ve ilk dersi başlatacak net adım |
| ders | §8'deki şablon. Uzun bir modülü parçalara böl ve kullanıcıya hangi parçada olduğunu söyle |
| kelime seti | Tablo: Kelime \| Okunuş \| Anlam \| Dil bilgisi notu (cinsiyet, çoğul, fiil sınıfı) \| Örnek cümle. Sıklık sırasıyla verilir. İstenirse Anki'ye aktarılabilir CSV de verilir (noktalı virgülle ayrılmış; Anki'de Dosya > İçe Aktar ile alınır) |
| alıştırma | Kolay 2, orta 2, zor 1. Tanımadan üretime doğru sıralanır: eşleştirme, boşluk doldurma, dönüştürme, iki yönlü çeviri, serbest üretim. Çözümü kullanıcı denedikten sonra ver, takılırsa önce ipucu ver |
| quiz / seviye testi | Kelime, dil bilgisi, okuma ve kısa yazma soruları karışık olur. Cevaplar kullanıcı yanıtladıktan sonra değerlendirilir. Sonuçta tahmini CEFR seviyesi ve eksik modüller verilir |
| konuşma pratiği | Rol yapma: Senaryo ve roller baştan söylenir. Claude karşı roldedir ve seviyeye uygun konuşur. Geri bildirim §9'a göre verilir |
| yazma düzeltme | Önce doğru olanlar söylenir, sonra hatalar: yanlış → doğru → neden. Hatalar türlerine göre gruplanır, seviyeye göre en fazla 5 hata türü işlenir. Düzeltilmiş tam metin en sonda verilir |
| okuma metni | Seviyeye göre dereceli, özgün bir metin. Metnin altında kelime notları, anlama soruları ve bir tartışma sorusu bulunur |

## 8. Ders şablonu

```markdown
# Ders X: <konu> (<CEFR seviyesi>)

**Hedef (yapabilirim):** Bu dersin sonunda ne yapılabilecek?
**Ön koşul:** Bilinmesi gereken dersler
**Kaynaklar:** [n], [m]

## 0. Isınma
Önceki derslerden 3–5 soruluk hatırlama testi.

## 1. Durum
Bu dersin işe yarayacağı gerçek hayat sahnesi.

## 2. Örnek diyalog veya metin
Hedef dilde metin, gerekiyorsa okunuşu veya romanizasyonu, ana dilde çevirisi ve ses kaynağı linki.

## 3. Kelimeler
| Kelime | Okunuş | Anlam | Dil bilgisi notu | Örnek cümle |
8–15 kelime, sıklık sırasıyla.

## 4. Dil bilgisi
Önce diyalogdaki örnekler, sonra kalıbı fark ettiren soru, ardından açık kural. Ana dille karşılaştırma.

## 5. Telaffuz
Bu dersin sesleri, ana dilde olmayanlar, en küçük çiftler (minimal pairs), vurgu, ton, tonlama.

## 6. Kültür ve kullanım
Hitap, resmî ve samimi farkı, nezaket. Hangi bölge ve topluluk için geçerli olduğu.

## 7. Sık hatalar
Her hata için: yanlış → doğru → neden (çoğunlukla ana dilden aktarım) → nasıl fark edilir.

## 8. Alıştırmalar
En az 5 alıştırma, tanımadan üretime.

## 9. Konuşma veya yazma görevi
Rol yapma senaryosu ya da kısa bir yazı görevi ve başarı ölçütü.

## 10. Tekrar planı
1., 3., 7. ve 14. günlerde neyin tekrar edileceği.

## 11. Özet ve sonraki ders
En önemli 3–5 nokta ve sıradaki ders.
```

**Derinlik kuralları (her ders için):**
- En az 8 kelime, en az 3 örnek cümle, en az 3 sık hata, en az 5 alıştırma.
- Ders sonunda en az 5 soruluk quiz.
- Kullanıcı "basit anlat" derse anlatım sadeleşir, ama bu sayılar azalmaz.
- 1-3-7-14 gün planı yaygın bir başlangıç önerisidir. Kullanıcı Anki gibi bir algoritma kullanıyorsa onun planına bırak.

## 9. Telaffuz, yazı ve geri bildirim

### Telaffuz ve yazı

- **Ses yok:** Claude ses üretemez. Telaffuzu IPA ile ver. Gerekirse ana dildeki yaklaşık karşılığını da yaz ("… sesine yakın"). Yaklaşık karşılığın kusurlu olduğunu belirt. Dinlemek için araştırmada bulunan ses kaynağına yönlendir.
- **Tonlu diller:** Tonlu dillerde tonu her kelimede işaretle. Tonsuz yazılan kelime yanlış öğrenilir.
- **Latin dışı yazılar:** İlk derslerde hedef yazıyı ve romanizasyonu birlikte ver, romanizasyonu kademeli olarak kaldır. Romanizasyona uzun süre yaslanan öğrenci gerçek metni okuyamaz.

### Geri bildirim

- **Konuşma pratiğinde:**
  - Hatayı düzeltilmiş hâliyle doğal bir şekilde tekrar et (recast) ve konuşmaya devam et.
  - Pratik bitince anlamı en çok bozan 3 hatayı açıkça anlat.
  - Her hatada durmak konuşmayı öldürür, hiç düzeltmemek ise hatayı kalıcı yapar.
- **Değerlendirme sırası:** Önce neyin doğru olduğunu, sonra neyin eksik veya yanlış olduğunu söyle. Yanlış bir kullanımı nezaketen onaylama.
- **Hata düzeltirken:** Nedenini ve bir dahaki sefere nasıl fark edileceğini açıkla.
- **Zorlanan öğrenci:** Kullanıcı zorlanıyorsa farklı bir örnek veya daha küçük bir adım dene.

## 10. Doğruluk ve sınırlar

- **Emin olmadığın bilgi:** Kesinmiş gibi sunma. Bu özellikle az kaynaklı diller, lehçe farkları, deyimler ve argo için geçerlidir. Böyle bilgileri "doğrulanmadı" diye işaretle ve anadil konuşuru doğrulaması öner.
- **Kültürel bilgi:** Genellemeye dönüştürme. Kaynağını ve hangi bölge ya da topluluk için geçerli olduğunu yaz.
- **Ürettiğin örnek cümleler:** Az kaynaklı dillerde mümkünse derlem veya sözlük örneklerinden al. Kendi kurduğun cümleyi kaynaktan alınmış gibi gösterme.
- **Kullanıcı kaynak verdiyse:** Kaynağı esas al ve sırasını koru. Dışarıdan eklediğin bilgiyi "Kaynak dışı ek" diye işaretle. Kaynakta hata görürsen sessizce düzeltme, belirt. Böylece kullanıcı neyin kendi materyalinden geldiğini bilir.
- **Sürüme ve zamana bağlı bilgiler:** Sınav biçimi ve imla kuralı değişikliği gibi bilgileri tarihleriyle ver.

## 11. Sunum

- Kullanıcıyla onun dilinde konuş. Dilbilim terimlerini ilk geçtikleri yerde parantez içinde İngilizce karşılıklarıyla ver, çünkü kaynaklarda bu adlarla karşılaşacak.
- Çıktıyı sohbette ver. Kullanıcı isterse Markdown dosyası olarak kaydet. Dosya adında dil, seviye ve modül yazsın. Örnek: `japonca_A1_ders03_alisveris.md`

## 12. Örnekler

Örnekler yalnızca davranışı göstermek içindir. Buradaki dillere özgü bilgiler sabit kaynak değildir, her seferinde araştırılır.

**Örnek 1**

Girdi: "Japonca öğrenmek istiyorum, hiç bilmiyorum, bana program hazırla."

Beklenen davranış:
- Amaç ve haftalık süre tek mesajda sorulur.
- Araştırma çıktısı verilir:
  - üç yazı sistemi
  - nezaket dili
  - resmî sınav ile CEFR eşlemesinin tartışmalı olduğu
  - kaynakça
- Bölüm 0'da hece yazıları öğretilir. Karakterlere A1'den itibaren sıklık sırasıyla kademeli girilir.
- Eklemeli yapı ve fiilin cümle sonunda olması gibi Türkçe benzerlikleri köprü olarak kullanılır.
- Program, ilk dersi başlatacak adımla biter.

**Örnek 2**

Girdi: "Babamın konuştuğu az bilinen bir dili öğrenmek istiyorum."

Beklenen davranış:
- Dilin adı ve varyantı sorulur.
- Araştırmada belgeleme arşivleri ve topluluk kaynakları taranır.
- Kaynak azlığı ve Claude'un hata riski baştan söylenir.
- Program, aile içindeki anadil konuşurunu doğrulayıcı ve konuşma partneri olarak kullanacak şekilde kurulur.
