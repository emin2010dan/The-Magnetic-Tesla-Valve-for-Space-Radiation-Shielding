# FAZ 3: YER PROTOTİPİ (5 m çap, 1:500 ölçek)

**Süre:** Yıl 7-12
**Bütçe:** $30-100M
**Çıktı:** TRL 6-7, tam ölçekli üretilebilirlik kanıtı

---

## Amaç

5 m çaplı (1:500 ölçekli, 5 km yerine) **tam prototip** üretmek. Tüm bileşenler tam ölçekli yörünge prototipinde aynı teknoloji ve malzeme.

**Kritik sorular:**
1. Tam ölçekli üretim süreçleri çalışıyor mu?
2. Tüm bileşenlerin entegrasyonu sorunsuz mu?
3. Quench yönetimi gerçek ortamda çalışıyor mu?
4. 1+ yıl sürekli işletimde güvenilirlik?

---

## Sistem: 5 m Çaplı Tam Prototip

**Not:** Gerçek sistem 5 km çaplı, biz 1:500 ölçekli (5 m) prototip yapıyoruz. MHD ölçeklenebilir (Mach sayısı, Alfvén sayısı korunur), ama **mekanik entegrasyon, üretim süreçleri, quench yönetimi** tam ölçekte test edilir.

### Bileşenler

#### 1. YBCO Süperiletken Tel (300+ km)
- Üretim ortakları: SuperPower, Fujikura, SuNam
- Özellik: 12mm genişlik, 0.1mm kalınlık, GdBa₂Cu₃O₇
- Alttaşık: Hastelloy (mekanik) + grafen (NASA MAARSS yaklaşımı)
- Toplam: 300-500 km (faz 3 üretim hatlarını ölçeklendirmek için yeterli)

#### 2. Çekirdek Solenoid (R=0.5m, L=1m)
- Bu prototip için: 1/200 ölçekli bile olabilir (sadece üretim kanıtı)
- Hedef: B = 0.1 T (prototip, 0.5 T değil)
- 1000 sarım, bakır test sargısı başlangıçta

#### 3. Orta Katman (12 halka, R=5m)
- Tam ölçekli topoloji (5 m yerine 1000m → ölçek 1:200)
- Asimetrik yerleşim, 60° döngüsel
- Her halka 0.1-0.3 mT katkı
- Toplam: 75 m tel × 12 halka = 900 m

#### 4. Dış Perdeleme (5 m çap, 5 sarım)
- Tam ölçekli: 5 m çap (ölçek 1:500)
- B_edge = 5-10 mT (prototipte daha düşük)
- Toplam: 80 m tel

### Plazma Test Odası

**Vakum odası:**
- Çap: 8 m (5 m kalkan + 1.5 m ölçüm alanı)
- Uzunluk: 20 m (plazma akışı için)
- Basınç: 10⁻⁷ Torr (iyon pompa + cryo)

**Plazma kaynağı:**
- Tip: RF (radiative heating, 1-5 kW)
- Çıkış: 5-50 eV, ~10¹⁶ m⁻³
- Akış hızı: 5-50 km/s (manyetik pompa ile)
- Çap: 50 cm

**Diagnostik:**
- Langmuir probu (5+ konum)
- Hall probu manyetometre (3 eksen, 3D harita)
- Yüksek hızlı kamera
- Emisyon spektroskopisi
- Enerji analizör

### Kontrol ve İzleme (Aktif Kontrol Yok!)

**Sadece izleme:**
- Akım seviyesi (her halka)
- Sıcaklık (her halka + cryocooler)
- Manyetik alan (iç ve dış)
- Plazma parametreleri
- Vakum basıncı

**Kontrol:**
- Sadece acil kapatma (quench detection)
- Dump resistor aktivasyonu
- Güvenlik kilitleri

---

## Aşamalar

### 3.1: Tesis Kurulumu (Yıl 7-8)

**Konum seçimi:**
- Çap 8m, uzunluk 20m vakum odası
- Mevcut tesis (NASA, ESA, JAXA, üniversite) kiralanabilir
- Örnek: NASA Glenn Research Center (tarihi vakum odaları), MIT Lincoln Lab

**Altyapı:**
- Güç: 1 MW
- Soğutma: 100 kW (cryocooler'lar)
- Plazma kaynağı: 50 kW
- Veri toplama: 1000+ sensör

**Bütçe tesis:** $20-40M (mevcut bir tesis modifikasyonu)

### 3.2: Süperiletken Üretim Hattı (Yıl 7-9, paralel)

**Hedef:** 300+ km YBCO şerit üretimi
- Mevcut üreticilerin kapasitesi: yıllık ~1000-5000 km (çok büyük)
- Faz 3 için 300 km ayrılması yeterli
- Özel alttaşık (grafen) ekleme: $2M Ar-Ge

**Tedarik:**
- SuperPower Inc. (ABD)
- Fujikura (Japonya)
- SuNam (Güney Kore)
- THEVA (Almanya)

**Bütçe tel:** $5-10M

### 3.3: Sistem İmalatı (Yıl 9-10)

**İç çekirdek:**
- 0.5 m çaplı solenoid yapısı
- Karbon fiber destek çerçevesi
- 1000 sarım, YBCO tel

**Orta ve dış katman:**
- 12 halka (R=5 m), asimetrik yerleşim
- 5 halka (R=5 m)
- Mekanik iskelet, karbon fiber

**Soğutma:**
- 5× cryocooler (5 K)
- 1× yedek
- Dağıtım manifoldları

**Quench yönetimi:**
- Dump resistor bankı (her halka için)
- Fiber-optik sıcaklık sensörleri
- Kontrollü enerji boşaltma

**Bütçe imalat:** $20-30M

### 3.4: Plazma Testi (Yıl 10-12)

**Test 1: Temel karakterizasyon (3 ay)**
- Plazma akışında manyetik profil
- Magnetopause oluşumu gözlemi
- Bow shock tespiti

**Test 2: Asimetrik vs simetrik (3 ay)**
- Aynı B değerinde iki konfigürasyon
- Sızıntı farkı ölçümü

**Test 3: Reconnection (6 ay)**
- Yapay IMF yön değişimi
- Southward koşullarda performans

**Test 4: Uzun süreli işletim (12 ay)**
- Sürekli plazma altında
- Akı kaybı ölçümü
- Quench yönetimi doğrulaması
- Recharge prosedürü testi

**Bütçe testler:** $10-20M (12 ay, 1 vardiya/gün operasyon, ekipman + personel)

---

## Toplam Bütçe Faz 3

| Kalem | Miktar |
|-------|--------|
| Tesis kurulumu | $20-40M |
| YBCO tel üretimi | $5-10M |
| Sistem imalatı | $20-30M |
| Plazma testleri (1 yıl) | $10-20M |
| Personel (5 yıl, ~10 kişi) | $15-20M |
| Yönetim, lisans, sigorta | $5-10M |
| Yedek | $5-10M |
| **TOPLAM** | **$80-140M** |

**Riskli kalemler:**
- Tesis kurulumu (lokasyona bağlı)
- Tel üretiminde graphene alttaşık gecikmeleri
- Test süresinde beklenmeyen sorunlar

**Gerçekçi bütçe:** $100M, NASA NIAC veya ESA CDF programlarıyla uyumlu.

---

## Çıktılar

1. **5 m çaplı tam prototip** (fonksiyonel)
2. **Plazma test verileri** (açık erişim)
3. **TRL 6-7 belgesi** (NASA standart)
4. **Patent güncellemesi** (topoloji + quench yönetimi)
5. **2-3 akademik makale**
6. **Faz 4 planlama dokümanı**

---

## Geçiş Kriteri → Faz 4

✅ 12 ay kesintisiz plazma testi başarılı
✅ Quench yönetimi doğrulanmış
✅ Recharge prosedürü çalışıyor
✅ Akı kaybı < %1/yıl
✅ Tam ölçekli (5 km) sistem için mühendislik spesifikasyonu hazır
✅ Bütçe ve zaman çizelgesi makul

**Eğer kriterler karşılanmazsa:** Yeniden tasarım, ek 2-3 yıl.

---

## Açık Standartlar

- Tüm tel özellikleri yayınlanır
- Plazma test prosedürleri standartlaştırılır
- Topoloji tasarımı açık kaynak
- Patent lisanslama: non-commercial ücretsiz, commercial royalty
- Tüm veri açık arşivde
