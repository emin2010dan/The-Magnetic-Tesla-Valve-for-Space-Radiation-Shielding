# MALZEME SEÇİMİ

## Pasif Asimetrik Manyetik Kalkan İçin Süperiletken Tel ve Diğer Bileşenler

**Versiyon:** 0.1 — 2026-06-02

---

## 1. SÜPERİLETKEN TEL

### 1.1 Gereksinimler

- **Kritik sıcaklık (T_c):** > 77 K (sıvı nitrojen sıcaklığında çalışabilir)
- **Kritik akım yoğunluğu (J_e):** > 1×10¹¹ A/m² (5K'de), > 1×10¹⁰ A/m² (77K'de)
- **Mekanik dayanım:** hoop stress ve vibrasyona direnç
- **Radyasyon dayanımı:** 25 yıl, 1 Gy/saat GCR ortamı
- **Boyut:** 10-20 m uzunluk, kaynak yapılabilir
- **Maliyet:** $10-50/kA-m (Faz 4 için toplam ~$300M tel)

### 1.2 Aday Malzemeler

#### A. YBCO (YBa₂Cu₃O₇-δ) — Birincil Tercih

**Avantajlar:**
- Yüksek T_c = 92 K (sıvı azot soğutma mümkün)
- Yüksek J_e = 1-9×10¹¹ A/m² (5K), 6×10¹⁰ A/m² (77K)
- Olgun endüstriyel üretim (SuperPower, Fujikura, SuNam)
- Şerit halinde (4-12mm genişlik) kullanılabilir
- **Fiyat: $20-50/kA-m (2026), 2030'da $5-15/kA-m bekleniyor**

**Dezavantajlar:**
- Kırılgan seramik, mekanik destek gerekli
- Radyasyona karşı orta hassasiyet
- AC kayıplar yüksek (ama biz DC kullanıyoruz)

**Tedarikçiler:**
- **SuperPower Inc.** (ABD, Schenectady NY) — 4-12mm şerit
- **Fujikura Ltd.** (Japonya) — 10mm standart
- **SuNam Co.** (Güney Kore) — yüksek J_e şeritler
- **THEVA GmbH** (Almanya) — Avrupa tedarik
- **Shanghai Superconductor Technology** (Çin) — ucuz, yüksek hacim

**Toplam küresel kapasite:** ~5000-10000 km/yıl (2026). Faz 4 için 2000 ton = ~12.000 km (birkaç yıllık üretim). Mümkün ama **erken tedarik sözleşmesi kritik**.

#### B. Bi-2212 (Bi₂Sr₂CaCu₂O₈) — İkincil

**Avantajlar:**
- Yuvarlak tel formu (daha kolay sarma)
- Çok yüksek J_e mümkün
- Uzun süredir araştırılmış

**Dezavantajlar:**
- T_c = 85 K (biraz düşük)
- AC kayıplar
- Isıl işlem gerektirir
- Şu an sınırlı üretim

**Uygunluk:** Yüksek performans gereken yerlerde, ana sistem için değil.

#### C. MgB₂ (Magnezyum Diborür) — Üçüncül

**Avantajlar:**
- Ucuz, bol malzeme
- T_c = 39 K (daha düşük, ama soğutma daha kolay)
- Tel olarak üretilebilir (ticari)

**Dezavantajlar:**
- J_e çok düşük: ~10⁹-10¹⁰ A/m² (10-100× düşük)
- YBCO'ya göre çok ağır sistem gerektirir

**Uygunluk:** Yedek seçenek. Eğer YBCO tedarik edilemezse.

#### D. Fe-tabanlı (Iron-Based Superconductor) — Gelecek

**Avantajlar:**
- Yüksek T_c (50-100 K arası)
- Daha ucuz hammaddeler
- Manyetik alana daha dayanıklı
- 2025-2030'da endüstriyel üretim bekleniyor

**Dezavantajlar:**
- Henüz olgun değil
- Ticari şerit 2026'da mevcut değil

**Uygunluk:** Faz 4 (yıl 12-25) için alternatif. Erken araştırma.

### 1.3 Önerilen Tel Mimarisi

**Birincil seçim:** YBCO 12mm şerit, 0.1mm kalınlık, Hastelloy alttaşık
- **Üretici:** SuperPower (ABD) veya Fujikura (Japonya)
- **Spesifikasyon:**
  - Genişlik: 12 mm
  - Kalınlık: 0.1 mm (süperiletken katman)
  - Alttaşık: 50 μm Hastelloy C-276
  - Kaplama: 20 μm bakır (termal stabilite)
  - Toplam kalınlık: 170 μm
  - J_e (5K, self-field): 9×10¹¹ A/m²
  - I_max (tek şerit): 1.08 MA

**Paralel şerit paketi:** 5-15 paralel şerit (güvenlik + kapasite)
- 5 paralel: 5.4 MA max, yedek 4 şerit var
- 15 paralel: 16.2 MA max, aşırı yedek

**Kaynak:** Şeritlerin birleştirilmesi zorlu. Yöntemler:
- **Ultrasonik kaynak** (~1 m uzunluk joint, düşük direnç)
- **Lazer kaynak** (daha kısa, daha yüksek direnç)
- **Mekanik sıkıştırma** (en kolay, sökülebilir)

**Kaynak direnci hedef:** < 10⁻¹² Ω (kalıcı akım korunması için)

---

## 2. ALTTAŞIK MALZEMESİ

### 2.1 Neden Önemli

YBCO tek başına çok kırılgan. 5 km çaplı halkayı 1.5 kN/m hoop stres taşıyacak. YBCO bunu yapamaz. Alttaşık, mekanik yükü taşır.

### 2.2 Adaylar

#### A. Hastelloy C-276 (Ni-Cr-Mo alaşımı) — Birincil

**Avantajlar:**
- Manyetik olmayan (kalkanı bozmaz)
- Korozyon dayanımı yüksek
- Süperiletken üretim ile uyumlu
- Olgun malzeme

**Dezavantajlar:**
- Yoğunluk yüksek: 8.9 g/cm³
- Mekanik özellikler orta

**Kullanım:** YBCO üretim hattında standart alttaşık

#### B. Paslanmaz Çelik 316L — Alternatif

**Avantajlar:**
- Ucuz, bol
- İyi mekanik özellikler

**Dezavantajlar:**
- Manyetik (paramanyetik, küçük etki)
- Korozyon riski (uzayda nem yok, sorun değil)

**Kullanım:** İkincil seçenek

#### C. Grafen Takviyeli Kompozit — Gelecek (NASA MAARSS)

**Avantajlar:**
- Çok yüksek dayanım/ağırlık oranı
- Manyetik olmayan
- Düşük yoğunluk: 1.5-2 g/cm³
- **NASA MAARSS çalışması grafen alttaşıklı YBCO'yu 5× daha verimli buldu**

**Dezavantajlar:**
- Yeni teknoloji
- Üretim henüz olgun değil
- Süperiletken üretim hattıyla entegrasyonu zor

**Kullanım:** Faz 1-2'de Ar-Ge, Faz 3'te uygulama

### 2.3 Önerilen Yapı

**Sandviç kompozit:**
- 0.1 mm YBCO
- 50 μm Hastelloy (üretim uyumu)
- 0.5-1 mm karbon fiber kompozit (yapısal destek)
- 50 μm bakır kaplama (termal stabilite)

**Toplam kalınlık:** 0.7-1.2 mm
**Toplam kesit alanı:** 12 mm × 1 mm = 12 mm² (10× standart şerit)
**Akım kapasitesi:** 9×10¹¹ × 12×10⁻⁶ = 10.8 kA (tek şerit!)

**Bu, 1-2 paralel şerit ile 5-10 kA ihtiyacı karşılar. Çok büyük kütle tasarrufu.**

---

## 3. CRYOCOOLER

### 3.1 Gereksinimler

- **Çalışma sıcaklığı:** 5 K (YBCO yüksek J_e için)
- **Soğutma kapasitesi:** 1 W @ 5 K (her cryocooler)
- **Güç tüketimi:** 1-2 kW @ 5 K soğutma için
- **Ömür:** > 25 yıl (veya modüler değişim)
- **Kütle:** < 200 kg
- **Titreşim:** düşük (süperiletkeni bozmamalı)

### 3.2 Adaylar

#### A. GM (Gifford-McMahon) Soğutucu — Birincil

**Avantajlar:**
- Ticari olarak mevcut (Sunpower, Cryomech)
- 5-10 W @ 4.2 K (küçük modeller)
- Uzay için uyarlanmış versiyonlar var
- 10+ yıl ömür (uzay görevlerinde kanıtlanmış)

**Dezavantajlar:**
- Ağır (150-300 kg)
- Yüksek güç (1.5-2.5 kW @ 5 K)
- Titreşim (mekanik kompresör)

**Örnek:** Sunpower CryoTel GT (150 kg, 1.5 kW → 1 W @ 4.2 K)

#### B. Pulse Tube Soğutucu — İkincil

**Avantajlar:**
- Titreşimsiz (pulse tube prensibi)
- Daha uzun ömür (hareketli parça yok)
- Uzay için optimize

**Dezavantajlar:**
- Daha ağır
- Daha pahalı
- Sınırlı tedarik

**Örnek:** Lockheed Martin / NASA Goddard tasarımları

#### C. Pasif Radyasyon Soğutma — Yardımcı

**Avantaj:** 50-100 K'a kadar sıfır güç
**Dezavantaj:** 5 K'a ulaşamaz (sadece ön soğutma)
**Kullanım:** GM/pulse tube öncesi, %50 güç tasarrufu

### 3.3 Önerilen Konfigürasyon

**5 aktif + 1 yedek GM cryocooler:**
- Her biri: 150 kg, 1.5 kW
- 5 aktif: 750 kg, 7.5 kW
- 1 yedek: 150 kg, 1.5 kW (bekleme)
- **Toplam: 900 kg, 9 kW**

**Ömür yönetimi:** Her 7-10 yılda bir değişim
- İlk değişim: Yıl 7-10 (yerel kaynaklardan)
- Toplam: 25 yılda 2-3 değişim

---

## 4. YAPISAL MALZEMELER

### 4.1 Halka İskeleti

**Gereksinimler:**
- 5 km çaplı dairesel geometri koruma
- Lorentz kuvvetlerine dayanım
- Termal genleşme yönetimi (-150°C ile +150°C arası, gölge/güneş)
- Manyetik olmamalı (kalkanı bozmaz)

**Seçim:** Karbon fiber kompozit (CFRP)
- Yoğunluk: 1.5-1.8 g/cm³
- Çekme dayanımı: 3-7 GPa
- Manyetik değil
- Termal genleşme: ~0 (boyuna)

**Mimari:**
- 12-24 ana kiriş (karbon fiber, 5-10 cm çap)
- Çapraz bağlantılar (daha ince)
- Halka segmentlerini taşıyan kelepçeler

### 4.2 Çekirdek Solenoid Çerçevesi

**Daha yoğun kuvvetler:** 0.5 T'de 100.000 N/m hoop stress
**Seçim:** Karbon fiber veya yüksek dayanımlı alüminyum
- Al-7075-T6: çekme 570 MPa, yoğunluk 2.8 g/cm³
- Karbon fiber: çekme 3-7 GPa, yoğunluk 1.6 g/cm³

**Karbon fiber avantajlı** ama daha pahalı.

### 4.3 Montaj Braketleri

**Seçim:** Alüminyum 7075 veya titanyum
- Alüminyum hafif, manyetik değil
- Titanyum daha güçlü ama pahalı

---

## 5. YALITIM MALZEMELERİ

### 5.1 Çok Katmanlı Yalıtım (MLI)

**Gereksinimler:**
- 5 K yüzeyden 300 K ortama minimum ısı transferi
- Boşluk ortamında çalışmalı (konveksiyon yok)
- 25 yıl ömür

**Seçim:** 20-30 katmanlı MLI
- Her katman: 12 μm Mylar (alüminyum kaplı)
- Ara katman: Dacron file (ayrıştırıcı)
- Toplam: 2-3 cm kalınlık
- **Yüzey başına ısı transferi: 1-5 W/m²** (5 K'da)

**Tedarikçi:** Sheldahl, Dunmore, İstanbul TÜBİTAK

### 5.2 Radyasyon Yalıtımı

**Gereksinimler:**
- GCR ve SPE protonlarını soğurma
- 25 yıl kümülatif doz

**Seçim:**
- 2-5 cm polietilen (yüksek hidrojen içerik)
- 1-2 mm alüminyum (X-ışını azaltma)
- Toplam: ~5 g/cm² (kısmi GCR azaltma)

---

## 6. MONİTORİNG VE KONTROL SİSTEMLERİ

### 6.1 Sensörler

**Manyetik alan:**
- 3 eksenli fluxgate manyetometre (iç bölge, 5+ adet)
- Hall prob (dış bölge, 10+ adet)

**Akım:**
- Rogowski bobinleri (her halka)
- Hall-effect akım sensörü (yedek)

**Sıcaklık:**
- Termokupl (her segment, 100+ adet)
- Fiber Bragg grating (quench detection, 1 ms tepki)

**Yapısal:**
- Strain gauge (halka üzerinde, 50+ adet)
- İvmeölçer (titreşim izleme)
- Akustik emisyon (çatlak tespiti)

**Plazma:**
- Langmuir probu (opsiyonel, üs çevresi)
- Enerji analizörü (radyasyon ortamı)

### 6.2 Veri Toplama

**OBC:** Uzay-grade rad-hard bilgisayar
- Örnek: NASA Goddard RAD750 (eski) veya RAD5500 (yeni)
- Veri hızı: 1 MB/saat, sıkıştırma ile
- Depolama: 1 TB SSD (radyasyon dayanımlı)

**Telemetri:** Yer istasyonuna sürekli veri
- X-band downlink (yüksek hız)
- S-band uplink (komut)
- Veri hızı: 100 kbps (downlink)

### 6.3 Aktif Kontrol (Minimum!)

**Felsefe:** Mümkün olduğunca az aktif kontrol. Sadece:
- **Acil kapatma** (quench detection → dump resistor)
- **Cryocooler kontrol** (sıcaklık ayarı)
- **Akım dengeleme** (çok küçük düzeltmeler, 1-10 A)

**Toplam aktif kontrol gücü:** < 100 W
**Akıllı karar:** Topoloji, sıfır-elektronik ilkesine sadık

---

## 7. MALİYET ÖZETİ

| Malzeme | Birim Fiyat | Toplam (Faz 4) |
|---------|-------------|----------------|
| YBCO tel (2000 ton) | $100-200/kg | $200-400M |
| Alttaşık + kaplama | $50-100/kg | $100-200M |
| Cryocooler (6 adet) | $1-2M/adet | $6-12M |
| Karbon fiber yapı | $50-100/kg | $50-100M |
| MLI yalıtım | $500/m² | $10-20M |
| Sensörler + veri toplama | $5M | $5M |
| Aktif kontrol | $1M | $1M |
| **Toplam malzeme** | | **$400-800M** |

**Bütçenin büyük kısmı tel + alttaşık.** Bu, Faz 1-2'de erken tedarik araştırmasını kritik yapıyor.

---

## 8. SONUÇ VE ÖNERİ

**Birincil malzeme seçimi:**
- YBCO 12mm şerit, Hastelloy alttaşık
- Karbon fiber yapısal destek
- 5+1 GM cryocooler konfigürasyonu
- Pasif MLI + aktif GM soğutma

**Erken aksiyon gerekli (Faz 1-2):**
- 5+ üretici ile uzun vadeli tedarik görüşmesi
- Özel alttaşık (grafen) için ek Ar-Ge fonu
- Cryocooler ömür testleri
- Akım dayanımı uzun vadeli testleri

**İkincil seçenekler (yedek):**
- Bi-2212 (yüksek performans)
- MgB₂ (düşük performans, ucuz)
- Fe-tabanlı (gelecek, 5-10 yıl)
