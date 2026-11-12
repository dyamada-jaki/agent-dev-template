# 取り出し元

このテンプレートは、別のプロジェクトで実際に回しているプロセスから取り出したもの。プロセスの改善は取り出し元で先に起き、ここへ移す。

| 項目 | 値 |
|---|---|
| 取り出し元 | `dyamada-jaki/overstrata-board` |
| コミット | `7f4d10158b38d9eb1b26e88d18782ba57fb4e1c7`（2026-10-27） |
| 対象 | `.claude/skills/`・`.agents/skills/`・`docs/workflow.md`・`docs/testing.md`・`docs/decisions/`（README と雛形）・`docs/issue-reports/README.md`・`CLAUDE.md`・README のプロセスの図 |

## 次に取り出すとき
1. 取り出し元で `git log <上のコミット>..main -- .claude/skills docs/workflow.md docs/testing.md docs/decisions/README.md docs/decisions/0000-template.md docs/issue-reports/README.md CLAUDE.md` を見る
2. プロセスの変更だけを選んで、ここへ移す。経緯の注記（「#番号 で…ため」）は、規則を残して理由を一般的な言葉に置き換える
3. 作るもの固有の値は、CLAUDE.md の「開発設定」と profiles に寄せる
4. 上の表のコミットを更新する

## テンプレートだけにあるもの
次のものは取り出し元に無く、テンプレートで足した。取り出し元から移すときに、差があっても消したり上書きしたりしない。
- `.claude/skills/setup-project/`（準備スキル）と `.agents/skills/setup-project`（そのリンク）
- `dev-team.sh doctor`（準備の点検）と、`dev-team.test.sh` の doctor のテスト
- CLAUDE.md・AGENTS.md の「準備がまだなら、まず準備する。」の案内
- CLAUDE.md・AGENTS.md の「開発設定」の「〜のモデル」の行と、それを読む書き方（dual-implement の「モデルの指定」、`dev-team.sh launch` が「開発チームのモデル」を読み Codex なら `orca agent launch` で起動する処理とそのテスト、doctor の「開発チームのモデル」の点検）
- README の「始め方」、`docs/workflow.md` の「最初に1回だけやる準備」の準備スキルを使う書き方と、起動係の名前に付けるリポジトリ名
- Docker を使わないときも worktree ごとにポートを分ける書き方（2026-11-09。「開発設定」の開発サーバーの行、implement-issue 手順4、dual-implement の .env と品質レビュー、setup-project の手順2）
- 指示文の点検（2026-11-12。Claude Code の prompt-audit の手順で、古い参照・食い違い・重ねた注意を直した。テストの決まりを dual-implement から testing.md に移した）
- `docs/definition-of-done.md`（完了の定義）と、それを使う implement-issue 手順5・dual-implement の相互レビューと一次判断・setup-project 手順2（2026-11-12。CLAUDE.md の「完了の定義」はこのファイルを指す1行にした。implement-issue 手順5の「PR を作る前に見直す」4点は、この表に移した）
- `work-times.py` の Orca 1.4.256 への対応（2026-11-10。`--full`・`worker-list --run`・`inbox --terminal run:<Run ID>`）。取り出し元の 494c692 の直し方とは別の形なので、取り出し元へも戻す
- CLAUDE.md・AGENTS.md の「PO の席でのやり方」と、setup-project 手順9でそれを読む一言（2026-11-10。PO が作るものを自分で作り始め、Issue にしないことが2回続いたため）
- implement-issue 手順5の「PR を作る前に見直す」と、CLAUDE.md「守ること」10 の文章の決まり（2026-11-08。Codex 案で繰り返し出た抜けを減らすため）
