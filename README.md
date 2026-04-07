# FigmaScan — Design vs. Live Checker

> Figma tasarımlarını canlı web sayfalarıyla karşılaştıran Chrome eklentisi.

---

## Ne Yapar?

FigmaScan, tasarım ve geliştirme sürecindeki en sık karşılaşılan soruyu yanıtlar:

**"Tasarımdaki ile canlıdaki aynı mı?"**

Figma frame'inden tüm design token'ları (renkler, tipografi, boşluklar, boyutlar) otomatik olarak çeker. Ardından açık olan web sayfasının DOM'unu tarar ve Gemini AI yardımıyla iki tarafı eşleştirip tutarsızlıkları listeler.

---

## Özellikler

- **Figma entegrasyonu** — Figma linkini yapıştır, token'lar otomatik çekilir
- **AI destekli eşleştirme** — Gemini AI, Figma elementlerini DOM elementleriyle eşleştirir
- **Kategori bazlı filtreleme** — Colors, Typography, Sizing, Padding, Borders, UX Copy
- **Canlı highlight** — Sonuçlarda bir karta tıklayınca ilgili element sayfada işaretlenir
- **Spreadsheet export** — Bulgular Google Sheets'e aktarılabilir
- **Yerel depolama** — API key'ler yalnızca tarayıcında saklanır, hiçbir sunucuya gönderilmez

---

## Kurulum

1. Bu repoyu ZIP olarak indir → **Code → Download ZIP**
2. ZIP'i aç
3. Chrome'da `chrome://extensions` adresine git
4. Sağ üstten **Developer mode**'u aç
5. **Load unpacked** butonuna bas ve klasörü seç

---

## Kullanım

### 1. API Key'leri Ayarla
Eklentiyi açtıktan sonra **Ayarlar** sekmesine git:

- **Figma Access Token** — [Figma → Settings → Personal access tokens](https://www.figma.com/settings) adresinden oluştur. `file_content:read` ve `file_metadata:read` scope'larını seç.
- **Gemini API Key** — [aistudio.google.com/apikey](https://aistudio.google.com/apikey) adresinden ücretsiz alabilirsin.

### 2. Karşılaştır
1. Figma'da karşılaştırmak istediğin frame'i seç
2. Sağ tık → **Copy link**
3. Karşılaştırmak istediğin canlı sayfayı Chrome'da aç
4. Eklentiyi aç, linki yapıştır ve **Karşılaştır**'a bas

### 3. Sonuçları İncele
- **Sonuçlar** sekmesinde tüm tutarsızlıklar listelenir
- Kategori filtrelerini kullanarak odaklanmak istediğin alana geç
- Bir karta tıkla, ilgili element sayfada otomatik olarak işaretlenir
- **Spreadsheet'te Aç** ile bulguları Google Sheets'e aktar

---

## Teknolojiler

- **Manifest V3** Chrome Extension
- **Figma REST API** — Design token çekme
- **Google Gemini AI** — Figma ↔ DOM eşleştirme
- **getComputedStyle** — Canlı CSS değerleri okuma

---

## Gereksinimler

- Google Chrome (v114+)
- Figma hesabı
- Google Gemini API key (ücretsiz)
