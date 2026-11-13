# Müfredat

Bu dosya iş akışının 4. adımında okunur: müfredat istendiğinde ya da bir konunun müfredattaki yeri ve ön koşulları bilinmesi gerektiğinde.

## İçindekiler
1. İskelet seçimi
2. Ana müfredat (Bölüm 1–5, 22 modül)
3. Bölüm 6: Uzmanlık (isteğe bağlı)
4. Her bölüm sonunda
5. Evrensel konu haritası
6. Kavram ağı (ön koşullar)
7. Kapsam matrisi
8. Sorgu dili müfredatı

## 1. İskelet seçimi

| Dilin birincil ailesi | İskelet |
|---|---|
| 1. Emperatif / nesne yönelimli | Ana müfredat olduğu gibi |
| 4. Sorgu / veri | Sorgu dili müfredatı (§8) |
| 5. İşaretleme / stil / veri biçimi | Ana müfredatın yalnızca yapı, ayrıştırma ve doğrulamayla ilgili modülleri. Algoritma ve bellek modülleri atlanır, nedeni söylenir. |
| Diğer aileler | Ana müfredat + aile bölümündeki "Ekle" ve "Çıkar / uyarla" maddeleri |

Dil birden çok aileye giriyorsa iskeleti birincil aile belirler. Diğer ailelerin "Ekle" maddeleri ilgili modüllere eklenir.

## 2. Ana müfredat

### Bölüm 1: Başlangıç
1. **Dili tanıma:** Neden var, nerede kullanılır, güçlü ve zayıf yanları, çalışma modeli. Kısa tarihçe, sürümler ve lehçeler. Dilin kavramsal makinesi: kodun nasıl çalıştığına dair, bütün derslerde kullanılacak basit model.
2. **Kurulum ve araçlar:** Derleyici veya yorumlayıcı, editör, ilk programı çalıştırma.
3. **Söz dizimi, değişkenler ve veri tipleri:** Tanımlama, sabitler, tip dönüşümleri, yorumlar.
4. **Operatörler, koşullar ve döngüler:** Karar verme, tekrar, yaygın akış kalıpları.
5. **Fonksiyonlar ve kapsam (scope):** Parametreler, dönüş değerleri, değişkenin yaşam alanı.
- **Bölüm projesi:** Girdi alan ve karar veren küçük bir komut satırı programı.

### Bölüm 2: Veri ve yapı
6. **Metinler ve temel koleksiyonlar:** Metin işlemleri; liste, sözlük ve küme benzeri yapılar.
7. **Özel veri tipleri:** Kullanıcı tanımlı tipler, sınıflar, yapılar veya dilin karşılıkları.
8. **Modüller ve bağımlılıklar:** Kodu bölme, paket yöneticisi, dış kütüphane kullanma.
9. **Hata yönetimi:** Dilin hata modeli; hata üretme, yakalama ve anlamlı mesaj verme.
10. **Dosya ve girdi/çıktı işlemleri:** Okuma, yazma, yaygın veri biçimleri.
- **Bölüm projesi:** Veriyi dosyada saklayan ve hataları düzgün yöneten bir uygulama.

### Bölüm 3: Dilin derinliği
11. **Bellek ve kaynak yönetimi:** Değer ve referans, yaşam süresi, dilin bellek modeli, kaynak kapatma.
12. **Programlama yaklaşımları:** Nesne yönelimli, fonksiyonel ve dilin desteklediği diğer yaklaşımlar.
13. **Tip sistemi ve genel programlama (generics):** Dilin soyutlama araçları.
14. **Standart kütüphane:** En sık kullanılan bölümler, belge okuma alışkanlığı.
15. **Eşzamanlılık (concurrency):** Dilin modeli, yaygın sorunlar, güvenli kullanım.
- **Bölüm projesi:** Dilin ayırt edici özelliklerini kullanan orta düzey bir program.

### Bölüm 4: Profesyonel kullanım
16. **Hata ayıklama (debugging):** Hata ayıklayıcı kullanımı, kayıt tutma, sistematik hata arama.
17. **Test yazma:** Birim testleri, dilin test araçları, test edilebilir kod.
18. **Yaygın yazım biçimi ve kod kalitesi:** Topluluk kuralları, biçimlendirici, statik analiz.
19. **Performans temelleri:** Ölçme, darboğaz bulma, yaygın maliyetler.
20. **Derleme, paketleme ve dağıtım:** Projeyi başkalarının çalıştırabileceği hâle getirme.
- **Bölüm projesi:** Önceki projeye test, hata ayıklama ve paketleme ekleme.

### Bölüm 5: Uygulama
21. **Yönlendirmeli orta boy proje:** Gereksinim, tasarım, kilometre taşları, kod incelemesi.
22. **Bağımsız final projesi:** Kullanıcının kendi tasarladığı proje ve son kod incelemesi.

## 3. Bölüm 6: Uzmanlık (isteğe bağlı)

Bu bölüm "baştan sona", "en ince ayrıntısına kadar" ya da "uzmanlık" istendiğinde veya Bölüm 5 bittikten sonra eklenir. Modüller dile göre seçilir. Dilde karşılığı olmayan modül atlanır, nedeni söylenir (ör. işaretleme dillerinde FFI).

23. **Spesifikasyon okuma:** Dilin resmi referansını okumayı öğrenme. Tanımsız (undefined), belirtilmemiş (unspecified) ve uygulamaya bağlı (implementation-defined) davranış.
24. **Değerlendirme sırası ve bellek modeli ayrıntıları:** İfadelerin değerlendirme sırası, sıralama noktaları, eşzamanlı bellek modeli.
25. **Üst programlama:** Makrolar, yansıma (reflection), kod üretimi, derleme zamanı hesaplama.
26. **Diller arası çalışma:** FFI, ABI, başka dillerle bağlantı kurma.
27. **Dile özgü güvenlik açıkları:** Dilin ve ekosisteminin tipik açıkları, güvenli kodlama rehberleri.
28. **Araç zincirinin iç yapısı:** Derleyici, yorumlayıcı ve çalışma zamanının nasıl çalıştığı: ayrıştırma, ara gösterim, optimizasyon, çöp toplayıcı.
29. **Dilin evrimi:** Tarihçe, sürüm geçmişi, lehçeler, öneri süreçleri (PEP, RFC, JEP, TC39 vb.).
30. **Ekosisteme katkı:** Açık kaynak projeye katkı, kütüphane yayımlama, öneri sürecine katılma.
- **Bölüm projesi:** Resmi referanstan seçilen ileri bir konuyu inceleyip küçük bir araç veya kütüphane yazmak ya da bir açık kaynak projeye katkı yapmak.

## 4. Her bölüm sonunda
- Bölüm projesi ve kod incelemesi
- Seviye ölçen bir quiz
- Eksik konular için tekrar önerisi
- Bölümün ana kavramlarının aralıklı tekrar takvimine eklenmesi

## 5. Evrensel konu haritası

Hangi dil olursa olsun, müfredat modülleri aşağıdaki kavramların dildeki karşılığıyla doldurulur. Her kavramda dilin bu kavramı nasıl gerçekleştirdiği (söz dizimi, bellek, çalışma zamanı) ve diğer dillerden farkı öğretilir. Diğer ailelerde harita, aile dosyasındaki kavramsal makineyle genişletilir.

- **Değişken, sabit, veri tipi, tip dönüşümü:** Değerin bellekte nasıl tutulduğu.
- **Operatör, koşul, döngü:** Akış kontrolü ve karar mekanizması.
- **Fonksiyon, parametre, dönüş değeri, kapsam:** Çağrı yığını ve yaşam alanı.
- **Koleksiyon (liste, sözlük, küme):** Veri yapısı ve karmaşıklık.
- **Metin işleme:** Kodlama (Unicode, UTF-8) ve karakter ile bayt farkı.
- **Sınıf, nesne, kalıtım, arayüz:** Nesne modeli.
- **Hata modeli (istisna, hata değeri):** Hatanın yayılımı ve yakalanması.
- **Modül, paket, bağımlılık:** Kodun organizasyonu.
- **Dosya ve girdi/çıktı:** Akış ve tampon bellek.
- **Bellek yönetimi (elle, çöp toplayıcı, sahiplik):** Kaynakların yaşam süresi.
- **Tip sistemi ve genel programlama:** Tip güvenliği ve soyutlama.
- **Eşzamanlılık:** İş parçacığı, eşzamanlı çalışma, yarış koşulu.
- **Test, hata ayıklama, performans ölçümü, derleme ve dağıtım.**

## 6. Kavram ağı (ön koşullar)

Müfredat doğrusal bir liste gibi görünse de konular arasındaki ilişki bir ağdır. Bir modül yalnızca ön koşullarına bağlıdır, önündeki bütün modüllere değil. Her modülün ön koşulu müfredat tablosunun "Ön koşul" sütununda modül numarasıyla yazılır.

**Varsayılan ön koşullar** (dile göre değişebilir):

| Modül | Ön koşul | Modül | Ön koşul |
|---|---|---|---|
| 1 | — | 12 | 7 |
| 2 | 1 | 13 | 7 |
| 3 | 2 | 14 | 6, 8 |
| 4 | 3 | 15 | 9, 11 |
| 5 | 4 | 16 | 5 |
| 6 | 4, 5 | 17 | 8, 9 |
| 7 | 5, 6 | 18 | 8 |
| 8 | 5 | 19 | 6, 11 |
| 9 | 5 | 20 | 8 |
| 10 | 6, 9 | 21 | 1–20 |
| 11 | 7 | 22 | 21 |

- Kullanıcı sıranın dışında bir konu isterse ön koşullar kontrol edilir. Eksik varsa varsayılan olarak dersin başına kısa bir ön koşul özeti eklenir ve eksik modüller dersin sonunda önerilir. Kullanıcı isterse önce eksik modül işlenir.
- Bölüm 6'daki modüllerin ön koşulu ilgili temel modüllerdir (ör. 26 için 8 ve 11).

## 7. Kapsam matrisi

"Baştan sona" iddiasını denetlenebilir kılar.

- **Ne zaman:** Bütün programı kapsayan her müfredatta verilir. Kullanıcı yalnızca bir bölümün müfredatını ya da kısa bir yol haritası isterse matris yerine tek satırlık bir özet yeterlidir.
- **Yöntem:**
  1. Araştırmada resmi referansın ve standart kütüphane dizininin içindekiler tablosu çıkarılır (araştırma protokolü, §6).
  2. Her bölüm bir modüle eşlenir.
  3. Eşlenmeyen bölüm ya uygun modüle veya Bölüm 6'ya eklenir ya da gerekçesiyle "kapsam dışı" yazılır.
  4. Matris müfredatın ekinde verilir.
- **Biçim:**

  | Resmi referans bölümü | Modül | Durum |
  |---|---|---|
  | ör. Go Spec "Go statements" (goroutine) | 15 | İşlenir |
  | ör. Go Spec "Program initialization and execution" | 24 | Bölüm 6 |
  | ör. Go Spec "Size and alignment guarantees" | — | Kapsam dışı: öğrencinin hedefi (web servisi) için gereksiz |

- **Sınır:** Eşleme bölüm başlığı düzeyinde yapılır. Kullanıcıya "her ayrıntı" iddiasının bu düzeyle sınırlı olduğu söylenir.

## 8. Sorgu dili müfredatı

Başlık: ilişkisel iskelet, diğer veri modellerine uyarlanır.

Bu şablon ilişkisel sorgu dilleri için yazılmıştır (SQL örneği). Ana müfredattaki tip, bellek ve nesne yönelimli konuların yerine veri modeli ve sorgu planı konuları gelir. Lehçe farkları (PostgreSQL, MySQL, SQLite gibi) her modülde ayrıca belirtilir.

Başka veri modellerinde bölümler araştırmaya göre uyarlanır. Graf (Cypher, SPARQL), belge, ağaç (XPath/XQuery) ve API sorgu dillerinde (GraphQL) ilişkisel modelin yerine dilin veri modeli, JOIN'in yerine dilin ilişki gezme biçimi gelir.

- **Bölüm 1: Veri tabanı temelleri:** İlişkisel model, tablo, satır, sütun, anahtar. Kurulum (SQLite ile başlanır, sqlite3 komut satırı) ve basit SELECT.
- **Bölüm 2: Sorgulama:** WHERE, ORDER BY, LIMIT, toplama ve gruplama (GROUP BY, HAVING), NULL semantiği, tip dönüşümü.
- **Bölüm 3: İlişkiler:** JOIN türleri (INNER, LEFT, RIGHT, FULL, CROSS, SELF), alt sorgu, CTE (WITH), küme işlemleri (UNION, INTERSECT, EXCEPT).
- **Bölüm 4: Veri değiştirme ve tasarım:** INSERT, UPDATE, DELETE, CREATE TABLE, kısıtlar (PRIMARY KEY, FOREIGN KEY, CHECK, UNIQUE), normalizasyon (1NF, 2NF, 3NF, BCNF).
- **Bölüm 5: Arka plan ve performans:** Sorgu işleyişi (ayrıştırma, mantıksal plan, optimizasyon, yürütme), EXPLAIN okuma, B-tree indeksi, indeksin ne zaman işe yaradığı, tam tablo taraması.
- **Bölüm 6: İşlemler ve eşzamanlılık:** Transaction, ACID, izolasyon seviyeleri, kilitleme, deadlock.
- **Bölüm 7: Pencere fonksiyonları ve ileri sorgular:** ROW_NUMBER, RANK, PARTITION BY, OVER.
- **Bölüm 8: Uygulama ve güvenlik:** Parametreli sorgular ve SQL enjeksiyonu, yetkilendirme, veri bütünlüğü.
- **Bölüm projesi:** Bir veri setinden ilişkisel şema tasarlayıp analiz sorgularıyla raporlayan küçük bir veri tabanı.

Uzmanlık istenirse ana müfredatın Bölüm 6'sı sorgu diline uyarlanır: standart ve lehçeler (SQL standardı ile motorların farkı), optimizer'ın iç yapısı, depolama motoru.
