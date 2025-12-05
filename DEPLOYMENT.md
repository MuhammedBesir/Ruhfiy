# 🚀 Ruhfiy Deployment Rehberi

## Uygulamayı Canlıya Alma

### Seçenek 1: Vercel (Önerilen - Ücretsiz)

1. **GitHub'a yükle:**

```bash
cd /home/MuhammedBesir/Projeler/Ruhfy
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/KULLANICI_ADIN/ruhfy.git
git push -u origin main
```

2. **Vercel'e deploy:**

   - [vercel.com](https://vercel.com) adresine git
   - GitHub hesabınla giriş yap
   - "Import Project" → GitHub repo'nu seç
   - Otomatik olarak Vite projesi olarak algılayacak
   - "Deploy" butonuna tıkla
   - 1-2 dakika içinde canlıya alınır!

3. **Şifre Koruması (Vercel Pro - Opsiyonel):**
   - Vercel Dashboard → Project Settings → Security
   - "Password Protection" aktif et

### Seçenek 2: Netlify (Ücretsiz)

1. **Build al:**

```bash
npm run build
```

2. **Netlify'a deploy:**
   - [netlify.com](https://netlify.com) adresine git
   - "Add new site" → "Deploy manually"
   - `dist` klasörünü sürükle bırak
   - Otomatik URL alırsın!

### Seçenek 3: GitHub Pages (Ücretsiz)

1. **vite.config.js'yi güncelle:**

```js
export default defineConfig({
  plugins: [react()],
  base: "/ruhfy/", // repo adın
});
```

2. **gh-pages kur ve deploy et:**

```bash
npm install -D gh-pages
```

3. **package.json'a script ekle:**

```json
"scripts": {
  "deploy": "npm run build && gh-pages -d dist"
}
```

4. **Deploy et:**

```bash
npm run deploy
```

---

## 🔒 Gizlilik Ayarları

Uygulama zaten şifre korumalı!

**Mevcut Şifre:** `ruhfy2024`

### Şifreyi Değiştirmek İçin:

`src/App.jsx` dosyasında bu satırı bul ve değiştir:

```jsx
const SECRET_PASSWORD = "ruhfy2024";
```

### Ek Güvenlik İçin:

1. **Repo'yu private yap** - GitHub'da ayarlardan
2. **Vercel'de şifre koruması** - Pro plan ile
3. **Özel domain kullan** - Tahmin edilemez URL

---

## 📱 Mobil Uygulama Gibi Kullanma (PWA)

Tarayıcıdan "Ana ekrana ekle" seçeneği ile mobil uygulama gibi kullanabilirsin!

---

## 🔧 Yerel Geliştirme

```bash
# Bağımlılıkları kur
npm install

# Geliştirme sunucusu
npm run dev

# Prodüksiyon build
npm run build

# Build'i test et
npm run preview
```

---

## 📦 Dosya Yapısı

```
Ruhfy/
├── src/
│   ├── App.jsx      # Ana uygulama + şifre koruması
│   ├── main.jsx     # React entry point
│   └── index.css    # Tailwind styles
├── index.html
├── package.json
├── vite.config.js
├── tailwind.config.js
└── DEPLOYMENT.md    # Bu dosya
```
