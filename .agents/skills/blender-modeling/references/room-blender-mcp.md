# room Blender MCP仕様

この資料は、roomプロジェクトの`.mcp.json`から起動される`room/scripts/blender-mcp.mjs`の仕様を記録する。room環境で確認した内容（2026-11-09）であり、別のプロジェクトやMCP実装にはそのまま適用しない。

## ツールの機能

- MCPツール名: `create_fbx`
- 既存Sceneを編集せず、Blenderの空のFactory Sceneから新しいSceneを作る。
- 対象は基本形状Meshのみ: `cube`、`sphere`、`ico_sphere`、`cylinder`、`cone`、`torus`、`plane`
- 一度の呼び出しで1〜200個のObjectを作成する。
- Objectごとに名前、形状、位置、回転、スケール、任意の基本Materialを指定できる。
- 成功すると`.blend`と`.fbx`の両方を出力し、実際のパスとBlenderバージョンを返す。

任意のメッシュ形状、既存Objectの変更、UV編集、レンダリング、任意のBlender Python実行はこのツールではできない。必要な場合は、別の利用可能な手段が確認できない限り未対応として伝える。

## 入力制約

- `outputName`: 1〜64文字。英数字で始まり、英数字・`_`・`-`を使用する。
- Object名: 1〜64文字。英数字で始まり、英数字・空白・`_`・`-`を使用する。同じ呼び出し内で大文字小文字を区別しない重複名は不可。
- 位置と回転角度: 各軸`-10000`〜`10000`。回転の単位は度。
- スケール: 各軸とも`0`より大きく`10000`以下。
- Materialの色、Metallic、Roughness: それぞれ`0`〜`1`。色はRGB。
- Materialを指定しない場合、ObjectにMaterialは明示追加されない。

## 出力先と上書き

- 既定の出力先はroomプロジェクトの`Assets/Generated/Blender`。
- `BLENDER_MCP_OUTPUT_DIR`が設定されている場合はその出力先を使う。
- `.blend`と`.fbx`のいずれかが既に存在する`outputName`は失敗する。上書きせず、別の一意な名前を選ぶ。
- Unityが生成する`.meta`ファイルはMCP出力ではない。手作業で作成・変更せず、Unity側の管理に任せる。

## FBX出力

現在の実装は選択したMesh Objectのみを出力し、軸はForward `-Z`、Up `Y`、Scaleは`FBX_SCALE_ALL`を指定する。アニメーションは出力しない。これらの設定が対象プロジェクトや利用目的に適合するかは別途確認する。

## 実行・検証

1. 依頼された内容が対応する基本形状だけで表現できるか確認する。表現できない細部を作成済みと偽らない。
2. 生成する各Objectの形状、名前、位置、回転、スケール、Materialを具体化する。
3. 同一の`outputName`が既存出力と衝突しない一意な名前を使う。
4. `create_fbx`を実行し、エラーが返った場合はその内容を報告する。
5. 戻り値の出力パスと両ファイルの存在を確認する。Unityでのインポートや見た目まで確認していない場合は未検証とする。
