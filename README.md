# StudyPilot（iPhone内保存版）

## GitHub Pagesで公開
1. ZIPを展開し、`StudyPilot` フォルダ内のファイルと `icon-192.png` と `icon-512.png`を取り出します。
2. GitHubで `studypilot` というリポジトリを作り、その**直下**に `index.html`、`app.js`、`style.css` などをアップロードします（StudyPilotフォルダごと入れ子にしないでください）。
3. リポジトリの Settings → Pages → Build and deployment で Source を Deploy from a branch、Branch を `main`、フォルダを `/ (root)` にして Save。
4. 公開された `https://ユーザー名.github.io/studypilot/` を開きます。

## iPhoneのホーム画面に追加
Safariで公開URLを開く → 共有 → ホーム画面に追加 →（表示される場合）「Webアプリとして開く」をオン → 追加。

## 保存と注意
- プロフィール、計画、完了チェックは同じURL・同じブラウザの localStorage に保存されます。端末間同期はありません。
- SafariのWebサイトデータ削除、ブラウザ変更、URL変更などでデータが失われる場合があります。プロフィール画面から定期的にJSONを書き出してください。
- GitHub Pagesは公開サイトです。個人情報や学校のログイン情報などは入力しないでください。保存データは暗号化されません。
- 更新時は同じリポジトリのファイルを上書きすればURLは変わりません。更新後に古い表示が残る場合はアプリを閉じて再度開いてください。サイトデータの削除は保存データも消える可能性があるため避けてください。

## この初期版の機能・制限
日々の条件からルールベースで通常プランと最低限プランを作り、チェック・履歴・バックアップを管理します。生成AIとの通信、大学の最新入試情報の自動取得、自由記述の高度な解釈は未実装です。


## Version 3 improvements
- The two app icon PNGs are stored in the repository root, so they can be uploaded as individual files without uploading a folder.
- Date and start-time inputs are separated; study duration is estimated from start time to bedtime minus meal and bath durations in the saved profile.
- Profile includes bedtime, desired sleep duration, club activity weekdays, qualifications, meal duration, and bath duration.
- Progress bar becomes more vivid as tasks are completed; completing every regular task triggers a celebration.
- Monthly and yearly tasks can be added, checked off, and deleted.
- A small original white chicken mascot, コッコ隊長, appears on the daily plan.
- The app migrates the previous `studypilot.v1` local data into the new `studypilot.v2` storage key when first opened.

After uploading this version, GitHub Pages keeps the same URL. The service worker cache was changed to `studypilot-cache-v4`. If the old screen remains, close the installed app/browser tab and reopen the same URL after the deployment finishes. Do not clear Safari/Chrome site data unless you have exported a JSON backup.

- The date and start-time fields now stack cleanly on narrow phone screens to prevent overlap.
- The plan summary also shows the selected weekday club status and desired sleep duration.
