# In C Simulator

> A browser-based generative realization of Terry Riley's *In C* (1964).
> Single static HTML — just open it and listen.

**Live demo:** https://dm99x.net/in_c/in_c_simulator.html
**Author:** Daisuke Matsuoka — [@dm99x](https://github.com/dm99x) / <https://dm99x.net>

---

## 概要 / Overview

Terry Riley の *In C*（1964）は、53 の短い音型（パターン／セル）を、奏者がそれぞれ自分の判断で繰り返し・先送りしながら順に進めていくミニマル／プロセス音楽の起点的作品です。全体は共通のパルスの上に置かれ、各声部の進行差から刻一刻と変化するテクスチュアが立ち上がります。

本シミュレータは、この「奏者ごとに独立して 53 パターンを進める」というプロセスを、ブラウザ上の生成的な自動演奏として実装したものです。固定された一回限りの演奏ではなく、開くたびに異なる実現（realization）が立ち現れます。

*An English summary:* this is a single-file, dependency-free web simulator that algorithmically performs Riley's *In C* — multiple independent voices advance through the 53 cells over a shared pulse, producing a different realization on each run.

## 鳴らし方 / How to run

ブラウザで `in_c_simulator.html` を開くだけで動作します（音が出ます）。
ローカルで確認する場合、ブラウザの自動再生制限を避けるため簡易サーバ経由が確実です:

```bash
# 例: Python の簡易サーバ
python3 -m http.server 8000
# → http://localhost:8000/in_c_simulator.html
```

## コンセプト / Concept

- **53 のパターン** — 原曲のセル構造をそのまま進行単位として用いる
- **共通パルス** — 全声部が共有する基準の鼓動
- **声部ごとの独立した進行** — 各ボイスが確率的に「留まる／次へ進む」を判断し、ズレからテクスチュアが生成される
- **自動演奏としての解釈** — 人間アンサンブルの慣習（合奏感・終わり方）を、規則と乱数でどう近似・逸脱させるか

<!-- ↑ 実装上の具体的な確率モデルや終止条件があればここに追記すると、評価面でさらに伝わります -->

## 技術 / Tech

<!-- 使用したものを記載してください。例:
- Web Audio API（または Tone.js など）
- 単一 HTML / 外部依存なし（CDN を使う場合はそのリンク）
-->

## ファイル構成 / Structure

```
in_c_simulator.html   # 本体（音源生成・UI を含む単一ファイル）
```

## ライセンス / License

このリポジトリで配布されるのは **私自身が書いた実装コードおよびその生成的実現** です。
*In C* の 53 パターン（楽曲そのもの）の著作権は Terry Riley に帰属します。本作はそれへのオマージュ／学習目的の実現であり、原曲の音楽素材を自作として主張するものではありません。

実装コードのライセンス: <!-- 例: MIT または GPLv3 -->
（参考: 生成音楽作品ではコードと美的出力が一体になりがちなため、「コード = MIT/GPL」「美的成果物 = CC BY-NC-SA 4.0」のデュアルライセンスにすると筋が通ります。NC を全体に効かせたい場合は CC BY-NC-SA 一本でも実務上は可。その場合 OSI 定義の "オープンソース" には該当しなくなる点だけ留意。）

## クレジット / Credits

- Concept & implementation: Daisuke Matsuoka
- Co-pilot: Claude (Anthropic)
- Original work: Terry Riley, *In C* (1964)

## 関連 / Related

- 作者サイト: <https://dm99x.net>
- 生成音楽に関する論考: 「生成音楽の諸相、および作曲論序論」 <https://dm99x.net/wp-content/themes/dm99x/assets/generative_music_20251227.pdf>
