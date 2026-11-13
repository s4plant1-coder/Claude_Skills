# Kurulum ve araçlar

Bu dosya iş akışının 5. adımında okunur: ilk uygulamalı derste ya da kullanıcı kurulumda takıldığında. Buradaki tablolar başlangıç kataloğudur. Güncel sürüm ve bağlantılar her öğretimde araştırmayla doğrulanır.

## İçindekiler
1. Kurulum rehberi
2. Aileye göre ortam farkları
3. Başlangıç dil profili örnekleri
4. Araç kataloğu
5. Ortam karşılaştırması
6. Sık kurulum sorunları
7. Kurulum kontrol listesi

## 1. Kurulum rehberi

Dili tanıma modülünden sonraki ilk uygulamalı ders kurulumdur. Kurulum doğrulanmadan modül anlatımına geçilmez. Bu, "ders anlatıldı ama kullanıcı çalıştıramadı" durumunu önler.

Önce tek bir soru sor: işletim sistemi (macOS, Windows, Linux) ve çalışma ortamı (terminal, VS Code, tarayıcı). Cevap yeterlidir, başka soru sorma. Dilin ailesi donanım gerektiriyorsa (assembly, GPU) işlemci veya ekran kartı da aynı soruda sorulur.

Kurulum adımları:
1. **Dilin derleyicisini veya yorumlayıcısını kur.** Derleyici tablosundaki ve araştırma çıktısındaki resmi kurulum sayfasını ve güncel kararlı sürümü belirt. Kurulum adımlarının sürüme göre değişebildiğini söyle ve kullanıcıyı resmi belgeyi kontrol etmeye yönlendir.
2. **Sürümü kontrol ettir.** Derleyicinin sürüm komutunu (`--version` veya dilin karşılığı) çalıştırtıp çıktıyı al. Çıktı alınmadan sonraki adıma geçme.
3. **Editörü seç.** Başlangıç için terminal ve düz bir editör önerilir. Alternatifler, dile özgü eklentisiyle VS Code ya da dilin IDE'sidir. Seçenekleri ortam karşılaştırması tablosuyla göster.
4. **Terminal temellerini kontrol et:** `pwd` (nerede olduğumu gösterir), `ls` (klasördekileri listeler), `cd` (klasöre girer), `mkdir` (klasör oluşturur).
5. **İlk programı derleyip çalıştır.** Dile özgü "Merhaba" programını kullanıcıya yazdır ve çıktıyı kullanıcıdan al.
6. **Derleme uyarılarını standartlaştır.** Uyarıları açan bayraklar dile göre belirlenir. Örnek: C++ için `-std=c++23 -Wall -Wextra -pedantic`. Diğer dillerde uyarı bayrakları veya ayarları araştırmadan alınır.

## 2. Aileye göre ortam farkları

Aile numaraları dil aileleri dosyasındaki numaralardır.

| Ortam türü | Aileler | Kurulumda ne değişir |
|---|---|---|
| Terminal + derleyici / yorumlayıcı | 1, 6, 10, 12, 17 | Kurulum rehberi olduğu gibi uygulanır |
| REPL merkezli | 2, 3, 10, 13 | "İlk program" yerine önce REPL'de ilk ifade değerlendirilir, dosyadan yükleme ikinci adımdır |
| Benzetici | 7, 8, 9, 17 (ana bilgisayar), 19 | Adım 1'de benzetici kurulur. İlk program ilk benzetimdir. Çıktı dalga biçimi, yazmaç görünümü veya ölçüm histogramı olabilir. |
| Grafik ortam | 9, 11 | Terminal temelleri (adım 4) atlanır. Adımlar ekran tarifi olarak verilir. Sürüm, "Hakkında" penceresinden okunur. |
| Tarayıcı tabanlı | 5, 11 (Scratch, Snap!), 14 (Remix), 15 (WebGPU, Shadertoy) | Kurulum gerekmez. Projeyi kaydetme ve paylaşma anlatılır, gizlilik uyarısı yapılır. |
| Donanıma bağlı | 7 (işlemci mimarisi), 15 (CUDA: NVIDIA, Metal: Apple), 8 (FPGA kartı, isteğe bağlı) | Önce donanım sorulur. Uygun değilse benzetici, tarayıcı veya bulut seçeneği önerilir. |
| Ait olduğu araçla | 4, 16 | Dil, aracın (veri tabanı, Terraform, Excel vb.) kurulumuyla birlikte gelir |

## 3. Başlangıç dil profili örnekleri

Bu tablo yalnızca başlangıç örneğidir. Her öğretimde araştırmayla doğrulanır. Tabloda olmayan dilin profili araştırma çıktısında oluşturulur.

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

## 4. Araç kataloğu

Resmi kaynaklardan alınmıştır. Kurmadan önce güncel sürüm kontrol edilir.

**Her ortam için zorunlu:**

| Araç | Ne için? | Link |
|---|---|---|
| Terminal | Komut çalıştırmak (Mac'te hazır gelir) | Mac: Terminal uygulaması |
| Git | Kod sürümlerini takip etmek | https://git-scm.com |
| VS Code | Editör | https://code.visualstudio.com |
| Homebrew (yalnızca Mac) | Paket kurmak | https://brew.sh |

**Dil bazlı derleyici ve yorumlayıcılar:**

Bu bir başlangıç kataloğudur. Güncel sürüm ve bağlantılar her öğretimde araştırmayla doğrulanır. Tabloda olmayan dilin derleyicisi araştırmayla bulunur.

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

Dile özgü diğer araçlar (paket yöneticisi, test aracı, biçimlendirici, statik analiz, veri tabanı araçları, çevrimiçi deneme ortamı) araştırma çıktısındaki araç tablosundan gelir.

## 5. Ortam karşılaştırması

| Ortam | Avantaj | Dezavantaj | Ne zaman |
|---|---|---|---|
| Terminal | Derleme adımları görünür | Başta alışmak gerekir | Öğrenmenin başı |
| VS Code + eklenti | Tek tuşla çalıştırma | Eklenti ayarı gerekebilir | Günlük çalışma |
| Dilin IDE'si | Büyük projelerde kolay | Ağır, öğrenme eğrisi | Büyük projeler |
| Tarayıcı derleyicisi | Kurulum gerektirmez | Dosya yönetimi zor, kod sunucuda işlenir | Hızlı deneme |

Tarayıcı derleyicisinde gizli veya kişisel kod paylaşılmamalıdır.

## 6. Sık kurulum sorunları
- **"command not found":** Derleyici kurulu değil ya da PATH'te yok. Kurulumu yeniden kontrol et.
- **"No such file or directory":** Yanlış klasördeyiz. `pwd` ile konumu doğrula.
- **Derleme hatası:** Hata mesajını aynen iste ve birlikte yorumla.
- **Çalıştırılabilir dosya:** Windows'ta `.exe` uzantılı olur. Mac ve Linux'ta `./ad` ile çalıştırılır.

## 7. Kurulum kontrol listesi

Hepsi tamamlanmadan ilk modüle geçilmez:
- [ ] Derleyici veya yorumlayıcı sürümü görünüyor
- [ ] Çalışma klasörü biliniyor (`pwd`)
- [ ] İlk program derlendi ve beklenen çıktı alındı
- [ ] Editör seçildi ve dosya kaydetme çalışıyor

Benzetici, grafik veya tarayıcı ortamlarında maddeler uyarlanır. "Derleyici sürümü" yerine aracın veya benzeticinin sürümü, "ilk program" yerine ilk benzetim, ilk basamak (ladder) ya da ilk blok betiği kontrol edilir.
