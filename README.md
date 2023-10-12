# オンデマンド動画配信 App

## 構成

- index.js - ルーティング設定
- App.js - トップページ（動画一覧）
- pages/
  - Dashboard.js - 管理画面（動画のアップロード）

## アーキテクチャ

- トップページ（動画一覧）
  - React → Aurora（動画一覧取得）
- 管理画面（動画のアップロード、削除）
  -

# AWS

Python による Lambda の制御が必要かも

- 動画をアップロードしてから hls に変換する指示

## MediaConverter ジョブテンプレート設定

- 入力
  - 入力ファイル URL：S3
- 出力グループ
  - Apple HLS
    - カスタムグループ名：動画 ID
    - 送信先：s3://動画 ID/
    - S3 ストレージクラス：Standard
    - セグメント：10 秒
  - H.264
    - 名前修飾子：ts
    - 最大ビットレート：5000000
- ジョブの設定
  - AWS の統合
    - サービスロール：arn:aws:iam::~~

## 開始

```bash
npm start
```

## アドレス

http://localhost:3000/
