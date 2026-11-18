# GameHub

**GameHub**, Windows bilgisayarınızdaki diskleri ve popüler oyun başlatıcılarını (Steam, Epic Games vb.) otomatik olarak tarayarak yüklü tüm oyunlarınızı tek bir modern arayüzde toplayan bir oyun kütüphanesi uygulamasıdır.

## Özellikler

* **Otomatik Oyun Taraması:** Steam (`libraryfolders.vdf` ve `.acf` dosyaları), Epic Games Launcher manifestleri ve sistemdeki ortak oyun dizinlerini (`Games`, `Oyunlar`, `GOG Games`, `Riot Games`, `EA Games`, `Ubisoft` vb.) otomatik tarar.
* **Tek Tıkla Başlatma:** Steam ve Epic Games oyunlarını kendi protokolleri (`steam://`, `com.epicgames.launcher://`) üzerinden, bağımsız oyunları ise doğrudan `.exe` dosyası üzerinden çalıştırır.
* **Oynama Süresi ve Geçmiş Takibi:** Oyunların en son ne zaman oynandığını kaydeder ve bağımsız (Diğer) oyunlar için toplam oynama süresini saat cinsinden hesaplar.
* **Steam OpenID Girişi:** Yerel bir sunucu aracılığıyla güvenli Steam girişi yaparak kullanıcı adınızı ve profil fotoğrafınızı arayüzde gösterir.
* **Modern Koyu Arayüz:** `customtkinter` ile geliştirilmiş şık, kategorize edilebilir ve anlık arama destekli kullanıcı arayüzü sunar.
* **Hızlı Erişim:** Seçili oyunun kurulu olduğu klasörü tek tuşla Windows Dosya Gezgini'nde açar.

## Gereksinimler

* **İşletim Sistemi:** Windows (Kayıt defteri `winreg` ve `os.startfile` işlevleri nedeniyle Windows odaklıdır)
* **Python:** Python 3.8 veya üzeri

### Kullanılan Kütüphaneler

Uygulama standart Python kütüphanelerine (`json`, `os`, `re`, `threading`, `http.server`, `winreg` vb.) ek olarak aşağıdaki harici paketleri kullanır:

* `customtkinter` (Modern arayüz bileşenleri için)
* `Pillow` (`PIL` - Steam profil avatarlarını işlemek için)

## Kurulum

1. Depoyu bilgisayarınıza klonlayın veya dosyaları indirin:
   ```bash
   git clone https://github.com
   cd gamehub
   ```

2. Gerekli harici Python kütüphanelerini yükleyin:
   ```bash
   pip install customtkinter pillow
   ```

## Kullanım

Uygulamayı başlatmak için terminal veya komut istemcisinde ana dosyayı çalıştırın:

```bash
python gamehub.py
```
*(Not: Dosya adınız farklıysa `gamehub.py` yerine kendi dosya adınızı yazın.)*

### Veri Depolama

Uygulama; Steam kullanıcı bilgilerinizi, son oynanma tarihlerini ve oyun sürelerinizi aşağıdaki dizinde JSON formatında saklar:
```text
%APPDATA%\GameHub\data.json
```

## Taranan Varsayılan Dizinler

Steam ve Epic Games kütüphanelerine ek olarak, sistemdeki tüm sürücülerde (`C:\` hariç `D:\` ve sonrası) şu klasörler taranır:
* `Games`, `Oyunlar`
* `GOG Games`, `Program Files (x86)\GOG Galaxy\Games`
* `XboxGames`
* `Riot Games`, `Program Files\Riot Games`
* `EA Games`, `Program Files\EA Games`
* `Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games`

## Lisans

Bu proje [MIT Lisansı](LICENSE) altında lisanslanmıştır.


# GameHub

**GameHub** is a modern desktop game library application for Windows that automatically scans your drives and popular game launchers (Steam, Epic Games, etc.) to gather all your installed games into a single unified interface.

## Features

* **Automatic Game Discovery:** Automatically detects games from Steam (`libraryfolders.vdf` and `.acf` manifests), Epic Games Launcher manifests, and common game directories (`Games`, `Oyunlar`, `GOG Games`, `Riot Games`, `EA Games`, `Ubisoft`, etc.) across your drives.
* **One-Click Launch:** Launches Steam and Epic Games titles via their native URI protocols (`steam://`, `com.epicgames.launcher://`) and runs standalone games directly via their `.exe` files.
* **Playtime & History Tracking:** Logs the last played date for every game and automatically tracks total playtime (in hours) for standalone ("Diğer") games.
* **Steam OpenID Login:** Authenticates securely via a local HTTP callback server to display your Steam username and profile avatar in the app.
* **Modern Dark UI:** Built with `customtkinter`, featuring collapsible platform categories, instant search filtering, and quick folder access.

## Requirements

* **Operating System:** Windows (Relies on Windows-specific modules such as `winreg` and `os.startfile`)
* **Python:** Python 3.8 or higher

### Dependencies

In addition to Python's standard library (`json`, `os`, `re`, `threading`, `http.server`, `winreg`, etc.), the project requires the following third-party packages:

* `customtkinter` (For modern UI components)
* `Pillow` (`PIL` - For loading and displaying Steam profile avatars)

## Installation

1. Clone the repository or download the source code:
   ```bash
   git clone https://github.com
   cd gamehub
   ```

2. Install the required third-party Python libraries:
   ```bash
   pip install customtkinter pillow
   ```

## Usage

Run the main Python script from your terminal or command prompt to launch the application:

```bash
python gamehub.py
```
*(Note: Replace `gamehub.py` with the actual name of your `.py` file if different.)*

### Data Storage

User session details, last played timestamps, and playtime statistics are stored locally in JSON format at:
```text
%APPDATA%\GameHub\data.json
```

## Scanned Default Directories

Alongside Steam and Epic Games libraries, GameHub scans drives (`D:\` and above) for the following directories:
* `Games`, `Oyunlar`
* `GOG Games`, `Program Files (x86)\GOG Galaxy\Games`
* `XboxGames`
* `Riot Games`, `Program Files\Riot Games`
* `EA Games`, `Program Files\EA Games`
* `Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games`

## License

This project is licensed under the [MIT License](LICENSE).
