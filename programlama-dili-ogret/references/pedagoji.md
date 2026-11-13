# Pedagoji

Bu dosya iş akışının 6. adımında okunur: ders, alıştırma veya quiz hazırlanırken. Kurallar programlama öğretimi araştırmalarına dayanır. Her kuralın yanında kanıt düzeyi parantez içinde verilmiştir.

## İçindekiler
1. Konu işleme şekli
2. Tahmin et → Çalıştır → İncele → Değiştir → Yap
3. Alıştırma türleri
4. Quiz ve yanlış kavramalar
5. Geri çağırma ve aralıklı tekrar
6. Transfer tablosu ve sahte dostlar
7. Seviyeye göre örnek ve problem dengesi
8. Üstbiliş soruları
9. Dayanaklar

## 1. Konu işleme şekli

Kullanıcı bir konu istediğinde (ör. "değişkenler", "pointer", "JOIN", "döngü") şu sırayla işlenir:

1. Konunun yerini müfredatta ve evrensel konu haritasında bul, hangi modül olduğunu söyle. Ön koşulları kavram ağından kontrol et.
2. **Geri çağırma:** Önceki modüllerden 2–3 kısa soru sor. İlk derste bu adım atlanır.
3. Konuyu bir sorunla başlat: bu kavram olmasaydı ne yaşanırdı?
4. Kavramı tanımla ve dilin kendi terimini parantez içinde ver.
5. Mantığı dilin kavramsal makinesiyle adım adım açıkla: kod çalışırken ne olur, değer nerede tutulur, karar hangi sırayla verilir.
6. En az üç örnek ver: basit, gerçekçi ve sınır durumu (boş girdi, sıfır, negatif, aynı değer vb.).
   - Her örnekte önce çıktıyı tahmin ettir.
   - Sonra çalıştırma komutunu ve beklenen çıktıyı ver.
   - Çözüm adımlarını alt hedef etiketleriyle böl (ör. "1. Girdiyi al", "2. Doğrula", "3. Hesapla").
7. Sık hataları ve yanlış anlamaları ayrı bir bölümde ver. Başka bir dilden taşınanları "⚠ Sahte dost" diye işaretle.
8. Alıştırma ve quiz ile ölç.
9. Üstbiliş sorularıyla bitir.

## 2. Tahmin et → Çalıştır → İncele → Değiştir → Yap

PRIMM yöntemi (Sentance ve Waite, 2017; kanıt: orta). Tahmin, çalıştırmadan önce yapılır, çünkü amaç öğrencinin zihnindeki modeli ortaya çıkarmaktır.

| Adım | Ne yapılır | Etkileşimli derste | Hazır materyalde |
|---|---|---|---|
| Tahmin et | Kod okunur, çıktı tahmin edilir | Kullanıcı tahminini yazar, çıktı ondan sonra gösterilir | "Çıktıyı tahmin et" sorusu kodun hemen altında; cevap "Cevaplar" bölümünde |
| Çalıştır | Kod çalıştırılır, tahmin ile gerçek çıktı karşılaştırılır | Kullanıcı kendi ortamında çalıştırır | Komut ve gerçek çıktı verilir |
| İncele | Satır satır iz sürülür, "neden" soruları sorulur | Soru-cevap | Açıklamalı satırlar ve iz sürme tablosu |
| Değiştir | Kod küçük değişikliklerle başka bir şey yaptırılır | Kullanıcı değiştirir, sonucu tartışılır | "Değiştir" alıştırması |
| Yap | Yeni ama benzer bir program yazılır | Kullanıcı yazar | "Yaz" alıştırması |

Varsayılan sıra şudur: önce iz sürme ve açıklama, sonra yazma (Lopez vd., 2008; Lister vd., 2009; kanıt: orta, korelasyonel). Bu katı bir ön koşul değildir. Öğrenci hazırsa doğrudan yazmaya geçilir.

## 3. Alıştırma türleri

| Tür | Ne ister | Zorluk | Neyi ölçer |
|---|---|---|---|
| Tahmin | "Bu kod ne yazdırır?" | Kolay | Kavramsal makine |
| İz sürme tablosu | Her adımda değişkenlerin değerini tabloya yazmak | Kolay–orta | Çalışma sırası ve durum |
| Parsons | Karışık verilen satırları doğru sıraya dizmek (girinti dahil) | Kolay–orta | Program yapısı, söz dizimi yükü olmadan |
| Açıkla | "Bu kod ne yapar? Kendi cümlelerinle, tek cümlede anlat." | Orta | Bütünü görme (soyutlama) |
| Kodu oku ve özetle | Daha uzun bir kodun amacını ve bölümlerini anlatmak | Orta | Kod okuma |
| Hata bul | Hatalı kodu ve varsa hata mesajını vermek; öğrenci hatanın kökünü bulur | Orta | Hata ayıklama, yanlış kavrama |
| Değiştir | Çalışan kodu yeni bir isteğe göre değiştirmek | Orta | Aktarım |
| Yaz | Boş sayfadan program yazmak | Orta–zor | Bütünleştirme |

- Bir alıştırma setinde (2 kolay, 2 orta, 1 zor) en az üç farklı tür kullanılır. Zor görev genellikle "Yaz" olur.
- Parsons problemlerinde ve çözümlü örneklerde alt hedef etiketleri öğrenmeyi artırır (Morrison, Margulieux vd.; kanıt: orta–güçlü).
- İz sürme tablosu örneği:

  ```text
  | Adım       | i | toplam |
  |------------|---|--------|
  | başlangıç  | – | 0      |
  | 1. tur     | 1 | 1      |
  | 2. tur     | 2 | 3      |
  ```

## 4. Quiz ve yanlış kavramalar

- Quiz kavram, kod okuma ve hata bulma sorularını karıştırır.
- Çoktan seçmeli sorularda **her yanlış şık (çeldirici) belirli bir yanlış kavramayı hedefler.** Rastgele yanlış şık yazılmaz. Böylece öğrencinin seçimi düşüncesini gösterir (Teach Computing; Wilson, *Teaching Tech Together*; kanıt: uzman rehberi).
- Çeldiricilerin kaynakları:
  - aile dosyasındaki "Tipik yanlış kavramalar",
  - araştırmada bulunan sık hata kaynakları,
  - transfer tablosundaki sahte dostlar,
  - ilerleme kaydında gözlenen yanlış kavramalar.
- Değerlendirmede her yanlış şık için şu yazılır: "Bu şıkkı seçtiysen şunu düşünmüş olabilirsin: … Doğrusu: …"
- Gözlenen yanlış kavrama ilerleme kaydına yazılır ve sonraki geri çağırma sorularında yeniden sorulur.

**Örnek (SQL):**

```sql
SELECT * FROM a LEFT JOIN b ON a.id = b.a_id WHERE b.durum = 'aktif';
```

Bu sorgu için hangisi doğrudur?
- A) `a`'daki bütün satırlar döner; `b`'de eşi olmayanlarda `b` sütunları NULL olur.
  → *Yanlış kavrama:* WHERE'in ON gibi birleştirme sırasında uygulandığı.
- B) Yalnızca `b.durum = 'aktif'` olan eşleşmeler döner; sorgu fiilen INNER JOIN gibi davranır. ✓
- C) Sorgu hata verir, çünkü LEFT JOIN ile WHERE birlikte kullanılamaz.
  → *Yanlış kavrama:* anlam sorununu söz dizimi kısıtı sanmak.
- D) `b.durum` değeri NULL olan satırlar da döner, çünkü `NULL = 'aktif'` bilinmiyor (UNKNOWN) değerini verir.
  → *Yanlış kavrama:* WHERE'in UNKNOWN sonuçlu satırları tuttuğu. WHERE yalnızca TRUE olanları tutar.

## 5. Geri çağırma ve aralıklı tekrar

Dunlosky vd. (2013) incelediği on teknik arasında yalnızca kendini sınamayı ve zamana yayılmış çalışmayı yüksek yararlı buldu (kanıt: güçlü).

- Her ders önceki modüllerden 2–3 geri çağırma sorusuyla başlar. Cevaplar kullanıcı yanıtladıktan sonra verilir; hazır materyalde dersin sonunda yer alır.
- Sorular öncelikle şu konulardan seçilir:
  - yanlış cevaplanmış quiz soruları,
  - gözlenen yanlış kavramalar,
  - yeni dersin ön koşulları.
- **Tekrar takvimi:** Aralıklar giderek genişler (ör. 1 gün → 3 gün → 1 hafta → 2 hafta → 1 ay). Bu aralıklar araştırmadan gelen kesin değerler değil, pratik bir başlangıçtır. Doğru cevaplanan konunun aralığı uzar, yanlış cevaplananın aralığı başa döner. Takvim ilerleme kaydında tutulur.
- Yeniden okuma ve özetleme düşük yararlıdır. Tekrar her zaman soru biçiminde yapılır.
- İsteyene modül sonunda söz dizimi bilgi kartları verilir: ön yüzde kavram veya soru, arka yüzde kod veya cevap (Hermans, 2021).

## 6. Transfer tablosu ve sahte dostlar

Önceki dil bilgisi yeni dili öğrenmeyi hem kolaylaştırır hem bozabilir. Shrestha vd. (ICSE 2020), Stack Overflow sorularında önceki dilden taşınan yanlış varsayımlara bağlı 276 karışma vakası buldu. Tshukudu ve Cutts'a (2020–2022) göre en zor yapılar, söz dizimi benzeyip anlamı farklı olanlardır (kanıt: orta; örneklemler küçük).

Öğrenci başka bir dil biliyorsa müfredatın başına transfer tablosu konur:

| Kavram | Bildiği dilde | Yeni dilde | Tür |
|---|---|---|---|
| Tam sayı bölme | Python 3: `7 / 2` → `3.5` | C: `7 / 2` → `3` | ⚠ Sahte dost |
| Dilim (slice) | Python: `a[1:3]` yeni bir liste kopyalar | Go: `a[1:3]` aynı diziyi paylaşır | ⚠ Sahte dost |
| Koşul | Python: `if x > 0:` | Go: `if x > 0 { }` | Farklı yazım, aynı anlam |
| Sahiplik (ownership) | Python'da yok | Rust: her değerin tek bir sahibi vardır | Yeni |

Satırlar farklı dil çiftlerinden alınmış örneklerdir. Gerçek tabloda yalnızca öğrencinin bildiği dil ile yeni dil karşılaştırılır.

Türler:
- **Aynı:** Yazım ve anlam aynıdır, doğrudan aktarılır. Konu "Hızlı tekrar" olarak işaretlenir.
- **Farklı yazım, aynı anlam:** Kavram aktarılır, yalnızca yazım öğretilir.
- **⚠ Sahte dost:** Yazım benzer, anlam farklıdır. Her derste işaretlenir ve quiz çeldiricisi olur. En çok zaman bu türe ayrılır.
- **Yeni:** Bildiği dilde karşılığı yoktur. Tam ders olarak işlenir.

Sahte dostlar araştırmayla bulunur (arama kalıpları araştırma protokolünde). Ders şablonundaki "Başka dillerle fark" başlığı bu tabloya bağlanır.

## 7. Seviyeye göre örnek ve problem dengesi

Bilişsel yük kuramı ve uzmanlık tersine dönme etkisi (Kalyuga vd., 2003; kanıt: orta–güçlü): Yeni başlayan için çözümlü örnek, düz problem çözmekten daha verimlidir. Deneyimli öğrencide ise aynı örnek gereksiz yük olur.

| Seviye | Denge |
|---|---|
| Yeni başlayan | Önce alt hedef etiketli çözümlü örnek, hemen ardından benzer bir problem (örnek–problem çifti). Adımlar küçük tutulur. |
| Orta | Kısmen çözülmüş örnekler (boşluk doldurma), sonra problem |
| Deneyimli veya başka dil bilen | Önce problem verilir, örnek yalnızca başvuru içindir. Bilinen konular "Hızlı tekrar" olarak işaretlenir ve tek bir kontrol sorusu sorulur. Ağırlık sahte dostlara verilir. |

Seviye yalnızca hangi konuların atlanacağını değil, anlatım biçimini de değiştirir.

## 8. Üstbiliş soruları

Yapay zekâ yardımı, zorlanan öğrencinin neyi anlamadığını fark etmesini zorlaştırabilir (Prather vd., ICER 2024; Liu vd., SIGCSE 2024). Bu yüzden modül sonunda, ders şablonunun "Kendini değerlendir" bölümünde, aşağıdaki sorulardan 2–3 tanesi sorulur:

- Bu modülde hâlâ emin olmadığın bir şey var mı?
- Hangi soruda tahmin ettin, hangisinde gerçekten biliyordun?
- Bu kavramı bir arkadaşına tek cümleyle nasıl anlatırsın?
- Bir sonraki adımda neyi denemek istersin?

"Anladım" cevabı tek başına yeterli sayılmaz. Kullanıcıdan kısa bir açıklama ya da tahmin istenir.

## 9. Dayanaklar
- Dunlosky, J. vd. (2013). *Improving Students' Learning With Effective Learning Techniques.*
- Sentance, S. ve Waite, J. (2017). PRIMM.
- Lopez, M. vd. (2008); Lister, R. vd. (2009). İz sürme, açıklama ve yazma becerileri.
- Morrison, B., Margulieux, L. vd. Alt hedef etiketleri ve Parsons problemleri.
- Kalyuga, S. vd. (2003). Uzmanlık tersine dönme etkisi.
- Shrestha, N. vd. (2020). *Here We Go Again: Why Is It Difficult for Developers to Learn Another Programming Language?* ICSE.
- Tshukudu, E. ve Cutts, Q. (2020). *Semantic Transfer in Programming Languages.*
- Hermans, F. (2021). *The Programmer's Brain.*
- Liu, R. vd. (2024). *Teaching CS50 with AI.* SIGCSE.
- Prather, J. vd. (2024). *The Widening Gap.* ICER.
- Teach Computing. *Designing and using multiple choice questions in computing.*
