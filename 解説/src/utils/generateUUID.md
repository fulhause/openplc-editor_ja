# src/utils/generateUUID.ts の解説

1. `import { toNumber } from 'lodash'`
   - 数値に変換するための `toNumber` 関数を lodash から読み込みます。
2. `export const generateNumericUUID = () => {`
   - 数字だけで構成された UUID を作る関数を定義し、外部から使えるようにします。
3. `const timestamp = Date.now()`
   - 現在の時刻をミリ秒で取得し `timestamp` に入れます。
4. `const shortnedTimestamp = timestamp.toString().slice(7, 13)`
   - 時刻を文字列にして下位の 6 桁だけを取り出し `shortnedTimestamp` とします。
5. `const randomNumbers = Math.floor(Math.random() * 10000000)`
   - 0 から 9,999,999 までのランダムな整数を作ります。
6. ``return `${toNumber(shortnedTimestamp) + randomNumbers}```
   - 切り出した時刻を数値に変換しランダム数を足して文字列にして返します。
7. `}`
   - 関数の終わりです。
