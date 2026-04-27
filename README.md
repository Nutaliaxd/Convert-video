# CONVERT.IO — Video & Ses Dönüştürücü

Tarayıcıda çalışan video & ses dönüştürücü. Tüm video formatlarını **MP4**'e, ses formatlarını **AAC**'ye dönüştürür. Dosyalar hiçbir sunucuya yüklenmez — tüm işlem tarayıcıda yapılır.

## Özellikler

- 🎬 Tüm video formatları → MP4 (H.264 + AAC)
- 🎵 Tüm ses formatları → AAC (128k bitrate)
- 🔒 Dosyalar yüklenmez — tarayıcıda işlenir
- ⚡ FFmpeg.wasm motoru
- 🎨 Modern, distinctive arayüz

## GitHub Pages'te Yayınlama

1. Bu repoyu kendi GitHub hesabında oluştur
2. Tüm dosyaları repoya yükle (`index.html`, `coi-serviceworker.js`, `.nojekyll`)
3. Repo ayarlarına git: **Settings → Pages**
4. **Source** kısmından `main` (veya `master`) branch'i seç ve **Save**
5. 1-2 dakika sonra siten `https://KULLANICI-ADIN.github.io/REPO-ADIN/` adresinde yayında olacak

## Neden `coi-serviceworker.js`?

FFmpeg.wasm tarayıcıda çalışmak için `SharedArrayBuffer` kullanır. Bu da `Cross-Origin-Opener-Policy` ve `Cross-Origin-Embedder-Policy` HTTP başlıklarını gerektirir. GitHub Pages bu başlıkları varsayılan olarak göndermez. `coi-serviceworker.js` bir service worker olarak bu başlıkları sayfa yüklendikten sonra ekler.

[coi-serviceworker (MIT lisansı)](https://github.com/gzuidhof/coi-serviceworker) tarafından sağlanır.

## Yerel Test

Çift tıklayarak çalışmaz çünkü service worker'lar `file://` protokolünde devre dışıdır. Yerel test için:

```bash
# Python 3
python -m http.server 8000

# veya Node.js
npx serve .
```

Sonra tarayıcıda `http://localhost:8000` aç.

## Tarayıcı Desteği

- ✅ Chrome / Edge (önerilen)
- ✅ Firefox
- ⚠️ Safari (kısmi destek)

## Lisans

MIT
