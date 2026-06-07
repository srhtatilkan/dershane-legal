# Dershane Yönetim Sistemi - Yasal Dokümanlar

Bu klasör, Dershane Yönetim Sistemi uygulamasının gizlilik politikası ve kullanım şartlarını içermektedir.

## 📋 İçerik

- **index.html** - Ana sayfa (landing page)
- **privacy-policy.html** - Gizlilik Politikası (KVKK & GDPR uyumlu)
- **terms-of-service.html** - Kullanım Şartları

## 🚀 GitHub Pages'e Yükleme

### Adım 1: GitHub Repository Oluştur

```bash
# GitHub'da yeni bir repository oluşturun (örnek: dershane-legal)
# Ardından bu klasörü push edin:

cd docs
git init
git add .
git commit -m "Add legal documents"
git branch -M main
git remote add origin https://github.com/KULLANICI_ADI/dershane-legal.git
git push -u origin main
```

### Adım 2: GitHub Pages'i Aktifleştir

1. GitHub repository'nize gidin
2. **Settings** > **Pages** tıklayın
3. **Source**: `Deploy from a branch` seçin
4. **Branch**: `main` / `(root)` seçin
5. **Save** butonuna tıklayın

### Adım 3: URL'yi Alın

5 dakika içinde siteniz şu adreste yayında olacak:
```
https://KULLANICI_ADI.github.io/dershane-legal/
```

## 🔗 Uygulama İçine Ekleme

Flutter uygulamanıza şu şekilde ekleyin:

### 1. url_launcher paketi ekleyin (zaten var)

```yaml
# pubspec.yaml
dependencies:
  url_launcher: ^6.3.1
```

### 2. ProfileScreen'e link ekleyin

```dart
// lib/features/shared/screens/profile_screen.dart

import 'package:url_launcher/url_launcher.dart';

// Profil ekranına eklenecek:
ListTile(
  leading: Icon(Icons.privacy_tip_outlined),
  title: Text('Gizlilik Politikası'),
  trailing: Icon(Icons.arrow_forward_ios, size: 16),
  onTap: () => launchUrl(
    Uri.parse('https://KULLANICI_ADI.github.io/dershane-legal/privacy-policy.html'),
    mode: LaunchMode.externalApplication,
  ),
),
ListTile(
  leading: Icon(Icons.description_outlined),
  title: Text('Kullanım Şartları'),
  trailing: Icon(Icons.arrow_forward_ios, size: 16),
  onTap: () => launchUrl(
    Uri.parse('https://KULLANICI_ADI.github.io/dershane-legal/terms-of-service.html'),
    mode: LaunchMode.externalApplication,
  ),
),
```

### 3. Google Play Console'a Ekleyin

**Store Listing > Privacy Policy** kısmına:
```
https://KULLANICI_ADI.github.io/dershane-legal/privacy-policy.html
```

## ✏️ Özelleştirme

### İletişim E-posta Adresleri

Dosyalarda şu e-posta adresleri kullanılmıştır. Kendi adresinizle değiştirin:

- `privacy@dershaneapp.com` → Gizlilik sorguları için
- `support@dershaneapp.com` → Genel destek için

**Değiştirme:**
```bash
# Tüm dosyalarda değiştir:
sed -i 's/privacy@dershaneapp.com/SIZIN_EMAIL@domain.com/g' *.html
sed -i 's/support@dershaneapp.com/SIZIN_EMAIL@domain.com/g' *.html
```

### Logo ve Renkler

`privacy-policy.html` ve `terms-of-service.html` dosyalarındaki CSS'te:

```css
/* Ana renk */
#6C63FF → Kendi markanızın rengi

/* Vurgu renkleri */
#FFB347 → Turuncu vurgu
#FF6B6B → Kırmızı uyarı
```

## 📱 Alternatif Hosting Seçenekleri

GitHub Pages dışında kullanabileceğiniz ücretsiz hosting:

1. **Vercel** - https://vercel.com
2. **Netlify** - https://netlify.com
3. **Firebase Hosting** - https://firebase.google.com/docs/hosting
4. **Cloudflare Pages** - https://pages.cloudflare.com

## ⚖️ Yasal Uyumluluk

### KVKK Uyumu
- ✅ Hangi verilerin toplandığı açıklanmış
- ✅ Veri işleme amaçları belirtilmiş
- ✅ Veri saklama süresi açıklanmış
- ✅ Kullanıcı hakları listelenmiş
- ✅ Veri sorumlusu bilgisi verilmiş
- ✅ İletişim kanalları açıklanmış

### GDPR Uyumu
- ✅ Data minimization prensibi uygulanmış
- ✅ Purpose limitation belirtilmiş
- ✅ Right to erasure (unutulma hakkı) açıklanmış
- ✅ Data portability hakkı belirtilmiş
- ✅ Consent (rıza) mekanizması açıklanmış

### Google Play Politikaları
- ✅ Privacy policy URL mevcut
- ✅ Account deletion açıklanmış
- ✅ Data collection şeffaf
- ✅ Third-party services listelenmiş
- ✅ Children's privacy açıklanmış

## 📞 Destek

Sorularınız için:
- 📧 E-posta: support@dershaneapp.com
- 🐛 Issue: GitHub Issues
- 📱 Uygulama: Profil > Yardım

---

**Son Güncelleme:** 7 Haziran 2026  
**Versiyon:** 1.0.0  
**Lisans:** Tüm hakları saklıdır
