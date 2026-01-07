\page grainer_manual_jp Grainer - グラニュラーシンセシス・プロセッサー

# Grainer - グラニュラーシンセシス・プロセッサー

VCV Rack向けのリアルタイム・グラニュラーシンセシス・プラグインです。

## 概要

Grainerは、ライブ入力をグレイン単位で分解・再構成するリアルタイム・グラニュラー・プロセッサーです。ピッチ・サイズ・位置・密度を細かく制御しながら、ランダマイズによって有機的なテクスチャを生成します。

最大64ボイス（初期値32）の同時グレイン処理と、5秒バッファに対応し、ライブ演奏からサウンドデザインまで幅広く活用できます。

本モジュールは Max for Live 版 grainer をベースにしています:
https://tsugumasa320.gumroad.com/l/grainer

## 主な機能

- **マルチグレインエンジン**: 最大64ボイス（初期値32）
- **リアルタイム処理**: 低レイテンシでライブ用途に最適
- **CVモジュレーション**: 主要パラメータをCV制御
- **高音質補間**: 線形補間による滑らかなピッチシフト
- **バッファ制御**: 5秒バッファと Freeze/Reverse
- **制作向け設計**: 制作・パフォーマンスの両方に対応

## クイックスタート

1. **オーディオ入力**: AUDIO INPUT L/R にソースを接続
2. **グレイン長**: Grain Length を調整 (1.6ms - 1000ms)
3. **密度**: Density を調整 (表示 0 - 50Hz)
4. **音色調整**: Pitch / Position / Stereo Spread
5. **ミックス**: Dry/Wet と Reverb を調整

## パラメータ

### 基本コントロール

- **Grain Length**: グレイン長 (1.6ms - 1000ms)
- **Density**: グレイン生成レート (表示 0 - 50Hz)
- **Pitch**: ピッチ比 (1/3x - 3x、中央=1x)
- **Position**: 再生位置 (0-100%: 0%=最古, 100%=REC位置)
- **Stereo Spread**: ステレオ位置のランダマイズ (0-1)

### 詳細コントロール

- **Pitch Random**: ピッチのランダム量 (0-3)
- **Pitch Quantize**: 量子化量 (0-1)
- **Window Shape**: Hann形状の左右偏り (-1〜+1)
- **Position Random**: 位置のランダム量 (0-1)
- **Input Gain**: 入力ゲイン (0-1、リニア)
- **Dry/Wet**: 原音と処理音の比率 (0-1)
- **Reverb**: 内蔵リバーブ量 (0-1)

### トランスポート

- **Forward/Reverse**: 再生方向の切替 (ボタン)
- **Freeze**: バッファのフリーズ (ボタン/CVゲート)

### CV入力

主要パラメータはCV対応（±5Vバイポーラ）:
- Grain Length CV
- Density CV
- Pitch CV（コンテキストメニューで1V/oct切替）
- Pitch Random CV
- Position CV
- Position Random CV
- Stereo Spread CV
- Input Gain CV
- Dry/Wet CV
- Reverb CV
- Window Shape CV

## 応用例

- アンビエントの質感生成
- リズミックなグラニュラーリピート
- 実験的なサウンド加工

## 技術仕様

- **バッファ**: 5秒のリングバッファ（44.1kHz基準）
- **同時グレイン**: 最大64ボイス（初期値32）
- **エンベロープ**: Hann窓
- **サンプルレート**: VCV Rackの全レートに対応
- **信号レンジ**: ±5V (VCV Rack標準)
