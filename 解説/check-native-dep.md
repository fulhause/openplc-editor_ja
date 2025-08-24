# scripts/check-native-dep.js の解説

1. `import chalk from 'chalk';`
   - 文字に色を付けて表示するためのライブラリを読み込みます。
2. `import { execSync } from 'child_process';`
   - コマンドを同期的に実行するための関数を取り込みます。
3. `import fs from 'fs';`
   - ファイルやフォルダを操作するためのモジュールを読み込みます。
4. `import { dependencies } from '../package.json';`
   - プロジェクトの依存関係一覧を `package.json` から読み込みます。
5. `if (dependencies) {`
   - 依存関係が存在する場合だけ、以下の処理を行います。
6. `const dependenciesKeys = Object.keys(dependencies);`
   - 依存関係の名前を配列として取り出します。
7. `const nativeDeps = fs ...`
   - `node_modules` フォルダを調べ、`binding.gyp` があるパッケージを探します。これはネイティブモジュールです。
8. `if (nativeDeps.length === 0) { process.exit(0); }`
   - ネイティブモジュールが無ければ、何もしないで終了します。
9. `try {`
   - 以降の処理でエラーが出てもアプリが止まらないように `try` ブロックに入れます。
10. `const { dependencies: dependenciesObject } = JSON.parse(execSync(...).toString());`
    - `npm ls` コマンドで依存関係の情報を取得し、JSON として解析します。
11. `const rootDependencies = Object.keys(dependenciesObject);`
    - 解析した結果から最上位の依存関係名を取り出します。
12. `const filteredRootDependencies = rootDependencies.filter((rootDependency) => dependenciesKeys.includes(rootDependency));`
    - プロジェクトが直接依存しているネイティブモジュールだけを残します。
13. `if (filteredRootDependencies.length > 0) {`
    - 直接依存しているネイティブモジュールがある場合の処理です。
14. `const plural = filteredRootDependencies.length > 1;`
    - メッセージを複数形にするかどうかを判断します。
15. ``console.log(` ... `);``
    - ネイティブモジュールの扱い方について、色付きの警告メッセージを表示します。
16. `process.exit(1);`
    - エラーとして処理を終了します。
17. `}`
    - 13 行目の `if` の終わりです。
18. `} catch (e) { console.log('Native dependencies could not be checked', e); }`
    - 依存関係の確認に失敗した場合にメッセージを表示します。
19. `}`
    - 5 行目の `if` の終わりです。
