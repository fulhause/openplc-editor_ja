# scripts/link-modules.ts の解説

1. `import fs from 'fs';`
   - ファイルやフォルダを扱うための `fs` モジュールを読み込みます。
2. `import webpackPaths from '../configs/webpack/webpack.paths';`
   - プロジェクト内の重要なパスが入った `webpackPaths` を読み込みます。
3. `const { srcNodeModulesPath } = webpackPaths;`
   - `webpackPaths` から `src` 用の `node_modules` パスを取り出します。
4. `const { appNodeModulesPath } = webpackPaths;`
   - `webpackPaths` から アプリ用 `node_modules` のパスを取り出します。
5. `if (!fs.existsSync(srcNodeModulesPath) && fs.existsSync(appNodeModulesPath)) {`
   - `src` の `node_modules` が存在せず、アプリの `node_modules` が存在する場合にのみ処理を行います。
6. `fs.symlinkSync(appNodeModulesPath, srcNodeModulesPath, 'junction');`
   - アプリの `node_modules` へのリンクを `src` から張ります。Windows では `'junction'` 方式を使います。
7. `}`
   - `if` 文の終わりです。
