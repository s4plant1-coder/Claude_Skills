# Dil aileleri

Bu dosya iş akışının 2. adımında okunur. Önce sınıflandırma kartı doldurulur. Ardından yalnızca dilin girdiği ailelerin bölümleri okunur.

Dosyada yalnızca öğretimi değiştiren bilgiler yer alır: kavramsal makine, müfredat farkı, tipik yanlış kavramalar, gözlem araçları ve ortam. Araç adları başlangıç önerisidir. Güncellikleri araştırmayla doğrulanır.

## İçindekiler
- Sınıflandırma kartı
- Aile seçimi kuralları
- 1. Emperatif / nesne yönelimli genel amaçlı
- 2. Fonksiyonel
- 3. Mantıksal / kısıt
- 4. Sorgu / veri
- 5. İşaretleme / stil / veri biçimi
- 6. Betik / kabuk
- 7. Assembly / makine düzeyi
- 8. Donanım tanımlama
- 9. Endüstriyel / PLC
- 10. Bilimsel / dizi
- 11. Görsel / blok
- 12. Yığın tabanlı
- 13. Kanıt asistanı / bağımlı tipli
- 14. Akıllı sözleşme
- 15. GPU / gölgelendirici
- 16. Alana özgü / yapılandırma
- 17. Tarihsel / eski sistem
- 18. Ezoterik
- 19. Kuantum

## Sınıflandırma kartı

Her dil için araştırmanın ilk çıktısıdır. İlk hâli genel bilgiyle doldurulur, araştırmayla doğrulanır.

| Boyut | Örnek değerler |
|---|---|
| Aile(ler) | Aşağıdaki 19 aileden bir veya birkaçı |
| Gösterim | Metin / blok / grafik / tablo |
| Çalıştırma modeli | Derlenir / yorumlanır / bayt kodu + sanal makine / sentezlenir (donanım) / PLC tarama döngüsü / sorgu motoru |
| Tip disiplini | Statik / dinamik / kademeli; güçlü / zayıf; nominal / yapısal; bağımlı tipler |
| Bellek yönetimi | Elle / çöp toplayıcı / sahiplik / referans sayma / yok (donanım) |
| Değerlendirme | Hevesli (strict) / tembel (lazy) / bildirimsel çözümleme |
| Eşzamanlılık modeli | İş parçacığı / aktör / CSP-kanal / async-await / doğal paralel (donanım) / yok |
| Alan | Genel, web, sistem, veri, bilim, gömülü, endüstri, eğitim, finans, blokzincir… |
| Kaynak zenginliği | Yüksek / orta / düşük (araştırmayla belirlenir) |
| Yaşam durumu | Aktif / bakımda / tarihsel / ezoterik |

## Aile seçimi kuralları

- Bir dil birden çok aileye girebilir (ör. Scala: 1 ve 2; Julia: 1 ve 10; Elixir: 2 ve aktör eşzamanlılığı).
- **Birincil aile** müfredat iskeletini belirler. Diğer ailelerin "Ekle" maddeleri ilgili modüllere eklenir.
- Ailenin kavramsal makinesi bir konuyu öne almayı gerektiriyorsa (ör. donanım tanımlamada eşzamanlılık) bu gerekçesiyle söylenir. Bunun dışında modül sırası korunur.
- Dil hiçbir aileye uymuyorsa en yakın aile esas alınır. Farklar araştırmayla belirlenir ve "yeni aile adayı" diye not edilir.

## 1. Emperatif / nesne yönelimli genel amaçlı
**Örnek diller:** C, C++, Java, C#, Go, Python, JavaScript, Rust, Swift, Kotlin
- **Kavramsal makine:** Komutlar sırayla çalışır ve program durumu değiştirir. Değişkenler bellekteki yerlere ya da nesnelere bağlı adlardır. Her fonksiyon çağrısı çağrı yığınına (stack) bir çerçeve ekler. Dinamik veriler yığın dışı bellekte (heap) tutulur. Dile göre değer ve referans semantiği farklıdır: C'de değişken bellekte bir yerdir, Python'da bir nesneye bağlanmış bir addır.
- **Ekle:** Ana müfredat olduğu gibi kullanılır.
- **Çıkar / uyarla:** Bellek modülü dile göre işlenir (elle yönetim, çöp toplayıcı, sahiplik). Kalıtımı olmayan dillerde (C, Go) nesne yönelimi bileşim ve arayüzlerle anlatılır.
- **Tipik yanlış kavramalar:**
  - Atamanın matematiksel eşitlik olduğu.
  - Değişkenin eski değerlerini hatırladığı.
  - `b = a` sonrası nesnenin kopyalandığı; oysa referans paylaşılıyor olabilir.
  - Parametrelerin hep kopyalandığı ya da hep referansla geçtiği.
  - Tam sayı bölmesi ve kayan nokta yuvarlamasının her dilde aynı olduğu.
  - `while` koşulunun gövdedeki her satırdan sonra denetlendiği.
- **Gözlem araçları:** Hata ayıklayıcı (gdb, lldb, IDE), Python Tutor (adım adım bellek görünümü), derlenen diller için Compiler Explorer.
- **Kurulum notu:** Kurulum dosyasındaki ana kurulum rehberi uygulanır.

## 2. Fonksiyonel
**Örnek diller:** Haskell, OCaml, F#, Elm, Scheme/Racket, Clojure, Erlang/Elixir
- **Kavramsal makine:** Program ifadelerin değerlendirilmesidir. Yerine koyma (substitution) modeliyle çalışır: bir fonksiyon çağrısı, gövdesinde parametre yerine değer konmuş hâliyle değiştirilir. Değerler değişmez. Fonksiyonlar da değerdir. Tembel dillerde (Haskell) bir ifade ancak sonucu gerektiğinde değerlendirilir.
- **Ekle:**
  - Özyineleme ve kuyruk özyinelemesi
  - Değişmezlik
  - Yüksek mertebeli fonksiyonlar: map, filter, fold
  - Cebirsel veri tipleri ve örüntü eşleme (pattern matching)
  - Tip çıkarımı (ML ailesi)
  - Tembel değerlendirme (Haskell)
  - Yan etkilerin yönetimi: Haskell'de IO tipi; Erlang/Elixir'de süreçler, mesajlaşma ve "çökmesine izin ver" (let it crash) yaklaşımı
- **Çıkar / uyarla:**
  - Modül 4 ile 5 yer değiştirir: önce fonksiyonlar, sonra döngü yerine özyineleme ve fold.
  - Modül 7'deki "sınıflar" cebirsel veri tipleri ve kayıtlarla işlenir.
  - Nesne yönelimi kısaltılır.
- **Tipik yanlış kavramalar:**
  - Bir değişkene yeniden atama yapılabileceği.
  - Özyinelemenin her zaman yığını taşırdığı; kuyruk çağrısı optimizasyonu dile bağlıdır.
  - Tembel dilde `foldl` ile `foldr`'ın bellek davranışının aynı olduğu.
  - Monad'ın "yan etki" demek olduğu.
- **Gözlem araçları:** REPL (ghci, utop, racket, iex), `:type` gibi tip sorgulama komutları, DrRacket'in adım adım değerlendiricisi (stepper).
- **Kurulum notu:** Dile özgü araç zinciri kurulur (ör. Haskell için GHCup, OCaml için opam). İlk adım REPL'de ilk ifadeyi değerlendirmektir.

## 3. Mantıksal / kısıt
**Örnek diller:** Prolog, Datalog, MiniZinc
- **Kavramsal makine:** Program, olgu ve kurallardan oluşan bir bilgi tabanıdır; çalıştırmak ona sorgu sormaktır. Prolog çözümleyicisi hedefleri soldan sağa, kuralları yukarıdan aşağıya dener. Değişkenleri birleştirme (unification) ile bağlar, başarısız olunca geri izler (backtracking). MiniZinc'te ise model yazılır, aramayı çözücü yapar.
- **Ekle:** Birleştirme, geri izleme ve arama ağacı, kesme (`!`), başarısızlık olarak olumsuzlama (negation as failure), listeler ve özyineleme, DCG (Prolog), kısıt programlama (CLP(FD)).
- **Çıkar / uyarla:** Atamalı değişken, döngü ve nesne yönelimi modülleri çıkarılır. Fonksiyonlar modülü "yüklemler (predicates) ve ilişkiler" olur; tek bir yüklem birden çok yönde kullanılabilir.
- **Tipik yanlış kavramalar:**
  - `=`'in atama olduğu. Aslında birleştirmedir; aritmetik `is` ile yapılır.
  - Kural sırasının önemsiz olduğu. Sol özyineleme sonsuz döngüye yol açabilir.
  - Bağlanan bir değişkenin sonradan değiştirilebileceği.
  - `\+`'nın mantıksal olumsuzlama olduğu.
- **Gözlem araçları:** `trace.` ile adım adım izleme (SWI-Prolog), arama ağacının elle çizilmesi.
- **Kurulum notu:** SWI-Prolog veya tarayıcıdaki SWISH; MiniZinc için MiniZinc IDE.

## 4. Sorgu / veri
**Örnek diller:** SQL, SPARQL, Cypher, GraphQL, XPath/XQuery, jq
- **Kavramsal makine:** Bildirimseldir: kullanıcı "ne" istediğini yazar, "nasıl" yapılacağını motor seçer. Akış şöyledir: ayrıştırma → mantıksal plan → optimizasyon → yürütme. SQL'de mantıksal işleme sırası: FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT.
- **Ekle:** Müfredat dosyasındaki sorgu dili müfredatı kullanılır ve dilin veri modeline (ilişkisel, graf, belge, ağaç, JSON) uyarlanır.
- **Çıkar / uyarla:** Ana müfredatın tip, bellek ve nesne yönelimi modüllerinin yerine veri modeli, sorgu planı ve işlem konuları gelir.
- **Tipik yanlış kavramalar:**
  - `NULL = NULL` ifadesinin doğru döndüğü. SQL'de üç değerli mantık vardır.
  - SELECT'te tanımlanan takma adın WHERE'de kullanılabileceği.
  - ORDER BY olmadan satır sırasının garanti olduğu.
  - LEFT JOIN'de sağ tabloya WHERE koşulu koymanın sonucu değiştirmediği. Aslında sorgu INNER JOIN gibi davranır.
  - `COUNT(*)` ile `COUNT(sütun)`'un aynı olduğu.
- **Gözlem araçları:** `EXPLAIN` / `EXPLAIN ANALYZE`, sorgu planı görselleştiricileri, GraphiQL, jqplay.
- **Kurulum notu:** Kurulum gerektirmeyen bir motorla başlanır (ör. SQLite). Diğer motorlar araştırmayla seçilir.

## 5. İşaretleme / stil / veri biçimi
**Örnek diller:** HTML, CSS, XML, JSON, YAML, LaTeX, Markdown
- **Kavramsal makine:** Metin ayrıştırıcıdan geçip bir ağaca (DOM, belge ağacı) dönüşür, ardından bir işleyici (tarayıcı, derleyici, uygulama) bu ağacı kullanır. CSS'te seçici eşleşmesi, basamaklama (cascade), özgüllük (specificity) ve kalıtım vardır. LaTeX makro genişletmeyle çalışır.
- **Ekle:** Şema doğrulama (XML Schema, JSON Schema), anlamsal HTML ve erişilebilirlik, CSS düzen modelleri (kutu modeli, flexbox, grid), YAML'ın girinti ve tip çıkarımı kuralları.
- **Çıkar / uyarla:** Ana müfredatın yalnızca yapı, ayrıştırma ve doğrulama modülleri uygulanır. Algoritma ve bellek modülleri atlanır, nedeni söylenir.
- **Tipik yanlış kavramalar:**
  - HTML'in görünümü belirlediği. HTML yapı ve anlamı belirler, görünümü CSS.
  - CSS'te en son yazılan kuralın her zaman kazandığı. Özgüllük önce gelir.
  - YAML'da `no`, `yes`, `on` değerlerinin metin kaldığı. YAML 1.1 ayrıştırıcıları bunları mantıksal değere çevirir.
  - JSON'da yorum ve sondaki virgülün yazılabileceği.
- **Gözlem araçları:** Tarayıcı geliştirici araçları (Elements, Computed), W3C doğrulayıcısı, `jq .`, `yamllint`.
- **Kurulum notu:** Tarayıcı ve editör yeterlidir. LaTeX için bir TeX dağıtımı kurulur ya da çevrimiçi bir editör kullanılır.

## 6. Betik / kabuk
**Örnek diller:** Bash, PowerShell, AWK, sed, Perl
- **Kavramsal makine:** Kabuk bir satırı okur ve önce genişletmeleri uygular: parametre, komut ikamesi, kelime bölme, glob. Sonra komutu ayrı bir süreç olarak çalıştırır. Boru hatları süreçleri birbirine bağlar ve her komutun bir çıkış kodu vardır. PowerShell'de boru hattından metin değil nesne akar. AWK, örüntü-eylem kurallarını her kayıt ve alan için çalıştırır.
- **Ekle:** Alıntılama (quoting) kuralları, genişletme sırası, çıkış kodları ve `set -euo pipefail`, standart akışlar ve yönlendirme, süreçler ve ortam değişkenleri, taşınabilirlik (POSIX sh ile bash farkı), komut enjeksiyonu.
- **Çıkar / uyarla:** Özel veri tipleri, nesne yönelimi ve tip sistemi modülleri kısalır. Eşzamanlılık modülü arka plan işleri, `wait` ve `xargs -P` ile işlenir.
- **Tipik yanlış kavramalar:**
  - Değişkeni tırnaksız kullanmanın güvenli olduğu. Kelime bölme ve glob devreye girer.
  - `[`'nin söz dizimi olduğu. Aslında bir komuttur, bu yüzden çevresindeki boşluklar zorunludur.
  - Boru hattında (alt kabukta) değiştirilen değişkenin üst kabukta da değiştiği.
  - Atamada `=` çevresine boşluk konabileceği.
- **Gözlem araçları:** `set -x` / `bash -x`, ShellCheck, `echo $?`.
- **Kurulum notu:** macOS'ta varsayılan kabuk zsh'dir ve hazır gelen bash eski bir sürümdür; bu fark baştan söylenir. Windows'ta WSL veya Git Bash kullanılır. PowerShell 7 çapraz platformdur.

## 7. Assembly / makine düzeyi
**Örnek diller:** x86-64, ARM (AArch64), RISC-V, 6502, WebAssembly metin biçimi
- **Kavramsal makine:** İşlemci getir-çöz-yürüt döngüsüyle çalışır. Yazmaçlar, bellek adresleri, durum bayrakları, program sayacı ve yığın işaretçisi vardır.
- **Ekle:** Komut kümesi mimarisi, adresleme modları, birleştirici sözdizimi lehçeleri (Intel ve AT&T), çağrı kuralı ve ABI, yığın çerçevesi, sistem çağrıları, birleştirici ve bağlayıcı, bayt sırası (endianness), C kodunun derleyici çıktısını okuma.
- **Çıkar / uyarla:** Koleksiyonlar, nesne yönelimi, genel programlama ve standart kütüphane modülleri "makine düzeyindeki karşılığı" olarak kısaca işlenir. Hata yönetimi bayraklar ve dönüş kodlarıyla anlatılır.
- **Tipik yanlış kavramalar:**
  - Tek bir "assembly dili" olduğu. Her mimarinin kendi dili vardır, aynı mimaride bile sözdizimi lehçeleri farklıdır.
  - `mov`'un veriyi taşıdığı. Aslında kopyalar.
  - Yazmaçların çağrıdan sonra korunduğu. Hangisinin korunacağını çağrı kuralı belirler.
  - İşaretli ve işaretsiz sayının veride ayrıldığı. Bu ayrımı veriyi yorumlayan komut yapar.
- **Gözlem araçları:** Hata ayıklayıcının yazmaç ve bellek görünümü, Compiler Explorer, benzeticiler (ör. RISC-V için RARS).
- **Kurulum notu:** Önce öğrencinin işlemci mimarisi sorulur. Apple Silicon'da yerel mimari ARM64'tür. Farklı bir mimari öğretilecekse benzetici veya emülatör (ör. QEMU) kurulur.

## 8. Donanım tanımlama
**Örnek diller:** Verilog, SystemVerilog, VHDL, Chisel
- **Kavramsal makine:** Kod bir program değil, bir devre tanımıdır. Bütün `always` / `process` blokları ve sürekli atamalar aynı anda çalışır. Kayıtlar saat kenarında güncellenir. Benzetici zamanı bir olay kuyruğuyla ilerletir.
- **Ekle:**
  - Kombinasyonel ve ardışık mantık
  - Bloklayan (`=`) ve bloklamayan (`<=`) atama
  - Saat ve sıfırlama, sonlu durum makineleri
  - Benzetim ile sentez farkı; sentezlenebilir alt küme
  - Test tezgâhı (testbench) ve dalga biçimi okuma
  - Zamanlama kavramı, FPGA akışı
- **Çıkar / uyarla:**
  - Eşzamanlılık dilin temeli olduğu için Bölüm 1'e alınır.
  - Döngüler modülü donanım çoğaltma (`generate`) olarak işlenir.
  - Dosya G/Ç, dinamik bellek ve nesne yönelimi atlanır; SystemVerilog'un doğrulama tarafı bunun dışındadır.
- **Tipik yanlış kavramalar:**
  - Satırların sırayla çalıştığı.
  - `for` döngüsünün zaman içinde tekrar ettiği. Aslında donanımı çoğaltır.
  - Benzetimde çalışan her kodun sentezlenebildiği.
  - `=` ile `<=`'nin birbirinin yerine kullanılabileceği.
  - Eksik `else` veya `case` dalının zararsız olduğu. İstenmeden mandal (latch) üretir.
- **Gözlem araçları:** Dalga biçimi görüntüleyici (GTKWave), `$display` / `$monitor`, sentez raporu ve şematik görünüm.
- **Kurulum notu:** Açık kaynak benzeticiler (Icarus Verilog, Verilator; VHDL için GHDL) veya tarayıcıda EDA Playground kullanılır. FPGA üreticilerinin araçları büyüktür ve kayıt gerektirebilir. Başlangıçta kart gerekmez.

## 9. Endüstriyel / PLC
**Örnek diller:** IEC 61131-3 dilleri: Ladder Diagram (LD), Function Block Diagram (FBD), Structured Text (ST), Sequential Function Chart (SFC). Instruction List (IL) kullanımdan kalkmıştır.
- **Kavramsal makine:** PLC programı bir olay geldiğinde değil, tarama döngüsü (scan cycle) içinde sürekli çalışır. Her taramada sırasıyla girişler okunup G/Ç görüntüsüne yazılır, program baştan sona çalışır, çıkışlar yazılır.
- **Ekle:**
  - G/Ç görüntüsü, kontaklar ve bobinler, mühürleme (self-holding) devresi
  - Zamanlayıcılar (TON, TOF, TP), sayaçlar (CTU, CTD), kenar algılama (R_TRIG, F_TRIG)
  - Görevler ve tarama süresi, SFC ile durum makineleri
  - Üretici farkları
  - Güvenlik ve acil durdurma ilkeleri: gerçek tesiste yalnızca yetkili kişi çalışır
- **Çıkar / uyarla:** Dosya G/Ç, dinamik veri yapıları ve paketleme modülleri kısalır. Test, benzetimde ve devreye almada yapılır. Dağıtım, programın PLC'ye yüklenmesidir.
- **Tipik yanlış kavramalar:**
  - Programın olay geldiğinde çalıştığı.
  - Çıkışın taramanın ortasında hemen değiştiği.
  - Aynı bobini birden çok basamakta yazmanın sorunsuz olduğu. Son yazan kazanır.
  - Zamanlayıcının kendi kendine saydığı. Girişin taramalar boyunca tutulması gerekir.
- **Gözlem araçları:** Çevrimiçi izleme (online monitoring), izleme tablosu (watch table), benzetici.
- **Kurulum notu:** Ortam üreticiye bağlıdır (ör. CODESYS, Siemens TIA Portal, Rockwell Studio 5000). Ücretsiz seçenekler araştırılır (ör. CODESYS geliştirme ortamı, OpenPLC). Ortam grafiktir; terminal adımları uygulanmaz. Gerçek ekipmana bağlanmadan benzetimle başlanır.

## 10. Bilimsel / dizi
**Örnek diller:** R, MATLAB/Octave, Julia, Fortran, APL/J/K
- **Kavramsal makine:** İşlemler tek tek öğeler yerine bütün dizi üzerinde yapılır (vektörleştirme). Dizi bellekte bitişik bir bloktur ve dile göre satır ya da sütun öncelikli dizilir. Sayılar kayan nokta aritmetiğiyle (IEEE 754) işlenir.
- **Ekle:** Vektörleştirme ve yayınlama (broadcasting), indeksleme kuralları (R, MATLAB, Julia ve Fortran'da 1'den başlar), kayan nokta ve sayısal doğruluk, eksik veri (NA, NaN), çizim, tekrarlanabilir analiz (betik, notebook), performans (döngü ile vektör farkı; Julia'da tip kararlılığı).
- **Çıkar / uyarla:** Nesne yönelimi ve paketleme modülleri dile göre kısalır. Standart kütüphane modülü bilimsel kütüphanelerle işlenir.
- **Tipik yanlış kavramalar:**
  - `0.1 + 0.2 == 0.3` ifadesinin doğru döndüğü.
  - Dizilerin 0'dan başladığı.
  - Döngünün her dilde yavaş olduğu. R ve MATLAB'da yavaştır, Julia ve Fortran'da değildir.
  - R'de kısa vektörün uyarısız tekrarlanmasının (recycling) zararsız olduğu.
  - APL'de işlem önceliği olduğu. Değerlendirme sağdan sola yapılır.
- **Gözlem araçları:** REPL, değişken gezgini (RStudio, MATLAB), profilleyici, `@code_warntype` (Julia).
- **Kurulum notu:** R ve RStudio; MATLAB yerine ücretsiz GNU Octave; Julia için juliaup; Fortran için gfortran.

## 11. Görsel / blok
**Örnek diller:** Scratch, Snap!, Blockly, LabVIEW, Node-RED
- **Kavramsal makine:** Scratch ve Snap!'te kuklalar (sprite) olayla tetiklenen betikler çalıştırır ve birden çok betik aynı anda çalışır. LabVIEW ve Node-RED'de veri akışı modeli vardır: bir düğüm, bütün girdileri geldiğinde çalışır.
- **Ekle:** Olaylar ve mesajlaşma (yayın), eşzamanlı betikler ve yarış koşulları, klonlar (Scratch), veri akışı yürütmesi (LabVIEW), mesaj nesnesi (Node-RED'de `msg`).
- **Çıkar / uyarla:**
  - Kod blokları yerine ekran adımları yazılır (ör. "Olaylar > yeşil bayrak tıklandığında").
  - Terminal kurulum adımları uygulanmaz.
  - Derleme ve paketleme modülü, projeyi paylaşma ve dışa aktarma olarak işlenir.
- **Tipik yanlış kavramalar:**
  - Ekrandaki bütün betiklerin tek bir sıra hâlinde çalıştığı.
  - LabVIEW diyagramının soldan sağa çalıştığı. Çalışma sırasını veri bağımlılığı belirler.
  - Bir mesaj yayınlandığında alıcı betiğin bitmesinin beklendiği. Bu, "yayınla" ile "yayınla ve bekle" arasındaki farktır.
- **Gözlem araçları:** Snap!'te görünür adımlama (visible stepping), LabVIEW'de yürütmeyi vurgulama (highlight execution), Node-RED'de debug düğümü.
- **Kurulum notu:** Scratch ve Snap! tarayıcıda çalışır. LabVIEW'in kişisel kullanım için ücretsiz bir sürümü vardır, koşulları araştırılır. Node-RED, Node.js üzerine kurulur.

## 12. Yığın tabanlı
**Örnek diller:** Forth, PostScript, Factor
- **Kavramsal makine:** Bir veri yığını ve bir dönüş yığını vardır. Her kelime (word) yığından değer alır ve yığına değer koyar. Tanımlanan kelimeler bir sözlükte (dictionary) tutulur. Sistem yorumlama ve derleme modu arasında geçiş yapar.
- **Ekle:** Yığın etkisi gösterimi `( a b -- c )`, ters Leh gösterimi, yığın düzenleme kelimeleri (DUP, DROP, SWAP, OVER, ROT), kelime tanımlama (`: … ;`), derleme zamanı kelimeleri (IMMEDIATE), bellek ve değişkenler (`VARIABLE`, `!`, `@`), dönüş yığını.
- **Çıkar / uyarla:** Tip sistemi ve nesne yönelimi modülleri büyük ölçüde atlanır. Koleksiyonlar modülü bellek bloklarıyla işlenir.
- **Tipik yanlış kavramalar:**
  - Yığın etkisinin yazılmasının gereksiz olduğu.
  - `.` kelimesinin yığını değiştirmeden yazdırdığı. Aslında en üstteki değeri tüketir.
  - Kelimelerin boşluksuz yazılabileceği. Kelimeler boşlukla ayrılır.
- **Gözlem araçları:** `.S` ile yığın içeriği, `SEE` ile kelimenin tanımı.
- **Kurulum notu:** Forth için Gforth (Forth-2012 standardı ile sistemler arasındaki lehçe farkı belirtilir), PostScript için Ghostscript.

## 13. Kanıt asistanı / bağımlı tipli
**Örnek diller:** Lean, Rocq (eski adı Coq), Agda, Idris, Isabelle (Isabelle/HOL bağımlı tipli değildir)
- **Kavramsal makine:** Önermeler birer tiptir, kanıtlar o tipin değerleridir (Curry–Howard eşlemesi). Tip denetleyici kanıtı kontrol eder. Taktik modunda hedef durumu (goal) adım adım dönüştürülür.
- **Ekle:** Tümevarımsal tipler, örüntü eşleme ve özyineleme (sonlanma denetimi), önermeler ve kanıtlar, taktikler, hedef durumunu okuma, tümevarımla kanıt, kütüphanede lemma arama (ör. Lean'de Mathlib).
- **Çıkar / uyarla:** Bölüm 1'in programlama kısmı fonksiyonel aile gibi işlenir. G/Ç, eşzamanlılık ve performans modülleri kısalır. Test modülünün yerini kanıt, hata ayıklama modülünün yerini hedef durumunu okuma alır.
- **Tipik yanlış kavramalar:**
  - Kanıt geçtiyse teoremin istenen şeyi söylediği. Tanım yanlışsa kanıt yanlış şeyi kanıtlar.
  - `sorry` / `admit` ile kapatılan kanıtın tamamlanmış olduğu.
  - Taktikleri ne yaptığını bilmeden deneme yanılmayla kullanmanın yeterli olduğu.
- **Gözlem araçları:** Lean infoview, hedef penceresi (VS Code eklentileri, CoqIDE / RocqIDE), `#check`, `#eval`, `#print`.
- **Kurulum notu:** Lean 4 için elan (sürüm yöneticisi), lake (yapı aracı) ve VS Code eklentisi. Rocq için opam veya platform paketi. Kurulum yolları sık değiştiği için araştırmayla doğrulanır.

## 14. Akıllı sözleşme
**Örnek diller:** Solidity, Vyper, Move
- **Kavramsal makine:** Sözleşme, blokzincirde yaşayan bir durum ve bu durumu değiştiren fonksiyonlardır. Her işlem (transaction) ağdaki düğümlerde aynı sonucu verecek biçimde (deterministik) çalışır ve gaz harcar. İşlem ya tamamen uygulanır ya da tamamen geri alınır.
- **Ekle:** Hesaplar ve işlemler, durum değişkenleri ve depolama maliyeti, gaz, çağrı bağlamı (`msg.sender` vb.), olaylar (events), değiştirilemez dağıtım ve yükseltme desenleri, test ağları, güvenlik açıkları (yeniden giriş, erişim denetimi, ön çalıştırma, eski sürümlerde tam sayı taşması), denetim (audit).
- **Çıkar / uyarla:** Dosya G/Ç ve eşzamanlılık modülleri yerine işlem sıralaması ve atomiklik işlenir. Performans modülü gaz optimizasyonu olur.
- **Tipik yanlış kavramalar:**
  - Dağıtılan kodun sonradan düzeltilebileceği.
  - Zincirdeki `private` verinin gizli olduğu. Herkes okuyabilir.
  - Dış çağrıdan sonra durumu güncellemenin güvenli olduğu. Yeniden giriş açığına yol açar.
  - Blok zaman damgasının güvenli bir rastgelelik kaynağı olduğu.
- **Gözlem araçları:** Remix IDE hata ayıklayıcısı, işlem izi, yerel test zinciri (ör. Foundry/Anvil, Hardhat).
- **Kurulum notu:** Tarayıcıda Remix ile başlanır. Gerçek para kullanan ana ağ yerine **yalnızca yerel zincir veya test ağı** kullanılır. Bu baştan söylenir.

## 15. GPU / gölgelendirici
**Örnek diller:** GLSL, HLSL, WGSL, CUDA, Metal Shading Language
- **Kavramsal makine:** Aynı çekirdek (kernel) veya gölgelendirici binlerce iş parçacığında paralel çalışır. Her iş parçacığı kendi indeksine göre veri seçer. Bellek hiyerarşisi vardır: global, paylaşılan ve yazmaç. Grafikte boru hattı şöyle ilerler: köşe → rasterleştirme → parça.
- **Ekle:**
  - İş parçacığı, blok ve ızgara (CUDA) ya da çalışma grubu (workgroup)
  - Bellek türleri ve birleştirilmiş erişim (coalescing)
  - Senkronizasyon (barrier), dallanma ayrışması (divergence)
  - Ana makine ile aygıt arası veri aktarımı
  - Grafik boru hattı aşamaları ve gölgelendirici girdileri (uniform, attribute)
- **Çıkar / uyarla:** Dosya G/Ç, nesne yönelimi ve paket yöneticisi modülleri kısalır. Performans modülü büyür. Hata ayıklama zor olduğu için ayrı bir ağırlık verilir.
- **Tipik yanlış kavramalar:**
  - GPU'nun her işi hızlandırdığı. Veri aktarımı ve dallanma maliyeti vardır.
  - İş parçacıklarının belirli bir sırayla çalıştığı.
  - Paylaşılan belleğe senkronizasyonsuz yazmanın güvenli olduğu.
- **Gözlem araçları:** GPU profilleyicileri (ör. Nsight, RenderDoc, Xcode GPU araçları), Shadertoy.
- **Kurulum notu:** Önce donanım sorulur: CUDA yalnızca NVIDIA GPU'da çalışır, Metal Apple aygıtlarında. Tarayıcıda WebGPU (WGSL) ve Shadertoy (GLSL) kurulumsuz seçeneklerdir.

## 16. Alana özgü / yapılandırma
**Örnek diller:** Terraform HCL, Nix, Make, CMake, düzenli ifadeler (regex), Excel formülleri
- **Kavramsal makine:** Araca göre değişir:
  - Terraform: istenen durum bildirilir, araç mevcut durumla farkı hesaplayıp uygular (plan / apply).
  - Make: hedef ve önkoşullardan oluşan bir bağımlılık grafiği vardır; dosyaların zaman damgasına bakılır.
  - Regex: motor girdiyi örüntüyle eşleştirir, çoğunlukla geri izleyerek.
  - Excel: hücreler arasında bir bağımlılık grafiği vardır ve değişince yeniden hesaplanır.
- **Ekle:** Dil kendi başına değil, ait olduğu araçla öğretilir. Akış şöyledir: aracın çözdüğü sorun → dilin yapı taşları → araçla çalışma akışı → sık hatalar → iyi uygulamalar.
- **Çıkar / uyarla:** Ana müfredatın çoğu atlanır. Gereken modüller (ör. fonksiyonlar, modüller, test) aracın karşılıklarıyla işlenir.
- **Tipik yanlış kavramalar:**
  - Make tarifinde girinti için boşluk kullanılabileceği. Sekme şarttır.
  - Regex lehçelerinin (POSIX, PCRE, JavaScript) aynı olduğu.
  - `.*`'ın açgözlü (greedy) olmadığı.
  - Terraform durum dosyasının önemsiz olduğu.
  - Excel'de göreli ve mutlak başvurunun (`A1`, `$A$1`) kopyalarken aynı davrandığı.
- **Gözlem araçları:** `terraform plan`, `make -n`, regex101 (lehçe seçerek), Excel'de "Formülü Değerlendir".
- **Kurulum notu:** Aracın kendisi kurulur. Dilin sürümü aracın sürümüne bağlıdır.

## 17. Tarihsel / eski sistem
**Örnek diller:** COBOL, Fortran 77, BASIC, Pascal, Ada, PL/I, RPG
- **Kavramsal makine:** Dile göre değişir. Örneğin COBOL'da program bölümlere (DIVISION) ayrılır, kayıt yapılı dosyalarla ve sabit noktalı ondalık aritmetikle çalışılır. Fortran 77'de sabit sütun biçimi vardır.
- **Ekle:** Hangi sürüm ve lehçenin öğretildiği (ör. COBOL-85, IBM Enterprise COBOL, GnuCOBOL), sabit biçim kuralları, dönemin araç zinciri ve iş akışı (ör. ana bilgisayarda JCL ve toplu iş), eski kodu okuma ve modernleştirme, günümüzdeki kullanım alanı.
- **Çıkar / uyarla:** Dilde olmayan modern modüller (paket yöneticisi, eşzamanlılık, genel programlama) atlanır, nedeni söylenir. Bölüm 5'teki proje, eski bir kodu okuyup değiştirme projesi olabilir.
- **Tipik yanlış kavramalar:**
  - Modern dil alışkanlıklarının geçerli olduğu: serbest biçim, blok kapsamlı yerel değişken, özyineleme. Örneğin Fortran 77 standardı özyinelemeye izin vermez.
  - COBOL'da değişkenlerin kullanıldığı yerde tanımlanabileceği. Hepsi DATA DIVISION'da tanımlanır.
- **Gözlem araçları:** Derleyici listeleme çıktıları, hata ayıklayıcı.
- **Kurulum notu:** Açık kaynak derleyiciler kullanılır (GnuCOBOL, gfortran, Free Pascal, GNAT). Ana bilgisayar ortamı için benzetici veya eğitim erişimi araştırılır. Kaynak azsa bu söylenir.

## 18. Ezoterik
**Örnek diller:** Brainfuck, Befunge, Whitespace
- **Kavramsal makine:** Her dilin kendine özgü küçük bir makinesi vardır. Brainfuck: hücrelerden oluşan bir bant, bir veri işaretçisi ve 8 komut. Befunge: iki boyutlu ızgarada hareket eden bir komut işaretçisi ve bir yığın.
- **Ekle:** Asıl amaç kavramsal makineyi ve hesaplanabilirliği (Turing tamlığı) anlamaktır. İlgi varsa proje olarak dilin yorumlayıcısı yazdırılır.
- **Çıkar / uyarla:** Bölüm 1–2 kısaltılır. Bölüm 4 (profesyonel kullanım) atlanır, nedeni söylenir.
- **Tipik yanlış kavramalar:** Hücre boyutu ve taşma davranışının her yorumlayıcıda aynı olduğu. Brainfuck'ta 8 bitlik sarma yaygındır ama standart değildir.
- **Gözlem araçları:** Bant veya ızgarayı gösteren görsel yorumlayıcılar.
- **Kurulum notu:** Çevrimiçi bir yorumlayıcı yeterlidir. Birincil kaynak çoğu zaman esolangs wiki ve dilin özgün tanımıdır.

## 19. Kuantum
**Örnek diller:** Q#, OpenQASM, Qiskit (Python kütüphanesi)
- **Kavramsal makine:** Kübitlerin durumu bir durum vektörüyle gösterilir. Kapılar bu vektöre üniter dönüşüm uygular. Ölçüm olasılıksal bir sonuç verir ve durumu çöktürür. Programlar devre modeliyle yazılır.
- **Ekle:**
  - Doğrusal cebir ön koşulu: vektör, matris, karmaşık sayı
  - Kübit ve Bloch küresi, tek ve çok kübitli kapılar, dolanıklık
  - Ölçüm ve istatistik (shots)
  - Temel algoritmalar: Deutsch–Jozsa, Grover, kuantum Fourier dönüşümü
  - Gürültü ve gerçek donanımın kısıtları
  - Klasik–kuantum karma programlar
- **Çıkar / uyarla:** Genel programlama konuları ev sahibi dil (ör. Python) üzerinden kısa tutulur. Hata ayıklama modülü benzeticide durum vektörünü incelemek olarak işlenir.
- **Tipik yanlış kavramalar:**
  - Kübitin "aynı anda 0 ve 1" olduğu ve bütün sonuçların paralel hesaplandığı.
  - Tek bir ölçümün kesin sonuç verdiği. Sonuç olasılıksaldır, çok sayıda tekrar gerekir.
  - Kübitin kopyalanabileceği. Kopyalama yasağı (no-cloning) vardır.
- **Gözlem araçları:** Durum vektörü benzeticisi, sonuç histogramı, devre çizimi.
- **Kurulum notu:** Benzeticiyle başlanır. Gerçek donanıma erişim hesap gerektirir. Kütüphane arayüzleri sık değiştiği için sürüm araştırması zorunludur.
