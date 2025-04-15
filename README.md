# LINE風 ChatGPT チャットボット

このプロジェクトは、OpenAI GPT APIを使用したシンプルなLINE風チャットボットです。ユーザーがメッセージを入力すると、OpenAIのAPI（gpt-4o-miniまたはgpt-3.5-turbo）を使用して応答を生成します。

## 機能

- LINE風のインターフェース
- テキスト入力と送信機能
- AIからの返信表示
- 送信時刻の表示
- メッセージ入力中のローディングアニメーション
- エラーハンドリング

## 技術スタック

- Next.js (React)
- OpenAI API
- CSS (LINE風デザイン)

## セットアップ手順

### 前提条件

- Node.js v14以上
- npm または yarn
- OpenAI APIキー

### インストール

1. リポジトリをクローンまたはダウンロード

```bash
git clone [リポジトリURL]
cd chatbot-app
```

2. 依存関係のインストール

```bash
npm install
# または
yarn install
```

3. 環境変数の設定

プロジェクトのルートディレクトリに `.env.local` ファイルを作成し、以下の内容を追加します：

```
OPENAI_API_KEY=あなたのOpenAI APIキー
```

### 開発サーバーの起動

```bash
npm run dev
# または
yarn dev
```

ブラウザで `http://localhost:3000` を開くと、アプリケーションが表示されます。

## ファイル構造

```
chatbot-app/
├── .env.local        # API認証情報（手動で作成）
├── .gitignore        # Git除外ファイル
├── package.json      # 依存関係
├── next.config.js    # Next.js設定
├── pages/
│   ├── _app.js       # アプリケーション設定
│   ├── index.js      # チャットインターフェース
│   ├── api/
│   │   └── chat.js   # APIエンドポイント
└── styles/
    └── globals.css   # スタイル定義
```

## APIキーの取得方法

1. [OpenAIのウェブサイト](https://platform.openai.com/)にアクセスし、アカウント作成（または既存アカウントでログイン）
2. 右上のプロフィールアイコンをクリック → 「View API Keys」を選択
3. 「Create New Secret Key」をクリックして新しいAPIキーを生成
4. 生成されたキーを `.env.local` ファイルにコピー

## Vercelへのデプロイ

このアプリケーションはVercelへのデプロイに対応しています。

1. [Vercel](https://vercel.com/)にアカウント作成（またはログイン）
2. 「New Project」をクリック
3. リポジトリをインポート
4. 「Environment Variables」セクションで、以下の変数を追加：
   - `OPENAI_API_KEY` = あなたのOpenAI APIキー
5. 「Deploy」ボタンをクリック

## トラブルシューティング

### APIエラーが発生する場合

- APIキーが正しく設定されているか確認
- OpenAIのアカウントが有効で、支払い情報が設定されているか確認
- モデル名が正しいか確認（APIエラーの場合は自動的にgpt-3.5-turboにフォールバック）

### 開発サーバーの問題

以下のコマンドで依存関係を再インストールし、開発サーバーを再起動：

```bash
rm -rf node_modules .next
npm install
npm run dev
```

## 注意事項

- OpenAI APIは有料サービスです。使用量に応じて料金が発生します。
- APIキーは公開リポジトリにコミットしないよう注意してください。

## ライセンス

MIT
