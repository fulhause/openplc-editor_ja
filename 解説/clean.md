# scripts/clean.js の解説

1. `import fs from 'fs';`
   - ファイルやフォルダの存在を確認するためのモジュールを読み込みます。
2. `import { rimrafSync } from 'rimraf';`
   - 指定したフォルダを削除する `rimrafSync` 関数を読み込みます。
3. `import webpackPaths from '../configs/webpack/webpack.paths';`
   - プロジェクトで使われるパスをまとめた `webpackPaths` を読み込みます。
4. `const foldersToRemove = [ ... ];`
   - 削除したいフォルダの一覧を配列として用意します。
5. `foldersToRemove.forEach((folder) => {`
   - 配列の中のフォルダを一つずつ取り出して処理します。
6. `if (fs.existsSync(folder)) rimrafSync(folder);`
   - フォルダが存在する場合に削除します。
7. `});`
   - `forEach` ループの終わりです。
