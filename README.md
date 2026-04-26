# 🚀 Profile-PDF-Automator

> **Automatically generate professional PDF resumes from Markdown files using GitHub Actions.**

This project provides a "Plug-and-Play" solution to convert your Markdown-based CVs/Profiles into high-quality PDF assets and publish them as GitHub Releases automatically on every push.

---

## 🇹🇷 Türkçe Kullanım Kılavuzu

Bu araç, GitHub profilinizdeki Markdown dosyalarından otomatik olarak PDF üretmenizi ve bunları "Releases" sekmesinde yayınlamanızı sağlar.

### 🛠️ Nasıl Kullanılır?
1. **Dosyayı Kopyalayın:** `.github/workflows/generate-pdf.yml` dosyasını kendi reponuza kopyalayın.
2. **Otomatik İsimlendirme:** Herhangi bir ayar yapmanıza gerek yok! Sistem, GitHub kullanıcı adınızı otomatik olarak algılar ve PDF dosyalarınızı `CV_KullaniciAdi_DosyaIsmi.pdf` şeklinde isimlendirir.
3. **Pushlayın:** Kodunuzu pushladığınızda Actions devreye girer.

### 🔑 Gerekli İzinler
Workflow dosyasında `permissions: contents: write` ayarının olduğundan emin olun, aksi takdirde Release oluşturamaz.

---

## 🇬🇧 English Guide

A standardized way to maintain professional PDF versions of your Markdown resumes without manual effort.

### 🛠️ How to Use?
1. **Copy the Workflow:** Place the `.github/workflows/generate-pdf.yml` file into your repository.
2. **Automatic Naming:** Zero configuration needed! The system automatically detects your GitHub username and renames the output as `CV_Username_Filename.pdf`.
3. **Push:** Just push your changes, and the automation handles the rest.

### 🔑 Permissions
Ensure your workflow includes `permissions: contents: write` to allow the Action to create and upload to Releases.

---

## 🤖 The Workflow (Actions Logic)

The automation uses `baileyjm02/markdown-to-pdf` for rendering and `softprops/action-gh-release` for asset management. It is configured to run on **Node.js 24** for future-proof stability.

---
## 📄 License
This project is licensed under the MIT License - feel free to use and share!

*Developed with ❤️ by [Cihad Kocaşahan](https://github.com/cihadkocasahan)*
