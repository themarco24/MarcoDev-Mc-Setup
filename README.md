# 🚀 Marco Development | Minecraft Sunucu Kurulum Aracı

**Marco Development MC Setup**, Windows üzerinde **Paper** veya **Purpur** tabanlı Minecraft Java Edition sunucularını kolayca kurmak için geliştirilmiş açık kaynaklı bir komut satırı aracıdır.

Kullanıcıdan sunucu yazılımını, Minecraft sürümünü, kurulum klasörünü, RAM miktarını ve portu seçmesini ister; ardından gerekli sunucu dosyasını indirip başlangıç yapılandırmasını hazırlar.

## ✨ Özellikler

- ✅ **Paper ve Purpur** sunucu yazılımları
- ✅ Minecraft sürümlerini listeleme veya sürümü elle girme
- ✅ Sunucu `server.jar` dosyasını otomatik indirme
- ✅ İndirme ilerlemesini ve hızını gösterme
- ✅ Geçici ağ sorunlarında yeniden deneme
- ✅ Paper indirmelerinde mevcutsa **SHA-256 doğrulaması**
- ✅ **Java sürümünü kontrol etme** ve gerektiğinde uyarma
- ✅ RAM, port ve kurulum klasörü seçimi
- ✅ `start.bat`, `server.properties`, `eula.txt` ve kurulum bilgilerini içeren `README.md` oluşturma
- ✅ Parametrelerle soru sormadan kurulum desteği

## 🖥️ Gereksinimler

- **Windows** (hazır `marco-server.exe` için)
- İnternet bağlantısı
- Minecraft sunucusunu çalıştırmak için seçilen sürümle uyumlu **Java**

> Kurulum aracı Java'yı kontrol eder ancak Java'yı otomatik yüklemez. Gerekirse [Eclipse Temurin](https://adoptium.net/temurin/releases/) üzerinden uygun sürümü kurabilirsiniz.

## 📥 Kurulum ve kullanım

1. Projedeki `marco-server.exe` dosyasını edinin.
2. Dosyayı çalıştırın.
3. **Paper** veya **Purpur** seçin.
4. Minecraft sürümünü ve kurulum klasörünü belirleyin.
5. Sunucuya ayrılacak RAM miktarını ve portu girin.
6. Araç sunucu dosyasını indirip gerekli ayar dosyalarını oluşturduktan sonra kurulum klasöründeki `start.bat` dosyasını çalıştırın.

> **Önemli:** Araç kurulum sırasında `eula.txt` dosyasına `eula=true` yazar. Kullanmadan önce [Minecraft EULA](https://aka.ms/MinecraftEULA) koşullarını okuyup kabul ettiğinizden emin olun.

## ⚙️ Komut satırından kullanım

```bat
marco-server.exe --help
```

Örnekler:

```bat
marco-server.exe --yes --software paper --version 1.21.8 --ram 6 --port 25565
marco-server.exe --yes --software purpur --version 1.21.4 --ram 8 --dir C:\Sunucular\survival
```

| Parametre | Açıklama |
| --- | --- |
| `--software` | `paper` veya `purpur` (varsayılan: Paper) |
| `--version` | Kurulacak Minecraft sürümü (belirtilmezse en son bulunan sürüm) |
| `--ram` | Sunucuya ayrılacak RAM, GB (otomatik modda varsayılan: 4) |
| `--port` | Sunucu portu (varsayılan: `25565`) |
| `--dir` | Kurulum klasörü |
| `--yes`, `-y` | Sorular olmadan otomatik kurulum |
| `--no-pause` | İşlem bitince Enter beklemeden çıkış |
| `--help`, `-h` | Yardım bilgilerini görüntüle |

## 🛠️ Kaynak koddan çalıştırma

Geliştirme için **Node.js** ve **npm** gereklidir.

```bash
npm install
npm start
```

Windows için çalıştırılabilir dosya oluşturma:

```bash
npm run build
```

Diğer komutlar:

```bash
npm run bundle
npm run build:exe
```

## 📁 Proje yapısı

```text
marco-dev-mc-setup/
├── bin/
│   └── index.js          # Kurulumun komut satırı akışı
├── src/
│   ├── api.js            # Paper ve Purpur API bağlantıları
│   ├── config.js         # Sunucu yapılandırma dosyaları
│   ├── downloader.js     # Sunucu dosyasını indirme ve doğrulama
│   ├── java.js           # Java sürümü tespiti
│   └── spinner.js        # Terminal ilerleme göstergesi
├── package.json
├── set-icon.js
├── icon.ico
└── README.md
```

`dist/`, `node_modules/` ve oluşturulan `.exe` dosyaları derleme/bağımlılık çıktılarıdır.

## ❓ Sık karşılaşılan sorunlar

**Java bulunamadı:** Uygun Java sürümünü yükleyin ve komut satırında `java -version` ile kontrol edin.

**İndirme başarısız:** İnternet bağlantısını ve seçilen Minecraft sürümünün Paper/Purpur üzerinde bulunup bulunmadığını kontrol edin.

**Sunucu açılmıyor:** Kurulum klasöründe `server.jar` dosyasının bulunduğunu ve Java sürümünüzün Minecraft sürümüne uygun olduğunu doğrulayın.

## 📌 Notlar

- Mevcut `server.properties` dosyası kurulum sırasında korunur.
- Sunucu özelliklerini kurulum sonrasında `server.properties` içinden değiştirebilirsiniz.
- Araç **Minecraft Java Edition** sunucuları içindir.
- Paper ve Purpur bağımsız projelerdir; bu araç resmî Minecraft ürünü değildir.

**Geliştirici:** Marco Development  
**Sürüm:** 1.1.0
