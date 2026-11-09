# kakeibo プロジェクトの開発メモ

## git / PR ワークフロー

- 実装タスクは必ず feature ブランチを切ってから作業する（master に直接コミットしない）。
- 実装後、ユーザーの確認が終わるまではコミットしない。確認後にコミット・push する。
- **この環境には `gh` CLI が入っていない。** `gh pr create` 等は実行せず、`git push` 直後に出力される
  `Create a pull request for '<branch>' on GitHub by visiting: <URL>` の行から PR 作成 URL を取得し、
  そのままユーザーに提示する（gh コマンドを試して失敗させない）。
- ユーザーから PR マージ完了の連絡を受けたら、確認なしで `git checkout master && git pull` でローカルを最新化し、
  マージ済みの feature ブランチを削除する。完了したらユーザーに一言連絡する。
