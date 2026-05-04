# Müşteri Ses Kaydı — 2026-05-04

- **Tarih:** 2026-05-04
- **Müşteri:** Av. Veli Onur Biçimli
- **Format:** Sesli mesaj (özet transkript)
- **Konu:** AVUTAP'ın neden tercih edildiği + temel mekanizmalar

## Aktarılan bilgiler (transkripsiyon)

> "AVUTAP'ın daha kullanılması sebebi **konum özelliği** var. Görevlendirenin **yerin kaç km olduğu**. **Adliyedeyim butonu** — eğer biraz daha acele işlerde adliyedeyim butonu seçersen, görev adliyede olduğu için, görev adliyede olduğu için sana veya senin gibilere atanıyor.
>
> **15 dakika görev süresi** var. Birisi görev verdiğinde o bölgeye açık avukatlara bildirim geliyor. 15 dakika içinde avukatlar cevap veriyor. O kişi avukatlardan herhangi biriyle iletişime geçip görevi yaptırıyor.
>
> **Yıllık üyelik** şeklinde çalışıyor — **2000 TL yıllık üyelik**. Eğer **1 yıl içinde 3 görev alamazsan abonelik ücretsiz uzatılıyor**.
>
> **Avukatlar tüm uygulamalara üye oluyor.** Görev başına **1000-2000 TL avukatlar para kazanıyor.**"

## Yeni öğrendiklerimiz (kritik)

### 1. 📍 Konum özelliği — AVUTAP'ın **gizli silahı**

Müşteri açıkça söylüyor: *"AVUTAP'ın daha kullanılma sebebi konum özelliği var."*

İki alt-özellik:

#### a) **"Adliyedeyim" butonu** (real-time location-based assignment)

- Avukat fiziksel olarak adliyede ise app'te toggle açıyor
- GPS ile lokasyon doğrulanır
- Acil görev geldiğinde **adliyede bulunan avukatlara öncelik** veriliyor
- "şehir dışı küçük işler" için ideal: dosya fotokopisi, bir imza, hızlı duruşma yardımı vb.

→ **Bu özellik competitor analysis'de yoktu**, screenshot'larda gözlemlenmedi (settings'te "Görev alma durumu" toggle'ından farklı). Müşteri kendi deneyimiyle aktardı.

#### b) **Mesafe gösterimi** (distance in km)

- Görev kartında "görev konumu sana X km uzaklıkta" gibi bilgi
- Avukat lokasyonuna göre filter/sıralama mümkün

### 2. Üyelik Garantisi (NETLEŞTİ)

**Kesinleşen koşullar (müşteri tarafından doğrulandı):**
- **Süre:** 1 yıl
- **Eşik:** <3 görev (1 yıl içinde 3 görev alınmadıysa)
- **Sonuç:** **Abonelik ücretsiz uzatılır** (para iadesi değil)

> Screenshot 21'de "ücretsiz uzatma" doğruymuş; benim ilk okumam ("7 görev") eşiği yanlıştı. Doğru eşik: **3 görev**.

→ Bu, **risk-free trial benzeri** ama daha hafif bir vaad: avukat ₺2.099 öder, yıl sonunda 3 görev alamazsa platform üyeliği bir yıl daha ücretsiz uzatır. Müşteri parasını geri alamaz, ama platforma ek bağlantı koparmaz.

### 3. Multi-platform üyelik davranışı

> *"Avukatlar tüm uygulamalara üye oluyor."*

- Avukatlar AVUTAP **VE** TEVKİL'e (ve muhtemelen başkalarına) üye oluyor
- Pazar **exclusive değil** — tek bir lider yok, herkes yan yana üye
- → Bizim için: **agresif kullanıcı edinme** mantıklı; "sadece bizde olsun" stratejisi gereksiz
- Düşük switching cost = bizim avantajımız (kayıt kolaysa hemen üye olur)

### 4. Ücret modeli — net rakamlar

| Veri | Değer |
|---|---|
| Yıllık premium üyelik | **₺2.000** (eski üyeye ₺2.099 - ₺200 indirim = ₺1.899 olabilir) |
| Görev başına avukat kazancı | **₺1.000 - ₺2.000** (ekran 4'te 1100-1250 TL gözlemledim — uyuşuyor) |
| İade garantisi | **3 yıl** (müşteri ifadesi) / **1 yıl** (uygulama ekranı) |

## Değişen / güncellenecek dökümanlar

| Dosya | Değişiklik |
|---|---|
| `competitor-analysis/avutap-app-ui-ux.md` | "Adliyedeyim" butonu + km mesafe gösterimi yeni bölüm |
| `competitor-analysis/avutap-feature-inventory.md` | Konum özellikleri madde ekle |
| `competitor-analysis/avutap.com.md` | "Konum = AVUTAP'ın gizli silahı" çıkarımı |
| `requirements/2026-05-initial-scope.md` | Modül 4'e konum tabanlı eşleştirme + "Adliyedeyim" toggle ekle |
| `pricing.md` | Konum modülü adam-gün tahminine ekle |

## Action Items

- [ ] **Adliyedeyim** özelliğini Modül 4'e gömerek requirements'ı güncelle (AI-485 sonrası iş)
- [ ] Müşteri ile **3 yıl iade garantisi** netleştirilsin (Gerçek mi, müşteri yanılgısı mı)
- [ ] AVUTAP'ı bir hafta deneyim deneyim — "Adliyedeyim" akışını canlı görmek için (test hesabı)
- [ ] Konum tabanlı eşleştirme için **GPS izinleri**, **konum doğruluğu**, **fake-location önleme** RFC açılsın
- [ ] Pricing.md'de konum modülü = ~10-12 adam-gün ekle
