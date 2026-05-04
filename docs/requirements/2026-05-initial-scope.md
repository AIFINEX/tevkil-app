# Initial Scope — 2026-05

- **Status:** Draft (müşteri onayı bekleniyor)
- **Hedef sürüm:** v1.0 (MVP — App Store & Google Play yayını)

## Hedefler

1. Türkiye'deki avukatlar arası **tevkil ağı**nı dijitalleştir.
2. Üç yüzeyle teslim et: **web landing**, **iOS uygulaması**, **Android uygulaması**.
3. Kayıt → görevlendirme oluştur → kabul et → tamamla → ödeme zincirini uçtan uca çalıştır.

## Hedef olmayanlar (MVP'de yok)

- AI tabanlı eşleştirme algoritması (faz 2)
- Sesli arama / video görüşme entegrasyonu
- E-imza entegrasyonu (UYAP, e-Devlet)
- Hukuk bürosu (çoklu hesap) yönetimi
- Çok dilli destek (sadece Türkçe başlıyor)
- Web tarafından görevlendirme oluşturma (sadece mobile MVP'de)

## 1. Landing Page (web)

| # | Özellik | Açıklama |
|---|---|---|
| L1 | Hero | Ürün vaadi, App Store/Google Play butonları |
| L2 | Nasıl çalışır | 3-4 adımlı görsel akış (kayıt ol → talep oluştur → eşleş → tamamla) |
| L3 | Özellikler bölümü | Anahtar özelliklerin kart şeklinde listesi |
| L4 | İstatistik bandı | Üye sayısı, görevlendirme sayısı, kapsanan adliye sayısı (canlı API'den) |
| L5 | SSS | En sık 8-10 soru |
| L6 | İletişim | Form + direkt iletişim bilgileri |
| L7 | Yasal sayfalar | KVKK, Kullanıcı Sözleşmesi, Çerez Politikası |
| L8 | SEO | Meta tag, OG image, sitemap, robots.txt |
| L9 | Analytics | Google Analytics / Plausible kurulumu |

## 2. Mobile App — iOS + Android

### 2.1 Kayıt & Hesap

| # | Özellik | Açıklama |
|---|---|---|
| M1 | Kayıt | E-posta + telefon + **baro sicil no** zorunlu |
| M2 | Sicil doğrulama | İlk sürümde **manuel admin onayı**; faz 2'de Baro API entegrasyonu |
| M3 | Telefon doğrulama | SMS OTP |
| M4 | E-posta doğrulama | Magic link |
| M5 | Şifre kurtarma | E-posta / SMS akışı |
| M6 | Profil | Ad, soyad, fotoğraf, baro, sicil no, çalışma şehri, uzmanlık alanları, IBAN (ödeme için) |
| M7 | KVKK / Sözleşme onayı | Kayıtta zorunlu, versiyonlu |

### 2.2 Görevlendirme (Tevkil) Akışı

| # | Özellik | Açıklama |
|---|---|---|
| M8 | Görev oluştur | İl, adliye, iş tipi (duruşma / haciz / dosya inceleme / tebligat), tarih-saat, ücret teklifi, notlar, dosya ek (max 3 PDF) |
| M9 | Görev listesi (feed) | Bulunduğu ilde / favori illerinde açık görevler — filtreleme: il, iş tipi, ücret aralığı, tarih |
| M10 | Görev detay | Tüm bilgi + "Kabul Et" / "Geç" |
| M11 | Görev kabul | Tek tıkla kabul; oluşturana bildirim |
| M12 | Görev iptal | Sınırlı koşullarla (kabul öncesi serbest, sonrası onaya tabi) |
| M13 | Görevlerim | Sekmeler: Aktif / Tamamlanan / İptal |
| M14 | Tamamla | Görev sahibi onaylar, sistem ödemeyi serbest bırakır |
| M15 | Sorun bildir | Görevle ilgili anlaşmazlık → admin'e açılır |

### 2.3 İletişim

| # | Özellik | Açıklama |
|---|---|---|
| M16 | In-app mesajlaşma | Görev başına thread; metin + dosya |
| M17 | Push notification | Yeni görev, kabul, mesaj, ödeme onayı |
| M18 | E-posta bildirimi | Kullanıcı tercihiyle açılır/kapanır |

### 2.4 Ödeme

| # | Özellik | Açıklama |
|---|---|---|
| M19 | Ücret modeli | Görev başı sabit ücret + platform komisyonu (örn. ₺30 — pricing'de netleşir) |
| M20 | Ödeme sağlayıcı | iyzico / PayTR (kredi kartı + banka transferi) |
| M21 | Cüzdan / bakiye | Kabul eden avukatın kazanımları biriken cüzdan, çekim talebi → IBAN'a havale |
| M22 | Fatura | Yarı-otomatik (e-arşiv entegrasyonu opsiyonel — gerekirse faz 2) |

### 2.5 Değerlendirme & Güven

| # | Özellik | Açıklama |
|---|---|---|
| M23 | Yıldız puanı | İki taraf birbirini puanlar (1-5) |
| M24 | Yorum | Görev sonrası kısa yorum |
| M25 | Profil rozetleri | "Hızlı yanıt", "tamamlama oranı" gibi hesaplanmış göstergeler |

### 2.6 Genel

| # | Özellik | Açıklama |
|---|---|---|
| M26 | Çevrimdışı temel destek | Liste cache'i; mesaj gönderme online gerekli |
| M27 | Push token yönetimi | FCM (Android) + APNs (iOS) |
| M28 | Crash reporting | Sentry / Firebase Crashlytics |
| M29 | Analytics | Etkinlik takibi (kayıt, görev oluşturma, kabul, tamamlama) |

## 3. Backend & Admin Panel

| # | Özellik | Açıklama |
|---|---|---|
| B1 | REST API | Mobile + web frontends'i besler; OpenAPI dokümanlı |
| B2 | Auth | JWT; refresh token; 2FA opsiyonel |
| B3 | RBAC | Roles: avukat, admin, support |
| B4 | Admin panel | Kullanıcılar, görevler, ödemeler, raporlar, sicil onayı |
| B5 | İstatistik dashboard | Aktif kullanıcı, açık görev, tamamlanan görev, gelir |
| B6 | Loglama / audit | Hassas işlem logları (ödeme, profil değişikliği) |
| B7 | Backup | Günlük DB snapshot |
| B8 | Bildirim altyapısı | Push, email (SMTP / Postmark), SMS (NetGSM / vb.) |

## 4. Teknoloji önerileri (RFC 0001'de detaylanacak)

| Katman | Öneri | Alternatif |
|---|---|---|
| Mobile | **React Native** (tek codebase, iOS+Android paralel teslim) | Native (Swift + Kotlin) — daha yüksek maliyet |
| Backend | Node.js (NestJS) **ya da** Python (FastAPI) | — |
| DB | PostgreSQL | — |
| Push | Firebase Cloud Messaging | — |
| Hosting | AWS / Hetzner | — |
| Web landing | Next.js (statik export) | — |

## 5. Geliştirme aşamaları

| Faz | Süre (hafta) | Çıktı |
|---|---|---|
| 0. Discovery + tasarım | 2 | Wireframe, UI kit, akış onayı |
| 1. Backend iskelet + admin | 3 | Auth, kullanıcı, sicil onayı, admin panel |
| 2. Mobile auth + profil | 2 | Kayıt, login, profil ekranları |
| 3. Görevlendirme akışı | 3 | Oluştur, listele, kabul, tamamla |
| 4. Mesajlaşma + bildirim | 2 | In-app mesaj, push, email |
| 5. Ödeme entegrasyonu | 2 | iyzico, cüzdan, çekim |
| 6. Landing page | 1 | Tanıtım sitesi |
| 7. Test + UAT | 2 | QA, müşteri kabul testi |
| 8. App store yayını | 1 | Apple + Google review süreci |
| **Toplam** | **~16 hafta** | MVP canlıda |

(Süreler 4 kişilik ekip varsayımıyla; pricing.md'de detaylı.)

## Açık sorular

- [ ] Komisyon modeli? (sabit ücret / yüzde / abonelik)
- [ ] Logo + marka kimliği bizden mi gelecek, müşteride mevcut mu?
- [ ] Domain + hosting müşteri mi alacak, biz mi yöneticeğiz?
- [ ] App Store / Google Play hesapları kimde açılacak (geliştirici hesabı maliyeti)?
- [ ] Sicil doğrulama Baro API'siyle mi (varsa) yoksa manuel mi başlıyor?
- [ ] KVKK metinleri / Kullanıcı Sözleşmesi avukat tarafından mı sağlanacak?
- [ ] Ödeme sağlayıcı tercihi (iyzico / PayTR / Stripe)?
