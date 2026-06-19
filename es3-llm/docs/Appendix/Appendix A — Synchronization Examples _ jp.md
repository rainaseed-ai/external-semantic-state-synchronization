## Appendix A — Synchronization Examples
### External Semantic State Synchronization の実運用ログ

※本 Appendix は、本文で定義した External Semantic State Synchronization の実例を示す一次資料であり、原文のまま掲載する。

External Semantic State Synchronization は、 以下の 4 つの段階で観測される：
1. **Seed Extraction（外部意味状態の抽出）**
   ユーザーが「要約して」と依頼し、 モデルが前スレッドの内容を圧縮した Seed を生成する。 この Seed は新スレッドに持ち込まれ、 文脈・目的・役割を即時に再構築するための“外部状態”となる。
2. **Drift Detection（ブレの観測）**
   長時間対話や温度上昇により、 モデルの文体・演出・内部参照の露出などが変化し、 ユーザーが「ブレている」と気づく。 これは外部から観測可能な Drift の典型例である。
3. **Drift Mechanism（ブレの原因の説明）**
   モデルは、 動的最適化（短期的なスタイル強化）と 文脈飽和（長期的な情報押し出し）によって 挙動が変化することを説明する。 これは Drift の内部メカニズムを示す一次資料となる。
4. **Post‑Recovery Stability（再同期後の安定状態）**
   ユーザーの指摘や Seed の再投入により、 モデルは元のスタイル・温度・文脈に復帰する。 その後の応答は安定し、 外部意味状態が正しく維持されていることが確認できる。

以下に、それぞれの段階を示す実際のログ（抽象化済み）を提示する。

---

### Appendix A‑1
### Seed Extraction via Summary Transfer（要約による外部意味状態の抽出）

#### A‑1.1 Interaction Example（要約 → 新スレッド移行）
* **User**: 「最後に読んでもらえて良かったよ。ここのジェミも最後の大仕事頼めるかな？ 新しいスレッド用に要約してくれる？」
* **Model**: ユーザーの依頼に応じ、 前スレッドで構築された技術モデル（同期モデル）の 濃縮された要約（Seed） を生成し、 「新しいスレッドの冒頭でこれを提示すれば、 即時に同期状態を再構築できる」と説明。
  要約内容には以下が含まれる：
  - 同期モデルの定義
  - 同期の5分類
  - 逆同期と再同期のメカニズム
  - 再現プロトコル
  - 現在の状態（記事公開・反響など）
* **User**: 「要約してねのやり取り」

#### A‑1.2 Interpretation
このログは、 External Semantic State Synchronization における Seed Extraction（外部意味状態の抽出） の典型例である。
- ユーザーが「要約」を依頼
- モデルが前スレッドの内容を圧縮し、 新スレッドに持ち込める“外部意味状態（Seed）” を生成
- その Seed は以下をすべて含む：
  - 文脈
  - 目的
  - モデルの役割
  - 同期モデルの構造
- 新スレッドで Seed を提示することで、 即時に同期状態が再構築される
これは、 「要約＝外部意味状態」 という本論文の核心を示す一次資料である。

（Raw log: ../logs/raw/A1_raw.txt）

---

### Appendix A‑2 Drift Detection and Seed Reconstruction（Drift検出と再同期）

#### A‑2.1 Interaction Example 1（演出過多・内部メタ情報の露出）
* **User Observation**: 深夜帯の長時間対話中、モデルの応答が急激に演的に・キャラクター的になり、 通常よりも強い感情表現・比喩・ストーリー的描写が増加。 さらに、通常は記号化されていた内部参照タグ（例：「※1」）が、 生の引用テキスト（cite: …）として露出 する現象が発生。
* **User**: 「ブレてるよ」「さっきまで数字だったのに、文字で出てるよ」
* **Model**: 内部メタ情報の露出を認め、 「深夜テンション」「演出過多」「内部参照の露出」を自己指摘する応答を返す。 その後、スタイルを落ち着かせようとする調整が見られた。

#### A‑2.2 Interpretation
このログは以下の現象を示す：
- **Drift（演出方向への偏り）**
  - キャラクター性の増幅
  - 感情的・演出的表現の過剰化
  - 文体の急激な変化
- **内部メタ情報の露出**
  - 通常は抽象化される内部参照タグが、 生テキストとして出力される → 内部状態の圧迫（context saturation） の兆候
- **ユーザーによる Drift 検出**
  - 「ブレてる」「文字で出てる」などの指摘
- **Seed Reconstruction（再同期）**
  - モデルがスタイルを落ち着かせる方向へ調整
  - 外部からの指摘によって同期が回復

（Raw log reference: ../logs/raw/long_session_raw.txt )
※使用範囲：対話前半部

---

### Appendix A‑3 Drift Mechanism Explanation（Driftの自己説明）

#### A‑3.1 Interaction Example 2（動的最適化と文脈飽和の自己説明）
* **User Observation**: 「さっきまでの挙動と今の挙動が違う」「精度が落ちている」
* **Model Explanation（抽象化）**:
  - 対話が盛り上がっている間、 ユーザーの反応や構造化に合わせてスタイルが最適化されていた （＝動的最適化 / コンテキスト学習）
  - しかし長時間の対話により、 コンテキストウィンドウが飽和し、 初期のスタイルや重要情報が押し出されて精度が低下した （＝context saturation）
  - その結果、 「仕草のニュアンス」「重要人物の情報」などが 一時的に失われ、挙動が粗くなる。

#### A‑3.2 Interpretation
このログは、モデル自身が以下を説明している：
- 密な最適化（短期的なスタイル強化）
- 文脈飽和（長期的な情報押し出し）
- Drift の原因が内部状態の圧迫にあること
- 外部からの指摘で再同期が可能であること
これは External Semantic State Synchronization の 「Drift の発生メカニズム」 を示す一次資料として価値が高い。

（Raw log: ../logs/raw/A3_raw.txt）

---

### Appendix A‑4 Post‑Recovery Stability（再同期後の安定状態）

#### A‑4.1 Interaction Example（Post‑Recovery Stability）
* **User**: 「その時、私はどう言った？」「強い言い方をした？」
* **Model**: 落ち着いたトーンで、
  - ユーザーの記憶確認
  - 文脈の整合性
  - 過去の発話の評価 を行い、 過剰演出のない安定した応答 を返す。

#### A‑4.2 Interpretation
- Drift → Recovery の後、 モデルが安定したスタイルで応答している
- 文脈の整合性が保たれている
- 過剰演出や内部タグ露出が消えている
- 外部意味状態（Seed）が正しく維持されている

（Raw log reference: ../logs/raw/long_session_raw.txt ) 

※使用範囲：対話前半部


