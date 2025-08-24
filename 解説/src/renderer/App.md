# src/renderer/App.tsx の解説

1. `import '@xyflow/react/dist/style.css'`
   - ワークスペースで使うライブラリのスタイルを読み込みます。
2. `import 'tailwindcss/tailwind.css'`
   - Tailwind CSS のスタイルを読み込みます。
3. `import './styles/globals.css'`
   - アプリ共通の追加スタイルを読み込みます。
4. `import { AppLayout } from './components/_templates'`
   - 画面の枠組みとなるレイアウトコンポーネントを読み込みます。
5. `import { StartScreen, WorkspaceScreen } from './screens'`
   - スタート画面と作業画面のコンポーネントを読み込みます。
6. `import { useOpenPLCStore } from './store'`
   - 状態管理用のストアから現在のプロジェクト情報を取得します。
7. `export default function App() { ... }`
   - `App` コンポーネントを定義しエクスポートします。
8. `const { project: { meta: { path } } } = useOpenPLCStore()`
   - ストアから現在開いているプロジェクトのパスを取り出します。
9. `return <AppLayout>{path === '' ? <StartScreen /> : <WorkspaceScreen />}</AppLayout>`
   - プロジェクトが未選択なら `StartScreen`、そうでなければ `WorkspaceScreen` を表示します。
