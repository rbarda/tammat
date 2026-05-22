# Tammat Akademi - Web Stil Kılavuzu (Style Guide)

Bu kılavuz, Tammat Akademi web sitesinin arayüz kodlamasında görsel bütünlüğü korumak amacıyla oluşturulmuştur.

## 1. Tipografi Standartları
Akademik ciddiyet ile modern dijital eğitimi harmanlamak için şu font yapılandırması kullanılmalıdır:
- **Ana Başlıklar (H1, H2):** font-family: 'Plus Jakarta Sans', sans-serif | Kalınlık: Bold (700) veya ExtraBold (800)
- **Alt Başlıklar ve Kart Başlıkları:** font-family: 'Plus Jakarta Sans', sans-serif | Kalınlık: SemiBold (600)
- **Gövde Metinleri ve Kurs Açıklamaları:** font-family: 'Inter', sans-serif | Kalınlık: Regular (400)

## 2. Tailwind CSS Yapılandırma Kodu
Claude ile kod yazarken `tailwind.config.js` dosyasını şu şekilde genişletmesini söyleyin:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        tammat: {
          turkuaz: '#0D5C75',
          orange: '#FF7A00',
          bgLight: '#F8FAFC',
          textDark: '#1E293B'
        }
      },
      fontFamily: {
        sans: ['Inter', 'Plus Jakarta Sans', 'sans-serif'],
      }
    },
  },
}