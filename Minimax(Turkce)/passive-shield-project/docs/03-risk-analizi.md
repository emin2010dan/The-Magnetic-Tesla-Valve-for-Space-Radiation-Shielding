# RİSK ANALİZİ

## Pasif Asimetrik Manyetik Kalkan Projesi

**Versiyon:** 0.1 — 2026-06-02

---

## 1. FİZİKSEL RİSKLER

### R-F1: Reconnection Sızıntısı (Yüksek Olasılık, Orta Etki)

**Açıklama:** Southward IMF koşullarında, kalkan manyetik alanı güneş rüzgârı alanıyla "kısa devre" yapar. Plazma içeri sızar. Dünya'da bu olay manyetik fırtınalara yol açar.

**Etki:** SPE sırasında doz 2-3× artar. Asimetrik topoloji bunu azaltır ama tamamen engelleyemez.

**Azaltma:**
- Asimetrik topoloji (Katman 2) → 2-3× sızıntı azalması (beklenen)
- MHD simülasyon ile en kötü senaryo hesaplanır
- İç çekirdek solenoid, son savunma hattı
- Üs sığınakları (5-10 m toprak üstü) kritik anlarda

**İzleme:** Manyetometre ağı (iç + dış), reconnection uyarıları

### R-F2: Quench (Süperiletkenlik Kaybı) (Orta Olasılık, Yüksek Etki)

**Açıklama:** Herhangi bir segment aşırı ısınırsa, süperiletkenlik kaybolur. Rezistif ısınma tüm sistemi "yığın halinde" çökertebilir (quench propagation).

**Etki:** Kalkan aniden çöker, tüm üs korumasız kalır.

**Azaltma:**
- Fiber-optik sıcaklık sensörleri (1 ms tepki)
- Quench detection + dump resistor (1-100 ms enerji boşaltma)
- Segmentasyon: Her halka ayrı devre, biri quench olursa diğerleri etkilenmez
- Karbon fiber alttaşıklı YBCO (NASA MAARSS yaklaşımı)
- Yedek soğutma (her cryocooler için 1+1 redundancy)

**İzleme:** Sürekli sıcaklık, akım, direnç

### R-F3: Kozmik Işın Hasarı (Düşük-Olasılık, Orta Etki)

**Açıklama:** 25 yıllık ömürde, kozmik ışınlar YBCO kristal yapısını bozabilir. Kritik akım azalır, tel ömrü kısalır.

**Etki:** 25 yılda akı kaybı %12'den %30'a çıkabilir.

**Azaltma:**
- Radyasyon shielding (MLI + alüminyum)
- Yedek segmentler (bozulanı değiştirme)
- Sürekli "trickle charge" (akı kaybını dengeleme)
- Periyodik yenileme (her 10 yılda bir segmentasyon)

**İzleme:** Periyodik akım testi, akı haritalama

### R-F4: Yapısal Yorulma (Orta Olasılık, Yüksek Etki)

**Açıklama:** Halkalar termal döngü (güneş/gölge), Lorentz kuvvetleri, mikrometeor darbeleri altında yorulur. 25 yılda çatlak/kopma oluşabilir.

**Etki:** Halka koparsa, o bölgede plazma sızıntısı artar.

**Azaltma:**
- Karbon fiber kompozit yapı (yorulma dayanımı yüksek)
- Yapısal izleme (strain gauge, akustik emisyon)
- Çift halka (1 koparsa diğeri taşır)
- Modüler tasarım (1 halka değiştirilebilir)

**İzleme:** Strain, ivme, sıcaklık

### R-F5: Manyetik Stres → Halka Deformasyonu (Düşük Olasılık, Orta Etki)

**Açıklama:** Lorentz kuvvetleri (özellikle dış halkada 1.27 GJ enerji) halkayı deforme edebilir. Dairesellik bozulursa, plazma sızıntısı artar.

**Etki:** Kalkan geometrisi bozulur, koruma zayıflar.

**Azaltma:**
- Karbon fiber dış destek
- Halka gerginlik ayarı (aktif tensioner — bu aktif bileşen!)
- **Not:** Bu, "pasif" ilkesinden küçük bir sapma. Sadece düşük güçlü (~100 W), yavaş tepkili, sadece geometri korumak için.

**İzleme:** Halka şekil sensörleri

---

## 2. MÜHENDİSLİK RİSKLERİ

### R-M1: Süperiletken Üretim Ölçeklenemez (Orta, Çok Yüksek)

**Açıklama:** 2000 ton YBCO tel, yıllık küresel kapasitenin %5-10'u. Özel alttaşıklı (grafen) tel yeni bir Ar-Ge gerektirir. Tedarik zinciri kırılgan.

**Etki:** Program durur veya 5-10 yıl gecikir.

**Azaltma:**
- **Erken tedarik araştırması** (Faz 1 sonu, Faz 2 başı)
- Çoklu tedarikçi (SuperPower, Fujikura, SuNam, THEVA)
- Yedek Ar-Ge: geleneksel Hastelloy alttaşıklı tel (daha az performans ama hazır)
- Devlet teşviki (YBCO üretim hattı için)
- Trade-off: 12mm yerine 4mm standart şerit (kolay tedarik)

### R-M2: Cryocooler Uzay Ömrü Yetersiz (Düşük, Yüksek)

**Açıklama:** Mars'ta 25 yıl çalışacak cryocooler, mevcut teknoloji ile garanti edilemez. Tipik uzay cryocooler ömrü 5-10 yıl.

**Etki:** 10 yılda cryocooler değişimi gerekir. 25 yılda 2-3 kez.

**Azaltma:**
- Modüler tasarım: 5 cryocooler, 1 yedek (6 toplam)
- Mars'tan cryocooler gönderimi (her 5-10 yılda)
- Alternatif: Pasif radyatif soğutma (gölge taraf, 50-100K)
- Trade-off: 77K'de YBCO kullanımı (daha düşük akım ama daha kolay soğutma)

### R-M3: Modüler Fırlatma Başarısızlığı (Orta, Orta)

**Açıklama:** 5-10 Falcon Heavy veya 20 Starship fırlatması. %95 başarı oranı = %86-99.9 görev başarısı (5-20 fırlatma).

**Etki:** 1-2 kayıp segment, ek fırlatma gerekebilir.

**Azaltma:**
- Yedek segmentler (tasarım payı)
- Sigorta
- Halka segmentasyonu (kayıp segmente komşu bölgeler paylaştırılabilir)
- Bağımsız segmentasyon (her halka bağımsız)

### R-M4: Yer Montajı Başarısızlığı (Düşük, Yüksek)

**Açıklama:** 60-2000 segmentin robotik montajı. Karmaşık, hata riski yüksek.

**Etki:** Montaj aylar-yıllar gecikir.

**Azaltma:**
- Yer testleri (Faz 3, 1:500 ölçekli)
- İnsanlı montaj (varsa, üs sakinleri)
- Modüler hata toleransı (1-2 segment eksikse kalkan hâlâ çalışır)
- AI destekli montaj (vision + machine learning)

### R-M5: İlk Şarj Sorunları (Orta, Orta)

**Açıklama:** 2000 tonluk sistemi ilk kez indüklemek büyük enerji gerektirir. 1+ yıl sürebilir. Süreçte hata riski.

**Etki:** Kalkan aktif hale gelmeden 1-2 yıl bekleme.

**Azaltma:**
- Kademeli şarj (önce çekirdek, sonra dış)
- Şarj sırasında kalkan zayıf, üs sığınak
- Batarya depolama (güneş panellerinden)
- Detaylı simülasyon öncesi

---

## 3. EKONOMİK / SİYASİ RİSKLER

### R-E1: Uzay Ajansları Bütçe Kesintisi (Yüksek, Çok Yüksek)

**Açıklama:** NASA, ESA, JAXA bütçeleri politik dalgalanmalara açık. Artemis, Mars programları iptal/gecikebilir.

**Etki:** Program 5-10 yıl gecikir veya iptal olur.

**Azaltma:**
- Çok uluslu konsorsiyum (bir ülke çıkarsa diğerleri devam)
- Ticari ortaklık (SpaceX, Blue Origin)
- Bağımsız finansman (vakıf, özel şirket)
- Düşük maliyetli Faz 1-2 (5-10M$) → "kanıtlanmış konsept" sonra büyük yatırım
- Anti-monokültür: farklı bütçe kaynaklarına yayılmış

### R-E2: Öncelik Kayması (Orta, Yüksek)

**Açıklama:** Yeni teknoloji (örn. nükleer füzyon, süper yapay zeka) uzay araştırmalarına yön değiştirebilir.

**Etki:** 25 yıllık program yarıda kalabilir.

**Azaltma:**
- Erken dönemde kanıtlanmış konsept (Faz 1-2)
- Teknoloji transferi (füzyon, AI ile entegre edilebilir)
- Topluluk oluşturma (insanların sahiplenmesi)

### R-E3: Kamuoyu İlgisi Kaybı (Düşük, Orta)

**Açıklama:** Uzay yorgunluğu, başarısızlıklar, dikkat dağınıklığı.

**Etki:** Uzun vadeli fon desteği zayıflar.

**Azaltma:**
- Sürekli medya görünürlüğü
- Eğitim programları
- Küçük başarıları kutla (Faz 1-2 gibi)
- **Bu doküman gibi açık kaynak yayınlar**

### R-E4: Uluslararası Gerilim (Düşük, Yüksek)

**Açıklama:** ABD-Çin uzay yarışı, savaş, ihracat kontrolleri.

**Etki:** Uluslararası işbirliği bozulur, proje daralır.

**Azaltma:**
- Çok kutuplu işbirliği
- Açık kaynak (herkes katkıda bulunabilir)
- Paylaşılan mülkiyet (patent lisanslama)

---

## 4. BİLİMSEL RİSKLER

### R-B1: MHD Simülasyonun Yetersizliği (Orta, Orta)

**Açıklama:** MHD, kinetik ölçekleri çözemez. Reconnection fiziği tam doğru modellenmez.

**Etki:** Simülasyon sonuçları yanıltıcı olabilir.

**Azaltma:**
- Hibrit: MHD global + PIC yerel
- Terrella deneyi (gerçek ölçüm)
- Çoklu model karşılaştırması (BATS-R-US, OpenMHD, Athena++)
- Deneysel doğrulama (Faz 2 küp uydu)

### R-B2: Asimetri Hipotezi Yanlış (Düşük, Çok Yüksek)

**Açıklama:** Asimetrik topoloji gerçekten avantaj sağlamıyor olabilir. Simetrik dipol aynı işi yapıyor olabilir.

**Etki:** 3-katmanlı mimari gereksiz, program sadeleşir.

**Azaltma:**
- **Bu iyi bir sonuç!** Paradigma değişir ama para boşa gitmez
- Simetrik tasarıma dönüş, daha az tel, daha düşük kütle
- Yine de 5-katlı bir sonuç: **bilim yapılmış olur**

**Not:** Bilim, hipotezin yanlış çıkmasıyla da ilerler. R-B2, "iptal" riski değil, "yön değişikliği" riski.

---

## 5. ZAMAN ÇİZELGESİ RİSKLERİ

### R-Z1: Toplam Süre 25+ Yıla Uzayabilir (Yüksek, Orta)

**Açıklama:** Uzay projeleri nadiren planlanan sürede biter. Apollo 8 yıl, Mars Sample Return 20+ yıl, ISS 30+ yıl.

**Etki:** 25 yıl → 35-40 yıl.

**Azaltma:**
- Her faz bağımsız başarı (her 3-5 yılda bir milestone)
- Kademeli konsept genişletme (Faz 1 → 2 → 3 → 4)
- Erken dur (her fazda "go/no-go" değerlendirmesi)
- Topluluk oluşturma (herkes süreci takip eder)

---

## 6. RİSK MATRİSİ

| Risk | Olasılık | Etki | Öncelik |
|------|----------|------|---------|
| R-F1 (Reconnection) | Yüksek | Orta | **Yüksek** |
| R-F2 (Quench) | Orta | Yüksek | **Yüksek** |
| R-F3 (Kozmik ışın) | Düşük | Orta | Orta |
| R-F4 (Yorulma) | Orta | Yüksek | Yüksek |
| R-F5 (Manyetik stres) | Düşük | Orta | Düşük |
| R-M1 (Tel üretimi) | Orta | Çok Yüksek | **Kritik** |
| R-M2 (Cryocooler) | Düşük | Yüksek | Orta |
| R-M3 (Fırlatma) | Orta | Orta | Orta |
| R-M4 (Montaj) | Düşük | Yüksek | Orta |
| R-M5 (İlk şarj) | Orta | Orta | Orta |
| R-E1 (Bütçe) | Yüksek | Çok Yüksek | **Kritik** |
| R-E2 (Öncelik) | Orta | Yüksek | Orta |
| R-E3 (İlgi) | Düşük | Orta | Düşük |
| R-E4 (Gerilim) | Düşük | Yüksek | Orta |
| R-B1 (MHD) | Orta | Orta | Orta |
| R-B2 (Asimetri) | Düşük | Çok Yüksek | Düşük |
| R-Z1 (Süre) | Yüksek | Orta | Yüksek |

---

## 7. EN KRİTİK RİSKLER VE AZALTMA

### 1. R-M1: Süperiletken Üretim (Kritik)

**Çözüm:** Faz 1'de (1-3 yıl) **erken tedarik zinciri araştırması**:
- 5+ üretici ile ön görüşme
- Uzun vadeli tedarik sözleşmesi (LTA)
- Özel alttaşık (grafen) için ek Ar-Ge fonu
- **Faz 1 başında (yıl 1-2) bu riski çöz**, yoksa 5-10 yıl kayıp

### 2. R-E1: Bütçe Kesintisi (Kritik)

**Çözüm:** Çoklu finansman:
- NASA NIAC (Faz 1-2, $5-10M)
- ESA CDF (Faz 1, $5M)
- Ticari ortaklık (SpaceX, Blue Origin — kargo ve fırlatma)
- Vakıf/Private (Faz 2-3, $20M+)
- Çok uluslu konsorsiyum (Avrupa, Japonya, Hindistan, BAE)
- **Herhangi birinin çekilmesi durumunda diğerleri devam**

### 3. R-F1 + R-F2: Reconnection ve Quench (Yüksek)

**Çözüm:** Simülasyon + deney + redundancy:
- MHD simülasyonu ile reconnection haritası
- Terrella deneyi ile gerçek ölçüm
- Çoklu segmentasyon (1 quench tüm sistemi çökertmez)
- Fiber-optik quench detection (1 ms tepki)
- Aktif tensioner (R-F5 için, küçük sapma)

---

## 8. RİSK İZLEME PLANI

**Her 3 ayda risk gözden geçirmesi:**
- Fiziksel riskler (MHD sonuçları, tel testleri)
- Mühendislik riskleri (üretim, test)
- Ekonomik riskler (bütçe durumu)

**Her faz geçişinde tam risk değerlendirmesi:**
- Go/no-go kararı
- Yeni azaltma stratejileri

**Açık risk günlüğü:**
- GitHub issues
- Topluluk görüşüne açık

---

## 9. SONUÇ

**Toplam risk profili:** Yönetilebilir. En kritik 3 risk için erken azaltma stratejileri var.

**En kötü senaryo:** Asimetri hipotezi yanlış, süperiletken tedarik edilemez, bütçe kesilir. → Proje durur, $5-10M harcanmış, **yeni bir bilimsel paradigma doğrulanmış veya yanlışlanmış olur**. Her iki durumda değerli.

**En iyi senaryo:** Tüm fazlar planlandığı gibi gider, 25 yılda Mars'ta 1000 kişilik üs. → İnsanlık için yüzlerce yıllık etki.

**Beklenen senaryo:** 30-35 yıl, $10-15B, kademeli başarılar. → 2055-2060'a kadar Ay'da, 2070-2080'e kadar Mars'ta kalkanlı üs.

**Sonuç: Bu riskler, insanlığın geleceği için kabul edilebilir seviyede.**
