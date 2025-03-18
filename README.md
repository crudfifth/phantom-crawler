# PhantomCrawler

PhantomCrawler は、動的・静的な Web ページのデータを取得するための軽量スクレイピングツール。  
GUI なしで動作し、シンプルな設定でスクレイピングを自動化できる。

## 特徴
- **JavaScript レンダリング対応**  
  Playwright / Scrapy / Requests を利用し、クライアントサイドで描画されるデータも取得可能。
- **データ出力**  
  CSV / JSON / SQLite に対応し、必要なフォーマットで保存できる。
- **プロキシ & ユーザーエージェント制御**  
  ローテーション対応で、ボット検出を回避。
- **スケジューリング**  
  タスクスケジューラと連携し、定期実行が可能。

## ディレクトリ構成
```
PhantomCrawler/
│── src/
│   ├── core/                  # スクレイピングのコアロジック
│   ├── extractors/            # HTML データ抽出ロジック
│   ├── storage/               # データ保存（CSV, JSON, DB）
│   ├── scheduler/             # 定期実行タスク
│   ├── config.py              # 設定ファイル
│   ├── main.py                # メインエントリポイント
│── requirements.txt           # 依存パッケージ
│── README.md                  # 本ドキュメント
│── LICENSE                    # ライセンス情報
```

## インストール
**1. リポジトリをクローン**
```bash
git clone https://github.com/yourusername/PhantomCrawler.git
cd PhantomCrawler
```

**2. 依存パッケージをインストール**
```bash
pip install -r requirements.txt
```

**3. Playwright のセットアップ**
```bash
playwright install
```

## 使い方
### 1. ターゲット URL をセット
`config.py` に取得対象の URL を記述。

```python
TARGET_URLS = [
    "https://example.com",
    "https://another-site.com"
]
```

### 2. スクレイピングを実行
```bash
python main.py
```

### 3. 取得データの確認
データは `output/` フォルダに `CSV` または `JSON` 形式で保存。

## 今後のロードマップ
- **ログイン認証対応**（クッキー管理 / セッション制御）
- **分散クローリング**（マルチスレッド / マルチプロセス最適化）
- **クラウド連携**（AWS S3 / Google Drive）
- **カスタム設定ファイル導入**（YAML / JSON ベースの設定管理）

## ライセンス
MIT License

## コントリビュート
バグ報告・機能追加の提案は `Issues` へ、プルリクエストは `PR` へ。
