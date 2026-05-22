# Tammat Akademi — Tek Sayfalık Website Planı

## Context
Tammat Akademi, LGS ve YKS sınavlarına hazırlık sunan butik bir özel ders kuruludur. Küçük sınıf yapısı (6–7 kişi), birebir özel ders ve sınav sonrası etüd hizmetleri sunmaktadır. Amaç: güven veren, profesyonel, dönüşüm odaklı tek sayfalık bir tanıtım sitesi.

---

## Brand Standartları

### Logo (`brand_assets/logo.svg`)
- Geometrik turkuaz prizma (diamond şekli) + turuncu aksan ve nokta
- "TAMMAT" yazısı: `#0D5C75`, Plus Jakarta Sans, ExtraBold (800), letter-spacing: 0.5
- "AKADEMİ" yazısı: `#FF7A00`, Plus Jakarta Sans, SemiBold (600), letter-spacing: 2
- SVG olduğu için her boyutta keskin kalır, `next/image` ile inline veya `<img>` ile kullanılabilir

### Renk Paleti (`brand_assets/colors.md`)
| Rol | İsim | HEX |
|---|---|---|
| Primary | Mat Turkuaz | `#0D5C75` |
| Accent / CTA | Dinamik Turuncu | `#FF7A00` |
| Background | Akademik Beyaz | `#F8FAFC` |
| Metin | Koyu Slate | `#1E293B` |

- **Turkuaz:** Header, navbar, section başlıkları, akademik ders etiketleri
- **Turuncu:** Tüm CTA butonları ("Kayıt Ol", "Ücretsiz Deneme Sınavı"), vurgu elementleri
- **Beyaz bg:** Sayfa zeminleri, kart arkaplanları
- **Koyu Slate:** Paragraflar, açıklamalar, footer metinleri

### Tipografi (`brand_assets/style-guide.md`)
- **H1, H2:** Plus Jakarta Sans — Bold/ExtraBold (700–800)
- **H3, kart başlıkları:** Plus Jakarta Sans — SemiBold (600)
- **Gövde, açıklamalar:** Inter — Regular (400)
- Büyük başlıklarda `letter-spacing: -0.03em`, gövdede `line-height: 1.7`

---

## Tech Stack
- **Next.js 14** (App Router) — `src/app/` yapısı
- **Tailwind CSS** — `tailwind.config.ts` ile özel brand renkleri (aşağıda)
- **Google Fonts** — Plus Jakarta Sans + Inter (`next/font` ile)
- **Static site** — veritabanı yok, form için `mailto:` yeterli
- **Brand assets** — `brand_assets/` klasöründen direkt kullanım

### Tailwind Brand Config
```ts
// tailwind.config.ts
colors: {
  tammat: {
    turkuaz: '#0D5C75',
    orange:  '#FF7A00',
    bg:      '#F8FAFC',
    dark:    '#1E293B',
  }
}
fontFamily: {
  display: ['Plus Jakarta Sans', 'sans-serif'],
  body:    ['Inter', 'sans-serif'],
}
```

---

## Sayfa Bölümleri (Sırasıyla)

### 1. Navbar (Sticky)
- Sol: `logo.svg`
- Sağ: Anchor linkler — Programlar · Dersler · Nasıl Çalışır · İletişim
- Sağ köşe: Turuncu `#FF7A00` "Kayıt Ol" CTA butonu
- Mobilde: hamburger menü

### 2. Hero
- Büyük başlık: LGS & YKS odaklı güçlü slogan (Plus Jakarta Sans, ExtraBold)
- Alt başlık: butik yaklaşım vurgusu
- İki CTA: "Kayıt Ol" (turuncu dolu) + "Ücretsiz Deneme Sınavı" (outline, turkuaz border)
- Arka plan: `#0D5C75` bazlı radial gradient + SVG grain dokusu

### 3. Neden Tammat? (3 kart)
- Kart 1: Butik Sınıf — "6-7 kişilik sınıflarda kaybolmazsın"
- Kart 2: Birebir İlgi — "Özel ders ile tam odak"
- Kart 3: Sınav Sonrası Etüd — "Sınav bitmez, hazırlık sürer"
- Her kart: SVG ikon + başlık (Plus Jakarta Sans) + açıklama (Inter)

### 4. Programlarımız (3 kart)
- **Butik Sınıf (6–7 Kişi):** LGS & YKS grupları
- **Birebir Özel Ders:** Kişiye özel program
- **Sınav Sonrası Etüd:** Çözüm, pekiştirme, takip
- Her kart: turuncu "Kayıt Ol" butonu

### 5. Dersler
- **LGS:** Matematik, Fen Bilimleri, Türkçe, Sosyal Bilgiler, İngilizce
- **YKS (TYT/AYT):** Matematik, Fizik, Kimya, Biyoloji, Edebiyat, Tarih
- Tab veya iki sütunlu grid görünüm, ders etiketleri turkuaz

### 6. Nasıl Başlarsın? (3 adım)
1. Bize Ulaş
2. Ücretsiz Seviye Testi
3. Kişisel Programa Başla
- Yatay timeline, adım numaraları turkuaz/turuncu

### 7. İletişim / Kayıt Formu
- Alanlar: Ad Soyad, Telefon, Hedef Sınav (LGS / YKS), Mesaj
- Form aksiyonu: `mailto:` (backend yok)
- Yan yana: telefon, adres, sosyal medya linkleri

### 8. Footer
- Sol: `logo.svg` + kısa slogan
- Orta: hızlı linkler
- Sağ: iletişim
- Alt: telif hakkı, `#1E293B` arka plan

---

## Proje Dosya Yapısı

```
Tammat2/
├── brand_assets/
│   ├── logo.svg
│   ├── colors.md
│   └── style-guide.md
├── src/
│   └── app/
│       ├── layout.tsx        ← fontlar, meta
│       ├── page.tsx          ← section'ları sıralar
│       ├── globals.css
│       └── components/
│           ├── Navbar.tsx
│           ├── Hero.tsx
│           ├── WhyUs.tsx
│           ├── Programs.tsx
│           ├── Courses.tsx
│           ├── HowItWorks.tsx
│           ├── Contact.tsx
│           └── Footer.tsx
├── tailwind.config.ts
├── package.json
├── next.config.ts
└── PLAN.md
```

---

## Doğrulama

1. `npm run dev` → `http://localhost:3000` aç
2. `node screenshot.mjs http://localhost:3000` ile görsel kontrol
3. Mobil görünüm (375px) test
4. Her CTA butonunda hover/focus/active state kontrolü
5. Anchor linklerin smooth scroll çalışması
6. Logo SVG'nin tüm boyutlarda net görünmesi
