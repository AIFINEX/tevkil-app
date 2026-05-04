# AVUTAP Mevcut Özellikler Listesi

> **Kaynak:** İç envanter dökümanı (müşteri/iç ekip kaynaklı, web crawl'a ek)
> **Amaç:** AVUTAP platformunun kullanıcılara sunduğu **tüm gözlemlenebilir özelliklerin** kategorize halini tutar. Hazırlayacağımız tevkil platformunun **BASE paketi** için referans listesidir.

## 1. Kayıt ve Üyelik Sistemi

- Avukat üyeliği (baro doğrulaması ile)
- Profil yönetimi (ad-soyad, fotoğraf, iletişim)
- İki tip kullanıcı: görev veren / görev alan (aynı kullanıcı her ikisi olabilir)

### 1.1. Premium Üyelik (AvutoPro)

- Yıllık abonelik modeli (örn. **2099₺/yıl**)
- Sınırsız görev kabul başvurusu
- Robot arama (otomatik sesli arama) ile bildirim
- SMS bildirimleri
- Acil görevlendirme oluşturma yetkisi
- 1 yıl sonunda alınan görev sayısı **3'ün altındaysa abonelik 1 yıl ücretsiz uzatılır** (müşteri teyitli)
- Eski üyelere indirim/iade promosyonu

## 2. Görev Oluşturma (Görev Veren)

- Görev ili seçimi (81 il)
- Görev adliyesi seçimi (~596 adliye)
- Adliye dışı görev toggle (lokasyon araması ile)
- Görev tipi seçimi: **Ceza Duruşması Katılımı**, **İcra Dairesi İşlemleri**, **Savcılık İşlemleri** vb.
- Görev bütçesi seçimi (kademeli sabit tutarlar — örn. **600₺ / 700₺ / 1100₺**)
- Görev tarihi ve saati
- Görev açıklaması (serbest metin + hazır şablonlar)
- Acil görev seçeneği (premium kullanıcılar için)

## 3. Görev Listeleri ve Yönetim

### 3.1. Görev Veren Tarafı

- Oluşturduğum Görevler
- Seçildiğim Görevler (atama yapılanlar)
- Tamamlanan Görevler

### 3.2. Görev Alan Tarafı

- Bekleyen Görevlerim (başvurulabilir)
- Başvurduğum Görevler
- Başvurmadığım Görevler
- Tamamladığım Görevler

### 3.3. Görev İptal Bildirimi

- Görev seçimi + iptal nedeni (görevlendirme sorunu) seçimi
- **Yıllık iptal hakkı sınırı** (örn. yıllık 5 hak)
- Geçmiş iptal talepleri listesi

## 4. Eşleştirme ve Bildirim Sistemi

- İl ve adliye bazlı otomatik eşleştirme
- Algoritma tabanlı uygun avukat tespiti
- E-mail bildirim (yeni görev, kabul, red, hatırlatma)
- SMS bildirim (premium)
- Robot arama / otomatik sesli arama (premium)
- Mobil push notification (iOS/Android app üzerinden)

### 4.1. Konum Tabanlı Özellikler (müşteri voice-note'undan)
- **"Adliyedeyim" butonu** — Avukat adliyede iken aktifleşir; acil görev geldiğinde adliyede bulunan avukatlara **öncelik** verilir
- **Görev mesafe gösterimi** (km) — Görev konumu kullanıcıya kaç km uzakta
- GPS doğrulama (fake-location önleme)
- Konum tabanlı sıralama / filtreleme

## 5. Ödeme ve Bakiye Sistemi

- İş Ortaklığı bakiyesi gösterimi (kullanıcı kazançları)
- **Ödeme Talebi Oluştur** formu:
  - Alıcı ad-soyad
  - Banka adı
  - IBAN bilgisi
  - Tutar (minimum eşik — örn. **100₺**)
- Son Ödemelerim listesi (geçmiş havale kayıtları)
- Görev başına sabit kazanç modeli (örn. **~30₺/görev**)
- Manuel IBAN havale ile ödeme (admin onaylı)

## 6. İş Ortaklığı Programı

- **Davet Et Kazan** (referral linki ile yeni kullanıcı kazanımı)
- **Görev Ver Kazan** (görev oluşturma teşviki)
- Ödeme Talebi Oluştur (ortaklık kazançları için)

## 7. Ana Sayfa ve Canlı Akış

- Hoş geldin mesajı (kişiselleştirilmiş)
- Hızlı erişim: **+ Yeni Görev Ver** butonu
- **"Avutap'ta neler oluyor?"** canlı feed (gerçek zamanlı görev oluşturma akışı)
- Arşiv paneli — Atama Yapılanlar / Tamamlananlar (son 10 görev)
- Görevlendirme geçmişim widget'ı
- Bekleyen / Başvurduğum görevler özet kutusu
- Duyuru bandı (örn. "E-Barobirlik ile ilgili önemli uyarı")

## 8. Uyuşmazlık Masası

- Görev sırasında çıkan ihtilafların kayıt altına alınması
- İhtilaf bildirim formu
- Admin tarafından çözüm süreci yönetimi

## 9. Yardım ve Destek

- Nasıl Çalışır? sayfası (kullanım kılavuzu)
- Öneri, İstek & Şikayet formu
- SSS / yardım merkezi

## 10. Mobil Uygulamalar

- iOS native uygulama
- Android native uygulama
- Push notification altyapısı

## 11. Admin Paneli (Arka Planda)

- Kullanıcı yönetimi (onay, blokaj, premium yönetimi)
- Görev moderasyonu
- Ödeme talepleri onay/red iş akışı (manuel havale takibi)
- İhtilaf yönetimi
- İçerik yönetimi (duyuru, hazır açıklama şablonları)
- Adliye / il / görev tipi referans veri yönetimi
- Raporlar (kullanıcı, görev, gelir)

## 12. Halka Açık Sayfalar

- Ana tanıtım sayfası (avutap.com.tr)
- Kayıtlı avukat ve adliye istatistikleri
- Hakkımızda / iletişim sayfaları
- Yasal sayfalar (Mesafeli Satış, Ön Bilgilendirme, KVKK, gizlilik)

## Özet — Modül Sayısı

AVUTAP yaklaşık **12 ana modülden** oluşmaktadır. Hazırlayacağımız platform için bu modüller **BASE paketin** temelini oluşturacak; üzerine **ek özellikler** ayrı fiyatlandırma kalemleri olarak eklenecektir:

- AI eşleştirme
- E-imza
- Kurumsal hesap
- UYAP entegrasyonu
- vb.
