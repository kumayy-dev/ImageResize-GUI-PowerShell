# ImageResize-GUI-PowerShell

## 🔥 PowerShell で作る高機能画像縮小ツール（GUI版）

このツールは、画像の一括縮小を簡単＆高速に行うための **PowerShell GUI アプリケーション** です。  
EXIF の向き補正、メタデータ削除、WebP 変換、ImageMagick による高画質処理など、  
実用的な機能をすべてまとめています。

---

## ✨ 主な機能

### 🖼 基本機能
- 画像やフォルダをドラッグ＆ドロップで追加  
- 縮小率（60〜10%）をワンクリックで選択  
- JPEG 品質調整（40〜90）  
- スマホ写真で発生する**回転ズレを防ぐ EXIF 自動回転処理**  
- メタデータ削除（位置情報などを安全に除去）  
- WebP 形式への変換  
- 進捗バーで処理状況を可視化  
- 大量処理でも安心の **中断ボタン**  
- **バッチファイルから起動可能**でアプリのように使える  

---

## 🧩 ImageMagick 対応（任意）

ImageMagick が PC にインストールされている場合は自動検出し、  
高画質・高圧縮の IM モードが利用できるようになります。

使用される主なオプション：

- `-auto-orient`（EXIF に基づく自動回転）
- `-strip`（メタデータ全削除）
- `-quality`（圧縮率）
- `-sampling-factor 4:2:0`（高圧縮向け）
- WebP 変換最適化

Windows 標準機能よりも **さらに小さく、綺麗な画像** を生成できます。

---

## 📁 出力フォルダ構造

各縮小率ごとにフォルダを自動生成します。

例：

```
/Pictures/photo.jpg
/Pictures/Resized_60/photo.jpg
/Pictures/ResizedIM_40/photo.webp
```

---

## 🖥 必要環境

- Windows 10 / Windows 11  
- PowerShell（標準で搭載されているものでOK）  

### 任意
- ImageMagick  
  （インストールされている場合、自動的に ImageMagick モードが有効になります）

---

## 🚀 使い方

### 1. リポジトリをクローン

```sh
git clone https://github.com/USERNAME/ImageResize-GUI-PowerShell.git
```

### 2. PowerShell から実行

```sh
powershell -ExecutionPolicy Bypass -File ImageResize-GUI.ps1
```

### 3. バッチファイルから起動（おすすめ）

```bat
@echo off
start "" powershell -NoProfile -ExecutionPolicy Bypass -File "%~dp0ImageResize-GUI.ps1"
exit
```

ダブルクリックで GUI が起動し、CMD ウィンドウも残りません。

---

## ⚙️ 仕組みの概要

### 🖼 Windows 標準モード
- System.Drawing による高品質リサイズ  
- EXIF Orientation を読み取り、自動回転補正  
- 高品質 Bicubic リサイズ  

### 🪄 ImageMagick モード
- より美しいリサイズ  
- さらに小さいファイルサイズ  
- WebP 最適化  
- メタデータ完全削除  

大容量画像の扱いが圧倒的に楽になります。

---

## 📄 ライセンス

MIT License  
商用・非商用問わず自由に利用できます。

---

## 👤 Author

YOUR NAME  
GitHub: https://github.com/kumayy-dev
