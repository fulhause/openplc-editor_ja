# scripts/check-build-exists.ts の解説

1. `// Check if the renderer and main bundles are built`
   - 「メインとレンダーのバンドルが作られているか確認する」というコメントです。
2. `import chalk from 'chalk';`
   - メッセージを色付きで表示するためのライブラリを読み込みます。
3. `import fs from 'fs';`
   - ファイルやフォルダの存在を調べるためのモジュールです。
4. `import path from 'path';`
   - パスを結合するためのモジュールです。
5. `import webpackPaths from '../configs/webpack/webpack.paths';`
   - プロジェクトのフォルダ構成が入った `webpackPaths` を読み込みます。
6. `const mainPath = path.join(webpackPaths.distMainPath, 'main.js');`
   - メインプロセスのビルドファイル `main.js` の場所を作成します。
7. `const rendererPath = path.join(webpackPaths.distRendererPath, 'renderer.js');`
   - レンダラープロセスのビルドファイル `renderer.js` の場所を作成します。
8. `if (!fs.existsSync(mainPath)) { ... }`
   - メインのビルドファイルが無ければエラーを投げます。
9. `if (!fs.existsSync(rendererPath)) { ... }`
   - レンダラーのビルドファイルが無ければエラーを投げます。
