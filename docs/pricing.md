# Fiyat Teklifi — Avukat Tevkil Platformu

| | |
|---|---|
| **Hazırlayan** | AIFINEX |
| **Müşteri** | Av. Veli Onur Biçimli |
| **Tarih** | 2026-05-04 |
| **Geçerlilik** | 30 gün |

---

## Özet

Türkiye'deki avukatların **şehir/il dışı adliye işleri** için meslektaşlarına vekâlet (tevkil) verebileceği bir platform. Üç yüzeyle teslim edilir:

- 🌐 **Halka açık tanıtım sitesi** (landing page)
- 📱 **iOS uygulaması** (App Store)
- 🤖 **Android uygulaması** (Google Play)

Üçü ortak bir backend altyapısıyla beslenir; web tabanlı admin paneli içerir.

---

## BASE Paket — Modül Bazlı Sabit Fiyat

| # | Modül | Fiyat (TL) |
|---|---|---:|
| 0 | Discovery + UX/UI Tasarım | **15.000** |
| 1 | Kayıt & Üyelik (avukat kaydı, **e-posta magic link doğrulama**, **telefon SMS OTP doğrulama**, **NVI TC Kimlik otomatik doğrulama**, **Baro Levhası admin panel kontrolü**, profil, premium tier, Mavi Tik, Yetki Belgesi PDF) | **15.000** |
| 2 | Görev Oluşturma (form, il/adliye/tip/bütçe/tarih, hazır şablonlar, acil görev) | **12.000** |
| 3 | Görev Listeleri & İptal | **10.000** |
| 4 | **Eşleştirme + Konum + Bildirim** (15 dk akış, anonim başvuru, "Adliyedeyim" toggle, km mesafe, push/SMS/email) | **22.000** |
| 5 | Ödeme & Bakiye (cüzdan, IBAN ödeme talebi, manuel havale akışı) | **13.000** |
| 6 | İş Ortaklığı (Davet Et Kazan, Görev Ver Kazan) | **7.000** |
| 7 | Ana Sayfa & Canlı Akış (hoş geldin, duyuru bandı, anonim feed, widget'lar) | **9.000** |
| 8 | Uyuşmazlık Masası (ihtilaf bildirimi, çift taraflı thread) | **7.000** |
| 9 | Yardım & Destek (Nasıl Çalışır?, SSS, İstek/Öneri/Şikayet) | **5.000** |
| 10 | Mobil Yayın & Altyapı (iOS + Android React Native, push, GPS, App Store + Google Play yayın) | **14.000** |
| 11 | Admin Paneli (kullanıcı/ödeme/görev moderasyonu, kısıtlamalar sistemi, içerik yönetimi, raporlar) | **17.000** |
| 12 | Landing + Yasal Sayfalar (tanıtım sitesi, KVKK, Üyelik Sözleşmesi, Mesafeli Satış, Ön Bilgilendirme) | **9.000** |
| 13 | **Marka Kimliği Paketi** ✨ *(isteğe bağlı, çıkarılabilir)* — marka adı önerileri (3-5 alternatif), logo (3 taslak + 2 revizyon + 4 final versiyon: yatay/dikey/monokrom/renkli), renk paleti, typography, app icon (iOS + Android), mini brand guideline PDF (5-10 sayfa) | **15.000** |
|   | Test + UAT | **8.000** |
|   | Proje Yönetimi & Koordinasyon | **7.000** |
|   | **TOPLAM (KDV hariç)** | **₺185.000** |
|   | KDV (%20) | ₺37.000 |
|   | **GENEL TOPLAM (KDV dahil)** | **₺222.000** |

> **Müşteri kendi marka kimliğini hazır getirirse Modül 13 çıkarılır → Toplam ₺170.000 + KDV (₺204.000 dahil)**

---

## BASE Pakete Dahil

✅ Yukarıdaki kalemlerin tamamı (Modül 13 isteğe bağlı, kaldırılabilir)
✅ App Store ve Google Play'e ilk yayın (geliştirici hesap kurulum desteği)
✅ Tüm yasal sayfa şablonları (avukat tarafından hukuki onay sonrası)
✅ **8 hafta hata garantisi** (canlıda ortaya çıkan kritik hataların ücretsiz düzeltilmesi)
✅ **6 saatlik kullanım eğitimi** (admin paneli + mobile, online)
✅ Teknik dokümantasyon

> **Not:** Yukarıda listelenmemiş herhangi bir ek modül talep edilirse, ayrıca fiyatlandırılarak bu dokümana eklenir.

---

## Aylık Operasyonel Destek (Opsiyonel)

8 hafta hata garantisi sonrası:

| Paket | Aylık (TL) | Kapsam |
|---|---:|---|
| **Standart** | 2.500 | Bug fix + minor güncellemeler + admin paneli destek |
| **Plus** | 5.000 | Standart + 24/7 izleme + öncelikli işler + aylık 4 saat geliştirme |
| **Pro** | 10.000 | Plus + adanmış proje yöneticisi + aylık 10 saat geliştirme |

Hosting yönetimi her pakete dahildir.

---

## Müşteriye Ait Sürekli Maliyetler

Geliştirme ücretine **dahil değildir**. Müşteri kendi adına aşağıdaki servisleri yönetir.

### A. Sabit Aylık Altyapı Maliyeti (kullanım bağımsız)

| Kalem | Aylık (TL) | Açıklama |
|---|---:|---|
| Hosting (AWS / Hetzner / DigitalOcean) | 3.000 – 5.000 | Sunucu + veri tabanı + dosya storage |
| E-posta sağlayıcı (Postmark / Mailgun) | 500 | $15+/ay (10.000 e-posta hedefiyle) |
| Apple Developer Hesabı (yıllık → aylık çevrim) | 275 | $99/yıl ÷ 12 |
| Domain `.com.tr` (yıllık → aylık) | 10 | ~₺100/yıl ÷ 12 |
| Push notification (FCM) | 0 | Ücretsiz |
| **Toplam Sabit Aylık** | **₺3.785 – ₺5.785** | **(orta tahmin: ~₺4.800/ay)** |

> Tek seferlik: **Google Play Developer hesabı $25** (~₺850, sadece kayıt anında).

### B. Kullanım Bazlı Maliyet (kullanıcı sayısına göre değişir)

| Kalem | Birim fiyat | Örnek |
|---|---|---|
| SMS sağlayıcı (NetGSM) | ~₺0.10 / SMS | 1.000 SMS/ay → ~₺100/ay |
| iyzico / PayTR komisyonu | %1.99 + ₺0.25 / işlem | 500 ödeme × ortalama ₺100 → ~₺1.120/ay |

### C. Üç Ölçek Senaryosu — Aylık Toplam Tahmini

| Senaryo | Aktif kullanıcı | SMS / ay | Ödeme / ay | **Aylık Toplam** |
|---|---:|---:|---:|---:|
| **Başlangıç** (ilk 3 ay) | ~100 | ~100 SMS | ~10 ödeme | **~₺4.900** |
| **Büyüme** (6-12. ay) | ~1.000 | ~1.000 SMS | ~200 ödeme | **~₺5.300** |
| **Olgun** (1.+ yıl) | ~10.000 | ~10.000 SMS | ~2.000 ödeme | **~₺10.500** |

> 💡 **Aylık operasyonel destek paketi alınırsa** hosting yönetimi pakete dahildir → sabit aylık maliyetten **₺3.000-5.000 düşer**.

---

## Zaman Çizelgesi

| Faz | Süre |
|---|---|
| Discovery + Tasarım | 4 hafta |
| Geliştirme (12 modül + altyapı) | 22 hafta |
| Test + UAT | 2.5 hafta |
| App Store + Google Play yayın | 1.5 hafta |
| **Toplam** | **30 hafta (~7.5 ay)** |

Sözleşme imzası sonrası:
- T0 + 4 hafta: Discovery + tasarım onayı
- T0 + 30 hafta: BASE teslim (App Store + Google Play yayında)
- T0 + 30..38 hafta: 8 hafta hata garantisi

---

## İletişim

| | |
|---|---|
| **AIFINEX** | Salih Karademir |
| **E-posta** | salih.karademir@aifinex.com |
| **Telefon** | 0 850 302 84 32 |
