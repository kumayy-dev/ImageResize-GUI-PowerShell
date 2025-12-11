# 📘 日本語 README（最新版）

## 🔥 PowerShell 画像一括縮小ツール（GUI版）

このツールは、画像の一括縮小を簡単＆高速に行うための **PowerShell GUI アプリケーション** です。  
Windows標準機能と ImageMagick の両方に対応し、目的に応じて最適な処理方式を選べます。

---

## ✨ 主な機能

### 🖼 基本機能（Windows標準機能）
- ドラッグ＆ドロップで画像／フォルダを追加
- 縮小率（60〜10%）ボタンで即リサイズ
- JPEG 品質調整（40〜90）
- **EXIF 自動回転補正**（スマホ写真の回転ズレ防止）
- メタデータ削除（位置情報などを除去）
- WebP 変換
- 進行バーつき
- **中断ボタンつき**
- バッチファイルから起動可能

---

## 🪄 ImageMagick 対応（任意）

ImageMagick がインストールされている場合は自動検出され、  
より高画質・高圧縮の処理が使用できます。

使用オプション例：

- `-auto-orient`（EXIFで自動回転）
- `-strip`（メタデータ削除）
- `-quality`（圧縮率）
- `-sampling-factor 4:2:0`
- WebP 最適化

---

## 🆕 新機能：幅指定リサイズ（写真系・アイコン系）

### 📸 写真系（1600px）
- 出力フォルダ（Windows標準）：`Resized_photo`
- 出力フォルダ（ImageMagick）：`ResizedIM_photo`

### 🧩 アイコン系（1280px）
- 出力フォルダ（Windows標準）：`Resized_icon`
- 出力フォルダ（ImageMagick）：`ResizedIM_icon`

### 特徴
- 入力画像の大きさに応じて自動で縮小率を計算
- 固定フォルダ名のため、**毎回フォルダ名が変わらず整理が楽**
- 写真やブログ用素材の最適化に便利

---

## 📁 出力フォルダ例

```
/Pictures/photo.jpg
/Pictures/Resized_60/photo.jpg
/Pictures/Resized_photo/photo.jpg
/Pictures/ResizedIM_icon/icon.webp
```

---

## 🖥 必要環境

- Windows 10 / 11
- PowerShell（標準搭載でOK）

### 任意（推奨）
- ImageMagick  
  → 入っていると IM モードが有効になります

---

## 🚀 使い方

### 1. リポジトリを取得

```sh
git clone https://github.com/kumayy-dev/ImageResize-GUI-PowerShell.git
```

### 2. 実行

```sh
powershell -ExecutionPolicy Bypass -File ImageResize-GUI.ps1
```

### 3. バッチファイルから起動（おすすめ）

```bat
@echo off
start "" powershell -NoProfile -ExecutionPolicy Bypass -File "%~dp0ImageResize-GUI.ps1"
exit
```

---

## ⚙️ 内部処理の概要

### Windows標準モード
- System.Drawing による高品質リサイズ
- EXIF 自動回転補正
- Bicubic による滑らかな縮小

### ImageMagickモード
- より高品質・高圧縮
- WebP対応
- 速度も高速

---

## 📄 ライセンス

MIT License

---

## 👤 Author

kumayy  
GitHub: https://github.com/kumayy-dev
