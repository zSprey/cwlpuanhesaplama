# CWL Klan Ligi — Vercel Deploy Rehberi

## 🚀 Vercel'e Deploy Adımları

### 1. Firebase Config'i Doldurun
`index.html` dosyasını açın, ~20. satırdaki `firebaseConfig` bölümünü Firebase Console'dan aldığınız değerlerle doldurun:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "cwlhesap-8520a.firebaseapp.com",
  databaseURL: "https://cwlhesap-8520a-default-rtdb.firebaseio.com",
  projectId: "cwlhesap-8520a",
  storageBucket: "cwlhesap-8520a.appspot.com",
  messagingSenderId: "878503636592",
  appId: "..."
};
```

### 2. GitHub'a Yükleyin
```bash
git init
git add .
git commit -m "CWL Klan Ligi ilk sürüm"
git remote add origin https://github.com/KULLANICI/cwl-klan-ligi.git
git push -u origin main
```

### 3. Vercel'e Bağlayın
1. [vercel.com](https://vercel.com) → **"Add New Project"**
2. GitHub reponuzu seçin
3. **Deploy** butonuna tıklayın
4. ✅ Bitti! Vercel size otomatik URL verir (örn: `cwl-klan-ligi.vercel.app`)

### 4. Firebase Güvenlik Kuralları (Önemli!)
Firebase Console → Realtime Database → **Rules** sekmesine gidin:

```json
{
  "rules": {
    "cwl_v2": {
      ".read": true,
      ".write": true
    }
  }
}
```

> ⚠️ Üretim için daha sıkı kurallar ekleyin (auth ile).

---

## 📁 Dosya Yapısı
```
cwl-vercel/
├── index.html       ← Ana uygulama
├── vercel.json      ← Vercel yapılandırması
├── .env.example     ← Örnek env değişkenleri
└── README.md        ← Bu dosya
```

## 🔄 Güncellemeler
Her `git push` sonrası Vercel otomatik olarak yeniden deploy eder.
