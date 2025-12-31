
```markdown
# 🔨 Thor Scraper - Tor Network CTI Tool

Bu proje, Sibervatan "Yıldız CTI" eğitimi kapsamında geliştirilmiş, **Go (Golang)** tabanlı bir Siber Tehdit İstihbaratı (CTI) toplama aracıdır.

## 🚀 Proje Amacı
Siber tehdit aktörleri izlerini kaybettirmek için Tor ağını kullanmaktadır. Bu proje, yüzlerce `.onion` uzantılı siber tehdit kaynağını (Ransomware blogları, Hacker forumları, Sızıntı veritabanları) belirlenen bir hedef listesi (`targets.yaml`) üzerinden otomatize şekilde tarar, HTML kaynak kodlarını ve ekran görüntülerini (screenshot) arşivler.

## 🛠️ Teknik Özellikler
- **Tor Proxy Entegrasyonu:** `127.0.0.1:9050` üzerinden anonim bağlantı (SOCKS5 Proxy) sağlar ve IP sızıntısını önler.
- **Headless Chrome (Chromedp):** Modern web teknolojilerini render ederek tam sayfa ekran görüntüsü alır.
- **Dinamik Klasörleme:** Her hedefi kendi URL ismine (`example.onion/`) göre ayrı klasörlerde saklar (PDF Madde 4.1 Uyumlu).
- **Raporlama:** Tarama sonuçlarını anlık olarak `scan_report.log` dosyasına ve terminale işler (bufio).
- **Concurrency & I/O:** `bufio` kütüphanesi ile optimize edilmiş dosya yazma işlemleri kullanır.

## 📦 Kurulum ve Kullanım

### Gereksinimler
- Go 1.20+
- Tor Service (Arka planda çalışıyor olmalı)
- Linux / macOS / Windows

### Çalıştırma Adımları

1. **Repoyu Klonlayın:**
   ```bash
   git clone [https://github.com/KULLANICI_ADIN/thor-scraper.git](https://github.com/KULLANICI_ADIN/thor-scraper.git)
   cd thor-scraper

```

2. **Bağımlılıkları Yükleyin:**
```bash
go mod tidy

```


3. **Tor Servisini Başlatın (Linux/Arch):**
```bash
sudo systemctl start tor

```


*(Not: Tor servisinin 9050 portunda çalıştığından emin olun.)*
4. **Aracı Çalıştırın:**
```bash
go run main.go

```



## 📂 Çıktı Yapısı (Output)

Program çalıştığında `output/` klasörü altında şu yapıyı oluşturur:

```text
output/
├── breachdbsztfykg...onion/
│   ├── index.html        # Sitenin HTML kaynak kodu
│   ├── screenshot.png    # Tam sayfa ekran görüntüsü
│   └── site_info.txt     # Meta veriler (Başlık, Tarama Tarihi)
└── scan_report.log       # Detaylı durum raporu (SUCCESS/FAIL kayıtları)

```

## ⚠️ Yasal Uyarı (Disclaimer)

Bu araç sadece eğitim ve savunma amaçlı (CTI) geliştirilmiştir. Yasadışı faaliyetlerde kullanılması kullanıcının sorumluluğundadır.

---

*Developed for Sibervatan 'Yıldız CTI' Program.*

```

```
