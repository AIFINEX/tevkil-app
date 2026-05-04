# Rakip Analizi — TEVKİL

> Avukat Dayanışma ve Yardımlaşma Ağı · [tevkil.com.tr](https://www.tevkil.com.tr/)

## 1. Künye

| | |
|---|---|
| **Marka** | Tevkil — Avukat Dayanışma ve Yardımlaşma Ağı |
| **Şirket** | Belirsiz (sitede sadece "Avukatlara özel bir projedir") |
| **Kuruluş** | 2010 (16 yıllık operasyon) |
| **Domain** | tevkil.com.tr |
| **iOS app** | [App Store](https://apps.apple.com/us/app/tevkil-mobil/id6761544021) — 404 (iOS sayfası şu an erişilemez) |
| **Android app** | [Google Play](https://play.google.com/store/apps/details?id=com.tevkilmobile.app) |
| **Android içerik derecesi** | PEGI 3 |
| **Dil** | Türkçe |
| **İletişim** | `/iletisim` |
| **Telif** | "Tevkil.com.tr 2010-2024" — **2026 güncellemesi yok** (bakım yetersiz işareti) |
| **Pazar duruşu** | Köklü, "kar amacı gütmez" konumlandırma |

## 2. Site mimarisi

```
Hakkımızda  |  İletişim  |  KVKK Aydınlatma Metni
```

**Yalnızca 3 footer linki.** Üst menüde "Giriş yap" dışında item yok. AVUTAP'a kıyasla **yarı yarıya az içerik** (7 vs 3 sayfa).

## 3. Pozisyonlama

### Slogan
> **"Avukat dayanışma ve yardımlaşma ağı"**

### Hero metni (kelimesi kelimesine)
> Türkiye'nin en büyük avukat dayanışma ve yardımlaşma ağına katılarak her il ve ilçeyi kapsayacak yardımcı meslektaş portföyüne sahip olabilirsiniz.

### Kullanım senaryoları (Hakkımızda)
> Bir dosya fotokopisi, duruşma, haciz yada kalem işleriniz için uzun ve yorucu yolculuklar yaparak başka bir şehre gitmek yerine o bölgedeki bir meslektaşınızdan yardım alarak işlerinizi yürütebilirsiniz.

### Markanın USP'leri
1. **2010'dan beri** — 16 yıllık marka değeri
2. **"Dayanışma" söylemi** — ticari değil mesleki
3. **"Kar amacı gütmez"** — açıkça vurgulu
4. **Avukat profil portföyü** — directory model (you find a lawyer's profile)
5. **Tarafsızlık vurgusu** — "Avukat olarak sizler belirlersiniz"

## 4. Sayısal göstergeler

| Metrik | Değer | Periyot |
|---|---:|---|
| Toplam üye | **10.000+** | Kümülatif |
| Yardım talebi | **5.326** | Son 1 yıl |
| Gelen cevap | **12.926** | Son 1 yıl |
| Yardımlaşma (gerçekleşen iş) | **3.813** | Son 1 yıl |

### Kritik analiz

| Hesap | Sonuç |
|---|---|
| Talep başına cevap | 12.926 ÷ 5.326 = **~2.4 cevap/talep** (sağlıklı arz) |
| Talep → iş dönüşüm | 3.813 ÷ 5.326 = **%72** |
| Cevap → iş dönüşüm | 3.813 ÷ 12.926 = **%29** |
| Aylık iş hacmi | 3.813 ÷ 12 = **~318 iş/ay** |
| Kullanıcı başına iş hacmi | 3.813 ÷ 10.000 = **0.38 iş/üye/yıl** |

> **Yorum:** %28 talebin ölü düşmesi (1.513 talep gerçek işe dönmemiş) **manuel modelin** boşluğunu gösterir. Aktif kullanıcı oranı düşük (0.38 iş/üye/yıl).
>
> **Mukayese:** AVUTAP 55.849 avukat / 596 adliye iddia ediyor; bu noktada AVUTAP TEVKİL'in **5.5 katı** ölçeği yakalamış — büyük ihtimal **otomasyon + 15 dk SLA** sayesinde.

## 5. Anasayfa bölümleri

1. Header (logo + giriş)
2. Hero
3. **App Store + Google Play butonları** (üstte, prominent)
4. **İstatistik kartları (4 adet)** — Üye / Talep / Cevap / Yardımlaşma
5. "Avukatlara Özel Neler Yapabilirsiniz?" tanıtım metni
6. **3 adımlı özellikler** kısmı (Üye olun / Yardım isteyin / Yardımcı olun)
7. Mobil uygulama promosyonu (mock görsel)
8. Footer (Hakkımızda / İletişim / KVKK)

## 6. CTA'lar

| Buton | Hedef |
|---|---|
| App Store | iOS app sayfası |
| Google Play | Android app sayfası |
| Giriş yap | `/auth` |

> **"Hemen Kayıt Ol" CTA YOK** — kayıt yalnızca app indirilerek veya `/auth` üzerinden. Bu **conversion açısından zayıflık**.

## 7. Özellik seti

### 3 ana özellik (anasayfada)

| Başlık | Tam metin |
|---|---|
| **Üye olun** | Türkiye nin en büyük avukat dayanışma ve yardımlaşma ağına katılarak her il ve ilçeyi kapsayacak yardımcı avukat portföyüne sahip olabilirsiniz. |
| **Yardım isteyin** | Şehir dışı işlerinizi o bölgedeki bir meslektaşınızın yardımı ile yürütebilirsiniz. Böylelikle zamandan kazanır, masraflarınızı azaltabilirsiniz. |
| **Yardımcı olun** | Türkiye nin her bölgesinden meslektaşlarınızın duyulabilecek yardım ihtiyaçlarına cevap verebilir bu sayede ek gelir sağlayabilirsiniz. |

### Sürecin doğası — directory + manuel

Hakkımızda'dan:

> "Sitemize kayıtlı avukatların **hangi il yada ilçede mesleklerini icra ettiğini, ilgili veya uzmanı oldukları dalları ve hangi dalda size yardımcı olabileceklerini görebilir, iletişim bilgilerine ulaşabilirsiniz**."

→ TEVKİL **directory + iletişim modeli**:
1. Avukat profili oluşturur (il, ilçe, uzmanlık dalları, iletişim)
2. Yardım arayan avukatlar profilleri **arar**
3. Buldukları meslektaşa **doğrudan iletişim kurar**
4. Pazarlık + iş yapımı **platform dışında** (avukatlar arasında)

> **AVUTAP'tan farkı:** AVUTAP **algoritmik atama**, TEVKİL **profil arama**. AVUTAP push, TEVKİL pull.

### Mobil uygulama promosyonu metni
> "Sizler için sunmuş olduğumuz web arayüzümüzün dışında, mobil uygulamamız ile Avukat Tevkil Ağı Projesine daha kolay ulaşın..."

→ Web öncelikli; mobil ek/yardımcı pozisyonlu (AVUTAP mobile-first vs).

## 8. Gelir / fiyat modeli

- **Açık fiyat tarifesi YOK**
- Resmi söylem (Hakkımızda + Footer):
  > "Hizmetinize sunduğumuz web sitesi, **çıkar amacı gütmemekte, iş getirme amacı taşımamaktadır**. Var olan işlerinizin meslektaşlarınıza isteğinize bağlı olarak tevdi edilmesi amacı güder. Yardım isteyeceğiniz veya yardımcı olacağınız avukatı **site belirlemez, avukat olarak sizler belirlersiniz**."
- *"Yeterli müvekkil portföyünüz oluşana kadar, diğer meslektaşlarınıza uygun ücreti karşılığı yardımcı olabilir ve bu yolla gelir elde edebilirsiniz"* — ek gelir modeli, platform aracılık etmiyor
- **Cüzdan / komisyon yapısı yok**
- **Aylık abonelik var mı belirsiz** (sitede yazmıyor; muhtemelen yok)

> **Strateji:** "Kar amacı gütmez" pozisyonu **Md. 48 (komisyonculuk yasağı)** ihlali endişesini bertaraf etmek için seçilmiş — ama bu, **gelir modeli olmaması demek değil**; muhtemelen sponsor/reklam veya başka kanaldan gelir var (sitede şeffaf değil).

## 9. Yasal pozisyon (Hakkımızda — detaylı)

Sayfada **Md. 48** ve **Md. 171** tam metniyle alıntılanıyor.

- **Md. 48 — Komisyonculuk yasağı:** "Avukat veya iş sahibi tarafından vaat olunan veya verilen bir ücret yahut da herhangi bir çıkar karşılığında avukata iş getirmeye aracılık edenler ve aracı kullanan avukatlar altı aydan bir yıla kadar hapis cezası ile cezalandırılır..."
- **Md. 56 — Yetki belgesi:** Anılıyor ama tam metni alıntılanmıyor
- **Md. 171 — İşi sonuna kadar takip + Başkasını tevkil:** Tam metin var. Tevkil eden avukatın **müştereken ve müteselsilen sorumluluk** vurgulu

> AVUTAP ile aynı yasal çerçeve referansı — ama TEVKİL daha uzun ve detaylı işliyor.

## 10. Teknolojik altyapı (gözlemlenen)

| Bileşen | Durum |
|---|---|
| **Otomatik eşleştirme** | ❌ — manuel directory model |
| **15 dk SLA** | ❌ |
| **Robot arama** | ❌ |
| **SMS bildirim** | Belirsiz |
| **E-mail bildirim** | Belirsiz |
| **Push notification** | Mobile app olduğuna göre muhtemelen var |
| **Cüzdan / banka transferi** | ❌ (platform ödemeye katılmıyor) |
| **Sicil onayı** | ✅ (kayıt sürecinde) |
| **SMS + e-mail doğrulama** | Belirsiz |
| **Anlaşmazlık çözümü** | ❌ |
| **Canlı aktivite akışı** | ❌ |
| **Live chat / destek** | ❌ |
| **Tanıtım videosu** | ❌ (sadece statik mock görsel) |
| **Müşteri yorumları** | ❌ |
| **Aktif sürüm yönetimi** | Şüpheli (iOS sayfası 404, footer "2024" yazıyor) |
| **YouTube embed** | ❌ |
| **Anonimleştirilmiş feed** | ❌ |

## 11. Tasarım & marka

- **Renk paleti:** Beyaz arka plan + lacivert/koyu vurgu
- **Tipografi:** Sans-serif, hiyerarşik
- **İkonografi:** 4 istatistik ikonu, 3 işlem ikonu — sade
- **Genel ton:** Profesyonel ama **eski moda hissi**
- **Mobile-first değil** — web öncelikli
- **Footer copyright "2024"** — 2026'da güncellenmemiş = aktif olmayan bakım sinyali
- **Sosyal medya simgeleri var ama linkler aktif değil** — yarı bırakılmış izlenimi

## 12. Güçlü yönler

- **16 yıllık marka değeri** (2010'dan beri operasyonda)
- **10.000+ kümülatif üye** — organik tabana sahip
- **"Dayanışma" duygusal söylemi** — avukat etiğine yakın
- **"Kar amacı gütmez"** mesajı — Md. 48 endişesini çürüten stratejik pozisyon
- **Düşük operasyonel maliyet** — manuel model, ağır otomasyon yok
- **Hukuki çerçeve metinleri** detaylı (md. 48, 171 tam alıntı)
- **Footer KVKK linki** — yasal uyum sinyali

## 13. Zayıf yönler / boşluklar

- **Otomatik eşleştirme yok** — AVUTAP karşısında yapısal dezavantaj
- **15 dk SLA gibi vaad yok** — hız iddiası eksik
- **Cüzdan + komisyon yok** — platform iş'in finansal akışında yer almıyor (güven açığı)
- **Modern UI eksik** — canlı feed, video, testimonial yok
- **Mobile app aktif değil** (iOS 404, footer 2024)
- **Yalnız 3 footer linki** — şirket bilgisi, kullanıcı sözleşmesi, gizlilik metni eksik
- **Şirket adı / KVKK metinleri haricinde şeffaflık zayıf**
- **Müşteri yorumları/testimonial yok**
- **Pazarlama söylemi pasif** — "katılarak portföye sahip olabilirsiniz" — eyleme çağıran üslup zayıf
- **Aylık 318 iş** ölçeği ile AVUTAP'ın hızlı büyümesinin gerisinde
- **Konversiyon: %29 (cevap → iş)** — manuel modelin verimsizliği
- **"Hemen Kayıt Ol" CTA YOK** — büyüme tıkanıyor
- **Hukuk bürosu (multi-tenant) yönetimi yok**
- **Tek dil (Türkçe)**
- **Sosyal medya inactive**

## 14. AVUTAP karşısındaki pozisyon

| Kriter | TEVKİL | AVUTAP |
|---|---|---|
| Yaş | 16 yıl (2010) | 6 yıl (2020) |
| Üye sayısı (iddia) | 10.000+ | 55.849 |
| Adliye kapsam | Belirtilmemiş | 596 |
| Otomatik eşleştirme | ❌ | ✅ 15 dk |
| Robot arama | ❌ | ✅ |
| SMS+E-mail bildirim | Belirsiz | ✅ |
| Push notification | Belirsiz | ✅ |
| Cüzdan / ödeme | ❌ | ✅ |
| Anlaşmazlık çözümü | ❌ | ✅ |
| Canlı feed | ❌ | ✅ |
| Tanıtım videosu | ❌ | ✅ YouTube |
| Müşteri yorumları | ❌ | ✅ 6 avukat |
| Mobile app aktif | Şüpheli | ✅ Eki 2025 |
| Site içerik sayfası | 3 (Hakkımızda/İletişim/KVKK) | 7+ |
| Marka tescili | Belirtilmemiş | ✅ Türk Patent |
| Yıllık iş hacmi | ~3.800 | Belirtilmemiş ama büyük olası |
| Komisyon modeli | Belirsiz | Açık (₺20/₺30, AvutaPro premium) |
| Pazarlama söylemi | Pasif | Aktif/agresif |
| Conversion (CTA) | Zayıf | Güçlü |

> **Net:** TEVKİL **köklü ama duraklamış**. AVUTAP **yeni ama agresif büyüme** modunda. AVUTAP, TEVKİL'in pazarını teknoloji + UX yatırımıyla çalmış görünüyor.

## 15. Bizim için çıkarımlar (tevkil-app)

| Karar | Gerekçe |
|---|---|
| **TEVKİL'in "dayanışma" tonunu çal** | Duygusal bağ, avukat etiğine uyum |
| **AVUTAP'ın otomasyon altyapısını çal** | 15 dk SLA + cüzdan + dispute resolution standart |
| **TEVKİL'in zayıf "kar amacı gütmez" stratejisini düşün** | Bu strateji büyümeyi tıkıyor; net komisyon modeli daha sürdürülebilir (Av. Veli Onur'la tartışılacak) |
| **TEVKİL'in conversion zayıflığından öğren** | Day-1 "Hemen Kayıt Ol" CTA'sı çok prominent olsun |
| **TEVKİL'in eski hissi vs AVUTAP'ın modern UX'i** | Bizim diferansiyel: **en modern arayüz** + **en aktif geliştirme** |
| **Şeffaflık** | Ticari isim, vergi no, KVKK, kullanıcı sözleşmesi, gizlilik metni Day-1 (TEVKİL'in eksiği) |
| **Aktif sürüm yönetimi sinyali** | App Store + landing'de "Son güncelleme" göster (TEVKİL footer "2024" hatasından öğren) |
| **Sosyal medya canlı tut** | TEVKİL'in inactive icon'ları kötü sinyal — Day-1'den linkler işlevsel |
| **Yıllık 3.800 iş = ~318/ay** | Pazar küçük — büyütmek için pazarlama bütçesi gerekiyor; pricing.md'ye agresif satış stratejisi yansısın |
| **TEVKİL "directory" modu, AVUTAP "assignment" modu** | Hibrit yapı tercih edilebilir: kullanıcı **manuel arama** yapabilsin (TEVKİL gibi) ya da **otomatik atama** isteyebilsin (AVUTAP gibi) — RFC 0001 konusu |
| **Müvekkil portföyü oluşturma argümanı** | TEVKİL'in "yeterli müvekkil portföyü oluşana kadar ek gelir" söylemi yan iş kazancını öne çıkarıyor — bizde de işe yarayabilir |
