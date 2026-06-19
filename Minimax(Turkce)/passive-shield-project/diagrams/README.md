# DİYAGRAMLAR

Bu dizin, projeyi görselleştiren diyagramları içerir. Şu an **metin açıklaması** mevcut; **görsel dosyalar** (PNG/SVG) sonraki aşamada üretilecek.

---

## D1: Sistem Mimarisi (3 Katman)

**Dosya:** `system-architecture.png` (üretilecek)

**Açıklama:**

```
                    ┌─────────────────────┐
                    │  KATMAN 3: DIŞ      │
                    │  R = 2500 m         │
                    │  5 ince halka       │
                    │  B_edge = 20 mT     │
                    │  Pasif, hafif       │
                    │  ~3 ton, 80 km tel  │
                    ├─────────────────────┤
                    │  KATMAN 2: ORTA     │
                    │  R = 1000 m         │
                    │  12 asimetrik halka │
                    │  60° döngüsel       │
                    │  ΔB ≈ 0.3 mT/halka  │
                    │  ~3 ton, 75 km tel  │
                    ├─────────────────────┤
                    │  KATMAN 1: İÇ       │
                    │  R = 100 m          │
                    │  L = 200 m          │
                    │  20,000 sarım       │
                    │  B = 0.5 T          │
                    │  ~490 ton, 12.5 km  │
                    └─────────────────────┘
                          ÜS YAPILARI
                       (100-1000 kişi)
```

---

## D2: Manyetik Alan Profili

**Dosya:** `magnetic-profile.png` (üretilecek)

**Açıklama:** Yarı logaritmik grafik, r'ye karşı |B(r)|

- İç solenoid: 0.5 T (merkez) → ~0.3 T (R=100m)
- Orta katman: 5-10 mT (R=1000m civarı)
- Dış perdeleme: 20 mT (R=2500m)
- Dışında: hızlı düşüş, ~5 mT (R=3000m)

---

## D3: Plazma Akışı (MHD Beklenen)

**Dosya:** `plasma-flow.png` (üretilecek)

**Açıklama:** XY düzleminde plazma akış çizgileri

- Sol taraftan (güneş yönü) rüzgâr gelir
- Katman 3'te (R=2500m) halkaya çarpar
- Bow shock oluşur (R=2700m)
- Plazma saptırılır, etrafından akar
- Magnetopause (R=2400m) iç bölgeyi korur
- Magnetotail (sağ taraf, R>5000m) geriye uzanır

---

## D4: AR-GE Yol Haritası (Zaman Çizelgesi)

**Dosya:** `phase-timeline.png` (üretilecek)

**Açıklama:** Yatay zaman ekseni, 4 faz gösterimi

```
Yıl:  0    3    5    7   10   15   20   25
      │    │    │    │    │    │    │    │
Faz1  ████████  MHD simülasyon + terrella
Faz2          ██████████████  Küp uydu
Faz3                       ████████████████  Yer prototipi
Faz4                                       ████████████  Uzay konuşlandırma
```

---

## D5: Tesla Valfi Topolojisi Detayı

**Dosya:** `tesla-topology.png` (üretilecek)

**Açıklama:** 12 halkanın asimetrik yerleşimi

```
       ┌─────────────────────┐
       │  1 halka (R=1000m)  │  düzlem: 0°
       └─────────────────────┘
       ┌─────────────────────┐
       │  2 halka (R=1000m)  │  düzlem: 30°
       └─────────────────────┘
       ... (60° döngüsel, 12 halkaya kadar)
       ┌─────────────────────┐
       │  12 halka (R=1000m) │  düzlem: 330°
       └─────────────────────┘
```

**Kritik gözlem:** Halkaların düzlemleri döngüsel, asimetrik yerleşim. Bu, plazma için "geçişi zor" geometri yaratır.

---

## D6: Enerji Akışı

**Dosya:** `energy-flow.png` (üretilecek)

**Açıklama:** Sankey diyagramı

- Güneş: 1.36 kW/m² (1 AU'da)
- Mars'ta: 590 W/m² (1.5 AU)
- 5 km çaplı alana gelen: 4.6 GW (güneş enerjisi)
- Bunun %99.5'i kalkan tarafından saptırılır
- İç bölgeye sızan: ~20 MW (ısı, sonra atıl)
- Üs yapılarına ulaşan: 0.5-1 mSv/gün (radyasyon, hedefin altında)

---

## D7: Quench Yönetimi Akış Şeması

**Dosya:** `quench-management.png` (üretilecek)

**Açıklama:** Quench detection → response akışı

```
Sıcaklık sensörü (1 ms örnekleme)
     │
     ▼
ΔT > 0.5 K?
     │
     ├─ Hayır → Normal işletim
     │
     └─ Evet → Quench alarm
              │
              ▼
         Dump resistor aktivasyonu (10 ms)
              │
              ▼
         Enerji ısıya dönüşür
              │
              ▼
         Komşu segmentler izole
              │
              ▼
         Yer istasyonuna alarm
              │
              ▼
         7 gün içinde onarım görevi
```

---

## NASIL ÜRETİLİR

Bu diyagramlar sonraki aşamada Python (matplotlib/plotly) veya SVG ile üretilebilir. visual-page skill kullanılarak interaktif HTML sayfası da yapılabilir.

**Önerilen ilk diyagram:** D1 (Sistem Mimarisi) — projeyi tek bakışta özetler.
