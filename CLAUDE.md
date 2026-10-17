# CLAUDE.md

統計検定を中間目標に、工学データの妥当性検証を段階的に学ぶ入門教材を作るプロジェクト。出発点のアイデアは `docs/idea_origin.md`、判断の経緯は `docs/qa_log.md`（QA表）にある。

## 公開を前提にした運用（必ず守る）

このリポジトリは、いつ公開（public）にしても問題のない状態を保つ。

- GitHub のリポジトリは private で作成した。public への切り替えはユーザーが判断し、ユーザー自身が操作する。Claude は visibility を変更しない。
- 機密情報・個人情報・第三者の著作物を、追跡するファイルにも、コミットの author・committer 欄にも入れない。手元にだけ置くものは `.gitignore` で除外する。
- 作成者の環境や事情を推測させる記述（PC の情報、ローカルのパス、アカウント名、個人の別の取り組み等）を、教材・記録の文書・コミットメッセージに書かない。
- push の前に、`public-release-review` スキルの手順1（機械点検）と手順2（目視点検）の観点で点検する。QA表などの記録の文書とコミットメッセージも点検の対象にする。

## Git の運用

- コミット規約は `git-conventions` スキルに従う（`[claude]` 接頭辞、Co-Authored-By トレーラー、最初のコミットの前に `git config user.email` が noreply アドレスかを確認）。
- push の承認は**都度確認**とする。commit は作業の区切りで自動で行ってよいが、`git push` は毎回承認を得る。
- 既定のブランチは `main`。

## 教材の作り方

- 教材は、作成者以外の学習者も1人で先頭から読む教科書として書く（`learning-text-authoring` スキルに従う）。役割分担を前提にした言い回しを本文に書かない。
- 閲覧は GitHub の Web 表示を想定し、文書間は相対リンクにする。入口は `README.md` の「読む順番」の表。
- 手順は Windows を本文にし、macOS・Linux の違いは「未確認」と明記した注記で添える。Notebook のエディタは VS Code（Microsoft 公式の Python・Jupyter 拡張機能）を例にする。
- ライセンスは、文章が CC BY 4.0、コードが MIT（`LICENSE`）。著作権者の表記は「statistics-certification-study contributors」。
- ステップの構成と各ステップの範囲は `docs/roadmap.md` を正とする（2級の範囲表の全項目をステップ0〜8に割り当て済み）。ステップ1は「1-1 1変数データ」「1-2 2変数データ」の2冊に分ける。
- 手計算の例は、試験で使える電卓（四則・%・√）だけで計算できる手順で書く。対数・指数が要る値は分布表から読み取る。
- 概念の説明と手計算の例は Markdown、Python を使う演習（工学の例題・シミュレーション）は Jupyter Notebook に分ける。
- Notebook は出力を残してコミットする。コミットの前に、出力にローカルのパスやユーザー名が残っていないかを確かめる。
- 例題のデータは、乱数のシードを固定した模擬データを基本にし、生成するコードを Notebook に残す。公開データセットを使う場合は、ライセンスと再配布の可否を確かめてからにする。
- 著作権: 公式テキスト・過去問題集・参考書の文章や問題を写さない。自分の言葉でまとめ直し、問題は自作する。参考にした資料は出典を書く。

## Python の環境

- python.org 版の Python で作るプロジェクト専用の venv（`.venv`、Git 管理外）を使う。Python 本体とパッケージの導入はユーザー自身が行う。手順は `docs/setup.md`。
- 導入済み: numpy・scipy・matplotlib・ipykernel。Notebook は VS Code で開く（JupyterLab は入れていない）。
- `.venv\Scripts\python` を直接呼ぶ形に統一する（有効化のスクリプトは使わない）。
