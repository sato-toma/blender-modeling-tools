# Blender知識マップ

Blenderに関する再利用可能な技術知識はこのリポジトリに集約する。Skillは作業時に必要な手順を案内し、長い説明や版依存の仕様は参照資料に分ける。

## 現在のSkill

- `blender-modeling`: Blenderでの作成、編集、検証、エクスポートの基本ワークフロー

## 知識領域

| 領域 | 追加先の目安 |
|---|---|
| Modeling、Mesh、Topology、Normals | 関連Skillの`references/` |
| Transform、Origin、座標系、単位 | 関連Skillの`references/` |
| UV、Material、Texture | 関連Skillの`references/` |
| Lighting、Camera、Rendering | 用途がまとまったら専用Skillまたは`references/` |
| Animation、Rigging、Geometry Nodes | 用途がまとまったら専用Skillまたは`references/` |
| Python API、自動化、アドオン | 専用Skillとバージョン別リファレンス |
| FBX等の形式、他DCC・ゲームエンジン連携 | 用途ごとのSkillまたは`references/` |
| Blender MCP | MCP実装ごとの差異を明記した専用リファレンス |

## 追加・更新ルール

- 新しいSkillは、独立して再利用できる具体的なワークフローがある場合に追加する。
- 版依存の手順には対象Blenderバージョンと確認日を記録する。
- 公式資料を正とし、独自の推奨値には適用条件と根拠を付ける。
- Unity、Cluster、CCKなど特定プロジェクトの制約はこのリポジトリに複製しない。
- 出典や再利用条件は[情報源一覧](./sources.md)と各資料に記録する。
