# Initial Scope — 2026-05 (BASE Package)

- **Status:** Draft (müşteri onayı bekleniyor)
- **Hedef sürüm:** v1.0 — Landing + iOS + Android (App Store & Google Play yayını)
- **Yapı:** 12 ana modül; AVUTAP feature parity + müşteri voice-note çıkarımları (konum tabanlı özellikler)

> **Pricing modeli:** BASE paket = aşağıdaki 12 modül + landing page. AI eşleştirme, e-imza, UYAP entegrasyonu, kurumsal hesap gibi gelişmiş özellikler **ek modül** olarak ayrı kalemde teklif edilir (bkz. [pricing.md](../pricing.md)).
>
> **Referans materyaller:**
> - [competitor-analysis/avutap-feature-inventory.md](../competitor-analysis/avutap-feature-inventory.md) — yazılı envanter
> - [competitor-analysis/avutap-app-ui-ux.md](../competitor-analysis/avutap-app-ui-ux.md) — 22 ekran üzerinden UI/UX analizi
> - [competitor-analysis/avutap.com.md](../competitor-analysis/avutap.com.md) — site analizi
> - [competitor-analysis/tevkil.com.md](../competitor-analysis/tevkil.com.md) — site analizi
> - [meetings/2026-05-04-customer-voice-note.md](../meetings/2026-05-04-customer-voice-note.md) — müşteri ses kaydı

## Hedefler

1. **AVUTAP feature parity** — pazarda eşit konum
2. **Konum tabanlı özelliklerle farklılaşma** — "Adliyedeyim" + km mesafesi (müşterinin AVUTAP'ı tercih sebebi)
3. Üç yüzeyle teslim: **landing**, **iOS**, **Android** (tek React Native codebase)
4. Avukat → görev oluştur → eşleş → tamamla → ödeme zincirini uçtan uca

## Hedef olmayanlar (BASE'de yok — Ek modül olarak teklif edilir)

- AI tabanlı akıllı eşleştirme algoritması
- E-imza / UYAP entegrasyonu
- Kurumsal hesap (multi-tenant hukuk bürosu)
- Çoklu dil desteği (BASE Türkçe-only)
- Web tarafından görev oluşturma (BASE: sadece mobil)
- Robot sesli arama (yüksek operasyonel maliyet)
- iyzico/PayTR escrow ödeme (BASE'de manuel IBAN havale)

---

## Modül 1 — Kayıt ve Üyelik Sistemi

### 1.1 Standart Üyelik

| # | Özellik | Detay |
|---|---|---|
| M1.1 | Kayıt | E-posta + telefon + **TC kimlik no** + **baro sicil no** + ad-soyad + doğum yılı zorunlu |
| M1.2 | 2 aşamalı doğrulama | SMS OTP + e-posta magic link |
| M1.3 | **NVI TC Kimlik doğrulama (otomatik)** | `tckimlik.nvi.gov.tr` SOAP servisiyle TC + ad + soyad + doğum yılı eşleşme kontrolü, kayıt anında otomatik. Eşleşmezse kayıt **reddedilir**. |
| M1.4 | **Baro Levhası kontrolü (admin paneli üzerinden manuel)** | Resmi public API olmadığı için, NVI'dan onay alan kullanıcı admin queue'suna düşer. Admin panelinde "Baro Levhası'nda Kontrol Et" butonu `e-baro.barobirlik.org.tr`'i yeni sekmede açar; admin gözle doğrular ve onaylar/reddeder. (TBB ile özel API anlaşması yapılırsa Ek Modül olarak otomatikleştirilebilir.) |
| M1.5 | Hesap durumu akışı | Kayıt → NVI doğrulama → onay bekliyor (admin queue) → admin onaylar → aktif hesap. Her aşamada SMS + e-mail bildirim. |
| M1.6 | Profil | Fotoğraf, baro, sicil no, çalışma şehri (il), uzmanlık alanları (multi-select), IBAN |
| M1.7 | Profil Doluluk Oranı | Yüzde göstergesi (gamification) — eksik alan kırmızı uyarı |
| M1.8 | Profil Resmi Yükleme | Crop + max 2MB |
| M1.9 | Hakkında | Serbest metin (max 500 karakter) |
| M1.10 | Şifre Değiştir | Eski şifre ile doğrulama |
| M1.11 | Şifre Kurtarma | E-posta / SMS |
| M1.12 | KVKK + Kullanıcı Sözleşmesi | Versiyonlu, kayıtta zorunlu onay |
| M1.13 | 2 kullanıcı tipi | Görev veren + görev alan (aynı kullanıcı her ikisi olabilir) |
| M1.14 | Mavi Tik (Verified Badge) | Manuel admin onaylı verification rozeti — profil + görev kartlarında görünür |
| M1.15 | Yetki Belgesi | Avukatlık Kanunu Md. 56 yetki belgesi PDF üretici (template + dinamik doldurma) |

### 1.2 Premium Üyelik (`tevkil-app Pro` — adı netleşecek)

| # | Özellik | Detay |
|---|---|---|
| M1.16 | Yıllık abonelik | Önerilen ₺2.000–₺2.500/yıl (müşteri ile netleşecek) |
| M1.17 | Sınırsız görev kabul | Free tier'da limitli, premium'da sınırsız |
| M1.18 | SMS bildirimi | Premium-only (free'de e-mail) |
| M1.19 | Acil görev oluşturma | Premium-only |
| M1.20 | Yıl sonu uzatma garantisi | 1 yıl içinde **<3 görev** alındıysa abonelik 1 yıl ücretsiz uzatılır (AVUTAP modeli — müşteri teyitli) |
| M1.21 | Eski üye indirimi | Promo kuponları, sadakat indirimi |
| M1.22 | Mesafeli Satış + Ön Bilgilendirme | Onay checkbox + arşivlenir |

> Robot sesli arama → BASE'de yok, **Ek Modül**

---

## Modül 2 — Görev Oluşturma (Görev Veren)

| # | Alan | Detay |
|---|---|---|
| M2.1 | İl (Görev Yeri) | 81 il dropdown — referans veri DB'de |
| M2.2 | Adliye (Görev Adliyesi) | Seçili ile bağlı, ~596 adliye dropdown |
| M2.3 | **Adliye Dışı toggle** | Aktifse harita üzerinden konum + adres girişi |
| M2.4 | Görev Tipi (Yapılacak Görev) | Ceza Duruşması Katılımı, Hukuk Duruşması Katılımı, İcra Dairesi İşlemleri, Savcılık İşlemleri, Dosya İnceleme, Kalem İşleri, Tebligat, Diğer |
| M2.5 | Bütçe (Görev Bütçeniz) | Kademeli sabit tutar (örn. 600₺ / 700₺ / 1100₺ / 1250₺ / 1500₺) — admin'den yönetilir |
| M2.6 | Tarih + saat | Date+time picker; saat opsiyonel |
| M2.7 | Açıklama | Serbest metin, max 1000 karakter |
| M2.8 | **Hazır Açıklama Şablonları** | Görev tipi başına önceden tanımlı şablonlar (admin'den yönetilir) |
| M2.9 | İletişim bilgisi guard'ı | Açıklama içinde telefon/e-posta tespit edildiğinde uyarı |
| M2.10 | Dosya eki | Maks. 3 PDF (eşleşene kadar gizli; eşleşince paylaşılır) |
| M2.11 | Acil Görev seçeneği | Premium-only checkbox; 15 dk dolmadan başvuru kapanabilir |

---

## Modül 3 — Görev Listeleri ve Yönetim

### 3.1 Görev Veren Tarafı (3 sekme)
- Oluşturduğum Görevler (aktif)
- Seçildiğim Görevler (atama yapılanlar)
- Tamamlanan Görevler

### 3.2 Görev Alan Tarafı (4 sekme)
- Bekleyen Görevlerim (başvurulabilir, filtre: il/adliye/tip/bütçe/**km mesafe**)
- Başvurduğum Görevler (durum: bekliyor/red/kabul)
- Başvurmadığım Görevler (gözardı edilen)
- Tamamladığım Görevler

### 3.3 Görev İptal Bildirimi
| # | Özellik | Detay |
|---|---|---|
| M3.1 | İptal sebebi | Dropdown (önceden tanımlı: müvekkil iptali, sağlık, planlama hatası, mücbir sebep, diğer) |
| M3.2 | Yıllık iptal hakkı | 5 hak/yıl (admin parametre) |
| M3.3 | Geçmiş iptal listesi | Kullanıcı + admin görür |
| M3.4 | Hak aşımı yaptırımı | Kısıtlamalar sistemine yansır (Modül 11'de detay) |

---

## Modül 4 — Eşleştirme, Konum ve Bildirim Sistemi

### 4.1 Eşleştirme (BASE — manuel başvuru tabanlı)
| # | Özellik | Detay |
|---|---|---|
| M4.1 | Adliye/il bazlı bildirim | Görev oluşunca o adliyedeki "görev alma açık" üyelere bildirim |
| M4.2 | 15 dk başvuru penceresi | Tüm avukatlar 15 dk içinde başvurur |
| M4.3 | Manuel atama | 15 dk dolunca görev veren listeden seçer |
| M4.4 | Sürenin uzatılması | Görev veren manuel olarak 15 dk daha açabilir |
| M4.5 | Anonim başvuru görüntüleme | Görev veren, başvuranın **sadece adının baş harfi + uzmanlık + Hakkında**'sını görür; profil resmi + tam isim **atanana kadar gizli** |

> AI/algoritmik otomatik eşleştirme = **Ek Modül**.
> "Adil dağılım" puanlama (kullanıcı performansına göre) BASE'de basit, gelişmiş algoritma Ek Modül.

### 4.2 Konum Tabanlı Özellikler ⭐ (müşterinin AVUTAP'ı seçme sebebi)

| # | Özellik | Detay |
|---|---|---|
| M4.6 | **"Adliyedeyim" toggle** | Avukat fiziksel olarak adliyede ise GPS doğrulamalı toggle açar; o anda gelen acil görevlere **öncelik atanır** |
| M4.7 | Mesafe gösterimi | Görev kartında "X km uzaklıkta" bilgisi (görev konumu vs avukatın kayıtlı konumu) |
| M4.8 | Konum tabanlı sıralama | Bekleyen görevler listesi mesafeye göre sıralanabilir |
| M4.9 | GPS izinleri yönetimi | Kayıtta açıklayıcı izin akışı (iOS + Android) |
| M4.10 | Fake-location önleme | Mock location detection (Android) + jailbreak/root tespiti |

### 4.3 Bildirim Kanalları
| Kanal | Tier | Sağlayıcı |
|---|---|---|
| Push (iOS/Android) | Tüm | FCM + APNs |
| E-mail | Tüm | Postmark / SMTP |
| SMS | Premium | NetGSM / iletimerkezi |
| Robot arama | — | **Ek Modül** |

### 4.4 Bildirim Tetikleyicileri
- Yeni görev (alıcı), başvuru (veren), atama (alıcı), red (alıcı), tamamlama, ödeme onayı, hatırlatma, "Adliyedeyim" eşleşmesi

### 4.5 Bildirim Ayarları
- Kullanıcı kanal bazında aç/kapa
- Görev tipi bazında opt-out ("**Görev Almak İstemediğiniz Kategoriler**")
- Adliye bazında opt-in (sadece seçili adliyelerden bildirim)
- "Görev Alma" durumu: Açık / Kapalı toggle (varsayılan açık)

---

## Modül 5 — Ödeme ve Bakiye Sistemi

### 5.1 Bakiye Görüntüleme
| # | Özellik | Detay |
|---|---|---|
| M5.1 | Mevcut bakiye | Kazanılmış − çekilmiş |
| M5.2 | Bekleyen bakiye | Henüz tamamlanmayan görevlerden |
| M5.3 | Geçmiş işlem listesi | Görev ID, tarih, tutar, durum |

### 5.2 Ödeme Talebi (Çekim)
| # | Özellik | Detay |
|---|---|---|
| M5.4 | Alıcı ad-soyad | Default profilden |
| M5.5 | Banka adı | Dropdown (referans listesi, admin'den yönetilir) |
| M5.6 | IBAN | TR + 24 hane validation |
| M5.7 | Tutar | Min ₺100, max bakiye |
| M5.8 | Talep statüsü | Bekliyor / onaylandı / red |
| M5.9 | Son ödemelerim listesi | Tüm geçmiş havale kayıtları |

### 5.3 Ödeme Akışı
- **BASE: Manuel IBAN havale**, admin onaylı (T+1 mesai içi gönderim)
- Otomatik EFT/havale entegrasyonu = **Ek Modül**
- Görev başı kazanç modeli: müşteri ile netleşecek (sabit ücret / yüzde komisyon / abonelik)

### 5.4 Görev Veren Ödeme Akışı (BASE: dışarıda)
- Görev verenden alınan ücret platforma değil, doğrudan tevkil edilen avukata gider (TEVKİL modeli)
- Veya: platform escrow (iyzico/PayTR) = **Ek Modül**
- Karar: RFC 0001'de finansal akış netleşir

---

## Modül 6 — İş Ortaklığı Programı

| # | Özellik | Detay |
|---|---|---|
| M6.1 | Davet Et Kazan | Referral linki + paylaş + kopyala butonları; doğrulanmış üye başına bonus (örn. ₺10-₺50) |
| M6.2 | Görev Ver Kazan | Görev oluşturma teşviki (örn. yeni AvutaPro üye bağlandığında ₺20) |
| M6.3 | Ortaklık bakiyesi | Drawer'da prominent gösterilir (`İş Ortaklığı: 0 ₺`) |
| M6.4 | Davet edilen tracking | Kim kimi getirdi (admin görür) |
| M6.5 | Ödeme talebi | Modül 5 ile aynı akış |

---

## Modül 7 — Ana Sayfa ve Canlı Akış

| # | Bileşen | Detay |
|---|---|---|
| M7.1 | Hoş geldin başlığı | "{Ad}, hoş geldin!" + günsel selam ("İyi Sabahlar / Akşamlar / Haftalar") |
| M7.2 | Duyuru bandı | Admin'den yayınlanan banner (örn. "E-Barobirlik uyarısı"); kapatılabilir |
| M7.3 | Premium upsell card | Eski üyelere kişiselleştirilmiş indirim |
| M7.4 | + Yeni Görev Ver CTA | Yeşil prominent buton (FAB ayrıca bottom nav'da) |
| M7.5 | Görevlendirme Geçmişim | Mini chart/widget (haftalık/aylık görev sayısı) |
| M7.6 | Bekleyen / Başvurduğum özet kutusu | Expandable card |
| M7.7 | Oluşturduğum görev özeti | Expandable card |
| M7.8 | **Canlı feed** ("Şu an neler oluyor?") | Anonimleştirilmiş aksiyon listesi (Av. **** Görev Oluşturdu / Atama / Seçildi / Tamamladı), 30sn refresh |
| M7.9 | Arşiv widget | Son 10 atama + tamamlanan görev (bottom nav'da Arşiv sekmesi de var) |

---

## Modül 8 — Uyuşmazlık Masası

| # | Özellik | Detay |
|---|---|---|
| M8.1 | Yeni uyuşmazlık formu | Kategori (gecikme, yanlış sonuç, ödeme, davranış), açıklama, dosya |
| M8.2 | Üst uyarı | "Bilgi almadan kullanmayınız" |
| M8.3 | Açıklama modal | Eylem öncesi onboarding |
| M8.4 | Uyuşmazlık listesi | Durum (yeni / inceleniyor / çözüldü / reddedildi) |
| M8.5 | Karşılıklı ifadeler | Görev veren + alan görür ve cevap atar |
| M8.6 | Admin moderation | Çözüm sonucu: bakiye iadesi / kullanıcı uyarısı / ban |

---

## Modül 9 — Yardım ve Destek

| # | Özellik | Detay |
|---|---|---|
| M9.1 | Nasıl Çalışır? | Kullanım kılavuzu (akordeon FAQ — adliye atama, başvuru, eşleşme, bildirim ayarları, vb.) |
| M9.2 | İstek/Öneri/Şikayet formu | Kategori, başlık, açıklama, ekran görüntüsü eki |
| M9.3 | SSS | Admin'den eklenebilir Q&A |
| M9.4 | İletişim | E-posta + form |

> Live chat = **Ek Modül**

---

## Modül 10 — Mobil Uygulama (iOS + Android)

### 10.1 Genel
- **iOS native** App Store yayını (min iOS 13.0)
- **Android native** Google Play yayını (min API 24 / Android 7.0)
- **Tek codebase: React Native** (alternatif Flutter — RFC 0001'de netleşir)

### 10.2 Tasarım
- 5 sekmeli bottom nav: Bekleyen | Arşiv | **+ Görev Ver (FAB)** | Davet Et | Ayarlar
- Drawer menu: 9 madde (Ana Sayfa, Görev İşlemleri, İş Ortaklığı, Görev İptal, Uyuşmazlık, Duyurular, Ayarlar, Nasıl Çalışır?, İstek/Öneri/Şikayet)
- **Drawer rotating hero** — günsel/sezonsal Türkiye görselleri (kullanıcının iline öncelik)
- Top bar: hamburger + home + premium upsell pill + bildirim zili + profil avatarı
- Card-based UI, rounded corners, 12pt grid
- Renk sistemi: Mavi (primary), Mor (premium), Yeşil (CTA), Sarı (ikincil), Kırmızı (uyarı)
- Empty state'lerde illüstrasyon + bilgi notu

### 10.3 Teknik
- Push notification: FCM (Android) + APNs (iOS)
- Crash reporting: Sentry / Crashlytics
- Analytics: kayıt, görev oluşturma, kabul, tamamlama
- Çevrimdışı temel destek (liste cache)
- GPS izinleri + konum doğruluğu

---

## Modül 11 — Admin Paneli

| # | Özellik | Detay |
|---|---|---|
| M11.1 | Web tabanlı | Admin/support rollerine açık |
| M11.2 | Kullanıcı yönetimi | Liste, filtre, profil görüntüle, sicil onayla, ban, premium tier ata, kullanıcı adına işlem |
| M11.3 | Mavi Tik onayları | Verification badge başvuru queue + onay/red |
| M11.4 | **Kısıtlamalar / Yaptırım Sistemi** | Skor: iptal limiti aşımı, geç yanıt, anlaşmazlık → otomatik kısıtlama (görev alma kapatma) + admin manuel ekleyebilir/kaldırabilir |
| M11.5 | Görev moderasyonu | Tüm görevler, manuel müdahale (iptal, atama değişikliği) |
| M11.6 | Ödeme talepleri | Bekleyenler listesi, onayla/red, manuel havale işareti, ödeme makbuzu yükleme |
| M11.7 | İhtilaf yönetimi | Liste, detay, çözüm |
| M11.8 | İçerik yönetimi | Duyuru banner (yayın + son tarih), Hazır şablonlar, SSS, Drawer hero görselleri |
| M11.9 | Referans veri yönetimi | İl, adliye, görev tipi, bütçe kademesi, banka listesi |
| M11.10 | Raporlar | Kullanıcı (kayıt/aktif), görev (oluşturulan/tamamlanan/iptal), gelir (komisyon + abonelik), top performers |
| M11.11 | Audit log | Hassas işlem logları |

---

## Modül 12 — Halka Açık Sayfalar (Landing + Legal)

### 12.1 Landing
| # | Bölüm | Detay |
|---|---|---|
| M12.1 | Hero | USP + App Store / Google Play butonları |
| M12.2 | Nasıl çalışır | 3-4 adımlı görsel akış |
| M12.3 | Özellikler | Anahtar özellikler kart |
| M12.4 | İstatistikler | Üye, görev, adliye sayıları (canlı API'den) |
| M12.5 | Müşteri yorumları | Testimonial (Day-1'den 4-6 erken kullanıcı) |
| M12.6 | SSS | 8-10 soru |
| M12.7 | İletişim | Form + bilgiler |
| M12.8 | SEO | Meta, OG image, sitemap, robots.txt |
| M12.9 | Analytics | Google Analytics / Plausible |

### 12.2 Yasal Sayfalar (zorunlu — premium tier sattığımız için)
- KVKK Aydınlatma Metni
- Üyelik Sözleşmesi
- Gizlilik Politikası / Çerez Politikası
- **Mesafeli Satış Sözleşmesi**
- **Ön Bilgilendirme Formu**

---

## Yorumlar ve Puanlama (Modül 1 ile entegre, ayrı modül değil)

| # | Özellik | Detay |
|---|---|---|
| MR.1 | Görev sonrası 5 yıldız puan | İki taraflı, görev tamamlanınca |
| MR.2 | Yorum (max 300 karakter) | Yıldıza ek olarak yazılı geri bildirim |
| MR.3 | Profil sayfasında ortalama puan | Yıldız + yorum sayısı |
| MR.4 | Yorum listesi | Profil sekmesi (Hakkında / Yorumlar) |
| MR.5 | Sahte yorum tespiti | Aynı IP/cihazdan tekrar engellenir |

---

## Geliştirme aşamaları

| Faz | Süre (hafta) | Çıktı |
|---|---|---|
| 0. Discovery + tasarım | 4 | Wireframe, UI kit, ~50 ekranın tasarımı |
| 1. Backend iskelet + admin core | 4 | Auth, RBAC, sicil onayı, kullanıcı yönetimi, referans veri |
| 2. Mobile auth + profil + Mavi Tik + premium tier | 3 | Modül 1 |
| 3. Görev oluşturma + listeler + iptal | 3 | Modül 2 + 3 |
| 4. Eşleştirme + konum + bildirimler | 3 | Modül 4 (özellikle "Adliyedeyim" + km) |
| 5. Ödeme + bakiye + ortaklık | 3 | Modül 5 + 6 |
| 6. Dashboard + canlı feed + uyuşmazlık | 2.5 | Modül 7 + 8 |
| 7. Yardım/destek + yorumlar/puanlama | 2 | Modül 9 + Yorumlar |
| 8. Admin tam set + kısıtlamalar sistemi | 3 | Modül 11 |
| 9. Landing + legal sayfalar | 2 | Modül 12 |
| 10. Test + UAT | 2.5 | QA + müşteri kabul |
| 11. App store yayın | 1.5 | Apple + Google review |
| **Toplam** | **~30 hafta (≈7.5 ay)** | BASE canlıda |

5 kişilik ekip varsayımıyla; pricing.md'de detaylı.

---

## Açık sorular (müşteri ile netleşecek)

- [ ] **Görev başına kazanç modeli:** sabit / yüzde / abonelik tabanlı mı?
- [ ] **Premium tier yıllık fiyatı:** önerilen ₺2.000-₺2.500
- [ ] **Premium uzatma garantisi koşulu:** 1 yıl <3 görev → 1 yıl uzatma (AVUTAP modeli teyit?)
- [ ] **Logo + marka kimliği:** müşteride hazır mı, biz mi yapacağız?
- [ ] **Marka adı ve domain:** tevkil-app placeholder, gerçek isim?
- [ ] **App Store / Google Play hesapları:** kimde açılacak?
- [ ] **Komisyon modeli:**
  - Görev başına sabit (₺30 gibi) mı?
  - Yüzde komisyon (%5-10) mu?
  - Tamamen ücretsiz, sadece premium gelirden mi?
- [ ] **KVKK + sözleşmeler:** avukat olarak müşteri kendi yazacak mı?
- [ ] **Ödeme sağlayıcı:** iyzico / PayTR / Stripe?
- [ ] **Görev verenden ücret tahsilatı:** BASE'de var mı? (escrow vs. doğrudan avukatlar arası)
- [ ] **Robot arama:** Day-1'de yok, ileride istenecek mi?
- [ ] **Bütçe kademeleri:** AVUTAP'taki gibi (600/700/1100/1250/1500) mi yoksa serbest girdi mi?
- [ ] **Görev tipi listesi:** Modül 2'de 8 tip — eklenecek/çıkarılacak var mı?
