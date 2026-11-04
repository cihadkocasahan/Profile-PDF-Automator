# Profile-PDF-Automator — Zero-Config CI/CD Markdown to PDF Release Pipeline

> **v1.0.0** • Free & Open Source • MIT License

**Profile-PDF-Automator**, GitHub profillerinizde veya repolarınızda bulunan Markdown (`.md`) formatındaki özgeçmiş, teknik doküman ve portfolyo dosyalarınızı; her kod gönderiminde (`push`) **tamamen otomatik olarak profesyonel PDF belgelerine dönüştüren ve GitHub Releases sekmesinde güncel olarak yayınlayan** tak-çalıştır bir CI/CD otomasyon hattıdır.

Geliştiricilerin Word, Canva veya harici PDF editörleriyle vakit kaybetmeden; sürüm kontrolü altında tutulan Markdown kaynak dosyalarından tek bir `git push` ile her zaman taze, profesyonel PDF çıktıları üretmesini sağlar.

> [!IMPORTANT]
> **Örnek & Eğitim Amaçlı DevOps Aracı:** Bu proje; GitHub Actions otomasyon hatları, Node.js tabanlı doküman motorları, otomatik versiyonlama ve Release yönetimi pratiklerini sergilemek amacıyla **açık kaynak ve referans portfolyo projesi** olarak hazırlanmıştır.
> 
> **Sorumluluk Reddi (Disclaimer):** Yazılım "olduğu gibi" (AS-IS) sunulmaktadır. Geliştirici; GitHub Actions kota aşımları, üçüncü parti npm paketlerinin çıktı farklılıkları veya oluşturulan PDF belgelerinin biçimlendirmesinden doğabilecek doğrudan veya dolaylı hiçbir zarardan sorumlu tutulamaz.

---

## ⚡ Temel Özellikler

- 🚀 **Sıfır Yapılandırma (Zero-Config):** Reponuza eklediğiniz anda hiçbir ayar gerektirmeden çalışır.
- 👤 **Akıllı Dinamik İsimlendirme:** Markdown dosyanız zaten `CV_` ile başlıyorsa adı korur; genel dokümanlar için ise GitHub kullanıcı adınızı (`github.actor`) ve standart formatı (`CV_Username_Filename.pdf`) otomatik uygular. Tekrarlanan ön ekleri önler.
- 🔄 **Otomatik GitHub Release Entegrasyonu:** Oluşturulan PDF dosyalarını her commit sonrası doğrudan reponuzun `Releases` sekmesine `latest` etiketiyle yükler ve linkleri güncel tutar.
- ⚡ **Saf Node.js & npx Altyapısı:** Hantal veya güvensiz üçüncü parti eklentiler yerine doğrudan güncel Node.js (`npx md-to-pdf`) motorunu çalıştırır.
- 🎯 **Akıllı Tetikleme (Filter Triggers):** Sadece `.md` dosyalarında değişiklik olduğunda devreye girer, gereksiz GitHub Actions dakikası harcamaz.

---

## 🚀 Hızlı Başlangıç (Nasıl Kullanılır?)

Kendi profilinizde veya herhangi bir projenizde kullanmak yalnızca 2 adım sürer:

### 1. Workflow Dosyasını Kopyalayın
Bu projedeki [`.github/workflows/generate-pdf.yml`](.github/workflows/generate-pdf.yml) dosyasını kendi reponuzun `.github/workflows/` dizinine yerleştirin.

### 2. GitHub İzinlerini Verin (Tek Seferlik)
Workflow'un Releases oluşturabilmesi için reponuzun yetkisini kontrol edin:
- Reponuzda **Settings** > **Actions** > **General** bölümüne gidin.
- **Workflow permissions** altında **"Read and write permissions"** seçeneğini işaretleyip kaydedin.

### 3. Değişiklikleri Gönderin (`git push`)
Markdown dosyanızı düzenleyip repoya gönderdiğiniz anda GitHub Actions otomatik olarak devreye girer ve saniyeler içinde **Releases** sekmesinde PDF çıktınızı hazırlar!

---

## 🏗️ İş Akışı Mimarisi (Pipeline Flow)

```text
  [ Markdown Dosyası (.md) ] ── (git push) ──► [ GitHub Actions Trigger ]
                                                         │
                                                         ▼
                                            [ Node.js & npx md-to-pdf ]
                                            (Temiz render motoru)
                                                         │
                                                         ▼
                                            [ Otomatik Dinamik İsimlendirme ]
                                            (CV_Cihad_Kocasahan_TR.pdf / CV_Username_Doc.pdf)
                                                         │
                                                         ▼
                                            [ GitHub Releases (Tag: latest) ]
                                            (Doğrudan indirilebilir PDF linki)
```

---

## 📄 Lisans

Bu proje **MIT Lisansı** altında özgürce kullanılabilir, incelenebilir ve paylaşılabilir. Detaylar için [LICENSE](LICENSE) dosyasına bakabilirsiniz.

---

## 🎯 Proje Hakkında & Geliştirme Notu

Bu proje; kurumsal CI/CD otomasyonlarını, doküman üretim hatlarını ve yapay zeka destekli mikro araç geliştirme pratiklerini somut bir örnek üzerinde sergilemek üzere **portfolyo ve referans aracı** olarak geliştirilmiştir.

Geliştirme sürecinde modern yazılım disiplini ve yapay zeka destekli araçlar harmanlanarak; sade, amaca odaklı ve herkesin tek tıkla projesine entegre edebileceği temiz bir otomasyon hedeflenmiştir.

Diğer çalışmalar ve detaylı teknik profil için: [cihadkocasahan](https://github.com/cihadkocasahan)
