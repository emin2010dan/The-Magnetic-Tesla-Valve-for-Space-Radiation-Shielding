# PASİF ASİMETRİK MANYETİK KALKAN PROJESİ

**5 km Çaplı Ay/Mars Üssü İçin Tesla Valfi Topolojili Süperiletken Kalkan**

---

## Projenin Özeti

Bu proje, **Ay ve Mars'ta kalıcı insan yerleşimi** için en büyük fiziksel engel olan güneş radyasyonuna karşı **tamamen pasif, sıfır-elektronik, enerji-tehdit orantılı** bir manyetik kalkan konsepti geliştirir.

**Temel felsefe:** Tesla'nın 1920 valfinin manyetik karşılığı. Aktif kontrol bileşeni yok; tüm koruma asimetrik süperiletken topoloji + Lenz yasası pasif indüksiyonu + plazmanın kendi enerjisinin dönüşümü üzerine kurulu.

**5 İlke (TASO):**
1. Pasif Asimetrik Topoloji (geometri > kontrol)
2. Tehdit → Enerji Dönüşümü
3. Diamanyetik Cevap (alana karşı koy)
4. Çok-Kademeli Konsolidasyon
5. Anti-Monokültür

---

## Dizin Yapısı

```
passive-shield-project/
├── README.md                          # Bu dosya
├── docs/
│   ├── 01-fizibilite-raporu.md        # Ana fizibilite raporu
│   ├── 02-topoloji-tasarimi.md        # (üretilecek) Topoloji detayları
│   ├── 03-malzeme-secimi.md           # (üretilecek) YBCO ve diğer
│   └── 04-risk-analizi.md             # (üretilecek) Detaylı riskler
│
├── calculations/
│   └── shield_calculations.py         # Tüm mühendislik hesapları (Python)
│
├── simulations/
│   └── mhd_simulation_plan.md         # MHD simülasyon planı
│   └── (BATS-R-US kodları eklenecek)
│
├── phase-1-lab/                        # Faz 1: Lab doğrulaması
│   ├── terrella-design.md             # Terrella deney tasarımı
│   └── expected-results.md
│
├── phase-2-cubesat/                    # Faz 2: Küp uydu demo
│   ├── cubesat-specs.md
│   └── mission-concept.md
│
├── phase-3-prototype/                  # Faz 3: Yer prototipi
│   ├── prototype-design.md
│   └── timeline.md
│
├── phase-4-deployment/                 # Faz 4: Uzay konuşlandırma
│   ├── launch-manifest.md
│   └── assembly-sequence.md
│
├── diagrams/                           # Diyagramlar (üretilecek)
│   ├── system-architecture.png
│   ├── phase-timeline.png
│   └── magnetic-topology.png
│
└── references.bib                      # Tüm referanslar
```

---

## Temel Sayılar (Hızlı Referans)

| Parametre | Değer |
|-----------|-------|
| Hedef çap | 5 km (R=2500 m) |
| Toplam tel uzunluğu | 12.720 km |
| Toplam sistem kütlesi | ~2000 ton |
| Sürekli güç tüketimi | 5-10 kW |
| İlk şarj enerjisi | ~700 kWh |
| Manyetik akı (tipik) | 1-3 Wb |
| Manyetik enerji | ~2518 GJ |
| 25 yıllık akı kaybı | %12 |
| Recharge sıklığı | 5-10 yılda bir |

---

## Neden Bu Proje?

İnsanlığın uzayda kalıcı varlığı, 50 yıldır bilim kurgu olarak anlatılıyor. Gerçekleşmesini engelleyen **tek büyük fiziksel bariyer** radyasyondur:

- **Alüminyum zırh** (ISS yaklaşımı): 5 km çaplı üs için **milyonlarca ton** — pratik değil
- **Yeraltı inşaatı**: 5 km çapta **mümkün değil**
- **Aktif manyetik kalkan**: 1 MW sürekli güç — Mars'ta nereden?
- **Gezegen ölçekli manyetik alan** (Zubrin önerisi): Şu an teknolojik olarak **5-10× büyük**

**Bu proje, aradaki boşluğu doldurur:** Üs ölçeğinde, **mevcut teknolojiyle yapılabilir**, **enerji verimli**, **25 yıl ömürlü** bir çözüm.

---

## Kullanıcı Profili ve Köken

Bu proje, 12 paralel yapay zekâ ile geliştirilen **Psikotarih v7.0** ve daha önceki **AI Council** deneyleri ile aynı felsefi temele dayanır. Daha fazlası için:

- **AI Council:** https://medium.com/@emin2010dan/the-ai-council-how-i-accidentally-discovered-a-better-path-to-artificial-general-intelligence-1af4c1f9c5da
- **Psikotarih:** https://github.com/emin2010dan/Psychohistory-in-the-Age-of-AI
- **Kullanıcının tüm çalışmaları:** https://medium.com/@emin2010dan

---

## Nasıl Katkıda Bulunulur

1. **Issue aç:** Simülasyon, hesap, tasarım konularında
2. **PR gönder:** Kod iyileştirmesi, dokümantasyon
3. **Council yöntemiyle:** Tartışmalı kararlar AI Council ile
4. **Akademik işbirliği:** MHD simülasyon, deney tasarımı

---

## Lisans

MIT Lisansı (serbestçe kullanılabilir, atıf beklenir)

---

## İletişim

GitHub Issues üzerinden.

---

**Son güncelleme:** 2026-06-02
**Versiyon:** 0.1 (ön-fizibilite)
**Durum:** Hesaplamalar tamamlandı, simülasyon ve lab doğrulaması bekliyor
