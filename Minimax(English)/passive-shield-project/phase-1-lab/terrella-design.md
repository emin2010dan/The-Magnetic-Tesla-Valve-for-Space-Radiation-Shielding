# FAZ 1: LABORATUVAR DOĞRULAMASI

**Süre:** Yıl 1-3
**Bütçe:** $200-500K
**Çıktı:** Optimize edilmiş topoloji + 1-2 akademik makale

---

## Amaç

3 katmanlı Tesla valfi topolojili pasif kalkanın MHD simülasyonu ve terrella deneyi ile doğrulanması.

**Kritik sorular:**
1. Asimetrik topoloji gerçekten simetrik dipolden daha mı iyi sızıntı azaltıyor?
2. Optimum halka sayısı, asimetri açısı, akım oranları neler?
3. Reconnection, asimetri ile ne kadar bastırılabilir?

---

## Aşama 1.1: MHD Simülasyonu (3-6 ay)

**Araç:** BATS-R-US (NASA)
**Detay:** Bkz. `simulations/mhd_simulation_plan.md`

**Kilit çıktılar:**
- Baseline (T1) simülasyonu → simetri dipolü ile karşılaştırma
- Southward IMF (T5) → asimetri kazancı
- Parametre taraması (625 simülasyon)

**Kadro:** 1 doktora öğrencisi + 1 postdoc

---

## Aşama 1.2: Terrella Deneyi (6-18 ay)

### Deney Düzeneği

**Vakum odası:**
- Çap: 2 m
- Uzunluk: 3 m
- Basınç: 10⁻⁶ Torr (turbo + cryo pompa)
- Malzeme: paslanmaz çelik 304

**Plazma kaynağı:**
- Tip: Hollanda katot (hollow cathode)
- Akım: 1-10 A
- Gerilim: 50-200 V
- Plazma yoğunluğu: 10¹⁵-10¹⁷ m⁻³
- Enerji: 5-50 eV
- Çap: ~10 cm (odaklı demet)

**Test modelleri (3D basılı):**
- Simetrik dipol (baseline)
- Asimetrik 6 halka, 30° asimetri
- Asimetrik 12 halka, 60° asimetri
- Asimetrik 24 halka, 90° asimetri
- Ölçek: 1:200 (R_outer = 12.5 cm)
- Tel: bakır (süperiletken değil, sadece topoloji testi)

**Manyetik alan kaynağı:**
- Helmholtz bobinleri: B=0-50 mT (homojen bölge)
- Plazma hızı için: $v = E \times B$ drift

**Diagnostik:**
- Langmuir probu (yoğunluk, sıcaklık)
- Hall prob manyetometre (B alanı)
- Yüksek hızlı kamera (plazma davranışı, 1000+ fps)
- Enerji analizör (parçacık spektrumu)
- Optik emisyon spektroskopisi (OES)

### Deney Protokolü

**Adım 1: Karakterizasyon (1 hafta)**
- Plazma kaynağını kalibre et
- Boş vakumda manyetik alan haritası
- Langmuir probu kalibrasyonu

**Adım 2: Simetrik baseline (2 hafta)**
- Simetrik dipol modeli
- Farklı B alanlarında (0-30 mT)
- Plazma sızıntısı ölçümü

**Adım 3: Asimetrik topoloji taraması (8 hafta)**
- 5+ topoloji, 5+ B alanı = 25+ konfigürasyon
- Her konfigürasyonda 3+ tekrar
- Toplam: ~100 deney

**Adım 4: Reconnection testleri (4 hafta)**
- Yapay IMF yön değişimi
- Southward vs northward simülasyonu (rotasyonel simetri ile)

**Adım 5: Veri analizi ve yayın (8 hafta)**
- İstatistiksel analiz
- Asimetrik topoloji üstünlüğünün nicellenmesi
- Akademik makale yazımı

### Beklenen Sonuçlar

**Eğer asimetri hipotezi doğruysa:**
- Asimetrik 12 halka, simetrik dipolden **2-3× az sızıntı**
- Southward IMF koşulunda asimetrik avantaj **3-5×**

**Eğer asimetri hipotezi yanlışsa:**
- Düzlemsel halka sayısı önemsiz, sadece B şiddeti belirleyici
- 3-katmanlı mimari gereksiz, tek solenoid yeterli

**Her iki durum da değerli bilgi.** Yanlış sonuç, 10-15 yıllık programı erken bitirir.

### Bütçe (Faz 1.2)

- Vakum odası kurulumu: $50K
- Plazma kaynağı: $30K
- Helmholtz bobinleri: $20K
- Diagnostik: $50K
- 3D baskı malzeme: $5K
- Postdoc maaşı (18 ay): $90K
- Doktora öğrencisi (36 ay kısmi): $60K
- Sarf + seyahat: $50K
- **Toplam: ~$355K**

---

## Aşama 1.3: Geçiş Kriterleri → Faz 2

**Faz 2'ye geçmek için:**

✅ MHD simülasyonu tutarlı sonuçlar verdi
✅ Terrella deneyi sonuçları simülasyonu doğruladı
✅ Asimetrik topoloji avantajı nicellendi (en az 1.5×)
✅ Patent başvurusu için yeterli özgünlük
✅ Topoloji tasarımı finalize edildi

**Geçilmezse:**
- Terella sonuçları olumsuz → konsept değişikliği
- MHD-terella uyumsuzluğu → model düzeltme
- Bütçe aşımı → yeniden kapsam belirleme

---

## Kilometre Taşları

| Ay | Kilometre Taşı |
|----|----------------|
| 3 | BATS-R-US kurulumu, ilk baseline simülasyonu |
| 6 | Parametre taraması başlangıcı, terrella kurulumu |
| 12 | İlk terrella sonuçları, simülasyon karşılaştırması |
| 18 | Topoloji optimizasyonu tamamlandı |
| 24 | İlk akademik makale (conference) |
| 30 | İkinci makale (peer-reviewed) |
| 36 | Patent başvurusu, Faz 2 planlaması |

---

## Yayın Stratejisi

**Hedef dergiler:**
- Journal of Geophysical Research: Space Physics
- Acta Astronautica
- AIAA Journal of Spacecraft and Rockets
- Physics of Plasmas

**Hedef konferanslar:**
- AIAA SPACE Forum
- COSPAR (Committee on Space Research)
- AGU Fall Meeting
- IEEE Aerospace Conference

**Açık erişim:** Tüm yayınlar açık erişim (anti-monokültür ilkesi)
