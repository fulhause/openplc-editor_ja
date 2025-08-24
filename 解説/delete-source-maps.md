# scripts/delete-source-maps.js の解説

1. `import fs from 'fs';`
   - ファイルが存在するか確認するために `fs` モジュールを読み込みます。
2. `import path from 'path';`
   - ファイルパスを結合するための `path` モジュールを読み込みます。
3. `import { rimrafSync } from 'rimraf';`
   - フォルダやファイルを削除する `rimrafSync` 関数を読み込みます。
4. `import webpackPaths from '../configs/webpack/webpack.paths';`
   - プロジェクトで使われるフォルダの場所をまとめた `webpackPaths` を読み込みます。
5. `export default function deleteSourceMaps() {`
   - `deleteSourceMaps` という関数を定義し、他のファイルからも使えるようにします。
6. `if (fs.existsSync(webpackPaths.distMainPath))`
   - メインプロセスのビルドフォルダが存在するか確認します。
7. `rimrafSync(path.join(webpackPaths.distMainPath, '*.js.map'), { glob: true, });`
   - 存在する場合、そこにある `*.js.map` という拡張子のファイルをすべて削除します。
8. `if (fs.existsSync(webpackPaths.distRendererPath))`
   - レンダラープロセスのビルドフォルダが存在するか確認します。
9. `rimrafSync(path.join(webpackPaths.distRendererPath, '*.js.map'), { glob: true, });`
   - 存在する場合、こちらも `*.js.map` ファイルを削除します。
10. `}`
    - 関数の終わりです。
