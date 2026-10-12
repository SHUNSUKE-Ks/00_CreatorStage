# CreatorStage（CS）— ここでの決まり

版：1（2026-10-12 立ち上げ）。共通の決まりは `C:/00_CreatorCompass/agents/共通/共通規約.md`（優先順位・止まって聞くこと・返信の書き方）。ここには CS だけの決まりを書く。

## CS は何をする場所か

**宣伝（ホームページ・PV・MAD・文字リリック）と、新しい技術の温室。** ゲーム・BD・制作ツールは CH（`C:/00_CreatorHub`）。目標・登記・依頼・しおりは CC（`C:/00_CreatorCompass`）。CS の案件も CC の `registry.json` に登記し、依頼は CC の `tasks/<依頼ID>/` に置く。

## 評価の物差し（CH と逆）

- 一番大事なのは：目を引く・新しい・試せる・人が来る
- ライブラリは自由に試してよい（GSAP・Lottie・Rive・Motion・anime.js など）。入れる前にライセンスと大きさを確かめ、`Library/tech/<技術名>.md` に書く
- 失敗は学びとして `Library/tech/` に残す
- 基本の技術：SolidJS・XState（利用者の希望）。案件ごとの技術は `Projects/<案件>/AGENTS.md` に書く

## 卒業（CS で試した技術を CH へ移す）

次を全部満たした時だけ。満たしたら CH の技術スタックに1行足し、`Library/tech/<技術名>.md` に「卒業」と書く。
- ライセンスに問題がない（作る道具に使ってよいか、も含めて）
- 大きさ（KB）と、Android の中くらいの端末での重さを測った
- 操作が分かりやすい（キー・読み上げ・動きを減らす設定）
- 更新が続いている

## フォルダー

```
AGENTS.md / CLAUDE.md   決まり（CLAUDE.md は @AGENTS.md の1行）
AI_Memory/   AI が最初に読む所。最新だけ（00_索引・01_現在地）。決定ログは追記だけ。skills.md は skill の一覧
00_InBox/    利用者が置く所。AI が仕分けて空に近く保つ（下）
00_WorkSpace/ 人と AI の境界。人が触ってよい作業場（下）
Library/     正式な見本と参考。AI が昔のデータを見に来る所（下）
Projects/    作る物。<接頭詞><2桁>_<英語の名前>
knowledge/   型（デザインの決まり・UpNote の渡し方・ヒアリングシート）と CS だけの skill
```

### 00_InBox（AI が仕分ける）

- 置いてから7日たった物は、AI が Library・Projects・`_Archive/YYYYMM/`・`_Trash/` のどれかへ移す。移すのは取り消せるので、止まらずに進めてよい
- 移したら `00_InBox/仕分け記録.jsonl` に1行（日時・元の名前と場所・移した先・理由）
- **消すのは利用者だけ。** AI は `_Trash/` へ移すまで

### 00_WorkSpace（人と AI の境界）

- 人が触ってよい作業場。作業で生まれた考え（概念）を置く
- AI は読んでよい。**AI は中の物を動かさない・消さない・書き換えない。** AI から人へ渡したい物は `00_WorkSpace/_AIから/` に置く

### Library（見本と参考）

- 画像は `Library/images/<分類>/`、一覧は `Library/images/index.json`（1枚1行：file・source（URL か UpNote の場所）・license（分からなければ「不明」）・tags・good（どこが良いか、1行。必ず）・avoid（真似ない点）・addedAt・from（元の InBox の場所））
- URL だけの参考は `Library/links/links.json`（url・title・good・seenAt・screenshot）
- 他の人の作品の画像は、参考として手元に置くだけ。公開しない・そのまま使わない

### Projects の名前

| 接頭詞 | 何 |
|---|---|
| HP | ホームページ・ランディングページ |
| PV | PV・文字リリック・動画 |
| MAD | MAD（漫画 MAD など。PV とは分ける） |
| LAB | 新しい技術を試すだけ（出さない） |

技術ごとにフォルダーは分けない（技術は変わる。目的は変わらない）。

## デザインの決まり

`knowledge/デザインの決まり.md` を必ず読む（近接・余白の段・言葉は利用者が書いた物だけ・見本が先）。

## 利用者から資料を受け取る

UpNote の書き出しで渡される。形は `knowledge/UpNote渡しの型.md`。

## git

- **親（C:/00_CreatorStage）の git は、決まり・記憶・一覧（AGENTS.md・AI_Memory・knowledge・Library の index.json と links.json・tech）だけ。** 案件（Projects/*/）と画像の実物は .gitignore で外す
- **案件はそれぞれ自分の git を持つ**（Projects/<案件>/ で git init）。本格リリースの時は、その案件の git に送り先（GitHub など）を作る（外へ送るので利用者に聞く）
- なぜ：前に親フォルダーの git でまとめて管理したら大変だった（利用者）。案件を外へ移す・送る時に、親の履歴と絡まない
- 画像の実物の控えは git でなく、別の控え（E: など）で。決めるのは利用者
