# FAZ 2: KÜP UYDU DEMONSTRASYONU

**Süre:** Yıl 3-7
**Bütçe:** $2-5M
**Çıktı:** Uzayda doğrulanmış konsept, TRL 5-6

---

## Amaç

Faz 1'de doğrulanan topolojinin **gerçek uzay ortamında** test edilmesi. Bu, simülasyon ve laboratuvarın ötesine geçer.

**Kritik sorular:**
1. Süperiletken tel, fırlatma vibrasyonuna dayanır mı?
2. Uzayda açılma mekanizması çalışır mı?
3. Pasif akım indüksiyonu (kalıcı mod) fonksiyonel mi?
4. Plazma ortamında kalkan gerçekten oluşuyor mu?

---

## Konsept: 3U Küp Uydu + Açılır Süperiletken Halka

### Küp Uydu (Bus)

**Form faktör:** 3U (10×10×30 cm, ~4 kg)
**Yerleşik sistemler:**
- OBC (On-Board Computer): ARM Cortex-M4
- Telemetri: UHF/VHF (amatör bant, 9.6 kbps)
- Komut alıcı: UHF
- Güç: Li-ion + güneş paneli (3-5 W)
- Yıldız izci: ince fiber gyro
- Manyetometre: 3 eksenli fluxgate, ±65 µT
- GPS: alçak yörünge konum belirleme

### Açılır Halka (Payload)

**Fırlatma konfigürasyonu:**
- Halka sıkıca sarılı, ~10 cm çapında mağaraya
- YBCO şerit mağazası: 50 m (5 cm × 5 cm × 10 cm hacim)
- Koruyucu kapak (release mechanism)

**Açılma sonrası:**
- Halka çapı: ~16 m (yarıçap 8 m)
- 1 sarım, ince YBCO
- Self-expanding mekanizma (shape memory alloy + yay)

**Akım indüksiyonu:**
- Halka yere yerleştirildikten sonra **kalıcı akım** indüklenir
- Yöntem: Dış bobin + anahtar (Flux pump tekniği)
- Hedef akım: 100-500 A (sınırlı, sadece konsept doğrulama)
- Bir kez indüklenir, kalıcı modda kalır

### Ölçüm Hedefleri

**Birincil:**
- Uzayda açılma başarısı
- Akım kalıcılığı (1-2 yıl boyunca)
- Halka geometrisi korunması

**İkincil:**
- Yörüngede plazma etkileşimi (TLE irtifasında ~400 km)
- Yapısal titreşim modları
- Termal performans (güneş/gölge döngüsü)

### Yörünge Stratejisi

**Hedef yörünge:** 400-600 km, ~28° eğim (SpaceX rideshare uyumlu)
**Ömür:** Doğal yörünge bozunması ile 1-2 yıl
**Maliyet:** Rideshare olarak $300-500K (3U slotu)

---

## Aşamalar

### 2.1: Tasarım (6-12 ay)

**Mekanik:**
- Açılma mekanizması (TESS-R asteroid sampling konsepti)
- Shape memory alloy (Nitinol) trigger
- Halka yapısal analizi (modal analiz)

**Termal:**
- YBCO 5K soğutma (mini cryocooler, 50 g)
- Güneş/gölge gradyanı yönetimi
- Pasif radyasyon (deep space side)

**Elektronik:**
- COTS bileşenler (tercihen rad-hard)
- Açılma zamanlaması (yörünge + konum)
- Veri paketi: 10 kB/gün (yeterli)

**Yazılım:**
- OBC firmware (C)
- Halka kontrol (sadece açılma, aktif kontrol yok)
- Telemetri paketleme

### 2.2: Yer Testleri (12-18 ay)

**Mekanik testler:**
- Vibrasyon: 14 g RMS (qualification)
- Şok: 100 g, 1 ms
- Termal vakum: -100°C ile +100°C, 10⁻⁵ Torr
- Açılma: 0 g simülasyonu, gerçek atmosfer

**Süperiletken testleri:**
- 5K cryocooler performans
- YBCO şerit vibrasyon testi
- Akım indüksiyonu demo (yerde, büyük bobinle)

**Entegrasyon:**
- Tüm alt sistemler
- EMI/EMC testleri
- Fonksiyonel testler (tüm modlar)

### 2.3: Fırlatma ve Operasyon (24-36 ay)

**Fırlatma:**
- SpaceX Falcon 9 rideshare (örn. Transporter-5)
- Yörünge: 525 km, güneş-senkron
- Yerleştirme: 1-2 ay içinde

**LEOP (Launch and Early Orbit Phase):**
- Telemetri kurulumu
- Sağlık kontrolü
- Açılma zamanlaması (yörünge+konum optimizasyonu)

**Operasyon:**
- Açılma sonrası: 1 yıl veri
- Toplam 2 yıl yörünge ömrü
- Yer istasyonu: Amatör radyo ağı + özel alıcılar

### 2.4: Veri Analizi ve Yayın (36-48 ay)

**Veri:**
- Açılma başarısı (y/n)
- Akım zaman serisi
- Halka geometrisi
- Plazma etkileşimi (sınırlı, 525 km'de plazma yoğun)

**Yayın:**
- AIAA/Acta Astronautica makalesi
- Topoloji tasarımı doğrulaması
- Faz 3 planlaması

---

## Bütçe

| Kalem | Miktar |
|-------|--------|
| Küp uydu bus (COTS) | $200K |
| YBCO halka payload | $300K |
| Cryocooler (mini) | $150K |
| Mekanik tasarım + imalat | $200K |
| Yer testleri (vibrasyon, termal vakum) | $300K |
| Yazılım geliştirme | $100K |
| Fırlatma (rideshare) | $500K |
| Operasyon (1-2 yıl) | $300K |
| Veri analizi | $100K |
| Konferans + yayın | $50K |
| Yönetim + yedek | $300K |
| **TOPLAM** | **~$2.5M** |

---

## Riskler ve Azaltma

| Risk | Olasılık | Etki | Azaltma |
|------|----------|------|---------|
| Açılma başarısız | Orta | Görev başarısız | Yer testleri sıkı, redundant trigger |
| YBCO vibrasyonda quench | Orta | Akım kaybı | Mekanik destek, vibrasyon izolatörü |
| Cryocooler başarısız | Orta | Tel sıcak, akım kaybı | Pasif radyasyon cooling, redundancy |
| Plazma ölçümü zayıf (525 km çok yoğun) | Yüksek | Bilimsel değer düşük | En azından konsept doğrulanır |

---

## Geçiş Kriteri → Faz 3

✅ Halka uzayda başarıyla açıldı
✅ Kalıcı akım 6+ ay korundu
✅ Halka geometrisi stabil kaldı
✅ En az 1 SPE olayı geçişi kaydedildi
✅ Patent güncellendi
✅ Tam ölçekli yer prototipi için yeterli veri

**Eğer tüm kriterler karşılanmazsa:** Tekrar tasarım, 6-12 ay ek süre.

---

## Açık Bilim Politikası

- Tüm veri ham haliyle NASA Open Data Portal'da
- Tüm kod açık kaynak
- Halka tasarımı patentlenmiş ama lisanslama açık (royalty-free non-commercial)
- Akademik gruplar davet edilir (workshop + veri erişimi)
