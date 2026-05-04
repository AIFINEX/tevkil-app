# Pricing Proposal — tevkil-app

- **Hazırlayan:** AIFINEX
- **Müşteri:** Av. Veli Onur Biçimli
- **Tarih:** 2026-05-04
- **Geçerlilik:** 30 gün
- **Status:** Draft (iç review bekleniyor)

> Adam-gün tahminleri `requirements/2026-05-initial-scope.md` ile birebir uyumludur. Günlük ücret oranı (`<RATE>`) iç onayla doldurulacaktır.

## Effort breakdown

| # | Modül | Adam-gün | Açıklama |
|---|---|---:|---|
| 1 | Discovery + UX/UI tasarım | **18** | Wireframe, UI kit, prototip, müşteri onay revizyonları |
| 2 | Backend (API + auth + RBAC + admin panel) | **40** | NestJS / FastAPI, PostgreSQL, sicil onay akışı, dashboard |
| 3 | Mobile (iOS + Android, React Native) | **50** | Kayıt, profil, görevlendirme akışı, mesaj, bildirim, cüzdan |
| 4 | Landing page (Next.js) | **10** | Tanıtım sitesi, SEO, KVKK sayfaları, App Store linkleri |
| 5 | Ödeme entegrasyonu (iyzico/PayTR + cüzdan) | **12** | Çekim, fatura altyapısı, test ortamı |
| 6 | Push notification + email + SMS | **8** | FCM/APNs, SMTP, NetGSM/vb. |
| 7 | Test + QA + UAT | **15** | Otomatik testler + manuel QA + müşteri kabul testi |
| 8 | DevOps (hosting, CI/CD, backup) | **8** | Sunucu kurulumu, deployment pipeline, izleme |
| 9 | App Store + Google Play yayın süreci | **5** | İçerik hazırlığı, review iterations |
| 10 | Proje yönetimi + müşteri toplantıları | **14** | Haftalık demo, scope yönetimi, dökümantasyon |
|   | **Toplam** | **180** | |

> Tahminler ±%15 toleransla verilmiştir. Discovery sonunda (Faz 0) sabit fiyat olarak güncellenecektir.

## Fiyat tablosu

| | TL | USD ek. |
|---|---:|---:|
| Toplam adam-gün | 180 | |
| Günlük ücret | `<RATE> TL` | |
| **Geliştirme ücreti** | **`<TOPLAM> TL`** | `<USD>` |
| KDV (%20) | `<KDV> TL` | |
| **Genel toplam** | **`<NET> TL`** | |

## Kapsama dahil

- requirements/2026-05-initial-scope.md'deki **MVP** fonksiyonları
- 1 (bir) Apple Developer hesabı + 1 (bir) Google Play Developer hesabı **kurulum desteği** (lisans ücretleri müşteriye aittir)
- App Store ve Google Play'e ilk yayın
- Logo ve temel marka kimliği (müşteri tarafından sağlanmazsa, bizim tarafımızdan tek revizyon hakkıyla)
- 6 hafta **post-launch hata garantisi** (canlıda ortaya çıkan kritik hataların ücretsiz düzeltilmesi)
- 4 saatlik **kullanım eğitimi** (admin paneli + mobile app, online)

## Kapsam dışı (talep halinde ek teklif)

- AI tabanlı eşleştirme algoritması
- Sesli arama / video görüşme entegrasyonu
- E-imza, UYAP entegrasyonu
- Hukuk bürosu (multi-tenant) yönetimi
- 2'den fazla dil desteği
- Robot SMS arama (avutap'taki gibi)
- 6 haftalık garantiyi aşan SLA / bakım anlaşması (ayrı sözleşme)

## Müşteriye düşen maliyetler (geliştirme ücretine dahil değil)

| Kalem | Tahmini bedel | Periyot |
|---|---|---|
| Apple Developer Hesabı | $99 | yıllık |
| Google Play Developer Hesabı | $25 | tek seferlik |
| Domain (.com.tr) | ~₺100 | yıllık |
| Hosting (AWS / Hetzner) | ₺2.000–4.000 | aylık |
| iyzico / PayTR komisyon | %1.99 + ₺0.25 | işlem başı |
| SMS (NetGSM) | ~₺0.10 | mesaj başı |
| E-posta (Postmark) | $15+ | aylık |

## Varsayımlar

1. Müşteri tarafı **karar verici tek kişidir** (Av. Veli Onur Biçimli) — her faz sonu onay 5 iş günü içinde verilir.
2. **Sicil doğrulama** ilk sürümde **manueldir**. Baro API entegrasyonu kapsam dışıdır.
3. Mobile app **React Native** ile tek codebase olarak yazılır; iOS ve Android arasında platforma özgü minimal fark olur.
4. **Türkçe tek dil**.
5. **KVKK metinleri ve Kullanıcı Sözleşmesi** müşteri (avukat olduğu için) tarafından sağlanır.
6. **Ödeme sağlayıcı**: iyzico (varsayılan); PayTR / Stripe seçilirse efor değişebilir.
7. Geliştirme ortamı için **gerçek zamanlı erişim** (test SMS, test ödeme) müşteri tarafından gerekli sağlayıcılar ile açtırılır.

## Ödeme planı

| Aşama | Yüzde | Tutar | Tetikleyici |
|---|---:|---:|---|
| 1. Sözleşme + kickoff | 30% | `<TUTAR>` | Sözleşme imzası |
| 2. Discovery + tasarım onayı (Faz 0 sonu) | 20% | `<TUTAR>` | Müşteri tasarımı onaylar |
| 3. Backend + mobile çekirdek (Faz 1-3 sonu) | 25% | `<TUTAR>` | İç demo + müşteri demo |
| 4. UAT geçişi (Faz 7 sonu) | 15% | `<TUTAR>` | Müşteri UAT'ı geçer |
| 5. App store yayın | 10% | `<TUTAR>` | İki app yayında |

## Zaman çizelgesi (öneri)

- Sözleşme imzası: T0
- Faz 0 (Discovery): T0 → T+2 hafta
- MVP teslim (App Store + Google Play): T+16 hafta
- Yayın sonrası 6 hafta hata garantisi: T+16 → T+22 hafta

## Kabul / red

Bu teklif `Status: Approved` olarak güncellendikten ve sözleşme imzalandıktan sonra çalışmaya başlanır. Teklifte yapılacak değişiklikler `git commit` üzerinden takip edilir; her revizyon yeni bir sürüm oluşturur.
