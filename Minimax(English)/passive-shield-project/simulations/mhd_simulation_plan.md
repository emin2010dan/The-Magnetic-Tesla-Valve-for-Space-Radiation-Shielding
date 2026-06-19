# MHD SİMÜLASYON PLANI

## Amaç

3 katmanlı Tesla valfi topolojili pasif manyetik kalkanın, gerçekçi Mars/Ay koşullarında plazma etkileşimini sayısal olarak modellemek. Simülasyon çıktıları:
1. Plazma sızıntı oranı (her koşul için)
2. Magnetopause / bow shock geometrisi
3. Reconnection sızıntısı
4. Asimetrik topolojinin amplifikasyon etkisi
5. Tasarım parametrelerinin optimizasyonu

---

## 1. Araç Seçimi

### Birincil: BATS-R-US (NASA / University of Michigan)

**Neden:**
- Uzay fiziğinde standart (MESSENGER, MAVEN, MMS misyonlarında kullanılmış)
- Çok-ölçekli MHD, paralel hesaplama
- Mars, Merkür, Titan modelleri açık kaynak
- SWMF (Space Weather Modeling Framework) parçası

**Kurulum:**
```bash
git clone https://github.com/MSTEM-UTSA/SWMF.git
cd SWMF
make
```

**Kaynaklar:**
- GitHub: https://github.com/MSTEM-UTSA
- Docs: https://csem.engin.umich.edu/research/swmf

### İkincil: OpenMHD (eğitim ve hızlı iterasyon)

**Neden:**
- Açık kaynak, küçük kod tabanı
- Hızlı prototipleme
- Eğitim amaçlı örnekler

**Kurulum:**
```bash
git clone https://github.com/PrincetonUniversity/OpenMHD.git
```

### Üçüncül: Athena++ (yüksek performans gerektiğinde)

- Modern, GR+MHD
- MPI + OpenMP + GPU
- Performans için

---

## 2. Simülasyon Alanı ve Sınır Koşulları

### 2.1 Koordinat Sistemi

**Heliocentric Inertial (HCI):** Güneş-merkezli, Mars yörüngesine yerleştirilmiş.

**Mars-centric:** Mars-merkezli, güneş yönünde +X, kuzey +Z (güneş ekvatoru düzlemi).

### 2.2 Grid Yapısı

**Bölge 1 (yakın alan, 0-10 R_habitat):**
- Yüksek çözünürlük: 1000×1000×1000
- R_habitat = 2500 m, yani 0-25 km
- Adaptif: reconnection bölgelerinde daha yoğun

**Bölge 2 (uzak alan, 10-100 R_habitat):**
- Düşük çözünürlük: 200×200×200
- 25-250 km
- Dış sınır koşulları için yeterli

### 2.3 Sınır Koşulları

**Giren sınır (+X yüzü, güneş yönü):**
- $n_p$ = verilen koşul
- $v_{sw}$ = verilen koşul
- $B_{IMF}$ = verilen yön ve şiddet
- $T_p$ = 1e5 K (tipik)

**Diğer yüzeyler:**
- Serbest çıkış (zero gradient)

---

## 3. Girdi Parametre Seti

### 3.1 Sabit Sistem Parametreleri

```python
SYSTEM = {
    "R_habitat": 2500,           # m, dış perdeleme yarıçapı
    "R_mid": 1000,               # m, orta katman
    "R_inner": 100,              # m, iç çekirdek
    "B_edge_target": 20e-3,      # T, dış kenar alanı
    "B_mid_segment": 0.3e-3,     # T, orta katman her halkanın katkısı
    "B_inner": 0.5,              # T, iç çekirdek
    "N_mid_segments": 12,        # orta halka sayısı
    "N_outer_turns": 5,          # dış sarım sayısı
    "asymmetry_angle_deg": 60,   # halkalar arası asimetri açısı
}
```

### 3.2 Değişken Koşullar (Test Matrisi)

| Test | İsim | n_p (m⁻³) | v_sw (m/s) | B_IMF (T) | IMF yönü |
|------|------|-----------|-----------|-----------|----------|
| T1 | Tipik (baseline) | 3e6 | 4e5 | 2e-9 | Kuzey (0°) |
| T2 | Ortalama | 8e6 | 5e5 | 5e-9 | Kuzey |
| T3 | Yüksek basınç (SIR) | 2e7 | 6e5 | 1e-8 | Değişken |
| T4 | ICME (ekstrem) | 3e7 | 7e5 | 2e-8 | Kuzey |
| T5 | Southward IMF (reconnection) | 8e6 | 5e5 | 5e-9 | Güney (180°) |
| T6 | Carrington-class | 1e8 | 1e6 | 1e-7 | Değişken |
| T7 | Radyal IMF | 5e6 | 5e5 | 5e-9 | Radyal (90°) |
| T8 | Disk üstü geçiş | 1e7 | 6e5 | 1e-8 | 0° → 180° (süreç) |

### 3.3 Parametre Taraması (Topoloji Optimizasyonu)

```python
TOPOLOGY_SCAN = {
    "asymmetry_angle": [30, 45, 60, 90, 120],
    "N_mid_segments": [6, 12, 18, 24, 36],
    "B_edge": [10e-3, 15e-3, 20e-3, 30e-3, 50e-3],
    "B_inner": [0.1, 0.3, 0.5, 1.0, 2.0],
}
```

Toplam: 5 × 5 × 5 × 5 = 625 simülasyon. Her biri ~1 saat. Toplam: ~26 gün, paralel koşturulursa ~3-4 gün.

---

## 4. Çıktı Metrikleri

Her simülasyon için kaydedilecek:

### 4.1 Skaler Metrikler

```python
OUTPUTS = {
    "plasma_leakage_pct": None,         # iç bölgeye ulaşan plazma yüzdesi
    "B_inside_avg_T": None,             # iç bölge ortalama B
    "B_inside_max_T": None,             # iç bölge maksimum B
    "magnetopause_radius_m": None,      # manyetopoz yarıçapı
    "bow_shock_stand_off_m": None,      # bow şok mesafesi
    "reconnection_rate": None,          # yeniden bağlanma oranı
    "magnetic_flux_Wb": None,           # toplam manyetik akı
    "energy_deposited_inside_J": None,  # iç bölgeye giren enerji
}
```

### 4.2 Vektör/Alan Çıktıları

- 2D dilimlerde (XY, XZ düzlemleri) manyetik alan haritası
- Plazma yoğunluğu haritası
- Akış vektörleri (streamlines)
- Akım yoğunluğu (J)

### 4.3 Zaman Serisi (süreç testleri)

T8 gibi geçiş olaylarında, 0-60 dakika arasında 1 saniyelik çıktı.

---

## 5. Kritik Test Senaryoları

### 5.1 Senaryo A: Baseline (Tipik Koşullar)

**Girdi:** T1
**Beklenen:**
- Magnetopause R ~3000 m (R_habitat'ın biraz üstü)
- Bow shock ~3500 m
- Plazma sızıntısı: < %5
- Reconnection: minimal (northward IMF)
- İç bölgede B: 0.5-0.7 T

**Başarı kriteri:** Tüm iç bölge doz hedefini karşılar.

### 5.2 Senaryo B: Southward IMF (En Zor Reconnection)

**Girdi:** T5 (southward IMF, 8e6, 5e5, 5nT, 180°)
**Beklenen:**
- Magnetopause sıkışır ~2500 m
- Reconnection aktif
- Plazma sızıntısı: %10-20
- **Bu, asimetrik topolojinin değerini gösterir**

**Başarı kriteri:** Simetrik dipolle karşılaştırıldığında sızıntı 2-3× az olmalı.

### 5.3 Senaryo C: Ekstrem (ICME)

**Girdi:** T4 (3e7, 7e5, 20 nT, kuzey)
**Beklenen:**
- Manyetik alan sıkışır
- Kalkan hâlâ çalışır, sızıntı %10-30

**Başarı kriteri:** Akut SPE dozu < 5 mSv/saat.

### 5.4 Senaryo D: Carrington Sınıfı (Tarihsel En Kötü)

**Girdi:** T6 (1e8, 1e6, 100 nT)
**Beklenen:**
- Kalkan aşırı yüklenir
- Kısmi sızıntı %50+
- Yapısal risk (Lorentz kuvvetleri)

**Başarı kriteri:** Sistem fiziksel olarak sağ kalır (yıkılmaz), sızıntı tolere edilebilir.

### 5.5 Senaryo E: IMF Geçişi (Zaman Serisi)

**Girdi:** T8 (northward → southward geçiş, 30 dakika)
**Beklenen:**
- Magnetopause yavaşça sıkışır
- Reconnection aktive olur
- Pasif cevap (Lenz) sınırlı katkı sağlar
- Geçiş sonrası yavaşça toparlanır

**Başarı kriteri:** Geçiş sırasında doz artışı < 50 mSv/saat.

---

## 6. Simülasyon İş Akışı

### 6.1 Faz 1: Kurulum ve Baseline (Ay 1-3)

1. BATS-R-US kurulumu
2. Mars modeli konfigürasyonu
3. Sistemi "engelleyici" olarak ekleme
4. İlk baseline simülasyonu (T1)
5. Sonuçların görselleştirilmesi (Paraview/VisIt)

### 6.2 Faz 2: Baseline Doğrulama (Ay 3-6)

1. T1-T8 tüm testleri çalıştır
2. Simetrik dipol ile karşılaştırma
3. Asimetrik topoloji üstünlüğünü nicelleştir

### 6.3 Faz 3: Parametre Optimizasyonu (Ay 6-9)

1. Topoloji taraması (625 simülasyon)
2. Pareto front: B_edge vs kütle vs sızıntı
3. Optimum noktanın seçimi

### 6.4 Faz 4: Hassas Doğrulama (Ay 9-12)

1. Optimize edilmiş tasarımın T1-T8'de yeniden testi
2. Kenar durumlar (köşe vakaları)
3. Uzun süreli kararlılık (>1000 simüle saniye)

---

## 7. Veri Yönetimi

### 7.1 Çıktı Formatı

**Vtk / HDF5:** Vektör alanları, 3D yapılar
**CSV:** Skaler metrikler, zaman serisi
**JSON:** Konfigürasyon, meta veri
**Markdown:** Otomatik rapor oluşturma

### 7.2 Depolama

```bash
passive-shield-project/
├── simulations/
│   ├── raw/                # ham vtk/HDF5
│   │   ├── T1_baseline/
│   │   ├── T5_southward/
│   │   └── ...
│   ├── processed/          # CSV metrikler
│   ├── figures/            # PNG/SVG grafikler
│   └── reports/            # Markdown otomatik raporlar
```

### 7.3 Versiyon Kontrolü

- Her simülasyon `git commit`'lenir (kod, config, çıktı)
- Parametre değişikliği izlenebilir
- Sonuçlar tekrarlanabilir (reproducible)

---

## 8. Açık Sorular / Sınırlamalar

### 8.1 MHD Sınırlamaları

MHD, kinetik ölçekleri (iyon jiroradyüsü ~100 km bizim sistemde) çözemez. Reconnection fiziği kinetik, Hall MHD veya full-PIC gerektirir. Çözüm:

- MHD sonuçları ilk tahmin için
- Kritik reconnection bölgeleri için **PIC (Particle-in-Cell)** alt simülasyonları
- Hibrit yaklaşım: MHD global + PIC yerel

### 8.2 Plazma Kinetik Etkileri

- İyon jiroradyüsü ~100 km (1 AU'da) → 5 km sistemde önemli
- Elektron jiroradyüsü çok küçük, ihmal edilebilir
- Sonuç: sızıntı tahminleri MHD'den %20-30 yüksek olabilir (kötümser tarafa)

### 8.3 Malzeme Etkileri

Süperiletken telde:
- AC kayıplar (yüksek frekanslı IMF değişimleri)
- Quench dynamics (süperiletkenlik kaybı)
- Yapısal rezonans

Bunlar simülasyona eklenmeli (sonraki faz).

---

## 9. Zaman Çizelgesi ve Kaynak

**Toplam süre:** 9-12 ay (Faz 1-4)
**Gerekli:**
- 1 doktora sonrası araştırmacı (tam zamanlı)
- 1 yüksek lisans öğrencisi
- Hesaplama: 100-200 CPU-çekirdek, 6 ay
- GPU opsiyonel (Athena++ ile hızlanma 5-10×)

**Maliyet:** $300-500K (araştırmacı + hesaplama + ekipman)

---

## 10. Beklenen Çıktılar

1. **Akademik yayın (1-2 makale):**
   - "Tesla Valve Topology for Passive Magnetospheric Shielding"
   - "MHD Validation of Asymmetric Superconducting Loops for Habitat Protection"

2. **Tasarım dokümanı (v1.0):**
   - Optimize edilmiş topoloji
   - Mühendislik spesifikasyonlar
   - Performans garantileri

3. **Patent başvurusu (opsiyonel):**
   - Asimetrik halka topolojisi
   - 3-katmanlı pasif kalkan mimarisi

4. **Açık kaynak katkı:**
   - GitHub'da simülasyon kodları
   - Parametre setleri
   - Topoloji tasarım aracı (GUI)
