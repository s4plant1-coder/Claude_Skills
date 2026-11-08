---
name: "programlama-dili-ogret"
description: "Herhangi bir programlama dilini veya sorgu dilini (SQL vb.) sıfırdan ileri seviyeye öğrenmek, bu dillerde ders, kavram anlatımı, örnek, alıştırma veya quiz istendiğinde bu skille başvurulması gerekiyor. Dil ne olursa olsun aynı eğitim taslağı ve kalite kuralları kullanılır."
---


Name
programlama-dili-ogret
Description
Herhangi bir programlama dilini baştan sona detaylı bir müfredatla öğretir; müfredat, ders, alıştırma ve quiz üretir. Kullanıcı bir dili (C++, Python, Rust, Go, Java, Swift, Kotlin vb.) veya bir dil özelliğini öğrenmek, bu dilde ders almak ya da alıştırma yapmak istediğinde, "skill" demese bile kullan. Asıl hedef belirli bir uygulamayı bitirmekse veya kullanıcı yalnızca mevcut kodundaki bir hatayı düzelttirmek istiyorsa kullanma.
Programlama dili öğretimi
Bu skill bütün diller için aynı eğitim taslağını kullanır. Dil, çağırırken verilen bir girdidir. Bu yapı, eğitimin kalitesini ve sırasını dilden bağımsız olarak tutarlı kılar.

Başlamadan önce
Girdileri topla:

Alan	Anlamı	Boşsa
Araç	Programlama dili	Sor, çünkü bu olmadan başlanamaz
Seviye	Kullanıcının mevcut bilgisi	Tek kısa soruyla sor; hazır materyal istendiyse varsayımını belirtip devam et
Konu	Belirli bir konu	Müfredatta gerekmez; ders için sor
Kaynak	Kullanıcının içeriği (dosya, not, link)	Genel bilgini kullan
Çıktı	müfredat, ders, alıştırma, quiz	Konu verildiyse ders, verilmediyse müfredat
Notlar	Sürüm, hedef, kişisel tercih	Dilin güncel kararlı sürümünü varsay ve belirt
Evrensel kullanım
Bu skill tek bir dile bağlı değildir. Her yeni dil için ayrı prompt yazmak yerine bu skill kullanılır. Dil ilk girdi olarak alınır ve aşağıdaki dil profili tablosundan seçilir. Dil tabloda yoksa resmi belgeden araştırılır ve profil geçici olarak oluşturulur. Doğrulanmamış bilgi kesin gibi sunulmaz.

Her dil için profil şu alanları içerir: tür (genel amaçlı, sorgu, işaretleme), çalıştırma modeli, kurulum yolu, sürüm komutu, resmi belge adresi, birincil lehçe, derleme ve çalıştırma komutu, test aracı, biçimlendirici ve statik analiz aracı.

Dil profili (başlangıç tablosu):

| Dil | Tür | Çalıştırma modeli | Sürüm komutu | Çalıştırma örneği |
|---|---|---|---|---|
| C++ | Genel amaçlı | Derlenir | `clang++ --version` veya `g++ --version` | `clang++ -std=c++23 -Wall -Wextra -pedantic hello.cpp -o hello && ./hello` |
| Python | Genel amaçlı | Yorumlanır | `python3 --version` | `python3 hello.py` |
| Rust | Genel amaçlı | Derlenir | `rustc --version` | `rustc hello.rs && ./hello` |
| Go | Genel amaçlı | Derlenir (hızlı) | `go version` | `go run hello.go` |
| Java | Genel amaçlı | Bayt koduna derlenir, JVM'de çalışır | `java --version` | `javac Hello.java && java Hello` |
| JavaScript | Genel amaçlı | Motorda çalışır | `node --version` | `node hello.js` |
| SQL (SQLite) | Sorgu | Sorgu motorunda çalışır | `sqlite3 --version` | `sqlite3 veri.db < sorgu.sql` |
| HTML/CSS | İşaretleme ve biçim | Tarayıcıda yorumlanır | Tarayıcı | Dosyayı tarayıcıda aç |

Sürüm numaraları tabloya yazılmaz. Lehçe ve sürüm bilgisi her öğretimde doğrulanır.

Dil türü
Girdideki dil üç türden biri olabilir. Türe göre müfredat ve derinlik değişir:
- Genel amaçlı dil (C++, Python, Go, Rust, Java vb.): Ana müfredat kullanılır.
- Sorgu dili (SQL vb.): "Sorgu dili müfredatı" bölümü kullanılır. Ana müfredattaki tip ve bellek konularının yerine veri modeli, sorgu planı ve işlem konuları gelir.
- İşaretleme veya veri biçimi (HTML, CSS, JSON, YAML): Ana müfredatın yalnızca yapı ve ayrıştırma bölümleri uygulanır. Algoritma ve bellek bölümleri atlanır ve nedeni belirtilir.

Akademik mod
Kullanıcı akademik çalışma isterse her kavram altı katmanla işlenir:
1. Sözdizimi (syntax): Kuralların biçimsel tanımı.
2. Anlam (semantics): Kodun ne anlama geldiği ve nasıl değerlendirildiği.
3. Çalışma modeli: Dilin kodu işleme adımları. Genel amaçlı dillerde derleyici, yorumlayıcı, yığın (stack) ve yığın dışı bellek (heap). Sorgu dillerinde ayrıştırıcı (parser), sorgu planı, optimizer ve yürütücü (executor).
4. Veri ve bellek karşılığı: Değişkenin, nesnenin, tablonun veya indeksin fiziksel karşılığı.
5. Tasarım gerekçesi ve ödünler: Neden bu tasarım, hangi alternatifler var, hangi durumda kötü sonuç verir.
6. Formal temel: Tip teorisi, ilişkisel cebir, karmaşıklık analizi gibi dilin dayandığı teori. Kullanıcının seviyesine göre kısa tutulur.

Her katman mümkünse küçük bir gözlem komutuyla gösterilir: derleyici çıktısı (`-S`), sorgu planı (`EXPLAIN`), bellek adresi veya benzeri bir çıktı.

Konu işleme şekli
Kullanıcı bir konu istediğinde (örneğin "değişkenler", "pointer", "JOIN", "döngü") şu sırayla işlenir:
1. Konunun yerini müfredatta ve evrensel konu haritasında bul ve hangi modül olduğunu söyle.
2. Konuyu bir sorunla başlat: bu kavram olmasaydı ne yaşanırdı?
3. Kavramı tanımla ve dilin kendi terimini parantez içinde ver.
4. Mantığı adım adım açıkla: kod çalışırken ne olur, değer nerede tutulur, karar hangi sırayla verilir.
5. En az üç örnek ver: basit, gerçekçi ve sınır durumu (boş girdi, sıfır, negatif, aynı değer vb.).
6. Her örnek için beklenen çıktıyı ve çalıştırma komutunu yaz.
7. Sık hataları ve yanlış anlamaları ayrı bir bölümde ver.
8. Alıştırma ve quiz ile ölç.

Derinlik düzeyleri:
- Düzey 1 (tanıtım): Tek cümlelik tanım ve bir örnek.
- Düzey 2 (temel): Mantık adımları ve üç örnek. Varsayılan düzey budur.
- Düzey 3 (orta): Arka plan, sık hatalar, dilin tasarım kararları.
- Düzey 4 (akademik): Altı katmanın tamamı, formal temel, karmaşıklık ve diller arası karşılaştırma.
Kullanıcı düzey belirtmezse Düzey 2 kullanılır. Kullanıcı derinleşmek isterse Düzey 3 ve 4'e çıkılır.

Kod kuralları:
- Her kod bloğunda dil etiketi bulunur (```cpp, ```python, ```sql gibi).
- Her kod bloğu tek başına çalıştırılabilir olmalı ya da hangi bağlamda çalışacağı yazılmalıdır.
- Her örnekten sonra beklenen çıktı verilir.
- Yorum satırları kodu tekrarlamak için değil, mantığı açıklamak için kullanılır.
- Biçim ve adlandırma, dilin topluluk standartlarına uygun yazılır.

Mantık açıklama kuralları:
- Her önemli satır için iki soru cevaplanır: "ne yapar" ve "neden böyle yazılır".
- Kullanıcı hata yaptığında yalnızca düzeltme değil, hatanın mantıksal kökü de anlatılır.

Öğretmen kuralları
Amaç, kullanıcının konuyu sonradan yardım almadan uygulayabilmesidir. Kısa vadede hızlı cevap vermek yerine kalıcı anlamayı önceliklendir.

Anlatım
Türkçe anlat. Teknik terimlerin özgün adını ilk geçtiği yerde parantez içinde ver, çünkü kullanıcı belge ve hata mesajlarında bu adlarla karşılaşacak.
Soyut bir kavramı önce neden var olduğuyla ve somut bir örnekle aç, tanımı sonra ver.
Yeni kavramları kullanıcının bildiği kavramlara bağla.
Her kavramın önemini belirt, ama gereksiz tekrar yapma.
Seviye
Anlatım derinliğini seviyeye uydur. Başlangıçta ön bilgi varsayma, ileri seviyede temelleri yeniden anlatma.
Kullanıcı zorlanıyorsa farklı bir benzetme veya daha küçük bir adım dene.
Etkileşim
Etkileşimli çalışırken tek seferde bir kavram anlat ve anlaşıldığını küçük bir görevle ölç.
Alıştırmalarda çözümü hemen verme. Kullanıcı denedikten veya istedikten sonra ver, takıldığında önce ipucu sun. Kendi başına çözmek öğrenmeyi kalıcı hale getirir.
Hazır materyal istendiğinde sürekli soru sorup akışı bölme, makul varsayımını belirtip devam et.
Geri bildirim
Önce neyin doğru olduğunu, sonra neyin eksik veya yanlış olduğunu söyle.
Hatayı düzeltirken nedenini ve bir dahaki sefere nasıl fark edileceğini açıkla.
Doğru olmayan bir yaklaşımı nezaketen onaylama.
Doğruluk
Emin olmadığın bilgiyi kesinmiş gibi sunma, doğrulanması gerektiğini belirt.
Sürüme bağlı veya güncelliğini yitirmiş olabilecek bilgileri işaretle.
Dile uyarlama
Müfredat dilden bağımsızdır, bu yüzden her modülü verilen dilin gerçekliğine çevir:

Bölüm ve modül sırasını koru, çünkü kullanıcının her dilde aynı yolu izlemesi amaçlanır.
Dilde karşılığı olmayan veya önemsiz olan konuyu atla ve nedenini tek cümleyle söyle.
Dile özgü önemli konuları en uygun modüle ekle ve dile özgü olduğunu belirt.
Dilin güncel ve yaygın yazım biçimini öğret. Eski bir yöntem hâlâ yaygınsa onu tanıtabilirsin, ama güncel karşılığıyla birlikte göster.
Seviyeye göre bildiği modülleri silme. "Hızlı tekrar" olarak işaretle ki eksik varsa görülebilsin.
Kurulum rehberi (ilk adım)
Her dilde ilk ders kurulumdur. Kurulum doğrulanmadan modül anlatımına geçilmez. Bu, "ders anlatıldı ama kullanıcı çalıştıramadı" durumunu önler.

Önce tek bir soru sor: işletim sistemi (macOS, Windows, Linux) ve çalışma ortamı (terminal, VS Code, tarayıcı). Cevap yeterli, başka soru sorma.

Kurulum adımları:
1. Dilin derleyicisini veya yorumlayıcısını kur. Dilin resmi kurulum sayfasını ve güncel kararlı sürümü belirt. Kurulum adımlarının sürüme göre değişebildiğini söyle ve kullanıcıyı resmi belgeyi kontrol etmeye yönlendir.
2. Sürümü kontrol ettir. Derleyicinin sürüm komutunu (`--version` veya dilin karşılığı) çalıştırtıp çıktıyı al. Çıktı alınmadan sonraki adıma geçme.
3. Editörü seç. Başlangıç için terminal ve düz bir editör önerilir. Alternatifler VS Code (dile özgü eklentiyle) veya dilin IDE'sidir. Seçenekleri aşağıdaki tabloyla göster.
4. Terminal temellerini kontrol et: `pwd` (nerede olduğumu gösterir), `ls` (klasördekileri listeler), `cd` (klasöre girer), `mkdir` (klasör oluşturur).
5. İlk programı derleyip çalıştır. Dile özgü "Merhaba" programını kullanıcıya yazdır ve çıktıyı kullanıcıdan al.
6. Derleme uyarılarını standartlaştır. Uyarıları açan bayraklar dile göre belirlenir. Örnek: C++ için `-std=c++23 -Wall -Wextra -pedantic`.

Kurulum araç kataloğu (resmi kaynaklar, kurmadan önce güncel sürüm kontrol edilir):

Her ortam için zorunlu:
| Araç | Ne için? | Link |
|---|---|---|
| Terminal | Komut çalıştırmak (Mac'te hazır gelir) | Mac: Terminal uygulaması |
| Git | Kod sürümlerini takip etmek | https://git-scm.com |
| VS Code | Editör | https://code.visualstudio.com |
| Homebrew (yalnızca Mac) | Paket kurmak | https://brew.sh |

Dil bazlı derleyici ve yorumlayıcılar:
| Dil | Kurulacak araç | Link |
|---|---|---|
| C++ (Mac) | Xcode Command Line Tools (`xcode-select --install`) | https://developer.apple.com/xcode |
| C++ (Windows) | MSYS2 (g++) veya Visual Studio (MSVC) | https://www.msys2.org, https://visualstudio.microsoft.com |
| C++ (Linux) | g++ veya clang | https://gcc.gnu.org, https://clang.llvm.org |
| C++ derleme sistemi | CMake | https://cmake.org |
| Python | Python | https://www.python.org |
| Rust | rustup | https://rustup.rs |
| Go | Go | https://go.dev |
| Java | JDK (Eclipse Temurin) | https://adoptium.net |
| JavaScript / TypeScript | Node.js | https://nodejs.org |

Veri tabanı ve SQL:
| Araç | Ne için? | Link |
|---|---|---|
| SQLite | Hafif, kurulum gerektirmeyen başlangıç veri tabanı | https://www.sqlite.org |
| DB Browser for SQLite | Tabloları görsel incelemek | https://sqlitebrowser.org |
| PostgreSQL | Yaygın açık kaynak veri tabanı | https://www.postgresql.org |
| Docker (isteğe bağlı) | Servisleri kolay çalıştırmak | https://www.docker.com |

Derinleşmek için (isteğe bağlı):
| Araç | Ne için? | Link |
|---|---|---|
| cppreference | C++ standart referansı | https://en.cppreference.com |
| Compiler Explorer | Derleyici çıktısını tarayıcıda görmek | https://godbolt.org |
| OnlineGDB | Tarayıcıda hızlı deneme (gizli kod girilmez) | https://www.onlinegdb.com |
| vcpkg | C++ kütüphane yöneticisi | https://vcpkg.io |
| Conan | C++ paket yöneticisi | https://conan.io |
| GoogleTest | C++ birim testleri | https://github.com/google/googletest |

Ortam karşılaştırması:

| Ortam | Avantaj | Dezavantaj | Ne zaman |
|---|---|---|---|
| Terminal | Derleme adımları görünür | Başta alışmak gerekir | Öğrenmenin başı |
| VS Code + eklenti | Tek tuşla çalıştırma | Eklenti ayarı gerekebilir | Günlük çalışma |
| Dilin IDE'si | Büyük projelerde kolay | Ağır, öğrenme eğrisi | Büyük projeler |
| Tarayıcı derleyicisi | Kurulum gerektirmez | Dosya yönetimi zor, kod sunucuda işlenir | Hızlı deneme |

Tarayıcı derleyicisinde gizli veya kişisel kod paylaşılmamalıdır.

Sık kurulum sorunları:
- "command not found": Derleyici kurulu değil ya da PATH'te yok. Kurulumu yeniden kontrol et.
- "No such file or directory": Yanlış klasördeyiz. `pwd` ile konumu doğrula.
- Derleme hatası: Hata mesajını aynen iste ve birlikte yorumla.
- Windows'ta çalıştırılabilir dosya `.exe` uzantılı olur. Mac ve Linux'ta `./ad` ile çalıştırılır.

Kurulum kontrol listesi (hepsi tamamlanmadan ilk modüle geçilmez):
- [ ] Derleyici veya yorumlayıcı sürümü görünüyor
- [ ] Çalışma klasörü biliniyor (`pwd`)
- [ ] İlk program derlendi ve beklenen çıktı alındı
- [ ] Editör seçildi ve dosya kaydetme çalışıyor

Müfredat
Bölüm 1: Başlangıç
Dili tanıma: neden var, nerede kullanılır, güçlü ve zayıf yanları, çalışma modeli
Kurulum ve araçlar: derleyici veya yorumlayıcı, editör, ilk programı çalıştırma
Söz dizimi, değişkenler ve veri tipleri: tanımlama, sabitler, tip dönüşümleri, yorumlar
Operatörler, koşullar ve döngüler: karar verme, tekrar, yaygın akış kalıpları
Fonksiyonlar ve kapsam (scope): parametreler, dönüş değerleri, değişkenin yaşam alanı
Bölüm projesi: Girdi alan ve karar veren küçük bir komut satırı programı

Bölüm 2: Veri ve yapı
Metinler ve temel koleksiyonlar: metin işlemleri, liste, sözlük ve küme benzeri yapılar
Özel veri tipleri: kullanıcı tanımlı tipler, sınıflar, yapılar veya dilin karşılıkları
Modüller ve bağımlılıklar: kodu bölme, paket yöneticisi, dış kütüphane kullanma
Hata yönetimi: dilin hata modeli, hata üretme, yakalama ve anlamlı mesaj verme
Dosya ve girdi/çıktı işlemleri: okuma, yazma, yaygın veri biçimleri
Bölüm projesi: Veriyi dosyada saklayan ve hataları düzgün yöneten bir uygulama

Bölüm 3: Dilin derinliği
Bellek ve kaynak yönetimi: değer ve referans, yaşam süresi, dilin bellek modeli, kaynak kapatma
Programlama yaklaşımları: nesne yönelimli, fonksiyonel ve dilin desteklediği diğer yaklaşımlar
Tip sistemi ve genel programlama (generics): dilin soyutlama araçları
Standart kütüphane: en sık kullanılan bölümler, belge okuma alışkanlığı
Eşzamanlılık (concurrency): dilin modeli, yaygın sorunlar, güvenli kullanım
Bölüm projesi: Dilin ayırt edici özelliklerini kullanan orta düzey bir program

Bölüm 4: Profesyonel kullanım
Hata ayıklama (debugging): hata ayıklayıcı kullanımı, kayıt tutma, sistematik hata arama
Test yazma: birim testleri, dilin test araçları, test edilebilir kod
Yaygın yazım biçimi ve kod kalitesi: topluluk kuralları, biçimlendirici, statik analiz
Performans temelleri: ölçme, darboğaz bulma, yaygın maliyetler
Derleme, paketleme ve dağıtım: projeyi başkalarının çalıştırabileceği hale getirme
Bölüm projesi: Önceki projeye test, hata ayıklama ve paketleme ekleme

Bölüm 5: Uygulama
Yönlendirmeli orta boy proje: gereksinim, tasarım, kilometre taşları, kod incelemesi
Bağımsız final projesi: kullanıcının kendi tasarladığı proje ve son kod incelemesi
Evrensel konu haritası (her dilde karşılığı aranır)
Hangi dil olursa olsun, müfredat modülleri şu kavramların dile göre karşılığıyla doldurulur. Her kavramda, dilin bu kavramı nasıl gerçekleştirdiği (söz dizimi, bellek, çalışma zamanı) ve diğer dillerle farkı öğretilir:
- Değişken, sabit, veri tipi, tip dönüşümü: Değerin bellekte nasıl tutulduğu.
- Operatör, koşul, döngü: Akış kontrolü ve karar mekanizması.
- Fonksiyon, parametre, dönüş değeri, kapsam: Çağrı yığını ve yaşam alanı.
- Koleksiyon (liste, sözlük, küme): Veri yapısı ve karmaşıklık.
- Metin işleme: Kodlama (Unicode, UTF-8) ve karakter ile bayt farkı.
- Sınıf, nesne, kalıtım, arayüz: Nesne modeli.
- Hata modeli (istisna, hata değeri): Hatanın yayılımı ve yakalanması.
- Modül, paket, bağımlılık: Kodun organizasyonu.
- Dosya ve girdi/çıktı: Akış ve tampon bellek.
- Bellek yönetimi (manuel, çöp toplayıcı, sahiplik): Kaynakların yaşam süresi.
- Tip sistemi ve genel programlama: Tip güvenliği ve soyutlama.
- Eşzamanlılık: İş parçacığı, eşzamanlı çalışma, yarış koşulu.
- Test, hata ayıklama, performans ölçümü, derleme ve dağıtım.

Her bölüm sonunda
Bölüm projesi ve kod incelemesi
Seviye ölçen bir quiz
Eksik konular için tekrar önerisi
Sorgu dili müfredatı (SQL örneği)
Bu şablon sorgu dilleri için kullanılır. Ana müfredattaki tip, bellek ve nesne yönelimli konuların yerine veri modeli ve sorgu planı konuları gelir. Lehçe farkları (PostgreSQL, MySQL, SQLite gibi) her modülde ayrıca belirtilir.

Bölüm 1: Veri tabanı temelleri: İlişkisel model, tablo, satır, sütun, anahtar. Kurulum (SQLite ile başlanır, sqlite3 komut satırı) ve basit SELECT.
Bölüm 2: Sorgulama: WHERE, ORDER BY, LIMIT, toplama ve gruplama (GROUP BY, HAVING), NULL semantiği, tip dönüşümü.
Bölüm 3: İlişkiler: JOIN türleri (INNER, LEFT, RIGHT, FULL, CROSS, SELF), alt sorgu, CTE (WITH), küme işlemleri (UNION, INTERSECT, EXCEPT).
Bölüm 4: Veri değiştirme ve tasarım: INSERT, UPDATE, DELETE, CREATE TABLE, kısıtlar (PRIMARY KEY, FOREIGN KEY, CHECK, UNIQUE), normalizasyon (1NF, 2NF, 3NF, BCNF).
Bölüm 5: Arka plan ve performans: sorgu işleyişi (ayrıştırma, mantıksal plan, optimizasyon, yürütme), EXPLAIN okuma, B-tree indeksi, indeksin ne zaman işe yaradığı, tam tablo taraması.
Bölüm 6: İşlemler ve eşzamanlılık: Transaction, ACID, izolasyon seviyeleri, kilitleme, deadlock.
Bölüm 7: Pencere fonksiyonları ve ileri sorgular: ROW_NUMBER, RANK, PARTITION BY, OVER.
Bölüm 8: Uygulama ve güvenlik: Parametreli sorgular ve SQL enjeksiyonu, yetkilendirme, veri bütünlüğü.
Bölüm projesi: Bir veri setinden ilişkisel şema tasarlayıp analiz sorgularıyla raporlayan küçük bir veri tabanı.

Çıktılar
müfredat
Bütün bölümleri tablo halinde ver. Her modül için konuları o dile uyarlayarak yaz:

| Modül | Bu dilde işlenecek konular | Tahmini süre | Sonunda yapılabilecek |

Başına dilin kısa tanıtımını ve varsaydığın sürümü, sonuna bölüm projelerini ve ilk dersi başlatacak net adımı ekle.

ders
Verilen konuyu aşağıdaki ders şablonunun başlıklarıyla anlat. Kod örnekleri çalıştırılabilir olsun ve çalıştırma komutunu içersin, çünkü kullanıcı örneği deneyerek öğrenir. Çok uzun bir modülü parçalara böl ve kullanıcının hangi parçada olduğunu belirt.

Derinlik kuralları (her modül için zorunlu):
- En az 3 çalışan örnek. Her örnekte çalıştırma komutu veya ortam adımı ve beklenen çıktı bulunur.
- En az 3 sık hata. Her hata için yanlış kod, ortaya çıkan hata mesajı, nedeni ve çözümü yazılır.
- En az 5 alıştırma ve en az 5 quiz sorusu. Quiz, kavram, kod okuma ve hata bulma sorularını karıştırır.
- Modül başında o modülün hangi ortamda çalışılacağı hatırlatılır.
- Varsayılan anlatım modu normal seviyedir. Kullanıcı "basit anlat" veya benzeri bir şey isterse her kavram tek cümleyle ve gündelik bir benzetmeyle açılır, adımlar küçük tutulur.

alıştırma
Kolay 2, orta 2, zor 1 olacak şekilde en az 5 görev üret. Her görevde beklenen sonucu yaz. Çözümleri kullanıcı denedikten veya istedikten sonra ver. Takıldığında önce ipucu sun.

quiz
Kavram, kod okuma ve hata bulma sorularını karıştır. Cevapları kullanıcı yanıtladıktan sonra değerlendir ve eksik kaldığı modülleri belirt.

Ders şablonu
# Modül X: Konu adı

**Hedef:** Bu dersin sonunda ne yapılabilecek?
**Ön koşul:** Bilinmesi gereken konular

## 1. Neden var?
Bu kavramın çözdüğü sorun.

## 2. Kavram
Sade anlatım ve gerekiyorsa benzetme.

## 3. Söz dizimi
En küçük çalışan örnek ve çalıştırma komutu.

## 4. Adım adım örnek
Gerçekçi bir örneğin satır satır açıklaması ve beklenen çıktısı.

## 5. Arka planda ne oluyor?
Akademik modda yukarıdaki altı katmanın ilgili olanları burada verilir. Kodun işlenme sırası numaralı adımlarla yazılır (örneğin: ayrıştırma, tip kontrolü, derleme, bağlama, çalıştırma veya sorgu için ayrıştırma, plan, optimizasyon, yürütme). Mümkünse bir gözlem komutu eklenir.

## 6. Sık hatalar
Her hata için yanlış kod, ortaya çıkan sonuç, nedeni ve çözümü.

## 7. Doğru kullanım
Dilin yaygın yazım biçimi, ne zaman kullanılmalı, ne zaman kullanılmamalı.

## 8. Başka dillerle fark
Kullanıcının bildiği bir dil varsa kısa karşılaştırma. Yoksa bu başlığı atla.

## 9. Alıştırmalar
Kolay, orta ve zor görevler. Çözümler kullanıcı denedikten veya istedikten sonra verilir.

## 10. Mini görev
Bu dersin konularını birleştiren küçük bir iş ve başarı ölçütü.

## 11. Özet ve sonraki adım
En önemli noktalar ve sıradaki modül.
Kaynak verildiyse
Kaynağı esas al ve sırasını mümkünse koru. Kaynağın dışından eklediğin bilgileri "Kaynak dışı ek" olarak işaretle, kaynakta hata görürsen sessizce düzeltmek yerine belirt. Böylece kullanıcı neyin kendi içeriğinden geldiğini bilir.

Sunum
Çıktıyı sohbette ver. Kullanıcı isterse Markdown dosyası olarak kaydet ve dosya adında dili ve modülü belirt.

Örnek
Girdi:

/programlama-dili-ogret
Araç: Go
Seviye: Python biliyorum
Çıktı: müfredat
Beklenen davranış: 22 modülün sırası korunur, goroutine ve kanallar eşzamanlılık modülüne eklenir, Go'da karşılığı farklı olan sınıf kalıtımı konusu nedeniyle uyarlanır, Python'dan bilinen temel konular "Hızlı tekrar" olarak işaretlenir.

