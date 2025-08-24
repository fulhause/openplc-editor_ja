# scripts/build-python-compiler.ts の解説

1. `import { join } from 'node:path'`
   - Node.js に標準で用意されている `path` モジュールから `join` 関数を取り込みます。パスを結合するために使います。
2. `import { access, constants } from 'fs/promises'`
   - ファイルの存在を非同期で確認する `access` 関数と、アクセス権限を表す `constants` を読み込みます。
3. `import webpackPaths from '../configs/webpack/webpack.paths'`
   - プロジェクト内で使われているパス情報が入った `webpackPaths` を読み込みます。
4. `// Verify if the compiler is already built`
   - 「コンパイラが既に作られているか確認する」というコメントです。
5. `access(join(webpackPaths.rootPath, 'assets', 'st-compiler'), constants.R_OK)`
   - `webpackPaths.rootPath/assets/st-compiler` というフォルダが読み取り可能かどうか調べます。
6. `.then(() => console.log('st-compiler exists'))`
   - フォルダが見つかった場合、「st-compiler exists」と表示します。
7. `.catch(() => console.log('st-compiler does not exist'))`
   - フォルダが無い場合、「st-compiler does not exist」と表示します。
