# scripts/check-port-in-use.js の解説

1. `import chalk from 'chalk';`
   - 文字に色を付けるためのライブラリを読み込みます。
2. `import detectPort from 'detect-port';`
   - ポートが使われているか調べる関数を提供するライブラリを読み込みます。
3. `const port = process.env.PORT || '1212';`
   - 環境変数 `PORT` があればその値を、なければ `'1212'` を `port` という変数に入れます。
4. `detectPort(port, (_err, availablePort) => {`
   - `detectPort` 関数で `port` が空いているかを調べます。結果は `availablePort` に入ります。
5. `if (port !== String(availablePort)) {`
   - 指定した `port` が利用可能なポートと違う場合、つまり既に使用されている場合の条件です。
6. `throw new Error(...);`
   - エラーメッセージを表示して処理を止めます。
7. `} else {`
   - それ以外、ポートが空いている場合の処理です。
8. `process.exit(0);`
   - プログラムを正常終了させます。`0` は成功を意味します。
9. `});`
   - `detectPort` の結果を受け取る関数の終わりです。
