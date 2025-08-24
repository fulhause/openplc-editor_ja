# scripts/check-node-env.js の解説

1. `import chalk from 'chalk';`
   - 文字を色付きで表示するためのライブラリを読み込みます。
2. `export default function checkNodeEnv(expectedEnv) {`
   - `checkNodeEnv` という関数を定義し、他のファイルからも使えるようにします。引数 `expectedEnv` は期待する環境名です。
3. `if (!expectedEnv) { throw new Error('"expectedEnv" not set'); }`
   - `expectedEnv` が与えられていない場合はエラーを出します。
4. `if (process.env.NODE_ENV !== expectedEnv) {`
   - 実行中の `NODE_ENV` が期待する環境と違うか確認します。
5. `console.log(chalk.whiteBright.bgRed.bold(...));`
   - 違っている場合、赤背景で警告メッセージを表示します。
6. `process.exit(2);`
   - エラーコード `2` でプログラムを終了します。
7. `}`
   - `if` 文の終わりです。
8. `}`
   - 関数の終わりです。
