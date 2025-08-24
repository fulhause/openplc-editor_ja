# scripts/notarize.js の解説

1. `const notarize = require('@electron/notarize')`
   - アプリを Apple に登録するための `@electron/notarize` モジュールを読み込みます。
2. `exports.default = async function notarizeMacos(context) {`
   - `notarizeMacos` という非同期関数を定義し、他のファイルから呼び出せるようにします。
3. `const { electronPlatformName, appOutDir } = context`
   - 引数 `context` からプラットフォーム名と出力フォルダを取り出します。
4. `if (electronPlatformName !== 'darwin') { return }`
   - macOS (`darwin`) 以外では何もしないで終了します。
5. `if (process.env.CI !== 'true') { ... return }`
   - CI 環境でない場合は署名処理をスキップします。
6. `const appName = context.packager.appInfo.productFilename`
   - アプリのファイル名を取得します。
7. `await notarize.notarize({ ... })`
   - Apple にアプリを送って notarization（公証）を行います。必要な情報（アプリIDやApple IDなど）を渡します。
8. `}`
   - 関数の終わりです。
