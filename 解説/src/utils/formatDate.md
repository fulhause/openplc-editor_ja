# src/utils/formatDate.ts の解説

1. `const padTo2Digits = (num: number) => num.toString().padStart(2, '0')`
   - 数字を2桁の文字列にする関数です。例えば 3 は `'03'` になります。
2. `const formatDate = (date: Date) =>`
   - 日付オブジェクトを受け取り ISO風の文字列に整形する関数を定義します。
3. ```${[date.getFullYear(), padTo2Digits(date.getMonth() + 1), padTo2Digits(date.getDate())].join('-')}T${[padTo2Digits(date.getHours()), padTo2Digits(date.getMinutes()), padTo2Digits(date.getSeconds())].join(':')}```
   - 年・月・日を `YYYY-MM-DD` 形式にし、`T` の後に時・分・秒を `HH:MM:SS` 形式でつなげて文字列を作ります。
4. `export default formatDate`
   - `formatDate` 関数を外部から使えるようにします。
