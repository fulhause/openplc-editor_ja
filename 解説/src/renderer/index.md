# src/renderer/index.tsx の解説

1. `import '@utils/i18n'`
   - アプリ全体で多言語対応を行う設定ファイルを読み込みます。
2. `import { createRoot } from 'react-dom/client'`
   - React コンポーネントを画面に描画するための関数を読み込みます。
3. `import App from './App'`
   - メインとなる `App` コンポーネントを読み込みます。
4. `const container = document.getElementById('root') as HTMLElement`
   - HTML 内の `id="root"` の要素を取得し、描画先とします。
5. `const root = createRoot(container)`
   - 取得した要素を React の描画用ルートに変換します。
6. `root.render(<App />)`
   - `App` コンポーネントを画面に表示します。
7. `postMessage({ payload: 'removeLoading' }, '*')`
   - 読み込み中表示を消すためのメッセージを送ります。
