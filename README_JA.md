# PPT Master — AIで任意の文書からPowerPointでそのまま編集できるPPTXを生成

[![Version](https://img.shields.io/badge/version-v2.11.0-blue.svg)](https://github.com/hugohe3/ppt-master/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/hugohe3/ppt-master.svg)](https://github.com/hugohe3/ppt-master/stargazers)
[![AtomGit stars](https://atomgit.com/hugohe3/ppt-master/star/badge.svg)](https://atomgit.com/hugohe3/ppt-master)
[![The Agentic Leaderboard](https://www.theagenticleaderboard.com/badges/ppt-master.svg)](https://www.theagenticleaderboard.com/agent/?q=ppt-master)

<p align="center">
  <a href="https://trendshift.io/repositories/25760?utm_source=repository-badge&amp;utm_medium=badge&amp;utm_campaign=badge-repository-25760" target="_blank" rel="noopener noreferrer"><img src="https://trendshift.io/api/badge/repositories/25760" alt="hugohe3%2Fppt-master | Trendshift" width="250" height="55"/></a>
</p>

[English](./README_EN.md) | [中文](./README_CN.md) | 日本語

> [!IMPORTANT]
> ### 日本語対応の修正版
> 日本語やCJKテキストが PowerPoint 書き出し後に崩れにくくなるよう、判定とレイアウトのルールを強化しました。
> - デフォルトで日本語のパワーポイントが出力されるようにしました
> - デフォルトで `Yu Gothic`のフォントを使うようにしました
> - `svg_quality_checker.py` に、テキストあふれ、テキスト同士の重なり、余白不足による書き出し後の崩れを検知するチェックを追加しました

<details open>
<summary>このプロジェクトは <a href="https://www.packyapi.com/register?aff=ppt-master">PackyCode</a>、<a href="https://apikey.fun/register?aff=PPT-MASTER">APIKEY.FUN</a>、<a href="https://runapi.co/register?aff=WMLJ">RunAPI</a>、<a href="https://www.compshare.cn/coding-plan?ytag=GPU_YY-git_pptmaster0624">YouYun ZhiSuan</a> ほかのスポンサー支援によって、無料かつオープンソースで維持されています。</summary>

<table>
  <tr>
    <td width="180"><a href="https://www.packyapi.com/register?aff=ppt-master"><img src="docs/assets/sponsors/packycode.png" alt="PackyCode" width="150"></a></td>
    <td>PackyCode の支援に感謝します。PackyCode は Claude Code、Codex、Gemini などに対応した安定的で高効率な API リレーサービスです。本プロジェクト向けの特典として、<a href="https://www.packyapi.com/register?aff=ppt-master">このリンク</a>から登録し、チャージ時にプロモコード <strong>ppt-master</strong> を入力すると 10% オフになります。</td>
  </tr>
  <tr>
    <td width="180"><a href="https://apikey.fun/register?aff=PPT-MASTER"><img src="docs/assets/sponsors/apikey-fun.png" alt="APIKEY.FUN" width="150"></a></td>
    <td>APIKEY.FUN の支援に感謝します。APIKEY.FUN は企業向けの AI リレー基盤で、Claude、OpenAI、Gemini などの主要モデルを安定・低コストで利用できます。価格は<strong>公式料金の 7%</strong>から。<a href="https://apikey.fun/register?aff=PPT-MASTER">専用リンク</a>経由で登録すると、チャージ時に<strong>最大 5% の恒久割引</strong>を受けられます。</td>
  </tr>
  <tr>
    <td width="180"><a href="https://runapi.co/register?aff=WMLJ"><img src="docs/assets/sponsors/runapi.png" alt="RunAPI" width="150"></a></td>
    <td>RunAPI の支援に感謝します。RunAPI は高効率で安定した API プラットフォームで、1つの API Key で OpenAI、Claude、Gemini、DeepSeek、Grok など 150 以上の主要モデルを利用できます。価格は<strong>公式料金の 10%</strong>からで、Claude Code などとの互換性も高いです。<a href="https://runapi.co/register?aff=WMLJ">専用リンク</a>から登録して管理者に連絡すると、<strong>¥7 の無料クレジット</strong>を受け取れます。</td>
  </tr>
  <tr>
    <td width="180"><a href="https://www.compshare.cn/coding-plan?ytag=GPU_YY-git_pptmaster0624"><img src="docs/assets/sponsors/youyun.png" alt="YouYun ZhiSuan" width="150"></a></td>
    <td>YouYun ZhiSuan の支援に感謝します。UCloud の AI クラウドとして、国内外の主要モデルを 1 つのキーで呼び出せるワンストップ API を提供しています。GLM5.2、Deepseek-v4 などを含むコスト効率の高い国内モデルパッケージに加え、海外モデルへの安定した公式チャネルも提供します。Claude Code や Codex を含む主要 AI コーディングツールと互換性があり、高並列、24時間サポート、セルフ請求にも対応しています。<a href="https://www.compshare.cn/coding-plan?ytag=GPU_YY-git_pptmaster0624">このリンク</a>から登録すると、最大 <strong>¥10 分の無料クレジット</strong>を受け取れます。このプロジェクトは Agent 化されており、<strong>PPT Master</strong> としてローカルデプロイなしで利用できます。</td>
  </tr>
</table>

</details>

> [!IMPORTANT]
> ### これは魔法の箱ではなく、実務向けのツールです
> 一度の指示で完璧な完成版が返ってくることは想定しないでください。このプロジェクトの価値は、面倒で時間のかかる作業の大半を肩代わりしてくれる点にあります。最後の詰めや仕上げは、使う側の役割です。PowerPoint でそのまま編集できる deck を出力するのは、あとから自分で直せるようにするためであって、編集できない画像を渡すためではありません。安いモデルほど人手で詰める余地は増えます。最終的な仕上がりを決めるのは、このプロジェクトと PowerPoint をどれだけ使いこなせるかです。

<p align="center">
  <a href="https://hugohe3.github.io/ppt-master/"><strong>ライブデモ</strong></a> ·
  <a href="https://www.hehugo.com/"><strong>Hugo He について</strong></a> ·
  <a href="./examples/"><strong>サンプル</strong></a> ·
  <a href="./docs/faq.md"><strong>FAQ</strong></a> ·
  <a href="./docs/roadmap.md"><strong>ロードマップ</strong></a> ·
  <a href="mailto:heyug3@gmail.com"><strong>連絡先</strong></a>
</p>

<h3 align="center"><a href="https://raw.githubusercontent.com/hugohe3/ppt-master/main/examples/ppt169_attention_is_all_you_need/exports/attention_is_all_you_need_narrated.pptx">音声ナレーション付きの <em>Attention Is All You Need</em> デッキ</a>も配布しています。PowerPoint で再生すれば、各スライドが自動で読み上げられます。PPT Master の機能は、ここまで広がっています。</h3>
<h3 align="center">まず実力を確かめたいなら、下にある 6 つのサンプル .pptx をそのまま PowerPoint で開くのがいちばん早いです。</h3>

<table>
  <tr>
    <td align="center" width="33%">
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_pritzker_2026"><img src="docs/assets/screenshots/preview_pritzker_2026.png" alt="Editorial magazine — Pritzker 2026 architecture review" /></a><br/>
      <sub><b>エディトリアル誌風</b> — 建築写真と静かなタイポグラフィグリッド<br/>
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_pritzker_2026">オンラインで見る</a> · <a href="https://raw.githubusercontent.com/hugohe3/ppt-master/main/examples/ppt169_pritzker_2026/exports/pritzker_2026.pptx">.pptx をダウンロード</a></sub>
    </td>
    <td align="center" width="33%">
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_global_ai_capital_2026"><img src="docs/assets/screenshots/preview_global_ai_capital.png" alt="Data journalism — Global AI Capital 2026" /></a><br/>
      <sub><b>データジャーナリズム</b> — Bloomberg 風のダークダッシュボードとチャート中心の構成<br/>
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_global_ai_capital_2026">オンラインで見る</a> · <a href="https://raw.githubusercontent.com/hugohe3/ppt-master/main/examples/ppt169_global_ai_capital_2026/exports/global_ai_capital_2026.pptx">.pptx をダウンロード</a></sub>
    </td>
    <td align="center" width="33%">
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_swiss_grid_systems"><img src="docs/assets/screenshots/preview_swiss_grid.png" alt="Swiss typographic grid — Grid Systems primer" /></a><br/>
      <sub><b>スイスグリッド</b> — 厳格なモジュラーグリッドと抑制の効いた赤アクセント<br/>
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_swiss_grid_systems">オンラインで見る</a> · <a href="https://raw.githubusercontent.com/hugohe3/ppt-master/main/examples/ppt169_swiss_grid_systems/exports/swiss_grid_systems.pptx">.pptx をダウンロード</a></sub>
    </td>
  </tr>
  <tr>
    <td align="center" width="33%">
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_glassmorphism_demo"><img src="docs/assets/screenshots/preview_glassmorphism_demo.png" alt="Glassmorphism SaaS — AI Agent engineering demo" /></a><br/>
      <sub><b>Glassmorphism SaaS</b> — 半透明レイヤーとグラデーションで奥行きを出したプロダクトUI調<br/>
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_glassmorphism_demo">オンラインで見る</a> · <a href="https://raw.githubusercontent.com/hugohe3/ppt-master/main/examples/ppt169_glassmorphism_demo/exports/glassmorphism_demo.pptx">.pptx をダウンロード</a></sub>
    </td>
    <td align="center" width="33%">
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_sugar_rush_memphis"><img src="docs/assets/screenshots/preview_sugar_rush_memphis.png" alt="Memphis pop — Sugar Rush festival" /></a><br/>
      <sub><b>メンフィスポップ</b> — 強い原色と幾何学パターンで押し出すポップな勢い<br/>
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_sugar_rush_memphis">オンラインで見る</a> · <a href="https://raw.githubusercontent.com/hugohe3/ppt-master/main/examples/ppt169_sugar_rush_memphis/exports/sugar_rush_memphis.pptx">.pptx をダウンロード</a></sub>
    </td>
    <td align="center" width="33%">
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_indie_bookstore_zine_guide"><img src="docs/assets/screenshots/preview_indie_bookstore_zine.png" alt="Risograph zine — Indie bookstore guide" /></a><br/>
      <sub><b>Risograph Zine</b> — 二色刷りの質感と手作り感のある書店カルチャー表現<br/>
      <a href="https://hugohe3.github.io/ppt-master/viewer.html?project=ppt169_indie_bookstore_zine_guide">オンラインで見る</a> · <a href="https://raw.githubusercontent.com/hugohe3/ppt-master/main/examples/ppt169_indie_bookstore_zine_guide/exports/indie_bookstore_zine_guide.pptx">.pptx をダウンロード</a></sub>
    </td>
  </tr>
</table>

<p align="center">
  <sub>生成モデル: Claude Opus 4.7 + <code>gpt-image-2</code>。<a href="https://hugohe3.github.io/ppt-master/">全サンプルをオンラインで見る →</a> · <a href="./examples/"><code>examples/</code>ディレクトリ</a> · <a href="./docs/why-ppt-master.md">なぜPPT Masterなのか</a></sub>
</p>

---

素材を渡して返ってくるのは、**本物のPowerPointファイル**です。PowerPoint上で直接編集でき、ネイティブの画面切り替えや入場アニメーションを使えます。スピーカーノートから音声ナレーションを作ることもでき、自分のPPTテンプレートに合わせることも可能です。そのまま発表に使えて、必要なら後から手直しも続けられます。各機能の使い方は[Getting Started](./docs/getting-started.md)を見てください。

> **⚠️ PPT Masterは単体で完結したエージェントではなく、エージェントを動かすためのワークフロー基盤です。** `harness + model = agent` の関係で、流れを担うのはこのツールですが、品質の上限を決めるのはモデルです。高品質なエージェントを組むなら、**大きなコンテキストウィンドウを持つClaude（約100万トークン級）+ AI画像生成（`gpt-image-2`）** が現状の推奨構成です。ほかのモデルでもパイプライン自体は動きますが、同じ品質上限には届きません。結果に不満がある場合は、まずモデルを見直してください。

> **どう動くのか** — PPT MasterはClaude Code、Cursor、VS Code + Copilot、CodebuddyなどのAI対応IDEの中で動くワークフローです。AIに「このPDFから資料を作って」と伝えると、AIがその手順に従って、手元のコンピュータ上に編集可能な`.pptx`を生成します。あなたがコードを書く必要はありません。IDEはAIとやり取りするための作業場所です。
>
> **利用者がやること**: Pythonを入れる。AI対応IDEを用意する。資料を渡す。

> **なぜこの形なのか** — PythonとAIエージェントを使いこなす力は、今後さらに重要になります。このプロジェクトは、その2つだけでどこまで実務に踏み込めるかを示すためのものです。最初は少し学習コストがありますが、越える価値のある壁です。PPT作成は入口にすぎません。本当に伝えたいのは、Pythonとエージェントの実用性です。

PPT Masterの違い:

- **本物のPowerPoint** — PowerPointで開けず、編集もできないなら、それはPPTと呼ぶべきではありません。PPT Masterの出力は、すべての要素を直接クリックして編集できます
- **コストが透明で予測しやすい** — ツール自体は無料のオープンソースで、費用は自分が使うAIモデル分だけです。利用量課金が主流になった今、使った分だけ支払えばよく、追加のPPTサブスクリプションは不要です
- **データはローカルに留まる** — プレゼンを作るためだけにファイルを他社サーバーへ上げるべきではありません。AIモデルとの通信を除き、処理全体は手元のマシンで完結します
- **プラットフォームに縛られない** — どこか1社にワークフローを握られる必要はありません。Claude Code、Cursor、VS Code Copilotなどで動き、Claude、GPT、Gemini、Kimiなど複数のモデルに対応します

AIプレゼンツールは概ね4つに分かれます。PPT Masterが扱うのは最後の1つだけです。

| 種類 | 出力物 | PowerPoint上で要素ごとに編集できるか |
|---|---|:---:|
| テンプレート流し込み型 | 固定テンプレートを埋めた PPTX | 部分的に可能。テンプレートの制約を受ける |
| 画像貼り付け型 | スライドごとに大きな画像を入れた PPTX | ❌ 各スライドは実質画像 |
| HTML プレゼン型 | Web ベースのプレゼン資料 | ❌ PPTX ではない |
| **ネイティブ編集型（PPT Master）** | **DrawingML の図形、テキストボックス、チャートをそのまま出力** | ✅ すべての要素を編集可能 |

---

## ツールより使い手の差が大きい

上のサンプルは、どれも一度で出したもので、細部をほとんど磨き込んでいません。それでもここまで作れますし、さらに手を入れれば見え方は大きく変わります。同じPowerPointを使っても、使い手によって仕上がりは大きく変わります。差を生むのはツールそのものより、使い方の理解と詰めの精度です。まだ思った品質に届かないなら、まず[Getting Started](./docs/getting-started.md)とサンプルプロジェクトでワークフローを掴んでください。

最高の結果を狙うなら、現時点ではClaudeが有利です。価格が気になるなら、同じ水準の資料を人に依頼した場合のコストと比較してください。GPT、Gemini、Kimiなどでもこのプロジェクトは動きますが、出てくる品質は変わります。最小コストで最高品質を期待するのは現実的ではありません。

---

## 作者について

私は投融資分野の実務家で、CPA、CPV、Consulting Engineer（Investment）の資格を持ち、日常的にプレゼン資料のレビューと修正に関わっています。AIが作ったスライドも画像に潰されるのではなく、PowerPointでそのまま編集できるべきだと考え、このプロジェクトを作りました。

🌐 [公式サイト](https://www.hehugo.com/) · 📧 [heyug3@gmail.com](mailto:heyug3@gmail.com) · 🐙 [@hugohe3](https://github.com/hugohe3)

---

## はじめ方

### 1. 前提条件

**必要なのはPythonだけです。** それ以外は`pip install -r requirements.txt`で入ります。

| 必要なもの | 必須か | 用途 |
|------------|:---------:|--------------|
| [Python](https://www.python.org/downloads/) 3.10+ | ✅ **必須** | コア実行環境。実際に自分で入れる必要があるのはこれだけです |

> **要点だけ** — Pythonを入れて`pip install -r requirements.txt`を実行すれば、PPT生成を始められます。

<details open>
<summary><strong>Windows</strong> — 専用の手順ガイドがあります ⚠️</summary>

WindowsではPATH設定や実行ポリシーなど、追加の注意点があります。Windows向けに**手順付きガイド**を用意しています。

**📖 [Windows Installation Guide](./docs/windows-installation.md)** — 何も入っていない状態から、10分ほどで最初の資料生成まで進めます。

短縮版: [python.org](https://www.python.org/downloads/)からPythonを入れる → インストール時に**Add to PATH**を有効化 → `pip install -r requirements.txt` → 完了。
</details>

<details>
<summary><strong>macOS / Linux</strong> — インストールしてすぐ使う</summary>

```bash
# macOS
brew install python
pip install -r requirements.txt

# Ubuntu / Debian
sudo apt install python3 python3-pip
pip install -r requirements.txt
```
</details>

<details>
<summary><strong>例外的なフォールバック</strong> — 99% のユーザーには不要です</summary>

**Pandoc** — レガシー文書形式のときだけ必要です: `.doc`, `.odt`, `.rtf`, `.tex`, `.rst`, `.org`, `.typ`。`.docx`, `.html`, `.epub`, `.ipynb` はPythonネイティブで処理できます。

```bash
# macOS
brew install pandoc

# Ubuntu / Debian
sudo apt install pandoc
```
</details>

### 2. 利用するAIエージェントを選ぶ

PPT Masterは、**AIエージェント機能を持つツールなら基本的にどれでも**動作します。ファイルの読み書きができて、コマンドを実行できて、複数ターンの対話を続けられれば十分です。

| 種類 | 代表例 | 説明 |
|---|---|---|
| **IDE内蔵型** | • VS Code系アーキテクチャ（[VS Code](https://code.visualstudio.com/)本体とその派生）: [Cursor](https://cursor.sh/), Trae, Codebuddy IDE, [Windsurf](https://codeium.com/windsurf), Voidなど<br>• そのほか: [Zed](https://zed.dev/)など | エディタ自体にエージェント機能が入っているタイプ |
| **IDE拡張型** | [GitHub Copilot](https://github.com/features/copilot), [Claude Code](https://claude.ai/code)（VS Code / JetBrains拡張）, [Cline](https://cline.bot/), [Continue](https://continue.dev/), Roo Codeなど | VS CodeやJetBrainsに追加して使うタイプ |
| **CLI型** | [Claude Code](https://claude.ai/code) CLI, [Codex CLI](https://github.com/openai/codex), [Aider](https://aider.chat/), Gemini CLI など | ターミナルで動かすタイプ。自動化、リモート、サーバー用途に向く |

> **モデル推奨**: 最高品質を狙うなら**Claude Opus**と`gpt-image-2`。**Gemini 3.5 Flash**も速度と価格のバランスが良く、十分試す価値があります。

**🔑 Claude / GPT / Geminiを使いたいが接続先がない場合**: 本プロジェクトのスポンサーである**[PackyCode](https://www.packyapi.com/register?aff=ppt-master)**、**[APIKEY.FUN](https://apikey.fun/register?aff=PPT-MASTER)**、**[RunAPI](https://runapi.co/register?aff=WMLJ)**が、Claude、GPT、Geminiなどへの従量課金アクセスを提供しています。サブスク不要で、本ページ上部に専用特典もあります。

**🔀 複数のプロバイダを使い分けたい場合**: [cc-switch](https://github.com/farion1231/cc-switch)はクロスプラットフォームのデスクトップアプリで、Claude Code、Codex、Gemini CLIなどのAPIプロバイダをワンクリックで切り替えられます。

### 3. セットアップする

**方法A — ZIPをダウンロード**（Git不要）: [GitHubページ](https://github.com/hugohe3/ppt-master)の**Code → Download ZIP**から取得して展開します。

**方法B — Git clone**（[Git](https://git-scm.com/downloads)が必要）:

```bash
git clone https://github.com/hugohe3/ppt-master.git
cd ppt-master
```

続けて依存関係を入れます:

```bash
pip install -r requirements.txt
```

後から更新する場合（方法A / B）: `python3 skills/ppt-master/scripts/update_repo.py`

> **方法C — Skill Marketplace**: このリポジトリには`.claude-plugin/marketplace.json`が含まれているため、[Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces)系からもインストールできます。
>
> ```bash
> # 複数エージェント対応CLI（Claude Code, Cursor, Codexなど）
> npx skills add hugohe3/ppt-master
>
> # Claude Code 内から追加する場合
> /plugin marketplace add hugohe3/ppt-master
> /plugin install ppt-master@ppt-master
> ```
>
> ただし、この方法で取得されるのは skill ファイルのみです。後処理スクリプトを動かすには、インストール先で `pip install -r requirements.txt` を別途実行してください。

### 4. 資料を作る

**元資料を渡す方法（推奨）:** PDF、DOCX、画像などを`projects/`配下に置き、AIのチャットで使うファイルを指定します。パスを取得する最短手順は、ファイルマネージャまたはIDEのサイドバーで右クリックし、**Copy Path**または**Copy Relative Path**を使うことです。

```
You: Please create a PPT from projects/q3-report/sources/report.pdf
```

**テキストを直接貼る方法:** 内容をそのままチャットに貼り付けても動きます。

```
You: Please turn the following into a PPT: [paste your content here...]
```

どちらの場合も、最初にAIがデザイン仕様を確認します。

```
AI:  Sure. Let's confirm the design spec:
     [Template] B) Free design
     [Format]   PPT 16:9
     [Pages]    8-10 pages
     ...
```

内容の整理、ビジュアル設計、SVG生成、PPTXへの書き出しまで、AIがまとめて処理します。

> **出力:** PowerPoint上で直接編集できるネイティブ図形の`.pptx`は`exports/<name>_<timestamp>.pptx`に保存されます。`svg_output/`は毎回`backup/<timestamp>/svg_output/`にスナップショット保存されるため、再エクスポートや保管にも使えます。`--svg-snapshot`を付けると、ネイティブ版に加えてSVG画像プレビュー版のpptxも`exports/`に出力されます。Office 2016以降が必要です。

> **すでに再利用したい`.pptx`がある場合**: そのデッキと新しい素材をAIに渡して、「このデッキに新しい内容を流し込んで」と頼んでください。既存デザインを保ったまま、テキスト、表、チャートデータを差し替え、必要なページだけを書き出せます。詳しくは[FAQ](./docs/faq.md)と[template-fill workflow](./skills/ppt-master/workflows/template-fill-pptx.md)を参照してください。

> **AIが文脈を見失ったら**: `skills/ppt-master/SKILL.md`を読ませてください。

> **問題が起きたら**: [FAQ](./docs/faq.md)を確認してください。モデル選択、レイアウト崩れ、エクスポート異常などを継続的に追加しています。

### 5. 画像を用意する（任意）

ユーザーが手元に持っていない画像については、同じデッキの中で行ごとに混在できる2つの取得経路があります。

APIを使う機能の設定は`.env`に入れます。cloneしたリポジトリなら`cp .env.example .env`、Skill Marketplace経由ならユーザー単位の永続設定がオススメです。

```bash
mkdir -p ~/.ppt-master
cp /path/to/installed/ppt-master/.env.example ~/.ppt-master/.env
```

PPT Masterはまず現在のプロセス環境変数を読み、その後、現在の作業ディレクトリ、skillディレクトリ（例: `~/.agents/skills/ppt-master/.env`）、cloneしたリポジトリのルート、`~/.ppt-master/.env`の順に、最初に見つかった`.env`を読み込みます。

**A) AI生成** — `image_gen.py`。`IMAGE_BACKEND`と対応する`*_API_KEY`（`OPENAI_API_KEY`、`GEMINI_API_KEY`など）を設定すると、パイプラインが自動で呼び出します。使えるバックエンドの一覧は`python3 skills/ppt-master/scripts/image_gen.py --list-backends`で確認できます。現在の標準推奨は`gpt-image-2`です。

**B) Web画像検索** — `image_search.py`。**設定なしでも使えます**が、高品質化には`PEXELS_API_KEY` / `PIXABAY_API_KEY`（どちらも無料）が有効です。キーがない場合はOpenverse / Wikimedia Commonsのみを使います。フォールバックとしては成立しますが、一般ユーザー投稿が混ざるため品質にはばらつきがあります。キーを設定するとPexels / Pixabayも検索チェーンに加わり、ストックフォト、人物、オフィス、ライフスタイル、イラストの品質が大きく安定します。既定では品質優先で、CC0、パブリックドメイン、Pexels / Pixabayのクレジット不要ライセンス、CC BY、CC BY-SAをまとめて候補に入れます。クレジットが必要な画像を採用した場合は、Executorが小さな帰属表記を自動で追加します。クレジット表記を絶対に載せられない場合だけ`--strict-no-attribution`を使ってください。表紙、商品写真、人物写真、ブランド表現のようにビジュアル品質が重要な場面では、ユーザー提供の高解像度素材 / AI生成 > Pexels / Pixabayキー付きWeb検索 > 設定なしWeb検索、の順が推奨です。

> 詳細: [image-generator.md](./skills/ppt-master/references/image-generator.md)（AI） · [image-searcher.md](./skills/ppt-master/references/image-searcher.md)（Web）

---

## ドキュメント案内

補足として、詳細ドキュメントは現状、主に英語版と中国語版が中心です。以下は既存ドキュメントへの入口です。

| | ドキュメント | 内容 |
|---|----------|-------------|
| 📘 | [Getting Started](./docs/getting-started.md) | 最初のデッキを3ステップで作る手順。テンプレート、ライブプレビュー、アニメーション、ナレーション、音声クローンも説明しています（**はじめて使うならここから**） |
| 🆚 | [Why PPT Master](./docs/why-ppt-master.md) | GammaやCopilotなどとの違い |
| 🪟 | [Windows Installation](./docs/windows-installation.md) | Windows 向けの手順付き導入ガイド |
| 📖 | [SKILL.md](./skills/ppt-master/SKILL.md) | コアワークフローとルール |
| 📐 | [Canvas Formats](./skills/ppt-master/references/canvas-formats.md) | PPT 16:9、Xiaohongshu、WeChat など 10 種類以上のフォーマット |
| 🛠️ | [Scripts & Tools](./skills/ppt-master/scripts/README.md) | すべてのスクリプトとコマンド |
| 💼 | [Examples](./examples/README.md) | サンプルプロジェクト一覧 |
| 🏗️ | [Technical Design](./docs/technical-design.md) | アーキテクチャ、設計思想、SVG を使う理由 |
| ❓ | [FAQ](./docs/faq.md) | モデル選定、コスト、レイアウト調整、テンプレート利用 |

---

## コントリビュート

参加方法は [CONTRIBUTING.md](./CONTRIBUTING.md) を参照してください。

## ライセンス

[MIT](LICENSE)

## 謝辞

[SVG Repo](https://www.svgrepo.com/) · [Tabler Icons](https://github.com/tabler/tabler-icons) · [Simple Icons](https://github.com/simple-icons/simple-icons) · [Phosphor Icons](https://github.com/phosphor-icons/core) · [Robin Williams](https://en.wikipedia.org/wiki/Robin_Williams_(author)) (CRAP principles)

## 関連ツール

[cc-switch](https://github.com/farion1231/cc-switch) — Claude Code、Codex、Gemini CLIなどのAPIプロバイダをまとめて管理し、ワンクリックで切り替えられるデスクトップアプリです。PPT Masterを複数のエージェントで使い分けるときに便利です。

## 問い合わせと協業

PPT Masterの導入、連携、質問については以下を使ってください。

- 💬 **質問と共有** — [GitHub Discussions](https://github.com/hugohe3/ppt-master/discussions)
- 🐛 **バグ報告と機能要望** — [GitHub Issues](https://github.com/hugohe3/ppt-master/issues)
- 🌐 **作者について詳しく知る** — [www.hehugo.com](https://www.hehugo.com/)

---

## Star History

<a href="https://star-history.com/#hugohe3/ppt-master&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=hugohe3/ppt-master&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=hugohe3/ppt-master&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=hugohe3/ppt-master&type=Date" />
 </picture>
</a>

---

## スポンサーと支援

PPT Masterは現在、主に私1人で開発と保守を続けています。新しいテンプレートの追加、バグ修正、ドキュメント整備には継続的なコストがかかっており、以下のスポンサーや個人支援に支えられています。

**企業スポンサー**

<a href="https://www.packyapi.com/register?aff=ppt-master"><img src="docs/assets/sponsors/packycode.png" alt="PackyCode" height="40" /></a>
&nbsp;
<a href="https://apikey.fun/register?aff=PPT-MASTER"><img src="docs/assets/sponsors/apikey-fun.png" alt="APIKEY.FUN" height="40" /></a>
&nbsp;
<a href="https://runapi.co/register?aff=WMLJ"><img src="docs/assets/sponsors/runapi.png" alt="RunAPI" height="40" /></a>
&nbsp;
<a href="https://www.compshare.cn/coding-plan?ytag=GPU_YY-git_pptmaster0624"><img src="docs/assets/sponsors/youyun.png" alt="YouYun ZhiSuan" height="40" /></a>
&nbsp;
<a href="https://m.do.co/c/547f129aabe1"><img src="https://opensource.nyc3.cdn.digitaloceanspaces.com/attribution/assets/PoweredByDO/DO_Powered_by_Badge_blue.svg" alt="Powered by DigitalOcean" height="40" /></a>

**個人サポート**

PPT Masterが役立ったなら、金額を問わず個人支援が開発継続と無料公開の維持に直結します。

<a href="https://paypal.me/hugohe3"><img src="https://img.shields.io/badge/PayPal-支援-00457C?style=for-the-badge&logo=paypal&logoColor=white" alt="PayPal で支援" /></a>

<img src="docs/assets/alipay-qr.jpg" alt="Alipay QR Code" width="220" />

---

Made with ❤️ by [Hugo He](https://www.hehugo.com/) — このプロジェクトが役に立ったら、ぜひ ⭐ を付けて、可能であれば [スポンサー支援](#スポンサーと支援) もお願いします。

<sub>公式配布元: <a href="https://github.com/hugohe3/ppt-master">GitHub</a>（本家）· <a href="https://atomgit.com/hugohe3/ppt-master">AtomGit</a>（ミラー）。その他プラットフォーム上の再配布は非公式です。MITライセンスですが、帰属表示は残してください。</sub>

[⬆ 先頭へ戻る](#ppt-master--aiで任意の文書からpowerpointでそのまま編集できるpptxを生成)